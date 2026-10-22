[← How a payment works](../02-How-a-payment-works/README.md) · [Contents](../README.md) · [Payment providers →](../04-Payment-providers/README.md)

<a id="часть-3-visa-mastercard-и-нюансы-схем"></a>
# Chapter 3. Cards: Visa and Mastercard

> Card network rules: participants, fees, tokens and restrictions.

**6 lessons** · Knowledge cutoff: **15 September 2026** · [Sources](Sources.md) · [Fact-check and limitations](../../Fact-check/Results.md)

## In this chapter

- [3.1 · A card network as a system of rules](#module-3-1)
- [3.2 · How Visa works](#module-3-2)
- [3.3 · How Mastercard works](#module-3-3)
- [3.4 · Other card networks](#module-3-4)
- [3.5 · Tokens, stored cards and subscriptions](#module-3-5)
- [3.6 · Merchant categories, prohibitions and high risk](#module-3-6)
- [Practice: a case, exercises and explained answers](#practice-a-case-exercises-and-explained-answers)
- [Summary, limits and further reading](#summary-limits-and-further-reading)

---

This chapter explains card schemes as a set of contractual rules, economic relationships and technical services. It covers 3.1–3.6 of the v02 structure. It assumes familiarity with the [payment lifecycle in Chapter 2](../02-How-a-payment-works/README.md). What matters here are the consequences of a specific scheme for integration; bank transfers, acquiring in general and the full dispute cycle are not repeated.

After reading, the reader will be able to:

- establish who has the right to issue a card, accept a payment and answer to the scheme;
- distinguish purchase, funding, push payment and refund;
- separate the PAN, network token, provider token, cryptogram and consent to charge;
- explain where the price of a payment, the currency difference and an interchange qualification error come from;
- check the MCC, a contractual prohibition and registration against the exact type of activity;
- find the applicable rule with its version, region and effective date, and not mistake a marketing page for production approval.

All examples below with fictional participants and amounts are **synthetic**. Tables of real fee lines are labeled separately. Sources were accessed on 2026-09-15; full details on reading, versions and rights are in [Sources](Sources.md), material claims in [Claims](Claims.md). Real-world financial or legal use requires the applicable contracts and specialist review.

<a id="module-3-1"></a>
<a id="31-scheme-как-институт"></a>
## 3.1 A card network as a system of rules

### Why a working API does not yet create a payment scheme

A **card scheme** is an organized set of rules for issuing and accepting payment cards. A **brand** is the mark by which a product is recognized. A **network** transmits and processes messages. A **processor** performs technical processing for a participant. These functions may belong to one group, but it helps to first separate them by role. The ECB studies card schemes and processing entities separately, because influence over the rules and technical processing are different positions in the payment chain. [P03-S029, §§1–3](https://www.ecb.europa.eu/pub/pdf/other/ecb.reportcardschemes202502~1614226b0a.en.pdf)

In the **four-party model**, the four corners are the cardholder, the issuer, the merchant and the acquirer. The scheme connects the participants through common rules; it is not a fifth bank account of the buyer. In the **three-party model**, the issuer and acquirer functions are combined in the scheme operator. The names describe the contractual architecture, not the number of companies, servers or payment messages. The ECB discusses both models in its textbook, §4.2 and the diagram on p. 56. [P03-S028](https://www.ecb.europa.eu/pub/pdf/other/paymentsystem201009en.pdf)

Imagine a network with a million cardholders but no shops: there is nowhere to use the card. A network of shops without buyers is just as useless. This is a **two-sided market**: the value for one side depends on the participation of the other. Synthetically, a 0.10 USD discount to the issuer might help issue more cards; growth in acceptance might help those cards get used. But it does not follow from this logic that any fee is optimal for society. The scheme, the issuer, the shop and the buyer have different benefits and costs. BIS Working Paper No. 1163 adds a sub-acquirer to the model: access to the network can be sold to a partner and used against a competitor at the same time. What was read here is the official summary, which is neither a proof of the model nor an empirical assessment of the market. [P03-S039, Focus/Contribution/Findings](https://www.bis.org/publications/working-paper-1163-interchange-fees-access-pricing-and-sub-acquirers-payment-markets)

### Authority and responsibility

**Issuing rights** give a participant the right to issue certain products; **acquiring rights** give the corresponding right to accept them. A sponsor provides a contractual route to participation under its own responsibility, within the limits of the program. Processor certification answers the question of technical compatibility; a scheme license, the question of contractual participation; a government authorization, the question of the right to carry out a regulated activity. No document automatically replaces the others. Mastercard separately describes principal, affiliate, BIN sponsor, the license and the area of its use. [P03-S002, §§1.1,1.6–1.9](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-rules.pdf)

**Synthetic example.** The startup "Port" has integrated acceptance and charges 0.20 USD per transaction. A merchant sells a course for 100 USD. The acquirer serves the merchant, the processor transmits messages, the issuer maintains the buyer's account. "Port" does not have its own right to issue cards merely because its interface returns `approved`. To work out the obligations, you need four separate answers: who signed the contract with the shop; who is a scheme participant; who must pay out to the shop; who will cover the refund of money in a dispute. Even if "Port" drew all four screens, the answers do not follow from the interface.

Visa's public rules have regional limitations and omit proprietary/security information. Mastercard warns that a posted public copy may lag behind the official applicable rules. So the claim "Visa allows this" should be turned into a record: product → activity → region → participant → clause → effective date → contractual confirmation. [P03-S041, Rules impacting processors and merchants](https://www.mastercard.com/us/en/business/support/rules.html); [P03-S042, introductory paragraphs](https://www.visa.com/en-us/support/visa-rules)

Local law is not overridden by a private rule. The reverse is also untrue: the legality of a business does not oblige a particular acquirer to serve it. A practical failure: getting a sales manager's agreement for "software", actually selling money exchange, and discovering after the first transactions that the sponsor had considered a different activity. The fix starts with an honest description of the transaction and the contractual perimeter, not with a new name for the button.

<a id="module-3-2"></a>
<a id="32-visa--развёртка"></a>
## 3.2 How Visa works

### 3.2.1 Product map

Debit, credit and prepaid describe where the ability to pay comes from: an account, a credit obligation or value provided in advance. Consumer and commercial describe the purpose of the program. Fleet is a specialization for vehicle fleets; virtual is a way of providing card details without a mandatory physical card. A virtual card can be a commercial credit card: these axes are not mutually exclusive. Visa has separate rules for virtual accounts and product programs, and the fee schedule distinguishes consumer debit, prepaid, credit and commercial. [P03-S001, §§4.1.7 and 4](https://usa.visa.com/content/dam/VCOM/download/about-visa/visa-rules-public.pdf); [P03-S016, product tables](https://usa.visa.com/content/dam/VCOM/download/merchants/visa-usa-interchange-reimbursement-fees.pdf)

A **Product ID** is a classification attribute of a product in the scheme's messages/reference tables. **Interchange qualification** is the check of whether a transaction meets the conditions of a fee category. The marketing word "business" on a website does not prove a specific product ID, and a product ID by itself does not yet determine the whole price. An analysis needs the country of issuance and of acceptance, the purpose of the product, the channel, and the characteristics of the transaction and its processing. Practical rule: two prices can be compared only after these inputs have been aligned.

### 3.2.2 Network and messages

VisaNet is Visa's processing infrastructure; authorization checks whether a transaction is possible, clearing presents the financial details, settlement discharges the obligations between participants. The public rules separate these stages (§1.7.3–1.7.6), and the US fee document also covers PIN-authenticated transactions with a separate reference to Visa Network 002. Therefore one cannot make a universal equation "Visa logo = the same two-message sequence". The share of dual-message in a specific segment was not measured in this research. [P03-S001, §1.7](https://usa.visa.com/content/dam/VCOM/download/about-visa/visa-rules-public.pdf); [P03-S016, p. 4, notes](https://usa.visa.com/content/dam/VCOM/download/merchants/visa-usa-interchange-reimbursement-fees.pdf)

**Synthetic timeline.** A 100 USD purchase: at 10:00 the issuer approves the authorization; at 18:00 the shop sends the capture; after the relevant cycle closes, clearing takes place; then the acquirer receives its settlement position, and the merchant receives a payout on a separate schedule. These hours are for teaching purposes, not a Visa SLA. If at 10:01 the buyer sees a decrease in the available balance, this is evidence of a hold/posting at the issuer, but not yet a bank payout to the shop. If the capture was 90 USD, you need to reconcile the authorization of 100, the presentment of 90 and the release of the remaining 10; you cannot require all messages to be equal.

### 3.2.3 VTS: token, PAR and cryptogram

**Visa Token Service, VTS** replaces the PAN — primary account number, the main card number — with a network payment token. In the published VTS diagram, the acquirer passes the token to Visa, Visa checks permitted use and maps it to the PAN, and the issuer makes the authorization decision. That is, the token does not shift responsibility for sufficiency of funds onto the shop. [P03-S009, How it works, p. 2](https://usa.visa.com/dam/VCOM/global/products/documents/visa-token-service-fact-sheet.pdf)

**PAR — Payment Account Reference** links the PAN and the related tokenized transactions for accounting, analytics and services such as loyalty. PAR by itself cannot be used to initiate a payment transaction. [P03-S048, FAQ1374, answer ¶3](https://www.pcisecuritystandards.org/faqs/1374/). A separate teaching inference: linking records does not prove the buyer's consent. The VTS product page separately describes PAR Inquiry, Cloud Token Framework and Click to Pay: the latter is a guest checkout method, not proof that a particular merchant has received permission to store the card for future payments. [P03-S008, PAR Inquiry / Cloud Token Framework / Click to Pay](https://usa.visa.com/products/visa-token-service.html)

**Synthetic example.** One card has a phone token T1 and a stored shop token T2; PAR makes it possible to link the history of one account. A 20 USD purchase with T1 and a 30 USD purchase with T2 give a turnover of 50 USD, not automatically two different customers. But disabling a stolen phone and ending a shop subscription are different events. Combining analytics must not combine permissions. A cryptogram confirms that a payment credential was used in the intended context; a successful cryptographic check does not confirm delivery of the goods and does not cancel the other risk checks. The general model of token requestor, domain controls and lifecycle is covered in §3.5.

### 3.2.4 Visa Direct: AFT and OCT

In **Visa Direct for Card**, AFT — Account Funding Transaction — is used to pull funds from a card account in a funding scenario; OCT — Original Credit Transaction — to send funds to a recipient using card details. An OCT does not require that a corresponding earlier purchase from the sender existed. The originator must be a licensed Visa acquirer or operate under its sponsorship; a production program requires the full cycle, including settlement, disputes and reporting. Availability of funds depends on the receiving institution, the account and geography. [P03-S007, Getting Started / Implementation Overview](https://developer.visa.com/capabilities/visa_direct/docs-getting-started)

**Synthetic transfer.** Anna sends Boris 100 USD and separately pays a 2 USD fee. Suppose an authorized program uses an AFT for 102 USD, keeps 2 USD as revenue and sends an OCT for 100 USD. The economic equation: 102 = 100 + 2. These are two linked transactions, not a negative purchase. A successful AFT with a declined OCT leaves an obligation to return/deliver 100 USD. You cannot record `transfer_completed` on the first half, and you cannot automatically retry the OCT after a timeout: first the result of that same request is established. A real program may have a different funding and fee model; this example says nothing about the eligibility of Anna's account.

For a company payout after work has been done, there may be no AFT at all: the sender funds the program by an authorized method. Hence three independent checks: does the sender have the right to dispose of the funds; does the program allow this use case; did the specific recipient accept the transfer. An ordinary purchase authorization is not a proper way to disguise funding.

### 3.2.5 Cross-border, DCC and multiple currencies

There are at least four currencies: that of the goods' price, of the card transaction, of the cardholder's account and of the payout to the merchant. **DCC — Dynamic Currency Conversion** means an offer of conversion on the acceptance side. Visa requires showing both amounts/currencies, the rate and the additional cost, and leaving the choice to the cardholder; the decision may not be made for the customer. [P03-S014, What to expect](https://www.visa.com/en-us/personal/travel/dynamic-currency-conversion)

**Synthetic example.** In the shop the price is 100 EUR; the buyer's account is in USD. If EUR is chosen, a teaching rate of 1 EUR = 1.10 USD and a 1% issuer fee give 111.10 USD. DCC offers 114 USD straight away. The difference is 2.90 USD — 114 − 111.10; but this comparison holds only for the given rates. If the issuer also charges an additional fee for a foreign transaction in USD, the final DCC amount may turn out higher than 114. Such a fee must be read separately before the charge.

**Multicurrency pricing** — a shop's ability to set prices in several currencies — is not the same as DCC. A price of 100 USD set in advance for the US market differs in meaning from converting a just-chosen 100 EUR on a particular card. And the cross-border nature of a transaction is not determined by a currency mismatch as such: a French buyer and a foreign merchant may both use EUR. So the currency fee, the cross-border fee and interchange are separate fields of the model.

### 3.2.6 Fees and economics

Interchange in an ordinary purchase is the interbank component; the merchant discount/MDR is the price of the acceptance service for the shop. Visa explicitly distinguishes these concepts. Network/scheme fees pay for the corresponding scheme services, and the acquirer/PSP adds its own price. In a pricing agreement they may be bundled together or passed through as separate lines. [P03-S043, Interchange reimbursement fees](https://usa.visa.com/support/small-business/regulations-fees.html)

**Synthetic 100 USD receipt:** interchange 1.50; network fees 0.20; processing/acquirer margin 0.40. The total cost is 2.10 USD; the merchant is owed 97.90 USD. If 1 USD is held in a rolling reserve, today's payout is 96.90, but the acceptance expense remains 2.10: the reserve is a withheld claim until there is a basis for writing it off as a loss. If after reconciliation a separate monthly charge of 10 USD is found with ten payments, the effective cost rises by another 1 USD per payment.

**A real illustration of reading a fee schedule, not an offer of services:** Visa USA, effective 2026-04-18, Exempt Check Card, CPS/e-Commerce Basic Debit — 1.65% + 0.15 USD; in the adjacent regulated column — 0.05% + 0.21 USD, plus 0.01 USD with the stated issuer certification. On 100 USD this is 1.80 and 0.26/0.27 USD respectively. These lines cannot be carried over to an Indonesian commercial card or treated as the full MDR. [P03-S016, p. 4](https://usa.visa.com/content/dam/VCOM/download/merchants/visa-usa-interchange-reimbursement-fees.pdf)

Three levers for investigating cost: the right product/region, the right processing qualification, the contractual pass-through of fee layers. Manipulating the MCC to make things cheaper is not allowed: that is a change in the description of the business, not processing optimization.

### 3.2.7 Disputes and pre-dispute

Visa groups disputes into categories 10 Fraud, 11 Authorization, 12 Processing Errors and 13 Consumer Disputes. The current rules separate the process for categories 10/11 and 12/13; the familiar names Allocation/Collaboration from old presentations cannot be applied to all deadlines without checking. VROL — Visa Resolve Online — is used by participants to process disputes. For categories 12/13, Table 11-2 in §11.2.3 gives the acquirer 30 calendar days from the Processing Date of the pre-arbitration attempt to respond; for domestic Tanzania, 10. The issuer is given 10 calendar days from the Processing Date of the response to file for arbitration. These are inter-participant deadlines, not the merchant's window for responding to its PSP. [P03-S001, §§11.2–11.3, pp. 669–673](https://usa.visa.com/content/dam/VCOM/download/about-visa/visa-rules-public.pdf)

**Compelling Evidence 3.0** is a specific evidence mechanism against first-party misuse, when a genuine transaction is mistakenly or dishonestly disputed as someone else's. Visa's FAQ describes a package with two prior undisputed transactions and matching data. This is not a general argument "the IP matched, so any dispute is won" and not a defense against non-delivery. The historical FAQ of October 2022 explains the intent; whether a particular package applies is established from the current rules. [P03-S019, questions 1–7](https://usa.visa.com/content/dam/VCOM/regional/na/us/support-legal/documents/evolution-of-compelling-evidence-external-faqs.pdf)

Order Insight passes on purchase details, helping to recognize a transaction before a formal dispute. Verifi states that Visa issuers have access through VROL and non-Visa issuers through direct integration. The fact that the service belongs to the Visa ecosystem does not mean brand exclusivity or that all banks are connected. [P03-S020, closing paragraphs](https://www.verifi.com/order-insight-improved-placement-in-visa-issuer-dispute-platform.html)

**Synthetic case:** a 40 USD payment for "Talking Garden" appears as `PGT*GS`. The customer does not recognize the name. Showing the receipt and a recognizable name may explain the purchase; if the promised lesson was not unlocked, the same information does not refute a non-delivery claim. Evidence must answer the reason, and an automatic refund must not run in parallel with an already accepted chargeback without reconciliation; otherwise you may return 80 instead of 40 USD.

### 3.2.8 Monitoring and activity rules

VAMP combines monitoring of fraud, disputes and enumeration. In the public fact sheet, the ratio uses TC40 + TC15 counts over settled TC05 for CNP VisaNet; exclusions depend on pre-dispute/CE3.0 and the timing of the data extract. From 2026-04-01, the Excessive Merchant threshold in AP/Canada/EU/US is stated as 150 bps with additional conditions, including at least 1,500 counted events and a specified state of the acquirer's portfolio. [P03-S013, p. 1 and footnotes](https://corporate.visa.com/content/dam/VCOM/corporate/visa-perspectives/security-and-trust/documents/visa-acquirer-monitoring-program-fact-sheet-2025.pdf)

**Synthetic check:** after the applicable exclusions, 1,600 counted events and 100,000 settled transactions give 1.6% = 160 bps. This fraction alone is not enough: you need the geography, the volume threshold and the state of the acquirer's portfolio. A low ratio for a small merchant also does not guarantee that it will be served. **Enumeration** — guessing card details — can overload authorizations even if there are almost no sales. Separate rules for high-integrity activity are covered in §3.6.

<a id="module-3-3"></a>
<a id="33-mastercard--развёртка-без-ложной-симметрии"></a>
## 3.3 How Mastercard works

### 3.3.1 Products and brands

Mastercard covers consumer/commercial credit, debit and prepaid; Maestro and Cirrus have their own areas of application. The rules describe Mastercard POS, Maestro POS and ATM separately. In particular, routing Debit Mastercard to the Single Message System may affect the applicable set of rules; Mainland China has caveats. The consequence for integration: determine processing by account range, product, region and route, not just by the logo on the card. [P03-S002, Applicability, pp. 29–31](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-rules.pdf)

### 3.3.2 Dual/single message and settlement

In dual-message, authorization comes first, followed by a separate financial presentment. In single-message, one message carries the data for authorization and clearing together. This is a real difference in integration behavior, but it is not a "Mastercard single, Visa dual" contrast. Mastercard publishes support for both options; a refund must also be matched to the actual message system. [P03-S021, §§2.1–2.2](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/chargebacks-made-simple-guide.pdf); [P03-S003, §2.2.1](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/transaction-processing-rules.pdf)

**Synthetic example.** A service expects a goods capture after any transaction. It received a successfully processed single-message charge of 12 USD and sent another separate 12 USD sale "for capture". A possible outcome is two financial claims totaling 24 USD instead of one. The correct action is chosen based on the semantics of the response and the provider's contract. An API abstraction may hide the message system; in that case the provider must explain what exactly its `capture`/`refund` means, and the developer should not build a hidden second step on top.

The Mastercard Switch Rules provide for net settlement, allow agreed bilateral settlement, and separate the irrevocability of a financial message after cutoff from the finality of the transfer in the national settlement system. A correction may be a separate compensating message. This is a good example of why finality and the impossibility of a later refund are different properties. [P03-S004, §§3.1–3.1.2, p. 40](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-switch-rules-manual.pdf)

### 3.3.3 MDES and merchant integration

**Mastercard Digital Enablement Service, MDES** provides network tokenization. Mastercard describes enrollment with an issuer decision and additional authentication when needed; for COF, the merchant receives a token, and for payments, the corresponding cryptographic data. [P03-S012, How does tokenization work / online card on file](https://newsroom.mastercard.com/news/perspectives/2024/what-is-tokenization/)

The confirmed similarity between VTS and MDES is the replacement of the PAN with a token and the involvement of the issuer. The difference for a developer lies primarily in the specific interface, the token requestor registration and the fields provided by their processor. Public overviews do not prove identical lifecycle APIs or cryptograms, or a right to move a token requestor between PSPs. If a provider combines both schemes into one `payment_method` object, you need a storage contract, data for subsequent MITs and a documented migration route. A unified SDK does not make the underlying credentials interchangeable.

### 3.3.4 Mastercard Send / Move and payment transactions

Mastercard Move is published as a family of money movement solutions, including payouts to businesses and merchants. This is the product level; the rulebook separately defines a **Payment Transaction** as a transfer of funds to an Account that is not a credit reversing a previous purchase, and includes MoneySend. So the word `send` cannot be implemented with an arbitrary refund API. [P03-S040, use cases](https://www.mastercard.com/europe/en/business/payments/mastercard-move/payments-to-businesses.html); [P03-S002, Applicability, p. 30](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-rules.pdf)

**Synthetic payout.** A platform owes a courier 80 USD. Through an agreed provider it initiates a payout of 80 and pays 0.50 USD separately; after confirmed delivery, the obligation to the courier decreases by 80, the platform's money by 80.50, and the expense is 0.50. If only a transaction number has been returned, the obligation to the courier is not closed yet. If the payout is declined, that is not evidence that the funding has returned to the platform's bank account. Detailed eligibility, sender funds, screening, statuses and returns for Mastercard Send are not confirmed in this version by a full accessible service guide; no universal SLA is claimed.

### 3.3.5 Cross-border and FX: comparison along axes

Confirmed parallels and limits:

1. For both schemes, the currencies of the purchase, the cardholder account and settlement are distinguished; a single logo does not determine the final rate.
2. The Mastercard Currency Converter explicitly warns that the bank may apply a different rate and additional fees; if the authorization rate cannot be used, the processing rate is applied. The calculator does not replace the statement. [P03-S015, Please Note](https://www.mastercard.com/us/en/personal/get-support/currency-exchange-rate-converter.html)
3. For Visa, the public DCC notice sets out requirements for choice/disclosure; for Mastercard, the rate page separately limits the applicability of its rate in merchant/ATM conversion. These documents have different purposes, so they cannot be used to compare "which scheme is cheaper".
4. In the Mastercard Switch Rules, settlement conversion into the settlement currency is defined separately in §3.1.1. This is not the issuer's fee for the buyer. [P03-S004](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-switch-rules-manual.pdf)

**Synthetic FX failure.** The original 100 EUR purchase became 110 USD; a 100 EUR refund a week later at 1.08 gave 108 USD. The merchant returned the full original transaction amount, but the cardholder's account shows a difference of 2 USD. To determine who should compensate it, naming the rate is not enough: you need the reason for the correction, the issuer agreement and the corresponding dispute rule. These 2 USD cannot be automatically recorded as an underpayment by the shop.

### 3.3.6 Qualification and the price of a digital good

Mastercard lists among the qualification factors the MCC, the authorization–clearing interval, transaction data, enhanced data and volume. All conditions of a category must be met together. A cheap "digital commerce" rate is not a right to rename any service as digital goods. [P03-S017, How rates are determined](https://www.mastercard.com/us/en/business/support/merchant-interchange-rates.html)

**A real fee illustration:** the Canadian table of May 2026 for domestic consumer credit shows Digital Commerce Core 1.67%, World 1.90%, World Elite 2.13%, World Legend 2.23%; for the same Core there is a separate Standard rate of 1.96%. On a synthetic 100 CAD payment, the Core difference between 1.67 and 1.96 is 0.29 CAD. This is the selected interchange component when the conditions are met; the table is not a global Mastercard price. May 2026 denotes the edition read, based on the file name; the exact start date of these lines is not separately confirmed. [P03-S018, p. 2](https://www.mastercard.com/content/dam/mccom/ca/en/business/support/documents/interchange-rates-en-may-2026.pdf)

Digital sales raise additional questions: an app or a game; one-time access or a subscription; a virtual item inside a game or convertible value; who is legally the seller; where is the evidence of access provided. Sending an email does not prove the right MCC or delivery. A change in the business may change the required classification, even if the HTTP endpoint stays the same.

### 3.3.7 Dispute cycle and Ethoca

At Mastercard, a first chargeback may receive a **second presentment** — a re-presentment with an objection. Pre-arbitration and arbitration may follow; Mastercom is the case management interface. The public Guide 2025 groups reasons as fraud, authorization, point-of-interaction error and cardholder disputes, and the specific reasons differ by message system. This is a confirmed difference from Visa category numbering, which matters for building a reason reference table and evidence packages. [P03-S021, §§3–5](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/chargebacks-made-simple-guide.pdf)

Practical consequence: an internal reason `goods_not_received` is acceptable for analytics, but the original network reason, message system, dates and case steps must be stored. You cannot submit a Mastercard second presentment as a Visa dispute response just by changing the name. The full current Chargeback Guide was not available; a universal "120 days" for all reasons and automatic merchant response deadlines are not established here.

Ethoca Consumer Clarity shows recognizable purchase information in banking channels and provides for API integration. Smart Subscriptions adds subscription management; the current page calls Ethoca brand-agnostic. This confirms the positioning of the service, but not full coverage of issuers and merchants. [P03-S022, What makes us different](https://www.mastercard.com/global/en/business/cybersecurity-fraud-prevention/dispute-management/ethoca-consumer-clarity.html); [P03-S023, Powering the global subscription economy](https://www.mastercard.com/global/en/business/cybersecurity-fraud-prevention/dispute-management/smart-subscriptions.html)

### 3.3.8 Monitoring and high-risk activity

In the SPME Merchant Edition dated 2026-08-04, §8.2 says that **GMAP is suspended until further notice**. ECP calculates basis points as the current month's chargebacks over the previous month's Mastercard transactions. The numeric ECM/HECM thresholds are referred to another manual; historical figures are not presented as verified current ones. [P03-S005, §§8.2–8.3, pp. 87–88](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/SPME-Manual.pdf)

**Synthetic denominator trap.** In August there were 10,000 sales, in September 5,000; in September, 100 chargebacks. Under the described ECP denominator this is 100/10,000 × 10,000 = 100 bps. The ratio to September sales — 200 bps — is a different metric. It cannot be compared with VAMP without checking the numerator, denominator, period and exclusions. Registration of an activity, for example crypto, is yet another control axis, not a reward for a low chargeback ratio.

<a id="module-3-4"></a>
<a id="34-смежные-схемы"></a>
## 3.4 Other card networks

### A comparison that helps choose an integration

You cannot infer the acceptance model, token support or payout method from how well-known a brand is. The table below is a map of the confirmed public perimeter. "Not verified" means a gap in this research; it does not mean the function is absent. Geography means the scope of the document read or of the specific service. Comparable market shares of all six schemes for 2026 are not given here.

| Scheme | Authorization and participants | Tokens | Push / payout | Disputes | Geographic reference point and limit |
|---|---|---|---|---|---|
| Visa | The issuer decides; participants and VisaNet, §3.2 | VTS, device and e-commerce, PAR | Visa Direct for Card: OCT; possible AFT funding leg | Visa rules; Verifi requires a separate integration | Rules are global with regional conditions; the numeric fee here is US only |
| Mastercard | Issuer; single/dual-message, §3.3 | MDES; exact merchant API comparability is open | Send/MoneySend and the broader Move | Mastercard rules, Mastercom; Ethoca is not limited to one scheme | Rules with regional chapters; the numeric example is Canada only |
| Amex | A combined model is possible; in the US under OptBlue, acceptance is serviced by a third-party provider | Separate offerings for COF and digital wallets | A universal card push interface was not verified in this research | Amex rules and the agreement for the given acceptance channel are needed; Visa reason codes do not carry over | The OptBlue example is the US; a global token platform does not prove availability in every country |
| Discover | The specific issuer/partner chain must be checked against the contract; the full message specification was not read | Stored Token Services / Discover Digital Exchange; domain controls | The current public push rulebook was not read | Its own applicable rules; exact windows not verified | The service is published by Discover Global Network; a measured acceptance map was not obtained |
| JCB | J/Secure is a 3DS authentication layer; it is not itself a financial authorization | JCB and Adyen announced a COF token rollout on 2025-05-13 | A public specification for card payouts was not read | The full current dispute guide was not obtained | The announcement speaks of domestic/global merchants; the rollout outcome and shares were not measured |
| UnionPay | The described transfer requires a suitable recipient debit account; the purchase/auth specification is separate | The current merchant COF specification was not read | MoneyExpress: cross-border crediting to UnionPay debit cards in China, RMB | A transfer and a purchase cannot be analyzed with one assumed reason code | China is the specific destination of this service, not a statement about the network's whole geography |

Basis for the rows: [P03-S030, OptBlue FAQ](https://www.americanexpress.com/us/merchant/optblue.html); [P03-S031, Tokenization Services](https://network.americanexpress.com/globalnetwork/v4/products/card-on-file-tokenization/tokenization-services.html); [P03-S032, Stored Token Services](https://www.discoverglobalnetwork.com/solutions/fraud-security/stored-token-services/); [P03-S033, JCB/Adyen announcement](https://www.global.jcb/en/press/2025/202505131100_products.html); [P03-S034, J/Secure FAQ](https://www.global.jcb/en/products/security/jsecure/faq/); [P03-S035, MoneyExpress](https://www.unionpayintl.com/en/servicesProducts/servicesBenefits/crossBorderRemittance/index.shtml). The first two rows summarize the documents of §§3.2–3.3.

With Amex OptBlue, the provider sets the acceptance price and is the merchant's point of contact. So "Amex always signs every merchant contract directly" is a wrong working model. To design reconciliation, you need to find out who sends the report, transfers the money and accepts dispute evidence. Similarly, the Discover brand on a payment instrument does not yet tell you the name of the party to your acquiring agreement. The term "three-party scheme" is useful for economics, but the architecture of a specific partner channel has to be drawn anew.

**Synthetic example.** A shop has one provider dashboard in which it receives payouts for Visa and Amex. One dashboard does not imply a single fee or the same dispute window. If the provider's report shows Visa 1,000 USD and Amex 400 USD, and the payout is 1,370 USD, the 30 USD of deductions must be broken down by the corresponding contracts. In a 100 USD dispute, you cannot send a Visa package just because the dashboard looks the same.

### National scheme and co-badging

A national debit scheme may serve a domestic purchase, while another scheme on the same card handles acceptance via a different route. **Co-badging** means having several payment brands/applications on one instrument. This differs from co-branding, where the card also carries the brand of an airline or a shop: a second commercial logo does not by itself create a second payment route.

In the ECB's 2025 report, national schemes are reviewed based on a 2024 survey and data from previous years. It is useful for mapping the market, not for a claim about today's share. In the EU, Art. 8 of Regulation 2015/751 governs co-badging and the choice of application: the payee may set a priority, but the cardholder must be able to change it among the accepted options. This article has been established to apply from 2016-06-09. What was read here is the official original text and its Art. 18, not a full up-to-date legal analysis. [P03-S029, §§1–3](https://www.ecb.europa.eu/pub/pdf/other/ecb.reportcardschemes202502~1614226b0a.en.pdf); [P03-S038, Arts. 8, 18](https://www.boe.es/buscar/doc.php?id=DOUE-L-2015-80958)

**Synthetic example.** Both card applications are accepted by the terminal. The domestic route costs the shop 0.08 EUR, the international one 0.22 EUR. The benefit of preferring the first is 0.14 EUR per transaction, or 1,400 EUR on 10,000 identical purchases. This arithmetic does not permit blocking the right of choice or sending a token of one domain over another network. First, the routing right, the presence of the required application and acquirer support are checked; then the price is calculated.

Whether a local solution is mandatory is a question of the specific law, instrument and transaction. For example, Bank Indonesia describes the national GPN and the logo requirements for ATM/debit cards, citing PBI 19/8/PBI/2017. This is not a basis for declaring GPN mandatory for any online purchase or any foreign visitor. An Indonesian launch will require separately checking the current act, the entities it covers and the domestic processing route. [P03-S036, Kartu ATM dan/atau Kartu Debet](https://www.bi.go.id/id/fungsi-utama/sistem-pembayaran/ritel/instrumen/default.aspx)

<a id="module-3-5"></a>
<a id="35-network-tokens-cof-subscriptions"></a>
## 3.5 Tokens, stored cards and subscriptions

### Four independent questions

Let us look not at abbreviations but at four decisions:

1. **What represents the card?** The PAN, a network payment token or the provider's internal identifier.
2. **What are the card details stored for?** Only for the current purchase or for subsequent transactions — credential on file, COF.
3. **Who initiates the transaction?** The cardholder in active interaction — CIT, or the merchant on a previously agreed basis without such interaction — MIT.
4. **How are identity and authority confirmed?** Establishing the owner at provisioning, authenticating a specific purchase and consent to future charges solve different tasks.

The Visa Stored Credential Framework 2017 defines CIT/MIT and distinguishes storage for future use from temporary processing of a single purchase. This is a historical original framework; the current fields of a specific integration are checked separately. Mastercard TPR dated 2026-06-09 distinguishes the initiation indicators C/M and types of MIT. Calling a server request "MIT" is not enough: the meaning of the transaction must match. [P03-S024, pp. 3–6](https://usa.visa.com/content/dam/VCOM/global/support-legal/documents/stored-credential-transaction-framework-vbs-10-may-17.pdf); [P03-S003, Transaction Identification Requirements, pp. 330–333](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/transaction-processing-rules.pdf)

**Synthetic matrix.** The buyer clicked "pay with saved card" — this is a CIT with COF. A monthly subscription charge submitted by the shop without the buyer's participation may be a recurring MIT if there is a valid basis. A one-time guest checkout may use a network token. A buyer may initiate a purchase through a wallet with a device token; this does not make the shop the holder of an open-ended permission to charge money. Neither "token", nor "server", nor "without entering the CVV" on its own answers the question of who the initiator is.

A **provider token** is usually a pointer inside its system: a notional `card_customer_42` is resolved by the provider into the credential in use. A **network token** takes part in the payment infrastructure with usage restrictions. Exporting the first value to a new acquirer may prove useless; transferring a network token also cannot be considered permitted without checking the token requestor, the domain and the contracts. This is an architectural conclusion, not a promise of VTS or MDES portability.

### How to trace a token from issuance to payment

In the EMVCo model there is a token requestor, which requests the token; a token service provider, which manages issuance; and an issuer, which performs the required establishment/verification of the owner. The token obtained is provisioned to the intended location, then presented and processed. Domain restrictions limit the context of use; the cryptogram, if used in the given scenario, protects dynamic data. In the guest-checkout use case studied, the merchant and the requestor may be different parties. [P03-S010, §§3–7 and 11.3, especially pp. 150–155](https://www.emvco.com/wp-content/uploads/2023/03/EMVCo-Payment-Tokenisation-A-Guide-To-Use-Cases-v2.2.1.pdf)

This is version 2.2.1 of the use-case guide, January 2023, not the latest technical specification. The current EMVCo index shows newer documents; a full reading of Technical Framework v2.4 was not included in this edition. [P03-S011, metadata only](https://www.emvco.com/emv-technologies/payment-tokenisation/) So the sequence above explains the roles rather than setting out an exhaustive current wire specification. The VTS and Mastercard product materials that were read confirm their own tokenization implementations, but do not prove that their APIs are identical.

**Synthetic state scenario.** Device token A and merchant token B have been issued for a card. The phone is lost; A is suspended. From this event one cannot logically infer that the subscription with B has been canceled or that the bank account has been closed. In the other direction, removing a card in the shop's interface should be tied to a clear action: a ban on future charges, deletion of the provider handle, a network token management request, or all of these. Verifying the result requires an event from each system; a vanished icon does not prove that all credentials have been revoked.

PAR helps match records, but does not make a payment anonymous. The research paper by Olivier-Anclin and co-authors, *Who Pays Whom?*, proposes separate privacy protocols, PrivBank/PrivProxy, for EMV contactless. The abstract, introduction, related work and Appendix B were read; the proofs and the experimental part were not fully checked. What matters for the chapter is the research question: protecting the PAN, making two purchases unlinkable and hiding the parties to a transaction are different properties. The paper does not prove deployment of its protocols in VTS/MDES. [P03-S045, pp. 1–2 of the paper and Appendix B](https://perso.limos.fr/~palafour/PAPERS/PDF/USENIX2025-Pay.pdf)

### Card updates and the life of consent

Visa Account Updater passes updated card details, expiry dates and statuses to participating parties; Mastercard ABU also handles old/new numbers and expiry. An update helps keep a credential working when a card is reissued. It does not create a new purchase agreement and does not replace cancellation of a subscription. The latter is a conclusion drawn from the difference between card data and the basis for a charge, not an agreement-management function claimed by the updater. [P03-S026, Visa Account Updater](https://developer.visa.com/capabilities/vau/docs); [P03-S027, How we use your personal information, effective 2025-10-01](https://www.mastercard.com/ca/en/abu-privacy.html)

**Synthetic example.** 20 EUR on the first day of each month has been agreed for a service. For July, August and September, 60 EUR was charged. The card was reissued in August, and the updater made it possible to process the August transaction. This is normal continuity of card details. If the subscription was canceled from September, the result permitted under the conditions of the example is 40 EUR; the updated card does not authorize the extra 20 EUR. If the monthly price changes to 25 EUR, contractual notice/consent and the applicable authentication scenario are checked separately. A credential may remain technically valid while there is no authority for the amount.

### Recurring and SCA: name the exact basis

Article 14 of RTS 2018/389 for the EU describes a series with the same amount and the same payee: SCA applies when the series is created, amended and first initiated; subsequent transactions may be processed without SCA under the conditions of the act. This is a narrow rule, not a universal exemption for all subscriptions. The original act applies from 2019-09-14. Changing 20 EUR to 25 EUR cannot be justified by the words "we already checked the card before". [P03-S037, Arts. 14, 38](https://www.boe.es/buscar/doc.php?id=DOUE-L-2018-80459); [P03-S044, correction to the Spanish text of Art. 14](https://www.boe.es/buscar/doc.php?id=DOUE-L-2020-80441)

The regulatory scope of a genuine payee-initiated MIT and the exemption for a payer-initiated series are different legal questions. The relevant EBA Q&As could not be reliably opened, so there is no promise here of "any MIT is outside SCA" or a full map of exemptions. For a real transaction, you need to determine the participants, geography, initiator, original consent and the actual behavior of the flow; then apply the legal rule and the scheme rule.

The public Mastercard recurring FAQ was updated in November 2022 and explains the requirements for subscriptions, trials and notifications. An important trap: after the October 2022 change, a receipt after each billing is called a best practice, with an exception for certain monitored merchants. So you cannot rewrite the old guidance as an unconditional present-day obligation of every SaaS. Current requirements, frequency, product type and region are checked against the partner's rules in force. [P03-S025, questions 1–9, 20–23](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/subscription_recurring-payments-and-negative-option-billing-merchants.pdf)

For an agent purchase, delegation must additionally be proven: who gave the instruction, what they authorized, how much, until when and how to revoke it. A scheduler that clicked a button on a person's behalf does not get MIT status by virtue of automation. Detailed delegated authorization belongs to Chapter 7; here it is enough to preserve the link "instruction → transaction → confirmation → money outcome".

<a id="module-3-6"></a>
<a id="36-mcc-prohibited-high-risk"></a>
## 3.6 Merchant categories, prohibitions and high risk

### Who classifies the business

**MCC — Merchant Category Code** — is the code for the merchant's type of activity. Mastercard places the assignment of the code on the acquirer, taking into account the main business and special rules. So the "category" field in a registration form is input information, not a final self-classification. The code must describe the real activity; the website text and the product range must be consistent with the registered perimeter. [P03-S002, §5.8.1, p. 116](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-rules.pdf)

The Mastercard Quick Reference Booklet dated 2026-06-02 distinguishes 5815 — digital audiovisual content, 5816 — games, 5817 — applications/software, 5818 — merchants selling digital goods from at least two of the categories 5815/5816/5817; the TCC must be compatible with the MCC. Buying in-game items does not automatically become buying cryptocurrency because of the word "token" inside a game. Nor does a digital form of delivery turn a financial asset into software. [P03-S006, MCC 5815–5818, pp. 162–164](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-quick-reference-booklet-merchant.pdf)

**Synthetic analysis of three baskets.** An editor license for 30 USD, an in-game item for 8 USD and an exchange of 100 USD for transferable cryptocurrency are three different economic transactions. To classify the third, you ask: what asset does the buyer receive; can the value be transferred/withdrawn; who is the counterparty to the exchange; where do the fiat and the crypto go; who bears the obligation if nothing is delivered. The label "digital delivery" answers none of these questions. A 103 USD receipt with a 3 USD fee does not make the 100 USD principal amount a payment for an app.

### Three different reasons to stop

| Level | What is established | What serves as evidence |
|---|---|---|
| Law | Whether the activity, the customer, the jurisdiction and the specific asset are permitted | The applicable act, license/registration and specialist assessment |
| Scheme | Whether the type of transaction is allowed, how to flag it and whether the merchant must be registered | The exact clause of the program in force and confirmation of compliance |
| Acquirer / sponsor / provider | Whether this partner takes on such a risk and on what terms | The contract and written confirmation of the specific business description |

These levels do not replace one another. "Prohibited" is a prohibition in the stated document and scope. "High-risk" is a classification that triggers additional conditions; it does not mean universal illegality. "Registered" is the fact of registration, not a promise of unobstructed operation in any region. A partner's approval may turn out to be narrower than the scheme's general list.

In the Mastercard SPME dated 2026-08-04, specialty categories include, among others, certain adult, gambling, skill games, cyberlocker, securities and cryptocurrency activities. This is a list of specific types, not a ban on all games and digital content. For cryptocurrency, §9.4.9 provides for registration before processing, a check of legal permissibility and special flagging: MCC 6051/TCC U; TTI P70 for the relevant crypto/token transactions, P76 for fully fiat-backed stablecoins and CBDCs. The document itself distinguishes the definitions from these reporting categories. [P03-S005, §9.1, p. 111; §9.4.9, pp. 126–127](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/SPME-Manual.pdf)

At Visa, Table 7-9 classifies crypto-related transactions and separates acquiring an NFT asset from certain transactions where the NFT is merely a form of representing an ordinary good/right. The High-Integrity Risk program refers to a separate guide. This cannot be replaced with Mastercard TTI, nor can the full current Visa list be reconstructed from someone else's blog. [P03-S001, §7.4.14.1, Table 7-9, pp. 563–565; §10.4.5, pp. 635–636](https://usa.visa.com/content/dam/VCOM/download/about-visa/visa-rules-public.pdf)

### Where exactly a crypto-adjacent product stops

Imagine an agent service: the buyer pays 103 USD by card, the service promises 100 USD in a stablecoin and takes 3 USD. The flow has to stop at the design stage before it can be treated as an ordinary software checkout: you need to determine who buys/sells the asset, which funding and special registration rules apply, who holds the money and what happens on partial fulfillment. If the card charge went through but the tokens were not issued, there is an unfulfilled obligation; charging again does not remove it.

Another model: a separate provider converts the buyer's asset and pays an ordinary shop for a lawful purchase in fiat. It cannot automatically be equated with the first model or declared free of crypto controls: the counterparties, flows and regulated roles change. This is a **working hypothesis about different models**, which is tested against contracts and primary rules. Assigning a merchant MCC is only one step. For money, the source of funding, sender identification, a permitted payout, refunds and reconciliation also matter.

It is convenient to record the result of the check on a single operational card: actual product → seller under the contract → scheme and program → MCC/additional indicators → country → approving participant → date → permitted money route → limitations. When the product or the payout route changes, it is exactly this card that is checked. That way it becomes visible where the established fact ends and the assumption begins.

---

## Practice: a case, exercises and explained answers

### A real DCC story and the limit of evidence

In a public post on r/CreditCards, user **u/gbcox** describes a restaurant in Brazil: according to him, he asked to pay in BRL, but the staff chose USD with a markup of about 12%, and the receipt stated that he had agreed. The author wrote about complaining to his bank; the outcome is not established in the original post that was read. The UI shows "2y ago"; the exact date is not confirmed here. This is a self-selected story, not a proven violation or an estimate of frequency. [P03-S047, original post](https://www.reddit.com/r/CreditCards/comments/1i851tq/international_travelers_beware_dynamic_currency/)

The author's claim that DCC is fraud in itself is not accepted: Visa publishes conditions for an informed choice, and the Mastercard guide requires offering a choice and not imposing DCC by default. An investigation needs the receipt, the amounts/currencies, the terminal data and the complaints to the bank. Comparing the story with the rule produces a verifiable question: who made the choice, and what confirms it? [P03-S014](https://www.visa.com/en-us/personal/travel/dynamic-currency-conversion); [P03-S046, Cardholder Experience Guidance, pp. 31–32](https://www.mastercard.com/content/dam/public/mastercardcom/na/global-site/documents/DCC-Guide-2025-Merchant-Version.pdf)

### Exercises

1. **Participants.** An app has a processor API key and a sandbox transaction with status `approved`. What three different grounds are still needed before claiming the right to issue cards?
2. **Price.** A 200 USD purchase; interchange 1.4% + 0.10 USD, scheme fee 0.20%, acquirer markup 0.30 USD, reserve 2%. What is the expense, what is the immediate payout, and what claim against the acquirer remains? All rates are for teaching purposes.
3. **Two legs of a transfer.** Funding of 51 USD went through, a 50 USD payout has an uncertain status, the fee is 1 USD. Can a second funding be launched? Which state must be established first?
4. **DCC.** The price is 150 EUR; the issuer route is 1.08 USD/EUR plus 1.5%; DCC offers 168 USD. What is the difference? What else needs to be checked besides the arithmetic?
5. **Monitoring.** Last month there were 20,000 Mastercard transactions; this month, 25,000 and 160 chargebacks. Calculate the ECP in bps using the definition discussed. Does the result prove inclusion in ECM?
6. **Credential.** A user chose a saved card and confirmed a new purchase. The provider passed a network token. Is this CIT or MIT, COF or guest? What changes with the next automatic bill under a valid subscription?
7. **Updater and consent.** A 12 EUR subscription was canceled before the next billing date; then the updater passed on a new PAN. How much may be charged for the next month under these conditions? Why does a technical success fix nothing?
8. **MCC.** A website offers to download a game and to buy a transferable stablecoin. Why can't the whole flow be assigned the games MCC, even if the shop has a single interface? What information does the acquirer need?
9. **Reading a source.** A blog says "GMAP has launched", while the public Mastercard SPME dated 2026-08-04 speaks of a suspension. Which claim can be included in the current chapter, and what could change the conclusion?
10. **Migrating an integration.** A PSP stored `card_42`; a new PSP accepts "network tokens". What questions prevent simply transferring the string? Why does the presence of a PAR not replace the answers?

### Answers and criteria

1. You need a government right to carry on the activity, contractual rights/a scheme program, and technical production approval for the relevant chain. The question is not settled by the number of successful sandbox requests. If issuing goes through a sponsor, you need to name it and the allocation of responsibility.
2. Interchange = 2.90; scheme fee = 0.40; markup = 0.30 USD. Expense = 3.60 USD, net before reserve = 196.40. Reserve = 4 USD, immediate payout = 192.40. The 4 USD withheld remains a separate contingent claim under the contract; treating it as already finally spent is wrong. Sum: 192.40 + 4 + 3.60 = 200.
3. No: uncertainty about the payout does not prove that it was not executed. First establish the fate of the original payout by its identifier, then reconcile the funding and the 50 USD obligation. A new funding may create a second charge if the first transfer has already been executed. The 1 USD fee does not prove delivery of the 50 USD.
4. 150 × 1.08 = 162 USD; with 1.5% = 164.43 USD. DCC is more expensive by 3.57 USD under these assumptions. Check the actual rate/the moment it was applied, additional issuer fees, disclosure of the markup and voluntary choice. The example does not promise a cheaper issuer route in all cases.
5. 160/20,000 × 10,000 = 80 bps. Dividing by 25,000 would give 64 bps, but that is a different denominator. One result is not enough: the current thresholds/counts/observation periods are in the applicable manual; its full edition was not read. Program status cannot be guessed.
6. The buyer's active choice is a CIT with COF; the credential type is a separate axis. The next bill correctly initiated by the merchant may be an MIT under the agreed subscription; the amount, references to the original transaction and indicators are checked against the integration. A network token does not give open-ended authority.
7. Zero EUR given the cancellation. The new card details report on the card; they do not renew the subscription. A successful authorization means technical approval of the request presented, not proof of the merchant's right to bill.
8. A product and a financial asset create different obligations and rules. You need the actual counterparty, the nature of the asset, the ability to transfer/withdraw, the money route, geography, licenses and the applicable specialty registration. The acquirer decides the classification based on the real business, not on the shared UI.
9. A narrow claim about the suspension in this edition of the SPME is acceptable. To change the conclusion, you need a later applicable official bulletin/rule, with a date and scope, not more reposts of the blog. This is a good example of the version taking precedence over a message's popularity.
10. Establish what is stored: a provider handle or a network credential; who the requestor/TSP is, where the token is permitted, whether servicing/the cryptogram is available, how consent and history are transferred. PAR links records but is not an instrument for charging. A successful CSV export does not prove new payment capability.

## Summary, limits and further reading

A scheme links participants' rights, messages, fees and ways of resolving errors. For integration, the exact money route and the applicable rule matter more than a list of logos. Visa and Mastercard have comparable roles, but different documents, fields, programs and separate regional conditions; similar names do not replace checking.

**Open limits of this edition:** the closed VTS/MDES message specifications; the full current Mastercard Chargeback Guide and Data Integrity Monitoring Program; the Visa Integrity Risk Program Guide; a full reading of the new EMVCo specifications; EBA Q&A on the scope of MIT; the contractual fees of specific partners; comparable current geographic shares and the full operating rules of Amex/Discover/JCB/UnionPay. Missing documents were not reconstructed from memory. The research paper was read partially, BIS only as a summary. A course with a verified full lesson/timecode is not included in the set; the teaching basis is the dated ECB textbook. An X post is not used as evidence.

Return to the lifecycle and 3DS in Chapter 2; to the PSP/PayFac/MoR roles in Chapter 4; to delegated/agentic authority in Chapter 7. To re-check this chapter, start with the rule cards in [Sources](Sources.md) and the specific verifiable claims in [Claims](Claims.md).

---

### Sources and fact-check

[Sources](Sources.md) · [Verifiable claims](Claims.md) · [Chapter fact-check](../../Fact-check/03-Visa-and-Mastercard-cards/README.md)

The text was prepared by agents and underwent an independent agent review on 15–17 September 2026. This teaching edition has limitations; dates and limits of applicability are given in the sources. [Edition record](../../Methodology/Edition-record.md).

<details>
<summary>History and metadata of the original manuscript</summary>

This information describes the research stage before publication. Current visibility is public; the status of the whole edition is `reviewed_with_limitations`. The earlier labels `private` and `independently_reviewed_draft` are kept only as history.

**Version:** v0.1 · **status:** independently_reviewed_draft · **cutoff:** 2026-09-15 · **author:** researcher part_03_research, Codex · **visibility:** private. Independent review: see REVIEW.md.

Historical closing note by the author: **The author's status remains independently_reviewed_draft: no independent verdict is issued by this entry.**

</details>

[← How a payment works](../02-How-a-payment-works/README.md) · [Contents](../README.md) · [Payment providers →](../04-Payment-providers/README.md)
