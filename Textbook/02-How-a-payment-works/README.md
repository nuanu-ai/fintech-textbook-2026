[← Market rules and licensing](../01-Market-rules-and-licensing/README.md) · [Contents](../README.md) · [Cards: Visa and Mastercard →](../03-Visa-and-Mastercard-cards/README.md)

<a id="часть-2-как-устроены-транзакции-сегодня-карты-банки-и-альтернативные-способы-оплаты"></a>
# Chapter 2. How a payment works

> The path from the "Pay" button to settlement, payout to the merchant and a possible refund.

**8 lessons** · Knowledge cutoff: **15 September 2026** · [Sources](Sources.md) · [Fact-check and limitations](../../Fact-check/Results.md)

## In this chapter

- [2.1 · Payment participants and their roles](#module-2-1)
- [2.2 · Authorization, clearing and settlement](#module-2-2)
- [2.3 · Bank transfers, instant payments and open banking](#module-2-3)
- [2.4 · Acquiring: what the price is made of](#module-2-4)
- [2.5 · Fraud, 3-D Secure and risk scoring](#module-2-5)
- [2.6 · Refunds, disputes and chargebacks](#module-2-6)
- [2.7 · How a card payment request travels](#module-2-7)
- [2.8 · Other ways to pay: wallets, QR and installments](#module-2-8)
- [Exercises](#exercises)
- [Answers and criteria for understanding](#answers-and-criteria-for-understanding)
- [Summary, sources and limits](#summary-sources-and-limits)

---

This chapter follows a payment from the buyer's intent to the merchant's money and the exceptions that come after. The examples cover card acquiring, US/UK/SEPA bank transfers, Indonesia and selected provider interfaces. There is no universal global payment procedure: the rules of the scheme, the country, the product and the contract add to the general mechanism.

After reading, you will be able to:

- find the participant who made a decision, moved the money or is answerable to the customer;
- separate authorization, presentment for settlement, interbank settlement, payout and delivery of the goods;
- reconstruct a decline or a dispute from events, amounts and identifiers;
- compare payment methods by their full economics and the protections available.

Prerequisite: the course map from [the Introduction](../00-Money-and-fintech-basics/README.md). The roles and balances you need are explained here; after the mechanics, the legal analysis in [Chapter 1](../01-Market-rules-and-licensing/README.md) is useful. For more depth on accounting and reconciliation, see [Chapter 8](../08-Integrations-and-reliability/README.md). This is a teaching study of payment mechanisms.

All amounts in the worked examples are **synthetic** unless explicitly stated otherwise. Taxes, currency revaluations and individual contractual fees are included only where they are named. Dated legal and product information must be checked by a qualified specialist before operational use.

<a id="module-2-1"></a>
<a id="21-участники-и-роли"></a>
## 2.1 Payment participants and their roles

**Question:** who exactly "processes the payment" if the buyer sees a single button?

**Short answer:** the interface hides a chain of different obligations. One participant sells the goods, another maintains the buyer's account, a third accepts the merchant's card transactions; a technical intermediary may only pass data along.

### Role map

| Role | What it does | What to find out when something fails |
|---|---|---|
| Cardholder | Uses the card and the account/credit line | What they actually authorized and which order they expected |
| Merchant | Accepts the order, presents the payment, arranges the goods and refunds | Who is the contractual seller and is responsible for fulfillment |
| Issuer | Issues the card, services the account, makes the authorization decision | The result of the decision, the hold, the final entry on the account |
| Acquirer | Enables card acceptance, submits transactions to the network | The clearing record, withholdings, the obligation to the merchant |
| Card scheme/network | Sets the rules and the infrastructure for exchange between participants | Routing, liability rules, settlement positions |
| Processor | Processes messages for the issuer or the acquirer | Which requests and responses actually passed through it |
| Payment gateway | Accepts the application's request, transforms it and forwards it | Whether the request was received, whether the data and retries are correct |

This is a functional map: one company can perform several roles. The name PSP, payment service provider, does not by itself show who holds the money. In Visa's public description, the acquirer retains responsibility for its merchants and for the intermediaries working on its behalf. The same document describes a payment facilitator as an intermediary that, under conditions provided for by the scheme, enters into acceptance agreements and/or receives funds for sponsored merchants. Such aggregation changes the contractual chain but does not remove the underlying participants. [P02-S034, Backdrop; Payment Facilitator](https://usa.visa.com/dam/VCOM/global/support-legal/documents/visa-acceptance-entities.pdf)

**ISO** in acquiring sales means Independent Sales Organization — an organization that sells and supports an acquirer's services. This is a different meaning of the abbreviation from International Organization for Standardization in ISO 8583. A sales agent does not become an issuer or an independent settlement bank just because it has its own brand. Sponsor bank/BIN sponsor — a bank or other eligible participant through which a program obtains contractually defined participation in the network and a range of card identifiers. Which entity actually issues the card, carries the obligation and bears the settlement risk is set by the program's agreements; for details, see Chapters 1 and 4.

### A 100 USD purchase: money, data and risk

Suppose a buyer purchases a book on a website for 100 USD; the card is a debit card with a balance of 500 USD. The website uses gateway G, processor P and acquirer A. The card was issued by bank I.

1. **Website → G.** The amount, currency, card details or token, and order number are passed on. The merchant has no money yet. The website is responsible for a correct order and for not repeating the transaction.
2. **G/P → A → network → I.** The authorization request is routed. Different intermediaries see different sets of data; you cannot assume that each of them necessarily sees the full PAN or the contents of the cart.
3. **I → back.** The issuer approves a 100 USD hold. The buyer's available balance becomes 400 USD. This is not yet the merchant's bank statement.
4. **The merchant presents 100 USD.** After capture and accepted clearing, the data for financial settlement appears. Money between participants may move as one total amount across thousands of transactions.
5. **A/PSP pays out to the merchant.** With a notional total fee of 3.20 USD, the merchant receives 96.80 USD. This fee contains payments to other participants and the intermediary's own revenue.
6. **The merchant delivers the book.** Only the delivery event confirms the corresponding outcome of the order. Even the arrival of 96.80 USD does not mean that the buyer received the book.

The words **clearing**, **settlement** and **funding** answer different questions: which obligations have been presented and agreed; with what and when the participants discharged them; when the money became available to the payout recipient. Settlement finality is defined by the rules of the specific system. PFMI Principle 8 requires a clear point of finality, not one common status for all stages. [P02-S001, Principle 8](https://www.bis.org/committees/cpmi/pfmi/overview)

**Edge case.** The gateway returns an error after the issuer has already approved the request. The buyer sees a hold, the store sees an error. You can conclude neither "there was no money" nor "the sale is complete". You need to find the same attempt along the chain of identifiers and establish whether there was a reversal, a capture or a repeat authorization. This is the first reason to store the order and the payment attempts separately.

<a id="module-2-2"></a>
<a id="22-authorization--clearing--settlement"></a>
## 2.2 Authorization, clearing and settlement

**Question:** why does an approved card not mean that the merchant has already received the money?

**Answer:** authorization permits a transaction under given conditions; financial presentment, settlement and payout are triggered by other events and may end differently.

### The states of a single transaction

```text
attempt created → authorization sent
                    ├─ declined
                    ├─ result unknown → status inquiry / permitted reversal
                    └─ authorized
                         ├─ canceled / expired
                         └─ capture requested → accepted or rejected
                              → clearing/presentment → settlement
                              → PSP available balance → payout → bank credit
```

Fulfillment — providing the goods or service — runs alongside this diagram. It is not a technical stage of the card message. A refund and a dispute may begin after settlement; they are additional obligations, not proof that the original settlement did not happen.

**Authorization request/response** — a request and a response on whether a payment is permissible. Authorization is usually accompanied by a hold on the available amount or credit limit. **Capture** — a command to present an authorized transaction for financial processing. **Void/cancel** is usually used in an API to cancel a financial presentment that has not yet completed; the specific network message behind this command is determined by the provider. **Reversal** links a canceling/correcting message to the original transaction. Button names at different PSPs do not guarantee the same processing stage.

At Stripe, the validity limit of a specific card authorization is available as `capture_before`. After an uncaptured authorization expires, the hold is released; the duration depends on the network, the mode and the product. A partial capture usually releases the remainder; multiple captures require separate support. So designing around "all cards always hold for seven days" is wrong. [P02-S004, Authorization validity windows; Capture the funds](https://docs.stripe.com/payments/place-a-hold-on-a-payment-method)

**Incremental authorization** increases a previously authorized amount in a permitted scenario, for example when a hotel bill grows. It is not a repeat sale for the whole total. The increase may be declined; the state of the original hold is established from the result of the specific transaction, without mixing up an increase in the amount with an extension of the validity period; you cannot promise the customer a service for the added amount just because the original authorization went through. Mastercard describes separate rules for preauthorization, increasing/extending an authorization and clearing, including regional changes. They need to be read for the specific transaction type. A practical API example distinguishes changing the amount from extending the validity period. [P02-S040, Adjust the pre-authorisation amount; Extend the authorisation](https://docs.adyen.com/online-payments/classic-integrations/modify-payments/adjust-authorisation). [P02-S002, §§2.5, 2.9, 2.18](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/transaction-processing-rules.pdf)

### A timeline with T+

Synthetic example: a 100 USD order, a fee of 3.20 USD, a capture of 80 USD after one item is canceled. For simplicity, the fee on the final sale is notionally 2.62 USD: 80 × 2.9% + 0.30.

| Moment | Event | Buyer | Merchant |
|---|---|---|---|
| T, 10:00 | Auth 100 USD | Balance 500; available 400 | Money not yet received |
| T, 14:00 | Capture 80 USD | 80 is presented; the rest of the hold should be released | A claim for 80 once processing is accepted |
| T, cut-off | The transaction is included in the cycle | Posting depends on the issuer | The data is included in clearing |
| T+1 | Settlement between participants | Notional final balance 420 | The PSP shows 77.38 due for payout |
| T+2 | Payout and credit | No new debit | The merchant's bank has received 77.38 |
| T+3 | Delivery | The buyer has received the goods | The order is fulfilled |

Here T+1 and T+2 are **assumptions of the example**, not the timing for any card. Cut-off is the boundary for acceptance into a settlement cycle; a transaction sent after it may fall into the next cycle. The time zone, weekends, the payout currency and the merchant's contract affect the calendar. Float is the time between two economic events when one party has already provided value and the other has not yet received available money; income from such an interval does not arise automatically.

**Net settlement.** If bank A owes B 1,000 USD and B owes A 700 USD, after bilateral netting a transfer of 300 USD from A to B remains. This saves liquidity but does not remove the need to keep all the original obligations. In multilateral settlement, each participant gets a single position against the whole system, rather than one transfer for each purchase.

**Prefund/postfund.** In the first case, a participant places money in advance for future transactions. In the second, it gets a limit or pays the calculated obligation later. You need to pin down the object: a bank's prefund in a settlement system, a program's deposit with a sponsor and a merchant's reserve at a PSP are three different relationships. A fast payout to the merchant before network settlement means that someone is funding this time gap and taking on the risk.

**FX.** A price of 100 EUR, a card account in USD and a payout to the merchant in IDR create several possible conversions. The rate applied to the hold does not have to match the rate of the final presentment. Reconciliation needs the original amount/currency, the debited amount, the settlement amount/currency, and the rate and fee of each conversion. Do not infer FX income from the difference between two amounts without units.

### Why a capture can also be incomplete

At Adyen, manual capture is asynchronous. The acknowledgment that the request was received, the `CAPTURE` notification and a possible later `CAPTURE_FAILED` have different meanings. The integration must handle these transitions, and financial reconciliation must be built on reports. [P02-S005, Manual capture; Failed capture](https://docs.adyen.com/online-payments/capture)

A practical check for the example: total capture equals 80; refunds do not exceed the permitted remaining capture; fee 2.62; net payout 77.38; 80 = 77.38 + 2.62. If the statement shows 76.38, the missing dollar is a separate unexplained difference, not "probably a fee". Until a document is found, it stays open.

<a id="module-2-3"></a>
<a id="23-банковские-платежи-instant-payments-и-open-banking"></a>
## 2.3 Bank transfers, instant payments and open banking

**Question:** how does a transfer from an account differ from a card purchase, and what exactly does open banking add?

**Answer:** a bank payment changes account balances through the banking system; open banking describes access and actions through an API. The API, the message format and the settlement system are separate layers.

### 2.3.1 Credit transfer and direct debit

In a **credit transfer**, the payer instructs its PSP to send money to the payee. In a **direct debit**, the payee initiates a collection from the payer's account on the basis of a prior authorization — a mandate. Permission to access a statement is not permission to debit money.

**Teaching credit transfer of 250 EUR.** Before the transaction, the buyer has 1,000 EUR and the merchant has 100 EUR. The buyer's bank accepts the instruction and checks the account, authority and restrictions. After execution, the buyer's balance is 750 and the merchant's is 350. Between the banks, one bank's settlement asset decreased and the other's increased by 250; at the aggregate customer level, 1,100 EUR were preserved. If both customers are at the same bank, internal entries are enough: there is no interbank transfer for this transaction.

**Teaching direct debit of 40 EUR.** A customer has authorized a utility company to collect regular debits. The company submits a collection with a reference to the mandate, its PSP sends the instruction into the system, and the customer's bank debits the account. The initial 200/300 EUR of the customer/company become 160/340. But a permitted later refund will create a reverse flow; the credit does not cancel the rights provided for by the scheme.

SEPA Direct Debit Core provides a refund on request without justification within eight weeks after the debit, and a separate regime for unauthorized debits, with a period of up to 13 months. In B2B there is no such right to a refund of an **authorized** transaction, and the payer's bank checks the mandate; this is not a universal "irreversibility of all business transfers". [P02-S010, Main differences between Core and B2B](https://www.europeanpaymentscouncil.eu/what-we-do/sepa-direct-debit)

It is important to read the words for exceptions in the local vocabulary:

- **Reject** — a refusal before the relevant stage of execution.
- **Return** — the return of a previously processed payment on grounds defined by the system.
- **Recall/request for return** — a request to return funds; the request itself does not prove a return.
- **Reversal** — a permitted correction of an original erroneous transaction; the rules limit the reasons and the deadlines.

For example, Nacha permits an ACH reversal for certain originator errors and requires it to be made within five banking days after the settlement date. This mechanism cannot be used as an arbitrary cancellation of a purchase or a return of a transfer that the customer knowingly sent to a fraudster. Even a permitted reversal may come back for lack of funds. This is a US ACH rule, not a rule for all A2A. [P02-S008, reversal versus return; permitted errors; timing; no funds available](https://www.nacha.org/news/second-chance-understanding-ach-reversals)

### RTGS and deferred net settlement

**RTGS**, real-time gross settlement, settles each accepted obligation separately in real time. **Deferred net settlement**, DNS, first accumulates/nets obligations and then settles the total. The speed of the customer interface does not determine this choice.

Imagine three banks: A owes B 100, B owes C 90, C owes A 80 EUR. The gross turnover is 270 EUR. The resulting positions: A pays 20, B receives 10, C receives 10. Netting reduced the required final transfer of liquidity to 20 EUR. However, until final settlement the system must manage the risk of non-performance. A future offsetting payment does not always help in RTGS: if the 100 from A goes first and A currently has 20, it needs incoming funds, credit liquidity or a designated liquidity-saving mechanism.

The Bank of England reports that Faster Payments processes customer payments in near real time 24/7, but net settlement in RTGS takes place three times per business day; weekend cycles are settled on the next business day. Prefunded money limits a participant's permitted net position. So "the money is available to the recipient" and "the banks have already settled with finality" may run on different clocks here. [P02-S006, Faster Payments Service; Prefunded net settlement](https://www.bankofengland.co.uk/payments/payment-settlement)

For FedNow, Operating Circular 8 (in effect from 2026-04-01) defines the Settlement Account as the master account of the participant or of its correspondent. §7.1 ties finality to the earlier of the debit/credit entry and the sending of the Advice of Credit; the on-screen balance may update later. A return is made as a new transfer referencing the original, and a request for return does not itself move money. When the outcome is unknown, the status is checked first so that a duplicate is not sent. Liquidity remains a separate task. [P02-S042, §§2.39,7.1,9.1.16,9.6–9.8](https://www.frbservices.org/binaries/content/assets/crsocms/resources/rules-regulations/040126-operating-circular-8.pdf). The early product sheet S007 is kept as historical material from before the 2023 launch.

| Class | What we compare | What must not be assumed |
|---|---|---|
| US ACH | Batch credits/debits, standard and same-day cycles | Same-day does not mean instant final protection from returns |
| SEPA Credit Transfer | A scheme for EUR transfers between participants | SEPA is not one bank and not one settlement engine |
| SCT Inst | An instant EUR transfer under separate rules | All European accounts/providers have the same availability |
| Faster Payments | A fast customer transfer in GBP | Customer-facing speed equals the frequency of RTGS settlement |
| FedNow | An instant service with Federal Reserve settlement | Any bank customer can automatically use it |

For SCT Inst, as of the reading date, the EPC points to rulebook 2025 v1.1: funds must become available within a ten-second limit; precise timestamp and timeout rules apply. The page explicitly separates the adopted edition from a future change to the address format on 2026-11-15. This is a useful example of why "version 2025" can remain in effect in 2026. [P02-S009, Rulebook currently in effect; Regulatory changes](https://www.europeanpaymentscouncil.eu/what-we-do/epc-payment-schemes/sepa-instant-credit-transfer/sepa-instant-credit-transfer-rulebook)

### 2.3.2 Cross-border: correspondents, FX and messages

If a bank has no direct access to the required currency system, it can use a correspondent bank. **Nostro** is "our account at another bank" from the owner's point of view; **vostro** is the same account as "your account with us" from the servicing bank's point of view. These are not two separate bags of money. A network of such accounts makes it possible to fulfill international obligations, but it adds counterparties, data checks and the need for liquidity. [P02-S035, Cross-border payments; correspondent banking example](https://www.bis.org/publications/aer-2025/next-generation-monetary-financial-system); [P02-S043, §7010.1 Vostro account, PDFp30](https://www.federalreserve.gov/boarddocs/supmanual/cbem/7000.pdf)

**Teaching transfer.** A customer pays 1,000 EUR; the agreed rate is 1.10 USD/EUR. The instruction comes to 1,100 USD. Notional deductions of 10 USD by an intermediary and 5 USD by the beneficiary's bank result in a credit of 1,085 USD. If the contract promised the recipient exactly 1,100 USD, the deduction arrangement breaks the expected result, even though all the bank messages may have been technically successful. You need to decide in advance who pays each fee, lock in the FX quote and check that the corridor is available.

Swift carries financial messages between organizations. Delivering an instruction over the network is not the same as moving the settlement asset and crediting the final recipient. A message acknowledgment is useful for tracing; the result of the transfer is established by the participants' statuses and the entries on the relevant accounts. [P02-S011, How does Swift work?](https://www.swift.com/about-us/who-we-are/what-swift)

**ISO 20022** is a set of models and definitions for financial messages. From the catalog you get message descriptions, schemas, usage guides and sometimes examples. Having ISO-compatible XML does not give access to a banking system and does not guarantee compliance with a specific profile. [P02-S012, Which documents can I download?](https://www.iso20022.org/catalogue-messages)

A teaching map of the families: `pain` — customer initiation; `pacs` — interbank processing; `camt` — account management, reporting and related requests. A typical transfer involves `pain.001` — credit transfer initiation, `pacs.008` — interbank customer credit transfer, `pacs.002` — status, `camt.053` — statement. These are labels of purpose, not a ready-made serialization scheme: the full version, which fields are mandatory and the permitted statuses are set by the profile. [P02-S039, Payments Initiation; Bank-to-Customer Cash Management](https://www.iso20022.org/iso-20022-message-definitions?business-domain%5B0%5D=1)

In practice, you need to match: the business message ID, the end-to-end reference, your own order ID, the bank transaction reference, the amount/currency and the remittance information — details of what the payment is for. One business payment can produce several messages and several statuses. For example, Fedwire describes `pacs.002/PDNG`, after which `ACSC` or `RJCT` arrives; a request to return a previously settled transaction has the type `camt.056`. These values are given here **in the Fedwire profile**, not as the global semantics of any `pacs.002` record. [P02-S013, FAQ: PDNG; return of funds; UETR](https://www.frbservices.org/resources/financial-services/wires/faq/iso-20022/format)

A practical case: the Reddit author `Consistent-Virus-959` explains why a valid `pain.001` is rejected by a bank after additional checks. The available date of the post is shown as "4mo ago"; the exact day has not been established. This is the author's description of an integration risk; the incidents at the named banks have not been independently verified. At the end of the post, the author promotes a validator/explainer they are developing; this interest is taken into account when assessing the post. The teaching conclusion is confirmed by the architecture of the standards itself: check the XML, the system profile, the bank profile, the sender's rights and the balances separately. [P02-S032, main post](https://www.reddit.com/r/fintechdev/comments/1tfi95l/why_a_valid_pain001_file_can_still_be_rejected_by/)

**DvP/PvP.** Delivery versus payment links the transfer of a security to the cash settlement; payment versus payment links two currency payments. The principle: the finality of one obligation occurs if and only if the finality of the other occurs. If you sell 1,000 EUR for 1,100 USD and hand over the EUR long before receiving the USD, principal risk arises — you can lose the entire principal amount, not just the exchange-rate difference. PFMI Principle 12 describes eliminating this risk by linking the settlements; it does not guarantee that any given international transfer already uses PvP. [P02-S001, Principle 12](https://www.bis.org/committees/cpmi/pfmi/overview)

### 2.3.3 Open banking and open finance

An account provider maintains the account. A data recipient receives the permitted data. A payment initiator transmits a payment instruction. Open finance extends the object of access beyond payment accounts; the ability to read data about a loan does not mean the ability to change the contract or debit money.

In the historical UK Open Banking profile, a domestic-payment consent goes through `AwaitingAuthorisation → Authorised → Consumed` or `Rejected`. The document explicitly warns that `Consumed` does not reflect the status of the payment transaction itself. This example is taken from a published page with the heading v3.1.2 inside the v3.1.3 path; it illustrates the separation of states and **is not claimed to be the current mandatory version for all UK banks**. [P02-S014, Status; State Model](https://openbankinguk.github.io/read-write-api-site2/standards/v3.1.3/resources-and-data-models/pisp/domestic-payment-consents/)

Authentication establishes who is taking part; authorization establishes which actions are permitted; consent describes the customer's agreement to a specific access. For long-term access, the duration, revocation and the list of accounts, data recipients and operations also matter. A one-time payment authorization and statement access lasting many months have different life cycles. FAPI 2.0 is an OAuth 2.0 security profile for the secure issuance and use of access tokens; an API security profile is not a payment scheme or a credit license. [P02-S015, §1 Scope; §5 Security profile](https://openid.net/specs/fapi-security-profile-2_0-final.html)

**Pay-by-bank for 250 EUR.** The store creates a payment link → the customer goes to the bank → the bank authenticates them and shows the payee/amount → the customer confirms → the initiator receives the result → the store checks the payment status. The browser's return via `return_url` means only navigation. The user may close the tab after successful execution; the return link may open before financial completion. So the order stores `pending`, and then the verified state from a server-side event/request and reconciliation. A refund is handled as a separate process, with the correct recipient and a link to the original payment.

### 2.3.4 Instant payments, fraud and choice

Fast transfers shorten the time in which an error can be noticed before execution. **Confirmation/verification of payee** matches the entered payee against the account in the designated system. A positive name match does not prove that the commercial offer is honest. **APP scam**, authorized push payment scam: the customer authorizes the transfer themselves, but does so as a result of deception; in an unauthorized payment, there is no authorization. Checks and reimbursement differ for these situations.

An example of local protection: the UK PSR describes a reimbursement regime for eligible APP transfers from 2024-10-07, with a maximum of 85,000 GBP, for individuals, microenterprises and charities; there are conditions and exclusions, and an ordinary civil dispute about goods does not automatically become APP fraud. This regime cannot be carried over to ACH, SEPA, QRIS or any foreign transfer. [P02-S016, protections; who is protected; exclusions](https://www.psr.org.uk/information-for-consumers/app-fraud-reimbursement-protections/)

When choosing A2A, ask: is the customer's account available; what information will be checked before sending; what is the point of finality; who funds liquidity; what happens with a wrong payee; how to handle an ordinary refund; what counts as proof of credit. "No chargebacks" can reduce one risk for the merchant and at the same time weaken buyer protection — the economics must be calculated together with trust and conversion.

<a id="module-2-4"></a>
<a id="24-эквайринг-и-ценообразование"></a>
## 2.4 Acquiring: what the price is made of

**Question:** who gets the "2.9% + 0.30 USD"?

**Answer:** this cannot be determined from the advertised rate. It shows the contractual price under the stated conditions; a breakdown of costs requires processing details and the provider's invoice.

**MDR**, merchant discount rate, is the merchant's rate/price for acceptance. **Interchange** in a typical purchase is an inter-participant fee directed to the issuer; **scheme fees** are the network's charges; **acquirer/PSP markup** is the add-on charged by the participant serving the merchant. Visa separately explains that the merchant negotiates the merchant discount with its financial institution, while interchange serves as a transfer fee between the acquirer and the issuer. [P02-S017, Interchange reimbursement fees](https://usa.visa.com/support/small-business/regulations-fees.html)

**Blended** combines the components into one rate. **IC++** shows interchange and scheme fees separately from the agreed markup. This increases cost visibility but does not guarantee a lower total for every card mix. In tiered pricing, the label non-qualified often denotes a pricing category in the contract; a specific scheme rate cannot be inferred from the word itself. Cross-border surcharge, currency conversion, the minimum monthly fee, the authorization fee and equipment are checked separately.

### A teaching breakdown and the effect of ticket size

A 100 USD purchase at a notional blended rate of 2.9% + 0.30 costs 3.20 USD. Suppose the report shows interchange 1.70, scheme fees 0.25 and other charges/markup 1.25. The sum adds up: 1.70 + 0.25 + 1.25 = 3.20. These components **are not published Visa or Stripe rates**.

| Ticket | Fee under the same formula | Effective percentage |
|---:|---:|---:|
| 5 USD | 0.445 USD before rounding | 8.9% |
| 20 USD | 0.88 USD | 4.4% |
| 100 USD | 3.20 USD | 3.2% |
| 1,000 USD | 29.30 USD | 2.93% |

With a 5 USD ticket, the exact accounting fee depends on rounding in the contract; you cannot promise to charge a fraction of a cent. The fixed part has a particularly strong effect on cheap digital goods.

Now let us compare teaching IC++ terms: interchange 1.70, scheme fees 0.25, markup 0.40, processing 0.10. The total is 2.45 USD versus 3.20; a saving of 0.75. But if another card has interchange of 2.70 and scheme fees of 0.50, the same contract will give 3.70 USD. You need to compare a weighted portfolio by country, card type, channel and purchase size, not the two best lines of the price list.

Adyen's documentation separates interchange, scheme fees and markup and explains how to reconcile the invoice with the payment accounting report. This is an example of the level of detail one PSP makes available, not independent proof of savings from its services. [P02-S018, Payment method fees; Interchange; Scheme Fees; Markup](https://docs.adyen.com/reporting/invoice-reconciliation)

### Full cost and profit

Consider 1,000 teaching purchases of 100 USD each: GMV 100,000, initial gross margin before payments 30,000. Processing at 3.20 gives 3,200. Add 10 unrecoverable fraud losses of 100 each and 10 dispute fees at a notional 15 each. Then 30,000 − 3,200 − 1,000 − 150 = 25,650 USD before other costs. If these fraud losses are already included in the initial margin, subtracting them again is a mistake — the model must state its base explicitly.

A refund fee, a non-returned original processing fee, a monitoring penalty and a chargeback fee are different line items. A penalty may relate to a program or a month rather than to an individual sale. A withheld reserve is a restriction on liquidity and potential coverage for future claims; it is not always an expense at the moment it is withheld. So a payout smaller than sales does not mean that the whole difference has become the PSP's revenue.

**Checking an offer:** gather the full tariff and a sample invoice; state the period/currency; reproduce the calculation on your own portfolio; separately calculate fraud, refunds, disputes, FX, the reserve and the cost of payout delay. Only after that does the claim "0.5% cheaper" become verifiable.

<a id="module-2-5"></a>
<a id="25-fraud-3ds-risk-engines"></a>
## 2.5 Fraud, 3-D Secure and risk scoring

**Question:** why can a successfully authenticated payment still be fraudulent, while very strict anti-fraud can harm the business?

**Answer:** an identity check does not answer every question about intent, the goods and the recipient of the money. Any filter at the same time lets through some bad transactions and declines some good ones.

### What 3DS checks

**EMV 3-D Secure**, 3DS, passes data about the purchase, the device and the context for authentication in remote card payments. A typical architecture involves a 3DS Server on the payment acceptance side, the network's Directory Server and the Access Control Server, ACS, on the issuer's side. The issuer can make a decision without additional interaction — the frictionless flow — or require a challenge: confirmation in an app, a one-time code or another supported method. 3DS authentication and the subsequent financial authorization are separate processes: a successful challenge does not create money in the account. [P02-S019, EMV 3DS overview](https://www.emvco.com/emv-technologies/3-d-secure/); [P02-S037, Challenge flow: Business Overview](https://www.emvco.com/dynamic/emv-3-d-secure-whitepaper-v2/challenge-flow/business-overview/); [P02-S041, Frictionless flow: Business Overview](https://www.emvco.com/dynamic/emv-3-d-secure-whitepaper-v2/improving-risk-emv-3-d-secure-whitepaper-v2-analysis-and-frictionless-flow/business-overview/)

**SCA**, strong customer authentication, is a regulatory category of strengthened authentication in the relevant regulation; **3DS** is a technical protocol. They are not synonyms. The European model has exemptions under defined conditions, for example low-value and transaction risk analysis, TRA. Requesting an exemption does not mean gaining an unconditional right to the payment: the issuer may require authentication. Specific amounts, cumulative counters and the limits of application must be checked against the rule in force. In this research, EUR-Lex did not return readable text of the consolidated rule; so a table of legal thresholds is deliberately not reproduced here. [P02-S022, §4, pp.27–32](https://www.ecb.europa.eu/press/intro/publications/pdf/ecb.ebaecb202512.en.pdf); [gap P02-S038](Sources.md#p02-s038)

### Liability shift: a narrow area of protection

Liability shift transfers a defined liability for fraud chargebacks when the network's conditions are met and the authentication results are passed on correctly. It is not insurance against any dispute. Stripe describes the typical shift of fraud liability to the issuer after successful 3DS and lists exceptions; not all situations and dispute reasons are covered. Even after authorization, protection may be downgraded or may require evidence. [P02-S020, Disputes and liability shift](https://docs.stripe.com/payments/3d-secure/authentication-flow)

| Teaching situation | What to establish | Why 3DS on its own is not enough |
|---|---|---|
| Stolen PAN, successful purchase without a confirmed shift | Fraud classification and the applicable rules | The merchant/acquirer may remain the bearer of the loss |
| Successful 3DS, correctly passed data, dispute over an unauthorized payment | Whether the shift is confirmed for this particular transaction | If the conditions are met, the fraud loss usually falls on the issuer |
| Successful 3DS, goods not delivered | Proof of delivery and the dispute reason | Authentication did not perform the sales contract |
| The user transferred the money to a fraudster themselves | The APP scenario and local means of reimbursement | The payer's identity may have been verified correctly |

In accounting terms, "the issuer bears the fraud loss" does not mean "the buyer has already been refunded". The date and mechanism of the credit to the customer, the merchant's documents and the settlements between PSPs are checked separately.

### Controls for different attacks

**Velocity** measures the intensity of events: many cards from one device, frequent small payments, a series of declines. **Device fingerprint** links the available attributes of a device/browser; it may change, be incomplete or wrongly merge users. A **network token** replaces the PAN in a defined context and can restrict reuse of the card details; it does not make the owner of a fraudulent store honest.

| Risk | Example | Suitable class of control |
|---|---|---|
| Card testing | Hundreds of checks of stolen card details | Rate limiting, linking attempts, monitoring declines |
| Account takeover | A hacked account with a saved card | Login protection, step-up, control of device/address changes |
| APP scam | A fake supplier persuaded the customer to pay an invoice | Payee verification and checks on changes to payment details, context-based warnings |
| Mule account | The recipient quickly disperses stolen money | Recipient verification, a graph of links and flows, control of outgoing transfers |
| Merchant fraud | The merchant takes money with no intention of fulfilling the order | Business due diligence, monitoring of fulfillment/refunds, reserves |

This is a design map of controls, not proof of their effectiveness. Excessive collection of device data also has a cost and legal limits; the usefulness of a specific attribute must be tested on your own task.

### The economics of false positives

Suppose that out of 10,000 teaching attempts, 100 are fraudulent and 9,900 are honest. A rule blocks 80 fraudulent and 300 honest attempts:

- recall = 80 / 100 = **80%** — the share of fraud found;
- precision = 80 / 380 = **21.05%** — the share of fraud among blocks;
- false-positive rate = 300 / 9,900 = **3.03%**;
- 20 fraudulent attempts get through.

With an expected loss of 100 USD per fraud and a margin of 25 USD per honest purchase, the prevented losses are 8,000 and the lost margin is 7,500. Before the cost of the check, customer churn and retries, the gain is only 500 USD. A system with an impressive recall may bring almost no benefit.

**Rules** set explicit conditions; **ML** estimates patterns from labeled data. A label is an observed outcome: confirmed fraud, a dispute, a manual investigation. A chargeback does not always mean fraud, and the absence of a chargeback on yesterday's transaction does not guarantee honesty. The practical scientific handbook by Le Borgne and co-authors shows the need to validate on a future time interval, with a delay in obtaining labels and with drift — changes in behavior — taken into account. This is a methodological argument, not a benchmark for someone else's store. [P02-S021, Validation strategies, introduction and hold-out approach](https://fraud-detection-handbook.github.io/fraud-detection-handbook/Chapter_5_ModelValidationAndSelection/ValidationStrategies.html)

In the 2025 EBA/ECB report, based on EU/EEA data for 2022–2024, card transactions with SCA usually had a lower fraud rate; for credit transfers a different relationship was observed, which the authors explain by the mix of riskier/larger transactions. More than half of the value of fraudulent transfers is linked to manipulation of the payer. These are observational data: the causal effect of a mandatory challenge for a specific store cannot be calculated from them. [P02-S022, Executive Summary, pp.6–7](https://www.ecb.europa.eu/press/intro/publications/pdf/ecb.ebaecb202512.en.pdf)

A practical cycle: identify the type of loss → choose a control → record the expected effect and the acceptable loss of conversion → run a limited experiment → wait for mature labels → check the monetary result and the segments → leave a human a clear analysis of the exceptions.

<a id="module-2-6"></a>
<a id="26-refunds-disputes-chargebacks"></a>
## 2.6 Refunds, disputes and chargebacks

**Question:** why are a merchant's refund and a chargeback different processes, even though the buyer may get the money back in both cases?

**Answer:** they differ in the initiator, the grounds, the deadlines, the evidence and the financial liability.

**Refund** — a return of money initiated by the merchant/payee under the rules of the product, the contract and applicable law. **Dispute** — a challenge to a payment. **Chargeback** — a process defined by the card scheme for allocating financial liability for a disputed transaction between the issuer and the acquirer. **Statutory redress** — remedies granted by law; they are not limited to a chargeback button. The detailed legal differences are in module 1.9.

For a purchase that has already been presented, a refund becomes a separate transaction linked to the original one. At Stripe, a refund can have pending/failed states; the refund reference helps the bank trace the movement. A merchant's message "we have issued a refund" does not confirm the bank credit to the customer. For an authorization that has not yet been presented, a cancellation rather than a refund may be required. [P02-S033, Refund and cancel payments; Pending refunds; Failed refunds; Trace a refund](https://docs.stripe.com/refunds)

### Dispute states and money

A simplified teaching diagram:

```text
purchase → customer complaint → check of the grounds
         → chargeback → merchant accepts → closed with merchant liability
                      → evidence / representment
                          → accepted: withheld amount returned
                          → dispute continues
                             → pre-arbitration, if applicable
                             → arbitration / decision
```

A reason code classifies the grounds: fraud, a processing error, an authorization problem, a dispute about goods/services. Representment/second presentment means presenting the transaction again with evidence that the original transaction was valid. Arbitration hands the dispute over for resolution under the network's procedure; it is not automatically a state court. At Mastercard, some further steps have conditions and exceptions: the simplified diagram does not replace the Chargeback Guide. [P02-S003, §§3, 5.1–5.3, pp.6–11](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/chargebacks-made-simple-guide.pdf)

**Teaching economics.** A sale of 100 USD, an original fee of 3.20, 96.80 paid out to the merchant. After a dispute, the PSP debits 100 and a notional dispute fee of 15. The net cash result of all these stages: 96.80 − 100 − 15 = **−18.20 USD**, still before the cost of the goods. If the merchant wins, the 100 is returned; if the contract does not return the fee, the result is **81.80 USD**. You must not subtract the original 100 from profit a second time if the reversal of the revenue has already been recorded by another entry.

Stripe describes exactly this kind of separate debit of the disputed amount and the fee, and does not allow an ordinary refund to be processed in parallel with an open dispute in its system. A customer's message "I have withdrawn the dispute" does not close the process automatically either: the provider requires the corresponding actions and evidence. These are the terms of one specific PSP; the size and refundability of fees depend on the contract and the country. [P02-S036, Receive a dispute; Dispute fees; Dispute withdrawals](https://docs.stripe.com/disputes/how-disputes-work)

### Evidence must address the reason

For "did not receive the goods", you need fulfillment data: what was delivered, to whom, when and to which address. For duplicate processing — the two identifiers, the amounts and an explanation of whether these really are two purchases. For "I don't recognize the payment" — a clear descriptor, the link between the order and the customer, and confirmation of authentication. A screenshot of `approved` does not answer the delivery question; parcel tracking by itself does not prove that the right cardholder authorized the payment.

**Friendly fraud/first-party misuse** — the buyer disputes their own genuine purchase or abuses the process. But a misunderstood descriptor, a family purchase, a technical duplicate and undelivered goods cannot automatically be declared the customer's lie. The facts are established first.

A dangerous race: the store made a refund of 100, and at the same time the buyer initiated a chargeback of 100. Two independent processes that both succeed financially can produce double compensation. The operator needs the original transaction, the refund status/reference, the dispute ID and a single ledger; a repeat refund "just in case" makes the problem worse.

There is no universal deadline of "120 days for any dispute": the count may depend on the reason, the expected fulfillment date and the network. A practical case card contains the provider's specific deadline, the source of the rule, the person responsible, the amount at risk and the list of evidence. The need to respond remains until the source of the process has confirmed closure.

<a id="module-2-7"></a>
<a id="27-message-level-card-tech-как-реально-ходит-auth"></a>
## 2.7 How a card payment request travels

**Question:** what data makes it possible to explain a decline without saying "the bank just won't let it through for some reason"?

**Answer:** you need the original request, the place where the decline arose, the message profile applied and the linking identifiers. A red indicator in the dashboard only presents part of this information.

### 2.7.1 Dual-message and single-message

In **dual-message**, authorization and financial presentment are separate. In **single-message**, one financial format combines authorization and clearing data. The name single-message does not mean there are no responses, reversals or subsequent interbank settlement. Mastercard publicly describes both modes and notes that single-message covers different products. So the formula "all debit = single, all credit = dual" is wrong as a global rule. [P02-S003, §2.2, p.5](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/chargebacks-made-simple-guide.pdf)

The practical consequence: the team needs to find out which financial action is hidden behind a PSP endpoint. A `sale` command may automatically perform several stages; manual capture is available only in a supported model. A refund after a financial transaction does not become a "hold release" just because the button looks similar.

### 2.7.2 ISO 8583: a minimal vocabulary

ISO 8583 is used through specific network/processor profiles. The public Worldpay ISO 8583 Reference Guide V2.63, March 2026, describes **its own** profile; it is not the full open text of the ISO standard and not the specification of any particular network. The MTI defines the message type; the bitmap shows which fields are present. For example, in this profile `0100/0110` is an authorization request/response and `0200/0210` is a financial request/response. [P02-S024, §1.2, p.6](https://docs.worldpay.com/assets/pdf/Worldpay_ISO_8583_Reference_Guide_V2.63.pdf)

| Field in the profile under review | Teaching purpose |
|---|---|
| DE2 | PAN or a designated network token |
| DE4 + DE49 | Transaction amount and currency |
| DE11 | STAN — systems trace audit number |
| DE18 | Merchant category, MCC |
| DE37 | RRN — retrieval reference number |
| DE38 | Authorization identification response |
| DE39 | Response code |
| DE55, where applicable | Chip/EMV transaction data |

[Fields: P02-S024, Chapter 5](https://docs.worldpay.com/assets/pdf/Worldpay_ISO_8583_Reference_Guide_V2.63.pdf)

STAN, RRN, the authorization code and the internal order ID cannot be treated as interchangeable, globally unique keys. For an investigation, a composite link is useful: provider, merchant account, time, amount/currency, a safe card identifier and network references. You must not store a full dump of sensitive card data just for the convenience of support.

A gateway often hides the message packaging, the network identifiers and the translation of response codes. This makes integration easier but does not remove the need to obtain this data through an authorized support/reporting channel when a transaction is disputed.

### 2.7.3 AVS, CVV/CVC and authentication data

**AVS**, address verification service, compares the cardholder's address data in a supported scenario. **CVV/CVC** checks the card verification value; its result is not confirmation of delivery or of the buyer's identity. Mastercard describes AVS and CVC2 separately and explicitly highlights their regional applicability. [P02-S002, §§2.2, 2.15, pp.45, 67–68](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/transaction-processing-rules.pdf)

3DS passes its results into the linked authorization chain: the authentication value, the ECI and the identifiers defined by the scheme/PSP. You cannot invent one mandatory ISO 8583 field for all variants of 3DS. A network-token cryptogram is verifiable cryptographic data for one specific use of a token; it is a different object from a static PAN and a printed CVV. PCI SSC separately describes the use of an EMV Payment Token with a dynamic cryptogram and/or sufficient domain controls. [P02-S028, Payment Tokens](https://www.pcisecuritystandards.org/faqs/1326/)

**DE55** is usually associated with EMV data from a chip transaction. It is not "a container where any 3DS and wallet credentials always go". You need the official profile, format and permitted set of tags for your route; closed network fields are not reconstructed here.

### 2.7.4 A decline, analyzed

Below is a **synthetic trace** built on a public vocabulary; it is not a log of a production purchase and not a serialized message ready to be sent.

```text
Order O-204: 125.00 USD
Attempt A-1: 14:03:11Z, card credential = masked/token reference
STAN: 731204; RRN: reference-R1
PSP result: Refused
Raw response: 65 — Authentication Required, Mastercard route
Capture: none
```

The diagnosis is limited: authentication is required on the route under review. The next step is an SCA/3DS flow supported by the PSP; then a new attempt linked to the same order and to the previous attempt. Simply repeating the unchanged request does not satisfy the requirement. Code `05` means a general decline and does not prove insufficient funds; `51` reports that reason in the mapping cited. A **soft decline** usually means a condition that can be fixed; a **hard decline** is a situation where retrying without changing the grounds is impermissible or useless. These are providers' working categories, not a magic universal ISO bit. [P02-S023, Visa and Mastercard raw responses](https://docs.adyen.com/development-resources/raw-acquirer-responses)

Another situation: the application received a timeout, but there is no raw response at all. Then the claim "issuer declined" is not confirmed. You need to find out whether the request reached the issuer, whether the network is answering for the issuer in the stand-in mode provided for by the rules, whether the PSP itself declined it, and whether there are financial consequences. A retry with a new random reference before the status is clarified can create a second hold or debit. An HTTP 200 is not enough either: it may contain a business decline.

### 2.7.5 Capture and presentment

Let us continue the example: after authentication, attempt A-2 received an approval for 125 USD. The delivery is split into two parts worth 80 and 45 USD. If the contract supports only one capture, the team has no right to assume that sequential captures of 80 and 45 are possible. If multicapture is allowed, you need separate capture IDs, a reference to the original authorization, the remaining authorized amount and a completion flag.

Clearing carries the financial presentment data and the links to the original transaction. Mastercard requires checking acknowledgments, correcting rejected messages and reconciling clearing with the net settlement advisement; the published rules separately define the proof of funds movement when reports diverge. [P02-S002, §2.18.1, pp.68–69](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/transaction-processing-rules.pdf)

A check for the teaching case: 80 + 45 = 125; presenting 80 a second time after a lost response does not turn the permitted total into 205. Even when all three API calls returned "received", the source of financial truth must show which presentments were accepted and which money entered settlement. If only two UI screenshots are available, the result remains unknown.

<a id="module-2-8"></a>
<a id="28-apm-device-wallets-qr-bnpl"></a>
## 2.8 Other ways to pay: wallets, QR and installments

**Question:** do all the alternative buttons at checkout replace the card or banking system?

**Answer:** no. Some change the interface and the credentials, others use a bank transfer, and others add credit. First determine exactly which layer is changing.

### 2.8.1 Device wallets

**Apple Pay**, in a card payment as Apple describes it, uses a Device Account Number and a unique security code after the user is verified. This changes how the card credential is represented, but does not remove the issuer, the acquirer, authorization or financial presentment. [P02-S026, Paying with cards using Apple Pay](https://support.apple.com/en-ca/guide/security/secfbd5c0e54/web)

In the **Google Pay Web API**, `PAN_ONLY` refers to a card stored in a Google Account and returns the PAN with expiry data; `CRYPTOGRAM_3DS` refers to supported Android device tokens and returns a cryptogram. So the claim "every Google Pay payment is tokenized by the device" is wrong. The name `CRYPTOGRAM_3DS` does not by itself mean that the buyer has just gone through a browser-based EMV 3DS challenge. [P02-S025, CardParameters.allowedAuthMethods](https://developers.google.com/pay/api/web/reference/request-objects)

The word **token** is ambiguous too. `PaymentMethodToken` can denote a signed and encrypted API envelope that contains either a PAN or a device PAN with a cryptogram. This is not the same thing as a network token. In a direct integration, the merchant verifies the signatures and decrypts the payload; in a gateway integration, a supported provider handles the envelope. The scope of data and key handling therefore differs. [P02-S027, ECv2 overview; verification and decryption](https://developers.google.com/pay/api/web/guides/resources/payment-data-cryptography)

PCI SSC excludes correctly used EMV Payment Tokens from Account Data outside the token provider's token data environment, but keeps the requirements where the PAN is processed or where there is a connection to the relevant environment. It does not follow that "we added a wallet button, so the whole site is out of PCI". Likewise, whether a liability shift is possible is determined by the actual data/conditions of the transaction, not by the wallet's logo. [P02-S028, Applicability of PCI DSS](https://www.pcisecuritystandards.org/faqs/1326/)

### 2.8.2 Account/bank APMs and returning from the bank

APM — alternative payment method — is a historical market label. For a local buyer, a widely used bank method may be the main one. iDEAL-like and Sofort-like here denote classes of checkout through a bank account with confirmation/initiation of a transfer; the current availability of a specific brand is checked separately.

With a redirect, the user goes to the bank's environment; an embedded flow keeps more of the interaction in the merchant's interface. In both cases the engineering task is the same: link the order, the payment session and the bank result; handle cancellation, a closed tab, a repeated callback, a long pending state and the expiry of the link. An old success URL opened a second time must not trigger a second shipment.

**Teaching case.** A buyer sent 60 EUR for order O-60 but closed the app. The store did not see the return URL and created a second payment. A correct investigation first checks the first payment ID and the bank statement. If the first transfer is found, the order is fulfilled once. If there are two real transfers, the second one is recorded as an overpayment and returned to the confirmed payer. The system has no right to "fix" a duplicate by deleting one of the receipt records.

### 2.8.3 QR and Indonesia

QR is a way of presenting data. In **merchant-presented mode**, MPM, the merchant shows the code; in **consumer-presented mode**, CPM, the buyer shows the code. A static MPM usually requires the amount to be entered; a dynamic one can tie the amount to a specific order. Scanning does not by itself say which account or payment instrument funds the purchase.

Bank Indonesia defines QRIS as the national standardization of QR payments; processing involves PJPs, switching institutions and other elements of infrastructure, and PJPs/switching institutions must have BI authorization. The merchant connects through an authorized PJP. So it is not enough for a foreign PSP to be able to draw a QR code: it needs a permitted participation model, local contracts and a suitable partner/access. [P02-S029, Para Pihak; Cara Menjadi Merchant; Karakteristik](https://www.bi.go.id/id/fungsi-utama/sistem-pembayaran/ritel/kanal-layanan/QRIS/default.aspx)

**Teaching purchase in a café:** 150,000 IDR; the merchant belongs to a category with an MDR of 0.7%. The fee is 1,050 IDR, and the amount after MDR is 148,950 IDR. The 0.7% rate is published by BI for the specified UKE/UME/UBE categories; the rules for microenterprises and special categories are different. This is a calculation based on the MDR, not a promise of the exact final bank payout without reading the contract. [P02-S029, Skema Tarif QRIS](https://www.bi.go.id/id/fungsi-utama/sistem-pembayaran/ritel/kanal-layanan/QRIS/default.aspx)

The customer funds the purchase through their supported PJP; the merchant/acquirer receives the result via QRIS, and the merchant expects settlement/payout under the contract. The domestic purchase is denominated in IDR. Cross-border QR adds a currency route; having a compatible QR does not mean that any foreign wallet is accepted in any SEA country.

**Failure:** the buyer shows a "success" picture. It does not prove a credit to this particular merchant: there could be a wrong payee, a replay of an old screenshot or a wrong amount in a static QR. The control is your own notification/record from the PJP with a merchant reference, amount and time. Refunds require your own PJP's procedure; card chargeback protection cannot be attributed to QRIS by analogy with card acquiring.

### 2.8.4 BNPL — credit at checkout

**Buy now, pay later**, BNPL, combines a sale with financing for the buyer. The lender assesses the risk, finances the purchase and receives repayments on a schedule. The contractual seller/Merchant of Record is determined by the sales model; the lender does not automatically become one. In the 2022 CFPB report, pay-in-four is treated as a separate class of interest-free consumer credit: usually 25% upfront and three subsequent payments at two-week intervals. This is how the study defines its sample, not the only BNPL variant in the world. [P02-S030, §2.1 Product Definition](https://files.consumerfinance.gov/f/documents/cfpb_buy-now-pay-later-market-trends-consumer-impacts_report_2022-09.pdf)

**Synthetic BNPL for 200 USD.** Under the contract, the merchant is due 190 after a fee of 10. The buyer pays 50 upfront and another 50 on days 14, 28 and 42. At the start, the lender transfers 190 to the merchant, receives 50 from the customer and finances a gap of 140. In the future it is owed another 150: the notional difference of 10 covers funding cost, processing, fraud, default, servicing and profit. Before these costs are accounted for, the 10 is the model's revenue spread, not net profit.

If the customer misses the last payment, a credit debt arises. If the merchant did not deliver the goods, a separate commercial dispute arises; which party bears the losses is determined by the product and the contract. Underwriting — assessing the ability and willingness to repay the debt — is different from checking whether a card has 50 USD right now. Loan stacking, several parallel loans, can worsen solvency even when the first installment succeeds.

With a full refund after two installments, the customer has already paid 100, and another 100 remains on the schedule. You need to settle at the same time the refund of the purchase price, what happens to the 100 already paid, and the remaining debt. Simply sending the customer 200 by a separate bank transfer does not guarantee that the credit schedule is canceled. Klarna has a separate refund operation with a `refund_id`; its documentation distinguishes full/partial refunds and states the limitations of authorizations. [P02-S031, Full/Partial refund; Success response](https://docs.klarna.com/acquirer/klarna/after-payments/order-management/manage-orders-with-the-api/refund-orders-and-manage-authorizations/)

**Delayed card capture is not BNPL:** with a later capture, the merchant postpones financial presentment, but this does not create a lender, underwriting or an installment schedule. Even if a BNPL provider also uses the word authorization, the economic contract is different. Whether a specific BNPL purchase can be funded via crypto-in cannot be inferred from the user holding crypto assets: it requires a permitted provider flow, activity, source of repayment and jurisdiction. No such combination is confirmed here.

### 2.8.5 How to choose a payment method

| Task | Candidate | What to check before choosing |
|---|---|---|
| A small ticket in Indonesia | QRIS through an authorized PJP | MDR category, your own confirmation, payouts/refunds |
| A remote sale to a European consumer | Card/wallet and pay-by-bank | Bank availability, conversion, fraud and different dispute rights |
| Regular bills under a mandate | Direct debit | Authority, deadlines, returns/refunds, a reserve for exceptions |
| An expensive item paid for in installments | BNPL | Lender, funding, borrower protection, refund allocation |
| An autonomous purchase by an agent | A supported card or bank flow | The agent's authority, consent, user-presence, limits, confirmation of the result |

These are options for analysis, not a recommendation for any specific business. The minimum comparison formula: **fees + fraud/credit losses + the cost of disputes and support + the cost of liquidity + margin lost to declines**. Then the constraints apply: country, license/contract, currency, ticket size, user-presence and the buyer rights required. A cheaper rail does not win if the target customers cannot use it or do not trust the purchase.

## Exercises

1. **States.** An auth of 120 USD is approved, a capture of 90 is accepted by the API, the webhook was lost, and the goods have already been delivered to the buyer. Which four questions are still open?
2. **Netting.** A owes B 200 EUR; B owes C 140; C owes A 90. Determine the resulting positions and explain why this is not a list of the original transfers.
3. **Price.** For 400 purchases of 25 USD each, the charge is 2.4% + 0.20 USD. In addition, there are five disputes at 15 USD each and two unrecoverable fraud losses of 25 each. Find the costs and the effective percentage of turnover.
4. **Anti-fraud.** Of 50 fraud attempts, 40 were found; 160 honest purchases were also blocked. Find precision/recall and state what is missing to estimate profit.
5. **Message.** A `pacs.002/PDNG` from Fedwire and a browser success URL were received for the same order. Can reconciliation be closed?
6. **Wallet.** The team claims: "Google Pay always sends a device token; so PCI and the risk of someone else's card disappear." Find two independent errors.
7. **Refunds.** After two BNPL installments of 50 USD, the store refunds a 200 USD order. Which money and debt objects need to be checked?
8. **Dispute.** The transaction is 3DS-authenticated; the buyer disputes undelivered goods. Which data matters more: the successful challenge or proof of fulfillment?

---

## Answers and criteria for understanding

1. Whether the capture was accepted financially; whether there is clearing/settlement; whether the remaining 30 of the hold was released; whether the money was paid out to the merchant, and how much. Delivery confirms that the goods were provided but does not answer these financial questions. On a timeout, the debit must not be repeated without clarifying the status.
2. A: −200 + 90 = **−110**; B: +200 − 140 = **+60**; C: +140 − 90 = **+50**. The positions sum to zero. The final payments total 110 instead of the original turnover of 430, but the primary transactions are kept for the obligations and for investigations.
3. Turnover 10,000; fee per purchase 0.60 + 0.20 = 0.80; processing **320**; disputes **75**; fraud **50**. Total **445 USD**, or **4.45%**. The answer is correct under the explicit condition that fraud and charges are not already included in the original fee and do not duplicate other losses.
4. Precision 40 / 200 = **20%**; recall 40 / 50 = **80%**. You need the size of the losses, the margin on an honest purchase, the cost of manual review and the effect of a decline on future sales; percentages alone are not enough.
5. No. PDNG means an intermediate state in this profile; the return URL is a browser event. You need the final status, the corresponding credit/statement and a match of the amount, currency and references.
6. `PAN_ONLY` and `CRYPTOGRAM_3DS` provide different credentials; an encrypted API envelope is not the same as a network token. PCI scope depends on the data actually processed and the connected environment, and fraud protection depends on the scenario and the conditions of the transaction.
7. Whether the merchant refund was accepted; whether the 100 paid earlier has been returned to the customer or correctly offset; whether the future 100 of debt has been canceled; whether the merchant's settlement and fees have been adjusted under the contract. A single refund ID does not prove the whole result.
8. Proof of fulfillment answers the "not delivered" grounds. 3DS helps establish authentication and the applicable fraud-liability shift; it does not deliver the goods for the merchant. The answer must preserve the distinction between dispute reasons.

## Summary, sources and limits

A payment map consists of several linked processes: permission → technical messages → financial obligations → settlement → available money → order fulfillment. Refunds, disputes and credit add processes of their own. The most useful habit for an operator is to name the specific object, amount, currency, participant and the evidence of the current state.

The [source catalog](Sources.md) contains the actual scope of reading, the versions and the limitations. The [claims register](Claims.md) links the material conclusions to sources. Public processor guides do not replace closed network specifications; real live decline/capture logs were not used in the research, and the examples are synthetic. Current SCA thresholds and the full legal regime across all jurisdictions have not been established. No BNPL/crypto-in combination is declared permitted or ready for use.

Next steps in your learning: [Chapter 3](../03-Visa-and-Mastercard-cards/README.md) — card schemes; [Chapter 4](../04-Payment-providers/README.md) — PSPs, PayFacs and MoRs; [Chapter 8](../08-Integrations-and-reliability/README.md) — accounting, reconciliation and engineering invariants; [Chapter 7](../07-AI-agent-payments/README.md) — agent scenarios, following the overall structure.

---

### Sources and fact-check

[Sources](Sources.md) · [Verifiable claims](Claims.md) · [Chapter fact-check](../../Fact-check/02-How-a-payment-works/README.md)

The text was prepared by agents and passed an independent agent review on 15–17 September 2026. The teaching edition has limitations; dates and limits of applicability are given in the sources. [Edition record](../../Methodology/Edition-record.md).

<details>
<summary>History and metadata of the original manuscript</summary>

This information describes the research stage before publication. The current visibility is public; the status of the whole edition is `reviewed_with_limitations`. The earlier labels `private` and `independently_reviewed_draft` are kept only as history.

**Version:** v0.1 · **Status:** `independently_reviewed_draft` · **Cutoff:** 2026-09-15 · **Author:** research agent part-02 · **First review:** REVIEW.md (historical or internal material; kept by the owner, outside this copy) · **Visibility:** private.

The author's historical closing note: The status remains `independently_reviewed_draft` until a separate independent review.

</details>

[← Market rules and licensing](../01-Market-rules-and-licensing/README.md) · [Contents](../README.md) · [Cards: Visa and Mastercard →](../03-Visa-and-Mastercard-cards/README.md)
