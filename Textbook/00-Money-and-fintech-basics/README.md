[← Cover](../../README.md) · [Contents](../README.md) · [Market rules and licensing →](../01-Market-rules-and-licensing/README.md)

<a id="часть-0-деньги-учёт-и-способ-понимать-финтех"></a>
# Introduction. Money and fintech basics

> How money, obligations and accounting work — and how to check financial claims.

**6 lessons** · Knowledge cutoff: **15 September 2026** · [Sources](Sources.md) · [Fact-check and limitations](../../Fact-check/Results.md)

## In this chapter

- [0.1 · How to use this textbook](#module-0-1)
- [0.2 · How to check sources](#module-0-2)
- [0.3 · Glossary: terms and units](#module-0-3)
- [0.4 · Money, banks and financial risk](#module-0-4)
- [0.5 · A first money ledger: accounting basics](#module-0-5)
- [0.6 · Fintech beyond payments](#module-0-6)
- [Check your understanding](#check-your-understanding)
- [Summary, connections and limits](#summary-connections-and-limits)

---

This chapter lays the groundwork for the payment chapters that follow: how to read claims, tell roles apart, trace financial claims between participants and check money arithmetic. The basic theory is not tied to any one country; legal examples are marked separately as EU or US. All money cases below are synthetic and do not describe Lab's finances.

After reading, you will be able to:

- explain whom the holder of a bank balance, e-money or a token has a claim against;
- break "the payment went through" down into verifiable states;
- build a simple double-entry journal and explain a mismatch with the bank statement;
- distinguish a payment service from credit, investment, insurance and financial data processing;
- check a source against a specific statement and the limits of its applicability.

Prerequisites: percentage arithmetic and a willingness to ask "from whose point of view?". For a first reading, a convenient order is **0.1 → 0.2 → 0.4 → 0.5 → 0.3 → 0.6**: the glossary is worth rereading after the examples. The [Sources](Sources.md) and the [claims register](Claims.md) let you check where the key statements come from.

<a id="module-0-1"></a>
<a id="01-как-работать-с-этим-учебником"></a>
## 0.1 How to use this textbook

**Question:** what do you need to understand before choosing a payment API or a business model? **Answer:** which customer problem the system solves, whose obligations it changes, who is entitled to act and what evidence confirms the result.

A financial interface hides several different systems. The buyer pressed a button; the app sent a request; a payment intermediary accepted it; a bank approved the transaction; the merchant received a claim against the intermediary; the money became available for withdrawal; the merchant's bank credited the payout; the buyer received the goods. A single screen rarely shows all of these events. That is why the phrase "we've connected payments" is almost useless unless it names the last confirmed step.

Imagine a teaching example: a ticket-selling service. The team tested a card payment of 100 USD. This may confirm that a particular API route works correctly. For a working business, you also need to know who sells the ticket, who must refund the money in case of cancellation, which participant holds the funds until the event and who is responsible if the entry QR code does not work. A payment confirmation does not check the right of entry. This gap should be found at the design stage, not after a buyer complains.

Knowledge here is divided into three layers:

| Layer | Example | What it lets you do |
|---|---|---|
| Explanation of a mechanism | A customer's deposit is a liability of their bank | Build a correct model of money |
| Working hypothesis | Paying from a bank account will reduce the total cost of acceptance | Design a comparison that measures the full cost |
| Execution task | Test the chosen method with a specific merchant in an authorized environment | Carry out limited work under the stated conditions |

The third layer cannot be derived automatically from the first. Being able to write a funds transfer in code does not establish the authority to make the transfer. Internal permission to conduct research does not replace a legal rule; a legal rule by itself does not prove that a specific partner has agreed to serve a specific product. This is a methodological distinction between technical capability, authority and a verified result.

The required minimum for understanding any project is roles, contract, asset, states, risk and proof of execution. Choosing a specific product remains a separate decision. For example, studying insurance does not mean that Lab plans to become an insurer. It helps you notice that an offer like "for a small fee, we will compensate future losses" requires a different analysis than selling monitoring software.

A boundary error is mistaking a convenient picture of the world for confirmed demand. If ten APIs can accept stablecoins, it does not follow that the chosen customer wants to pay with them. Testing demand requires observations of the customer's behavior and constraints; testing a mechanism requires technical documents; establishing permission to operate requires the applicable law and contracts. Different questions require different evidence.

<a id="module-0-2"></a>
<a id="02-метод-учебник-из-ресёрча"></a>
## 0.2 How to check sources

**Question:** how do you turn the links you have found into knowledge? **Answer:** formulate a narrow claim, read the passage that supports it, check alternative explanations and keep track of the limits of the conclusion.

### Worked example: what "the money has already been received" means

Consider three real documents read for this chapter.

| Source | What it actually says | What does not follow from it |
|---|---|---|
| Stripe, *Payment Intents lifecycle*, row `Succeeded` | The corresponding payment process has completed; the documentation allows the order to be fulfilled | That the payout has already arrived at an external bank |
| Stripe, *Balances and settlement time*, `Balance states` | There are `pending` and `available` states; the transition between them is tied to the availability of funds in Stripe | That the available balance has already been withdrawn, or that a dispute is no longer possible |
| CPMI–IOSCO, PFMI, Principles 8–9 | An infrastructure must define settlement finality and manage the risk of the settlement asset | That a field in a particular API is a universal legal definition of finality |

The first document is a source about a product; the second clarifies a different object of the same product; the third is an international standard for financial infrastructures, applied through the relevant legal and supervisory frameworks. These are not three votes for one sentence. They answer different questions. [P00-S001, Lifecycle](https://docs.stripe.com/payments/paymentintents/lifecycle), [P00-S002, Balance states](https://docs.stripe.com/payments/balances), [P00-S003, Principles 8–9](https://www.bis.org/committees/cpmi/pfmi/overview).

For a synthetic purchase of 100 USD, let us record four observations: `payment succeeded`; the provider shows 97 USD after a notional fee; 0 USD is available for withdrawal; there is no payout. These facts are compatible. The conclusion "97 USD is already in the merchant's bank" is wrong. To check it, you need the payout object, the bank record and a link from both of them to the original purchase. Even after the payout, delivery of the goods is checked separately.

The second trap hides in identical names. In the Modern Treasury documentation, `pending_balance` includes **both posted and pending** entries; `posted_balance` contains posted ones; `available_balance` takes pending outgoing entries into account but does not add pending incoming ones. In Stripe, `pending` on the page in question means incoming funds that are not yet available. So two fields cannot be merged on the basis of their names. First read the definition and the sign, then convert. [P00-S004, Types of Balances](https://docs.moderntreasury.com/platform/reference/ledger-balances-object).

### Source quality depends on the question

A primary source is close to the action: a law sets a rule; an operator describes its own protocol; a researcher presents their own data and method. A secondary source explains or compares primary ones. A company's marketing text is primary for its own promise but weaker for a claim about effectiveness across the whole market. Technical documentation may also fail to describe all contractual exceptions.

For example, in December 2025 the CFPB published a BNPL study based on aggregated data from six large companies for 2019–2023. It explicitly limits its representativeness, and it cannot eliminate double counting of a person across different lenders. Hence the sum of the companies' "users" does not equal the number of unique people in the country. Nor does the 2025 publication date make the data observations of 2025 or 2026. [P00-S005, §3 and §4.2](https://files.consumerfinance.gov/f/documents/cfpb_bnpl-market-report_2025-12.pdf).

Reliable reading includes arithmetic. In the version of OpenStax §4.2 that we read, `Assets − Liabilities = Equity` is shown correctly, but one text exercise describes the direction of subtraction the other way round. An editor must check the formula against the example rather than carry the error over together with an authoritative reference. The correct equation is used here; this specific defect is recorded in the source card. [P00-S006, The Accounting Equation; formulas 4.2–4.3](https://openstax.org/books/principles-finance/pages/4-2-economic-basis-for-accrual-accounting).

The practical unit of research is a row "claim → source → location → scope → limitation". The status `confirmed` means support within the stated scope, not eternal truth. `Working_hypothesis` requires testing. `Open` marks missing information. `Rejected` keeps a refuted wording so that it does not come back in the next document.

The search turned up a relevant Reddit question about the difference between a successful payment and an available payout, but the thread text itself did not open. It is kept as an inaccessible candidate in the [notes](Research-notes.md), without an invented author identity and without any conclusion that Stripe was at fault. The question helped choose the topic; the documents that were read became the evidence. This is the practical line between research and decorating a text with links.

<a id="module-0-3"></a>
<a id="03-словарь-и-единицы"></a>
## 0.3 Glossary: terms and units

**Question:** which words cannot be used interchangeably? **Answer:** words about messages, obligations, settlement, legal role and asset describe different dimensions of the same transaction.

### Events and states

A **payment instruction** states what needs to be done: debit a certain amount from a certain source in favor of a payee. It can be accepted, rejected, queued or executed. **Money movement** is a general informal term for a change in monetary claims; always specify the system and the participants. A file containing an instruction does not by itself change a bank balance.

**Authorization**, in the card context, is a decision to approve a request under given conditions; it may be accompanied by reserving the available amount. **Authentication** answers the question of confirming identity or possession of an access credential. Verifying the customer through 3DS and the issuer's decision on the payment are different functions. **Capture** submits a previously authorized transaction for further financial processing. **Clearing** matches and processes instructions, determining settlement obligations; **settlement** discharges them by transferring the agreed settlement asset. An overview of card messages and stages is given in [P00-S007, §§2.1–2.2](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/chargebacks-made-simple-guide.pdf); the point of finality is set by the rules of the relevant infrastructure: [P00-S003, Principle 8](https://www.bis.org/committees/cpmi/pfmi/overview).

**Settlement finality** concerns whether the execution itself can be revoked or unwound in a given system. It does not erase all future claims between people. A final interbank transfer may be followed by a separate, later refund. A **payout** is the payment of a balance to a recipient along a specific route; a **refund** is a return of money for a purchase; **fulfillment** is the completion of an order. These are three different actions, even if they are linked by the same order.

Card example: 100 USD approved, 80 USD captured, 77 USD credited to the merchant after a notional fee of 3 USD, nothing sent to an external bank yet. Crypto example: a wallet signed an instruction for 80 token units; a hash appeared; the transaction has not yet been included in a block. In neither example does an intermediate identifier prove the final result. The Ethereum documentation separately describes transaction propagation, inclusion in a block and the subsequent finalization of the block. This is an example of one network; its rules are not carried over to all blockchains. [P00-S008, Transaction lifecycle](https://ethereum.org/developers/docs/transactions/).

### Who plays which role

| Term | Working definition and an important boundary |
|---|---|
| Merchant | The seller in a specific transaction; the app's brand may belong to another party |
| Issuer | The issuer of an instrument or obligation. A card issuer and a stablecoin issuer may be different organizations |
| Acquirer | Services the acceptance of card transactions on the merchant's side and participates in the relevant scheme; does not automatically become the seller of the goods |
| Scheme | The rules, roles and contractual relationships of the participants. The network connection is only part of its work |
| Processor | A processor of payment data; technical processing by itself does not tell you whose balance is used |
| Gateway | A gateway that accepts and passes on payment data; the name does not prove that it holds money |
| PSP | Payment service provider. A commercial umbrella term; the specific legal category depends on the activity and the country |
| ISO | Here, an Independent Sales Organization, an intermediary in selling and servicing payment solutions; not the International Organization for Standardization of ISO 20022 |
| PayFac | Payment facilitator: in the Mastercard model, a provider registered by an acquirer to facilitate transactions for sub-merchants; not a standalone, universal legal authorization |
| MoR | Merchant of Record: the party responsible to the buyer for a specific sale in the contractual and payment model under consideration; not simply software that sends a charge |

Card roles are easy to trace using [P00-S007, Transaction Flow](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/chargebacks-made-simple-guide.pdf). The OCC separately describes the acquirer, agent banks and ISOs/MSPs: [P00-S024, Types of Merchant Processors, pp.2–4](https://occ.treas.gov/publications-and-resources/publications/comptrollers-handbook/files/merchant-processing/pub-ch-merchant-processing.pdf). For a PayFac, the scheme's own definition is the primary source: [P00-S009, About payment facilitators](https://www.mastercard.com/gb/en/business/support/payment-facilitators.html). Using Connect as an example, Stripe separately links the MoR to responsibility for the sale and refunds and to identification of the party to the customer: this is a document about its own integration, not a universal legal test for all markets. [P00-S010, introduction and Clear identification](https://docs.stripe.com/connect/merchant-of-record).

A crypto purchase may involve a merchant, a checkout provider, a wallet operator, a token issuer and a provider that exchanges into bank money. You cannot assign card terms to them without grounds: a network validator does not become an acquirer, and a token issuer is not automatically responsible for the ticket sold. One company may combine several roles; one role may be served by several technical companies.

### Instrument, asset and means of presentation

**Fiat** denotes a government currency unit, such as USD; **rail** is an informal name for transfer and settlement infrastructure. A **crypto rail** uses cryptographic ledger infrastructure; you also need to name the network and the asset. **Stablecoin** is a general family of tokens that aim to stabilize their value relative to a reference; the name does not guarantee stability, a reserve or every holder's right to redemption.

**EMT**, e-money token, is a separate definition in MiCA of a crypto-asset that aims to maintain a stable value by referencing one official currency. **E-money**, in the EU definition, is linked to stored electronic value, a claim on the issuer, issuance against funds received and acceptance by another person. These terms should not be attached to a product merely because of the word "wallet". [P00-S011, Article 3(1)(7)](https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/mica/article-3-definitions), [P00-S012, Final answer](https://www.eba.europa.eu/single-rule-book-qa/qna/view/publicId/2022_6336). **CBDC** is a central bank digital currency; its digital form does not make it a private bank deposit. [P00-S014, Tokenisation and the monetary system](https://www.bis.org/publications/aer-2023/blueprint-future-monetary-system-improving-old-enabling-new).

A **credential** is data or a means that lets you present an authority or an instrument: a card token, a key, a mandate. It is not the settlement asset itself. **APM**, alternative payment method, means a method that is "alternative" relative to the baseline accepted in a given discussion; this class has no universal technical property. **QR** encodes data. EMV QR standardizes the format, while the messages after the code is read are left to payment providers. So the question "do you accept QR?" needs a follow-up: which format, app, scheme and settlement route? [P00-S015, What are the EMV QR Code Specifications?](https://www.emvco.com/emv-technologies/qr-codes/).

**Dual-message** separates authorization and clearing; **single-message** combines their information in one financial message. This is not a promise of instant arrival in the merchant's bank account. [P00-S007, §2.2](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/chargebacks-made-simple-guide.pdf).

**Custody** is the safekeeping or administration of someone else's asset in a given model; **control of funds** is the actual ability to dispose of the funds. Control can be shared. The FATF's 2021 guidance explicitly considers multisignature: the absence of a sole key does not rule out control. This is international guidance, not a local license; the publisher warns of later changes to the standards. [P00-S016, §§72–76 and the warning on the publication page](https://www.fatf-gafi.org/en/publications/Fatfrecommendations/Guidance-rba-virtual-assets-2021.html).

AML is anti-money laundering. Points for analysis arise when establishing a customer relationship, accepting and transferring value, exchanging and redeeming; obligations are determined by role and applicable law. The phrase "we're just an API" does not replace an analysis of actual control. A detailed legal analysis is in [Chapter 1](../01-Market-rules-and-licensing/README.md).

<a id="module-0-4"></a>
<a id="04-основы-денег-банков-и-финансового-риска"></a>
## 0.4 Money, banks and financial risk

**Question:** are 100 units of cash, a bank balance and a stablecoin the same? **Answer:** they may share a unit of account, but they have different debtors, availability, transfer rules and risks.

### The money hierarchy: whose promise you hold

Money serves as a unit of account, a means of payment and a store of purchasing power. These functions can diverge: the price is quoted in USD, payment is made with a token, and the merchant keeps the revenue in another currency. For analysis, it is more useful to start with the claim and the debtor than with what the app looks like.

| Form | What the holder gets | Who stands behind the claim | How it is usually transferred |
|---|---|---|---|
| Central bank banknote | A cash unit of currency | The central bank in the relevant monetary system | Handing over the physical instrument |
| Central bank reserves | A balance in an eligible participant's account at the central bank | The central bank | Entries on participants' accounts |
| Commercial bank deposit | The customer's claim on the bank | The commercial bank | A change in deposits; between banks, settlement through the chosen system |
| E-money | In the EU model described, a claim on the e-money issuer | The relevant issuer | A change in records and/or transfer of an electronic money asset, depending on the model |
| Backed stablecoin | A token; the extent of the claim and the redemption path are determined by its legal structure | The issuer and the contractual framework, if provided for | A record of the token transfer on the relevant network |
| CBDC | A digital liability of the central bank | The central bank | Depending on the architecture of the specific system; wholesale and retail access differ |

This table is an analytical scheme, not a global safety ranking. Banknotes have their own issuance specifics; coins may be issued by the treasury. For a stablecoin without an ordinary claim on an issuer, you cannot invent a debtor obliged to redeem it. A stablecoin reserve, bank reserves at the central bank and a merchant's reserve against disputes are three different meanings of the word "reserve". The basis for distinguishing bank claims is given in [P00-S013, pp.15–18](https://www.bankofengland.co.uk/-/media/boe/files/quarterly-bulletin/2014/money-creation-in-the-modern-economy.pdf); the principle of the singleness of money is in [P00-S014, introduction](https://www.bis.org/publications/aer-2023/blueprint-future-monetary-system-improving-old-enabling-new).

The BIS uses **singleness of money** for the property of a system in which different forms of money in one sovereign unit are used at par. A buyer does not have to work out a separate exchange rate for "bank A's dollar" against "bank B's dollar" every time. This is supported by institutional relationships and settlement infrastructure. However, the same face value does not mean the same claim if an intermediary goes bankrupt.

### Balance sheet and credit

An **asset** is a controlled economic resource; a monetary claim on another person is one kind of asset. A **liability** is an existing obligation to transfer a resource. **Equity** is what remains of the assets after liabilities. A simplified balance sheet obeys the equation:

`Assets = Liabilities + Equity`.

A deposit of 100 USD is an asset of the customer and a liability of the bank. A loan of 100 USD is an asset of the bank and a liability of the borrower. The single word "account" hides the opposite positions of the parties. [P00-S006, The Accounting Equation](https://openstax.org/books/principles-finance/pages/4-2-economic-basis-for-accrual-accounting).

The BoE explains how deposit money is created through bank lending: the bank's loan claim and the borrower's deposit appear at the same time. This does not make a bank an unlimited source of wealth: profitability, risk, capital, monetary policy and the ability to make outgoing payments all matter. Repaying the principal reduces the loan and the deposit; paying interest is a separate transaction. [P00-S013, Money creation in reality; Limits to broad money creation](https://www.bankofengland.co.uk/-/media/boe/files/quarterly-bulletin/2014/money-creation-in-the-modern-economy.pdf).

**Synthetic example, USD, no interest, fees or revaluations.** Two banks already exist. Their opening balance sheets:

| Bank and point in time | Reserves at central bank | Loans | Total assets | Customer deposits | Equity |
|---|---:|---:|---:|---:|---:|
| A, start | 200 | 800 | 1,000 | 900 | 100 |
| B, start | 150 | 450 | 600 | 540 | 60 |

Anna takes out a new loan of 100 at bank A. The bank increases loans to 900 and deposits to 1,000. Reserves stay at 200 and equity at 100: `1,100 = 1,000 + 100`. Anna now has a deposit of 100 and a debt of 100; her net wealth has not grown just from receiving the loan.

Anna buys equipment from Boris for 100, transferring the money to his account at bank B. Assume that the banks settle directly in central bank reserves, without netting against other payments and without correspondents.

| Bank and point in time | Reserves at central bank | Loans | Total assets | Customer deposits | Equity |
|---|---:|---:|---:|---:|---:|
| A, after the loan | 200 | 900 | 1,100 | 1,000 | 100 |
| A, after the transfer | 100 | 900 | 1,000 | 900 | 100 |
| B, after the transfer | 250 | 450 | 700 | 640 | 60 |

A discharged 100 of its deposit liability to Anna and transferred 100 in reserves. B received the reserves and increased its liability to Boris by 100. At the central bank, the liability to A decreased and the liability to B increased; the two banks' total reserves remained 350. In the banking system, deposits grew from 1,440 to 1,540 because of the loan; the transfer between banks did not wipe out this increase. Boris holds a claim on **bank B**, not a share of bank A's reserve account.

Anna now has equipment worth 100 and a loan debt of 100. For Boris, the equipment has been replaced by a deposit; for simplicity, the price equals its original book value. Within a single bank, a transfer could be limited to reallocating deposit liabilities without any movement of reserves between banks. Interbank mechanics of this type are confirmed by the BoE and the BIS; the specific numbers and starting states are invented for a teaching exercise.

### Liquidity and solvency

**Liquidity** is the ability to meet a monetary obligation on time. **Solvency**, in this simplified analysis, means that the value of the assets is sufficient to cover the liabilities. After the transfer, bank A has positive equity of 100 but only 100 in reserves. A demand to transfer 150 immediately creates a liquidity shortfall of 50 if funds cannot be raised or an asset sold in time. The assets have not necessarily lost value yet.

The reverse scenario: A's loans lost 120 in value. Assets became 880 against liabilities of 900, and equity is minus 20. The remaining 100 in reserves allows a small payment today but does not cure the shortfall in assets. A liquidity loan of 50 will increase assets and liabilities by 50; equity will remain minus 20. This difference is visible directly from the balance sheet. Real assessments of capital, impairment and insolvency are more complex and depend on accounting and legal rules.

### Interest, FX and units

A **basis point** is 0.01 of a percentage point. 25 bps of 20,000 USD is `20,000 × 25 / 10,000 = 50 USD`. A rate rise from 4% to 5% is one percentage point, or 100 bps; the relative increase in the rate itself is 25%. These three numbers answer different questions.

With simple interest, income equals `P × r × t`. For a notional 1,000 USD at 12% per year for 30 days on an ACT/365 basis, this is `1,000 × 0.12 × 30 / 365 = 9.863...`, which after the chosen rounding is 9.86 USD. An ACT/360 basis would give 10 USD. Stating "12%" without the period and the calculation method is incomplete. With annual compounding and a constant rate, the future amount after two years is `1,000 × 1.12² = 1,254.40 USD`. The present value of 1,100 received in a year at a discount rate of 10% is `1,100 / 1.10 = 1,000`. These are mathematical scenarios, not a promise of returns.

An **FX quote** sets the direction of exchange. Suppose a notional EUR/USD quote is 1.0800/1.0820: the dealer buys EUR at 1.0800 USD and sells at 1.0820 USD. A customer buying 100 EUR will pay 108.20 USD; one selling 100 EUR will receive 108 USD. The difference between the quotes, the **spread**, is 0.0020 USD per EUR. Relative to the mid of 1.0810, this is about 18.50 bps, not automatically 20 bps. A fee may be charged on top of the spread.

A money record must contain the currency, precision, direction and time. `100` does not reveal whether it is 100 USD or 100 cents. For a token, you also need the network and the asset identifier: an identical ticker does not confirm identity. 100 USD and 100 EUR can be added together only in a report with an explicitly chosen rate and date; the original balances remain separate.

### Risks of a single payment

| Risk | What can go wrong in a notional sale for 100 USD |
|---|---|
| Credit | The intermediary owes the merchant 97 but cannot pay |
| Liquidity | Funds become available in two days, but the refund is needed today |
| Market | The value of the token or the FX rate changes before the exchange |
| Operational | A duplicate event increased the balance twice |
| Legal | The obligation or the customer's right in a dispute is defined differently than the team assumed |

Several risks can materialize at once. The PFMI separately link settlement to the credit and liquidity risk of the settlement asset. [P00-S003, Principle 9](https://www.bis.org/committees/cpmi/pfmi/overview). Fast delivery of a message does not automatically eliminate any of them.

<a id="module-0-5"></a>
<a id="05-учет-денег-первый-ledger"></a>
## 0.5 A first money ledger: accounting basics

**Question:** how can you make sure the system knows how much it owes and to whom? **Answer:** record every economic event as a balanced change in accounts, track pending items separately and regularly match the records against external evidence.

### What double-entry bookkeeping does

A **ledger** contains accounts and entries; a **journal** organizes entries by transaction and time. **Debit** (Dr) is the left side of an entry; **credit** (Cr) is the right side. These are not universal synonyms for withdrawal and deposit. For ordinary accounts, the following table applies:

| Account type | Increase | Decrease |
|---|---|---|
| Asset | Dr | Cr |
| Liability | Cr | Dr |
| Equity | Cr | Dr |
| Income | Cr | Dr |
| Expense | Dr | Cr |

In a transaction, the sum of the debits equals the sum of the credits; at least two accounts are affected. Several debit or credit lines are allowed. Income and expenses change the result for the period and, through it, equity. [P00-S006, Double-Entry Accounting; Debits and Credits](https://openstax.org/books/principles-finance/pages/4-2-economic-basis-for-accrual-accounting).

Double-entry bookkeeping checks internal consistency, not truth. You can enter a fully balanced purchase twice. You can record a nonexistent bank asset against nonexistent income. That is why you need event uniqueness, confirmation of the underlying basis and external reconciliation.

### End-to-end example: a wallet and a merchant

Consider a **synthetic operational subledger** of a notional payment operator. We assume that the model is permissible and that the necessary contracts exist, for the purposes of the teaching exercise only. This is not a guide to obtaining a license, nor a prescription for presenting customer assets in IFRS/GAAP financial statements: the legal structure and accounting policy may require a different presentation.

Everything is in USD. There is a buyer, a merchant and an operator. The operator keeps two separate bank positions: a **client** one and its **own** one. The buyers' and merchants' money is not the operator's revenue. In the books, the liabilities to the buyer and to the merchant are shown in separate accounts. The operator's fee is 5 USD per successfully completed purchase; an external service charges the operator 2 USD. There are no taxes or interest in the example. Under the terms of the example, the fee of 5 is not returned on a partial refund.

| No. | Event | Debit | Credit | USD |
|---:|---|---|---|---:|
| 1 | The owner contributed starting capital | Own bank position | Equity | 20 |
| 2 | The buyer topped up the wallet | Client bank position | Liability to the buyer | 200 |
| 3 | The purchase was completed within the wallet | Liability to the buyer | Liability to the merchant | 100 |
| 4 | The operator's fee was charged | Liability to the merchant | Fee income | 5 |
| 5 | The earned fee was moved to the operator's own account | Own bank position | Client bank position | 5 |
| 6 | The fee to the external service was paid | External service expense | Own bank position | 2 |
| 7 | A payout was made to the merchant's external account | Liability to the merchant | Client bank position | 60 |
| 8 | On the merchant's instruction, money was returned to the buyer's external account | Liability to the merchant | Client bank position | 30 |

In row 3, the money does not leave the operator's bank. What changes is the party to whom the operator owes 100: previously the buyer, now the merchant. In row 4, the operator earns 5, so the debt to the merchant falls from 100 to 95. In row 5, the transfer between bank positions **does not create new income**: the income has already been recognized. In row 7, part of the debt to the merchant is paid off. In row 8, the debt is paid off in favor of the buyer under the terms of the partial refund.

The last two rows are recorded here after execution has been confirmed. Creating a payout request is not, by itself, grounds to treat the bank asset as reduced and the recipient as paid. More complex accounting for incomplete transfers uses intermediate accounts; here it is covered through the states below.

Let us check the closing balances:

| Account | Calculation | Balance, USD |
|---|---|---:|
| Client bank position | 200 − 5 − 60 − 30 | 105 |
| Own bank position | 20 + 5 − 2 | 23 |
| Debt to the buyer | 200 − 100 | 100 |
| Debt to the merchant | 100 − 5 − 60 − 30 | 5 |
| Result for the period | Income 5 − expense 2 | 3 |
| Equity including the result for the period | 20 + 3 | 23 |

Total: assets `105 + 23 = 128`; liabilities and equity `100 + 5 + 23 = 128`. A separate control of the client position: `105 = 100 + 5`. The journal's debits total 422, and its credits total 422. The journal turnover of 422 is neither revenue nor purchase volume: it includes the top-up, an internal transfer and payouts.

External cash flows also reconcile. The buyer put in 200, got 30 back and left 100 in the wallet: their net cost of the purchase is 70. The merchant received 60 and is entitled to another 5: 65 in total. The difference of 5 is the operator's fee, of which 2 went to the external service and 3 remained as the operator's result. The starting 20 belongs to a separate equity story.

### Ledger, available and pending balance

Before row 3, the buyer creates a purchase for 100. The operator reserves the amount — a **hold**. In our model, the buyer's posted balance is still 200, the hold is 100 and 100 is available. A separate hold register contains the purchase ID, the expiry and the state. A hold on its own creates no financial journal entry here.

If the purchase goes through, row 3 reduces the liability to 100 and the hold is released. The available balance remains 100. If the purchase is canceled before posting, the hold is released without row 3: 200 is available again. You must not first reduce the balance by 100 and then subtract the same hold again: that would restrict the same amount twice.

Before the payout of 60 to the merchant, the merchant's posted balance is 95. The payout request reserves 60, leaving 35 available. After row 7 is confirmed, the balance becomes 35 and the hold drops to zero. If the request is rejected before the debit, availability returns to 95. On a timeout, the state is unknown: the hold is kept until the situation is clarified, and you look for **the same** transaction by its identifier. A timeout is not a rejection.

This is one explicit model. Another ledger may store a pending item as a balanced pending transaction and compute balances from the statuses of the entries. Modern Treasury documents the transitions `pending`, `posted`, `archived`; a posted entry is corrected with a reversing transaction. Having `posted` in your own database does not by itself prove bank execution: the meaning of the status must be tied to an external event. [P00-S017, Ledger Transaction Statuses](https://docs.moderntreasury.com/ledgers/docs/transaction-status-and-balances).

### Reconciliation: three views, one fact under investigation

Suppose that, after all eight rows, the internal register shows 105 in the client position, the bank statement shows 45, and the payout system reports one payout of 60. A difference of exactly 60 is an important clue, but not yet a proven cause. We check the time cutoff, the account number, the currency, bank references, duplicate debits and transactions in transit. If two separate bank payouts of 60 are found against one valid instruction, a duplicate external debit has been established.

You cannot record one more ordinary payout to the merchant: the remaining debt to the merchant is only 5. That would hide the loss by reducing someone else's balance. What is needed is a separate entry for an asset under investigation, if the right to recover the excess is confirmed, or for an expense/loss, if such a right or recovery is not confirmed; the exact classification depends on the facts and the accounting policy. Once the error is proven, you fix the money, the books and the mechanism that caused the duplicate. A new correction does not erase the original event.

For each reconciliation, record the opening balance, the movements over **the same** interval and the closing balance; first by each currency and account, then by transaction. The internal journal shows the business's interpretation; the provider's report shows its processing; the bank shows posted bank entries. You cannot pick the most pleasant result of the three. Multiple currencies, accounts in transit, chargebacks and reconciliation automation are covered in [Chapter 8](../08-Integrations-and-reliability/README.md).

<a id="module-0-6"></a>
<a id="06-карта-финтеха-за-пределами-платежей"></a>
## 0.6 Fintech beyond payments

**Question:** what else does fintech do besides moving money? **Answer:** it provides access to accounts, finances time, distributes investment and insurance risk, and helps make decisions based on data and fulfill supervisory obligations.

### Digital banking, neobanks and BaaS

Digital banking describes digital service; neobank is a commercial label that by itself does not reveal whether there is a banking license. **Banking-as-a-Service (BaaS)** usually means providing banking functions through a partnership and technical interfaces. For analysis, look for the **regulated principal** — the specific regulated entity that bears the relevant obligation and provides the regulated service. It may differ from the owner of the app.

The customer's job is to keep money, receive incoming funds, pay and have access to service. Revenue in different models comes from subscriptions, payment fees, a share of the partner's revenue or the bank's interest margin. Credit risk on the bank's assets sits on the bank's balance sheet; the app retains its own operational and contractual obligations.

Synthetic example: a customer sees 500 USD in app F, which works with bank B. To answer "what happens if F fails?", you need the account agreement and records that make it possible to establish who the 500 belongs to. The FDIC warns that a US nonbank company does not itself become FDIC-insured because of a partnership; any pass-through coverage requires certain conditions to be met and relates to the failure of the insured bank, not of the fintech company itself. [P00-S018, Nonbank companies](https://www.fdic.gov/consumer-resource-center/2024-06/banking-third-party-apps). This is a US example, not a description of every wallet in the world.

### Lending, BNPL and credit scoring

Credit shifts purchasing power over time. **Funding** is the source of money for lending; **underwriting** is the decision on which risk to accept and on what terms; **servicing** is administering the debt; **collections** is handling arrears and recovery. **Credit scoring** assesses risk from data, but it does not provide funds and does not bear losses in place of the lender.

In a synthetic BNPL scenario, an item costs 120 USD and the customer pays in four installments of 30. The lender immediately transfers 114 to the merchant, withholding a notional merchant fee of 6; on the same day it receives 30 from the buyer. The lender's net cash outflow is 84, and its future inflows are 90. Before the cost of funding, losses and servicing, the expected margin is 6. If one future installment of 30 is never received, the buyer has paid 90 in total against a payout of 114 to the merchant: a loss of 24 before other expenses. A zero rate for the buyer does not mean there is no credit risk or no cost of the service.

The further timeline: application → assessment and offer → acceptance of the agreement → disbursement → due dates arrive → repayment or arrears → resolution. A return of the goods requires aligning the buyer's obligation with the settlements with the merchant; pressing refund in the store has not necessarily reduced the debt in the credit system yet. Payments service the loan, but a successful first debit says nothing about full repayment of the loan.

The CFPB treats pay-in-four as a credit product and distinguishes it from other point-of-sale financing options. So the numerical example above describes one possible structure, not the whole BNPL market. [P00-S005, Introduction](https://files.consumerfinance.gov/f/documents/cfpb_bnpl-market-report_2025-12.pdf). Checking the quality of scoring should look at subsequent defaults, calibration and errors across customer groups; a high approval rate on its own may simply mean that a higher risk was accepted. This criterion is the chapter's analytical recommendation, not the result of research on a specific model.

### Investing, wealthtech and capital markets

Investing exchanges money today for a right to future cash flows or for an asset with a changing price. A broker executes customer transactions, an exchange organizes trading, a clearing organization matches obligations, and depository infrastructure keeps positions and ownership records. An investment adviser helps with decisions; a **custodian** is responsible for safekeeping functions in a particular structure. How the functions are combined depends on the market. The SEC describes these roles separately. [P00-S019, Market Participants](https://www.investor.gov/introduction-investing/investing-basics/how-stock-markets-work/market-participants).

A teaching purchase: a customer transferred 1,005 USD to a broker, bought ten units of a security at 100 each and paid a fee of 5. Confirmation of the bank top-up speaks only about money. For the purchase, you need the trade execution, the quantity and the price; for settlement, the state of the transfer of money and securities; for custody, the position record. If the price falls to 90, the position is worth 900. The loss of 100 from the price change is different from the fee of 5. Even without any error by the broker, an investment can lose value.

The business model includes commissions, fees for advice, a percentage of assets under management, and interest income in permitted models; each is checked for conflicts of interest. In **wealthtech**, a portfolio allocation algorithm changes how the service is delivered but does not remove the customer's market risk. "Purchase accepted" and "security credited" differ in the same way as a payment order and a bank credit.

### Insurtech

Insurance takes on a defined future risk in exchange for a **premium**. The policyholder pays for coverage; the insurer must perform the obligations set out in the contract when a qualifying event occurs. Underwriting assesses the risk, pricing/rating sets the price, claims handling reviews the insurance claim. A distributor sells the policy and may receive a commission; that alone does not make it the bearer of the insurance risk. Using auto insurance as an example, the NAIC shows how risk, coverage, rate and deductible are connected. [P00-S020, Background; Pricing](https://content.naic.org/insurance-topics/auto-insurance).

A synthetic pool: 1,000 identical policies at 100 USD each bring in 100,000 in premiums. If 20 covered events occur with a payout of 3,000 each, payouts total 60,000. With expenses of 25,000, 15,000 remains before other items. If 40 such events occur, the result is minus 45,000. Assuming identical terms, the frequency and size of losses determine the outcome more strongly than checkout speed. This is a simplified cash scenario for a fully completed period, without the rules for recognizing insurance revenue, reserving or reinsurance.

An edge case: the app accepted the premium, but the event turned out to be excluded under the policy. The payment went through, but there are no grounds for an insurance payout. Or there are grounds, but not enough data: an automatic denial without review can cause harm. The usefulness of insurtech should also be measured by how understandable the coverage is, how correct the decisions are and how long claims settlement takes. Telematics and automation can change the input data and the process; by themselves they do not prove that the rate is fair.

### RegTech, SupTech, open finance

**RegTech** applies technology to meet organizations' regulatory and compliance obligations; **SupTech** applies it to the work of supervisory agencies and other financial authorities. The difference lies in the user and the responsibility. In a 2019 FSI study, the authors further narrow SupTech to big data/AI applications and stress the need for supervisory expertise in interpreting the results. Their classification is a research one, not a mandatory universal definition. [P00-S021, Executive summary; §2](https://www.bis.org/publications/fsi-insight-19-suptech-generations.pdf).

For example, a monitoring system flagged 100 transactions; an analyst confirmed that ten of them were significant. These numbers do not let you assess detection completeness: it is unknown how many significant transactions were missed among the rest. Selling an identity verification API solves the task of obtaining a signal; the final decision and responsibility require a separate model. Here the cash flow is a fee for the service; the main product is information, not the transfer of the funds being checked.

**Open finance** gives access to financial data with the customer's permission and extends open banking to a wider range of products, including investments, insurance and pensions. [P00-S022, introduction](https://www.bis.org/publications/fsi-summary-key-considerations-open-finance-executive-summary). In a teaching case, a customer allowed a budgeting app to read 90 days of transactions. It sees the spending, but the right to read does not imply the right to transfer the balance. You need to know the scope of the data, the purpose, the duration, how access is revoked and who is responsible for a wrong interpretation. This is useful to a lending service, but consent for one scenario is not unconditional permission for any use of the data.

### How to assess the value of the whole map

Financial inclusion includes the actual ability to use a suitable service. Having an account is only one indicator; cost, stable access, clear terms, data protection, error correction and the ability to withstand a financial shock also matter. Global Findex 2025 is based on 2024 surveys of the population aged 15 and over in 141 economies; the methodology distinguishes interview methods and sample limitations. It cannot be read as a log of all financial transactions or as causal proof of the benefit of a particular app. [P00-S023, Appendix A, pp.267–269](https://thedocs.worldbank.org/en/doc/be6615202d1f08a25855c8ac2d615122-0050012025/related/Survey-methodology.pdf).

The map is held together by one question: **who takes on which obligation, for what income, and at whose expense is an error borne?** For credit, the main unknown is future repayment; for an investment, future value; for insurance, random loss; for a payment system, the performance of obligations; for financial data, lawful and correct use. In-depth volumes on lending, investing and insurance are beyond the scope of this payments specialization.

## Check your understanding

1. The provider shows the payment as `succeeded`, and the available balance is 0. Name one valid conclusion and two premature ones.
2. Bank A from the example lends another 40 USD, and the borrower immediately pays a customer of bank B. What will the reserves, loans and deposits of both banks be, relative to the state after the first transfer?
3. In the 0.5 journal, change only the refund from 30 to 20. Find the client bank position, the debt to the merchant and total assets.
4. The merchant is owed 95; a pending payout of 60 has been created. In the chosen model, the posted balance is 95 and available is 35. The API call timed out. Can you return available to 95 and send a new payout?
5. A bank has assets of 1,000, liabilities of 920 and reserves of 30 included in its assets. Tomorrow it must transfer 50, and it cannot sell assets or borrow. Then it turns out that its loan assets have lost 100 in value. Name two different problems.
6. A buyer purchases 250 EUR at a notional EUR/USD of 1.1000/1.1040; there is no additional fee. How many USD will they pay? How many would they receive when selling 250 EUR?
7. A study reports a total of 53.6 million users across six lenders. What data are needed to claim that these are 53.6 million unique people?
8. An app holds the key of one of the two required signers of a customer's wallet. Can you confidently write "there is no control over the assets"? What question needs to be investigated?
9. A buyer paid an insurance premium of 100, and the loss amounted to 3,000. Why are these two facts not enough to declare that the insurer owes 3,000?

---

### Answers and explanations

1. The relevant provider process has completed. It is premature to declare a payout to an external bank or delivery of the goods. Availability of funds is a separate state; future disputes are not ruled out.
2. A: reserves 60, loans 940, deposits 900, equity 100; `1,000 = 900 + 100`. B: reserves 290, loans 450, deposits 680, equity 60; `740 = 680 + 60`. Reserves total 350; deposits grew by another 40. This tests the creation of a new claim and its subsequent transfer through interbank settlement.
3. Client position 115; debt to the merchant 15; debt to the buyer 100; own position 23. Assets 138; liabilities and equity `100 + 15 + 23 = 138`. A refund smaller by 10 does not change the notional non-refundable fee.
4. No. The timeout did not establish that the money was not sent. You need to check the same payout, the bank records and its identifier; while the uncertainty remains, a new attempt may create a duplicate.
5. First, a liquidity shortfall of 20 with positive equity of 80. After the impairment, assets of 900 against liabilities of 920, and equity of minus 20. Even restoring short-term liquidity does not by itself restore capital.
6. Buys EUR at the ask: `250 × 1.1040 = 276 USD`. Sells at the bid: `250 × 1.1000 = 275 USD`. The direction of the quote and the side of the trade matter more than the word "rate".
7. You need to eliminate double counting of the same person across several companies and to know the coverage and the definition of a user. Aggregates by individual lender do not provide this; the source explicitly states this limitation.
8. No. Investigate the actual ability to authorize, block or change the disposal of the asset, as well as the contracts and local rules. A joint signature is not automatic proof that there is no control; the FATF discusses this within the limited area of VAs/VASPs.
9. You need the validity of the coverage, the period, the insured risk, the exclusions, the limit, the deductible and proof of the event. The premium confirms one cash flow, not all the conditions of a future insurance claim.

## Summary, connections and limits

A payment has no single universal field of truth. There is a specific claim on a specific participant, a processing state, an accounting record and external confirmation. Double-entry bookkeeping helps maintain consistency; bank and provider reconciliation checks whether it matches reality. The same logic lets you see credit, investment, insurance or data handling behind any fintech interface.

Next: [Chapter 1 — law and liability](../01-Market-rules-and-licensing/README.md), [Chapter 2 — payment mechanisms](../02-How-a-payment-works/README.md), [Chapter 5 — accounts and wallets](../05-Wallets-accounts-and-cards/README.md), [Chapter 6 — crypto and stablecoins](../06-Crypto-and-stablecoins/README.md), [Chapter 8 — ledger and reliability](../08-Integrations-and-reliability/README.md).

Limits of this version: there is no audit of a specific product, no legal opinion and no model for mandatory financial reporting. The EU definitions were checked against ESMA/EBA; the full current EUR-Lex text was not read because of access restrictions. The 2014 BoE background material is used for the mechanism, without carrying its old money shares and operating framework over to 2026. Several pages were available only as a search-index text representation; this is explicitly noted. For insurance, the NAIC basics were read, and the IAIS report, which could not be read in substance, is not presented as studied work. Online documents were not saved as immutable copies and have no verified commit/hash. All direct sources, the extent of reading and unresolved questions are in [Sources](Sources.md), [Claims](Claims.md) and [RESEARCH_NOTES](Research-notes.md).

---

### Sources and fact-check

[Sources](Sources.md) · [Verifiable claims](Claims.md) · [Chapter fact-check](../../Fact-check/00-Money-and-fintech-basics/README.md)

The text was prepared by agents and underwent an independent agent review on 15–17 September 2026. This teaching edition has limitations; dates and limits of applicability are given in the sources. [Edition record](../../Methodology/Edition-record.md).

<details>
<summary>History and metadata of the original manuscript</summary>

These details describe the research stage before publication. The current visibility is public; the status of the whole edition is `reviewed_with_limitations`. The earlier labels `private` and `independently_reviewed_draft` are kept only as history.

**Status:** `independently_reviewed_draft` · **version:** v0.1 · **cutoff and writing date:** 2026-09-15 · **author:** researcher `part_00_research` · **language:** Russian · **visibility:** private. First review: see REVIEW.md (historical or internal material; kept by the owner, outside this copy).

</details>

[← Cover](../../README.md) · [Contents](../README.md) · [Market rules and licensing →](../01-Market-rules-and-licensing/README.md)
