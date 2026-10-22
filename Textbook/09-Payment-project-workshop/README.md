[← Integrations and reliability](../08-Integrations-and-reliability/README.md) · [Contents](../README.md) · [Back to contents →](../README.md)

<a id="часть-9-сквозная-практика-и-применение-к-платежному-проекту"></a>
# Chapter 9. Payment project workshop

> We bring money, contracts, data and licenses together into one picture and solve end-to-end problems.

**5 lessons** · Knowledge cutoff: **15 September 2026** · [Sources](Sources.md) · [Fact-check and limitations](../../Fact-check/Results.md)

## In this chapter

- [9.1 · Project map: money, contracts, data and licenses](#module-9-1)
- [9.2 · Working hypotheses and how to test them](#module-9-2)
- [9.3 · The limits of this textbook](#module-9-3)
- [9.4 · How research becomes a lesson](#module-9-4)
- [9.5 · End-to-end cases and final review](#module-9-5)

---

This is the final teaching chapter: how to turn scattered knowledge about rails, contracts and software into an explanation of one completed purchase. All merchants, transactions, balances and pricing below are **synthetic**, except for the specifically named public documents and the historical incident. They do not describe Lab's sales, partnerships, licenses or product readiness. Legal and accounting conclusions for a real launch require the specific activity to be reviewed by qualified specialists.

Dynamic pages were read two days after the cutoff date. Their text confirms the content observed on **2026-09-17**, but without an archived version it does not prove that the content was unchanged on 2026-09-15. Dated acts and historical publications are kept separate from such observations. In particular, the current Stripe documentation and the x402 README are not declared to be specifications fixed as of the cutoff date.

Prerequisites: [accounting 0.5](../00-Money-and-fintech-basics/README.md), [models 1.3](../01-Market-rules-and-licensing/README.md), [lifecycle 2.2](../02-How-a-payment-works/README.md), [crypto→fiat 6.4](../06-Crypto-and-stablecoins/README.md), [agentic payments](../07-AI-agent-payments/README.md) and [reconciliation and recovery 8.5–8.6](../08-Integrations-and-reliability/README.md). After reading, you will be able to:

- build a map of one transaction across money, contract, data and regulated roles;
- calculate the outcome of a sale, a partial refund and a delayed payout;
- recover an unknown outcome without charging twice;
- separate a testable product hypothesis from market evidence and from a Lab decision.

<a id="module-9-1"></a>
<a id="91-сквозная-карта-деньги--договор--данные--лицензия"></a>
## 9.1 Project map: money, contracts, data and licenses

**Question:** what exactly must be clear before a payment scheme can be called explained? **Answer:** who owes what to whom, under which contract, which fact changes the obligation, which data proves it, and who has the right to carry out the corresponding activity.

### Four maps of one purchase

Imagine a digital product priced at 100 EUR. On the screen the buyer sees a single button. Behind it there are several independent relationships. The merchant promises to deliver a specific product. The payment service provider promises to carry out operations within the limits of its contract. The bank maintains its customer's account. The store operator provides the software interface. One participant sometimes combines roles, but this has to be proven, not assumed from a logo.

The **money map** shows assets and obligations at every step. A hold on the card is not the merchant's money. A confirmed receivable from the PSP is not a bank balance. Coins at the partner's address are not available EUR in the merchant's account. For every arrow, record the amount, the currency, the conditions of performance and the party that bears the risk of delay. If the fee is withheld before payout, gross and net are shown separately.

The **contract map** answers a different question: against whom will the buyer bring a claim for undelivered goods? In a direct sale, against the merchant, under the terms of sale and the applicable law. The acquiring agreement defines the relationship between the merchant and the acquirer, including fees and recourse. A software services agreement does not turn the developer into the merchant or a holder of funds. A disclaimer in the user interface does not replace the actual relationships between the participants.

The **data map** links commercial intent to evidence. You need identifiers for the order, the payment attempt, the specific money transaction, the refund and the fulfillment. A settlement batch and a bank payout may have other identifiers. Data about the product and the delivery address should not be passed automatically to all financial participants: each one needs a specific set for its task. A full card or wallet secret is not a required element of proof of purchase.

The **permissions map** describes the activity of a legal entity in a particular country. Here a license is not a property of an API. In the EU, Article 3(j) of PSD2 excludes certain technical services where the provider does not possess the funds being transferred; payment initiation and account information services are expressly carved out of this exclusion. Therefore the single argument "we do not hold the money" is not enough for every financial function. This is a narrow EU rule, not a universal exemption for developers. [P09-C001; PSD2, consolidated 2025-01-17, Article 3(j)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02015L2366-20250117).

### Route matrix

The matrix below is a teaching method of analysis, not a conclusion that the named models are permissible. Every row assumes a separate check of the entity, the country, the contract and the authorizations.

| Route | Who moves the money | Merchant's main contract | Key data | Responsibility that does not transfer automatically |
|---|---|---|---|---|
| Card ecommerce | Issuer, scheme, acquirer/PSP, banks | Sale to the buyer; acquiring/PSP agreement | Order, authorization/capture, balance transaction, payout | Delivering the product; refunds; contractual dispute risks |
| Local A2A | Payer's and payee's bank/PSP | Sale; account/payment acceptance services | Payment reference, account, amount, bank credit | Matching the payment to the order; refund via a permitted route |
| QRIS with a chosen source of funds | Approved payment participants of the relevant route | Sale; merchant agreement with a PJP | Merchant ID, QR request, transaction reference | Correct payee, amount, execution and reconciliation |
| Crypto→fiat via a partner | Crypto partner, its liquidity and fiat partner/bank | Sale; custody/conversion/settlement terms | Quote, asset/network, transaction hash, conversion, payout | Exchange rate and the moment the debt is discharged; ensuring refunds |
| Purchase by an agent | Participants of the chosen card/A2A/crypto rail | The same contracts plus the basis for delegation | Principal, mandate, order, payment, fulfillment | Limits of authority; correctness of the choice; dispute handling |

QR is deliberately not equated with a bank transfer here. Bank Indonesia describes QRIS as a standard for exchanging payment data that allows different sources of funds; a merchant-presented dynamic QR contains the amount, while a static QR requires it to be entered. In a specific case a bank source can be chosen, but neither that source nor the method of settlement between participants can be inferred from the QR image. [P09-C002; BI, Sources of Funds / What are the QRIS standards?](https://www.bi.go.id/en/fungsi-utama/sistem-pembayaran/ritel/kanal-layanan/QRIS/default.aspx).

### Proof of success depends on the question

For the fulfillment service, a defined payment basis set by the contract and the risk policy is sufficient; waiting for each bank payout before delivery is usually not part of the model in this example. For treasury, the available incoming funds are what matter. For the buyer, what matters is receiving a usable product. A sales researcher needs a linked set of these facts. That is why the question "was the transaction successful?" is replaced by the question "which obligation has already been performed and which is still open?".

Synthetic snapshot: the PSP recognized 100 EUR, the fee was 3 EUR, 10 EUR were withheld, 87 EUR were sent to the bank; the bank has not yet confirmed the credit. The product has already been delivered. The commercial obligation is closed, while the merchant still has a 10 EUR claim held in reserve and 87 EUR in transit. The bank balance has not grown yet. The assets from the transaction after expenses total 97 EUR. Recording "revenue 87 EUR" or "all money received" would mean mixing different maps.

A typical mistake also arises when processing is outsourced to a third party: "we connected a hosted checkout, so we are no longer responsible for payment data." PCI SSC explicitly keeps the merchant's obligations for selecting the provider, allocating responsibility in writing and checking the provider's compliance. The specific assessment scope is determined separately; this FAQ does not choose the SAQ form for the merchant. [P09-C003; PCI SSC FAQ 1092, answer / merchant responsibilities](https://www.pcisecuritystandards.org/faqs/does-pci-dss-apply-to-merchants-who-outsource-all-payment-processing-operations-and-never-store-process-or-transmit-cardholder-data/).

The practical result of the map is the ability to trace a finger from the promise to the external evidence. If an arrow ends with the words "the partner will sort it out from there," then either the contractual obligation or the observable state has not been established. That is where the inconvenient tail most often hides: a frozen reserve, an unconfirmed refund, a lost order or a timing promise that cannot be kept.

<a id="module-9-2"></a>
<a id="92-working-hypotheses-не-канон"></a>
## 9.2 Working hypotheses and how to test them

**Question:** how do you apply the textbook to a product idea without passing off an attractive scheme as a proven business? **Answer:** formulate separate assumptions about demand, the payment route and the economics, then look for data that could refute each of them.

### Hypothesis H1: crypto-in / fiat-out for an ordinary PSP

`Working_hypothesis`: some ordinary merchants want to accept payment from buyers who hold crypto funds while keeping prices, accounting and payouts in fiat. The assumed product connects checkout, a conversion partner and the existing merchant workflow. This is not a claim that such demand exists in sufficient volume or that the current PSP is permitted to use this route.

Testing starts with the reason for the purchase. The buyer wants the product itself; otherwise even a cheap rail does not create a sale. Next, the reason for choosing the method is tested: card availability, a wallet balance, cost, convenience or another observable factor. Finally, the merchant compares the net result with the alternative, taking into account support, refunds, liquidity and declines. A positive answer only to the question of technical integration leaves the market hypothesis open.

Synthetic economics: 200 purchases a month at 50 EUR give 10,000 EUR of turnover. The connector charges 0.40 EUR per successful purchase: 80 EUR of revenue. Variable costs are 0.10 EUR per transaction; another 30 EUR a month goes to support and 100 EUR to fixed infrastructure. Result: `80 − 20 − 30 − 100 = −70 EUR`. Without changing costs, the break-even point is `130 / (0.40 − 0.10) = 433.33`, that is, at least 434 purchases. This calculation does not account for growing support costs, losses, taxes or the cost of capital; in a real test they may shift the threshold. Large turnover alone does not prove profitability.

### Hypothesis H2: a partner rail reduces your own complexity

The class names from the outline — Bridge-like SSP, Triple-A-like, Coinbase Business-like, CoinGate-like — are useful as search labels for different partner approaches. They are not a shortlist, a promise of equivalent capabilities or permission to use someone else's license. What you should compare is the receiving entity, the customers' countries, custody, conversion, the payout route and the servicing of legacy obligations when the contract ends.

A real example of separating roles is the Stripe Stablecoin Payments document, updated 2026-04-16: it describes a separate agreement between the merchant and a Settlement Services Provider, and its definition of the services includes custody, conversion and the transfer of fiat to the relevant Stripe entity. This confirms the contractual architecture of this document, but not the onboarding of any given merchant. [P09-C004; Stripe terms, §§1–2, 7–8](https://stripe.com/au/legal/stablecoin-payments).

In the teaching experiment, success for H2 would mean that the partner actually accepts the agreed customer type, takes on the named functions under contract and provides sufficient evidence of transactions. A refutation would be, for example, a refusal to serve the required product type or the impossibility of a partial refund after payout. A partner with a working API but without a suitable contract does not settle this hypothesis.

### Hypothesis H3: an agentic storefront is useful regardless of settlement

An agentic storefront is an interface through which a program understands the product, obtains the current price, creates an order and checks fulfillment. It can use the existing card rail. A separate hypothesis about stablecoin settlement answers the question of how to transfer value. Mixing the two experiments makes it impossible to establish the cause of the result: buyers might have valued the convenient search rather than the new payment method.

For example, in a teaching setup 20 users receive the same catalog: one group places the purchase through an agent with the existing payment method, the other through the ordinary interface. The evaluation needs completed orders and selection errors, not just the number of API calls. The next, separate test compares payment methods with the same product and interface. A small sample makes it possible to find defects and formulate questions, but does not guarantee a statistical conclusion about market conversion.

It is useful to write hypothesis states in words: `confirmed` within the verified scope, `working_hypothesis` before testing, `open` when data is lacking, `rejected` when refuted. "Interesting to a partner" does not mean "buyers pay," and a teaching calculation is not a budget. In the teaching method, the research analysis, the product decision and the authorization for real-world actions are considered separately. [P09-C005–C007: hypotheses of this chapter; P09-C008: editorial principle of the public edition.]

<a id="module-9-3"></a>
<a id="93-что-не-входит-в-учебник-v1"></a>
## 9.3 The limits of this textbook

**Question:** where does payment analysis end and a different professional task begin? **Answer:** where the subject of the promise, the risk or the required evidence base changes. A payments textbook helps you see the boundary, but it does not give you the competence to cross it unnoticed.

### Payment liquidity is not an investment portfolio

Treasury must have resources for expected payouts and refunds under stress. If the team proposes placing these resources in DeFi for yield, a new task appears: credit and market risk, exit terms, protocol risk and legal classification. It cannot be included in the payment scheme with a single line "the balance is working."

Synthetic example: by morning 10,000 EUR of refunds are required, and the only reserve sits in a product with a three-day withdrawal period. Even if its reported value is 10,500 EUR, availability by morning is zero. The payment task is not solved. Analysis of yield, trading, leverage, token design and investment strategies is outside v1. The ability to distinguish an asset's value from available liquidity remains mandatory within the course.

### A sales contract and taxes cannot be derived from the rail

The same 100 EUR can be received for your own license, as an intermediary on behalf of another seller, or as an advance before delivery. The money arrow looks similar, but revenue, tax documents and liability may differ. Our ledgers are operational teaching models; they do not determine the VAT/GST rate, the place of supply, the tax status of a token or the moment of recognition under reporting standards.

If it is unknown who owns the product and who is named as the seller, you cannot calculate "net profit after all taxes." The correct result is the known money and fees plus the tax and contractual parameters that are explicitly left open. A full tax treatise and in-depth lending, capital markets and insurance are not part of this version: an overview of them is in [0.6](../00-Money-and-fintech-basics/README.md), and specialized work requires a separate subject of research.

### The teaching environment and other people's businesses

Card-present POS is not the core of the course: knowledge of ecommerce does not replace the requirements for terminals, physical card acceptance and local certification. Likewise, HR processes, organizational budgeting and third-party environments do not become payment experiments just because a convenient API exists.

The boundary is simple: discussing a synthetic purchase does not create the right to carry out a real one. The example analyzed here does not grant access to customer data, the right to test a charge or the right to publish anyone's financial history. For a teaching exercise, made-up amounts, open documents and a local ledger are enough. A private database does not automatically turn into a public dataset.

These editorial exclusions are listed in the [outline v02, 9.3](../../Methodology/Original-plan.md). [P09-C009: limits of the textbook.] A typical mistake is to read "out of scope" as "unimportant." The correct conclusion is the opposite: if a decision depends on such an area, checking it becomes a separate dependency, and the outcome remains limited.

<a id="module-9-4"></a>
<a id="94-путь-структура--датасет--уроки"></a>
## 9.4 How research becomes a lesson

**Question:** how does the reader check that a teaching conclusion really follows from the sources? **Answer:** by reproducing the chain from a specific claim to the passage of the document that was read, then separately checking the calculation and the scope.

### Example: turning a general phrase into knowledge

The phrase "stablecoin is refunded automatically" is too broad. It does not name the provider, the product, the refund initiator, the source of liquidity, the recipient or the completion criterion. The Stripe documentation that was read states that stablecoin refunds are returned to the original wallet, and the payment method table shows support for full and partial refunds. This is a limited property of the described product; it does not mean that every blockchain transfer has a built-in refund. [P09-C010; Stablecoin payments, Limitations / Refunds](https://docs.stripe.com/payments/stablecoin-payments).

A source card stores the URL, the publisher, the date read, the section and the version limitations. A claim card formulates only the supported conclusion. Then a synthetic exercise introduces a specific obligation, for example 25 EUR, a chosen exchange rate and a confirmed recipient wallet. Finally, the answer shows which new transfer closes the debt. This way four different objects — document, thesis, exercise and solution — do not substitute for one another.

A change to a page after it was read shows why a version is needed. If the documentation used to say USD settlement and the version read today says local currency, you cannot quietly "correct history." You keep the earlier dated card, add a new observation and establish which product, country and period are being discussed. In this work, an archived version of the Stripe page as of 15 September was not obtained, so the exact earlier state is left open.

### Reproducibility on three reference questions

The outline proposes the sequence **0.5 → 2.2 → 1.3**: accounting, lifecycle and liability. One small example tests all three. There is a 100 EUR payment, 3 EUR of costs and a 97 EUR receivable from the PSP. The accounting must balance; the lifecycle must explain why this is not yet in the bank; the contractual model must explain why the receivable belongs specifically to the merchant. Any gap makes the example pedagogically weak, even if an individual paragraph is flawless.

Then **6.4** adds the asset, the network, conversion and the fiat exit. New numbers require units and an exchange rate; a new company requires a specific role; a new promise of a refund requires a source of money. The material becomes more complex only where the properties of the mechanism change. There is no need to rewrite the whole book when one provider is added, as long as the definitions and dependencies are preserved.

Sandve and co-authors propose preserving how a result was obtained, the versions of tools and the link between textual conclusions and the underlying results. This is a 2013 methodological article on computational research, not a study of the effectiveness of payment products. What applies here is the principle of traceability itself. [P09-C011; Rules 1, 3–5, 9](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1003285).

### What exactly the reviewer checks

The reviewer should try to refute an important thesis: was a phrase taken from marketing, were the customer's country and the merchant's country confused, did the document change, does a table hide a fee? For a calculation, the reviewer starts from the opening balances and repeats the entire path, including the failure. Equality of debits and credits checks the form of the ledger; an external statement checks its correspondence with the world. These checks complement each other.

A good teaching question changes at least one condition of the example. If in the text the refund comes before the payout, the exercise puts it after the payout; if the exchange rate is fixed, the exercise changes the rate. Then the reader demonstrates an understanding of the obligation rather than a memorized number. The author can check the arithmetic, but an independent review is done by another person or agent. A later PDF edition requires a separate check of rendering and links; this batch produced Markdown. A teaching `reviewed` status also does not mean approval to launch a product or acceptance of a research hypothesis.

<a id="module-9-5"></a>
## 9.5 End-to-end cases and final review

**Question:** what stays the same if the same product is paid for with a card, a local transfer, a stablecoin or through an agent? **Answer:** the merchant's obligation and the need to explain every amount. What changes are the rights, payment states, fees, liquidity and methods of recovery.

### Common accounting conditions

Cases A–C describe one commercial idea: a digital bundle, part of which is refunded after the purchase. These are **alternative independent purchases**, not one order paid three times. The price in A/C is 100 EUR, the local price in B is 1,600,000 IDR; this teaching comparison of prices does not imply a real FX rate or that all methods are available to one merchant. Case D separately shows a purchase by an agent.

The ledger is kept from the merchant's point of view. Dr increases an asset or an expense, Cr increases a liability, equity or revenue; a decrease is recorded on the opposite side. "Receivable from PSP" is an asset of the merchant, "refund payable" is a liability. The opening money is contributed as equity. Taxes, the cost of goods and impairment of receivables are excluded from the numbers; the result shown is what remains after the named payment costs, not full profit. Operational journal entries do not replace an approved accounting policy.

### Case A. Ordinary card ecommerce: payout, reserve and partial refund

**Roles and contracts.** Teaching merchant A sells its own product to an EU buyer. It has a direct contract with a suitable acquirer/PSP; the buyer has an issuer's debit card linked to a EUR account. Under the conditions of the example, the purchase and the refund go through in EUR with no separate fee to the buyer and no conversion; after the debit and the refund are confirmed, the balance of the buyer's account changes. The store operator passes on the order and receives a limited payment reference; it does not accept customer money into its own account. The PSP's right to provide acquiring and the specific merchant onboarding are assumed as conditions of the exercise, and in a real review they require documents. The merchant is responsible for the product, the refund terms and the dispute risks agreed with the PSP.

**Data and timing.** Order `A-1` records 100 EUR, the contents of the bundle and the buyer. Attempt `PA-1` receives an authorization; this is not yet a record of a bank receipt. After capture and a confirmed financial basis at the PSP, the merchant's receivable arises. The product is delivered once, with `FA-1`. As an illustration, the Stripe API recommends reusing a PaymentIntent when resuming an interrupted purchase and keeping its link to the order. Its lifecycle helps find the earlier attempt but does not replace the commercial order. [P09-C012; Payment Intents, Best practices / After the payment](https://docs.stripe.com/payments/payment-intents).

Terms of the **synthetic contract**: fee 3 EUR; reserve 10 EUR; the rest is paid out; the original fee is not refunded; the fee for a partial refund is 0.50 EUR. At the start, the merchant's bank holds 1,000 EUR and the buyer's account 500 EUR. The buyer receives the product and then has an approved refund claim of 25 EUR.

| Step | Dr | Cr | EUR |
|---|---|---|---:|
| Opening equity | Bank | Equity | 1,000.00 |
| PSP recognized the purchase | Receivable from PSP | Obligation to deliver product | 100.00 |
| Bundle delivered | Obligation to deliver product | Revenue | 100.00 |
| Purchase fee | PSP expenses | Receivable from PSP | 3.00 |
| Reserve withheld | Reserve at PSP | Receivable from PSP | 10.00 |
| Payout sent | Money in transit | Receivable from PSP | 87.00 |
| Bank confirmed payout | Bank | Money in transit | 87.00 |
| Refund approved | Sales returns | Refund payable | 25.00 |
| Reserve released | Receivable from PSP | Reserve at PSP | 10.00 |
| Merchant topped up PSP; both ends confirmed | Receivable from PSP | Bank | 15.50 |
| Refund executed and confirmed | Refund payable | Receivable from PSP | 25.00 |
| Refund fee | PSP expenses | Receivable from PSP | 0.50 |

Before the top-up there is only 10 EUR at the PSP against the 25.50 EUR needed. The sale is profitable in a narrow sense, but the refund requires liquidity. If there is a gap between the bank debit of the top-up and its credit at the PSP, a separate "top-up in transit" account is used; a combined line is acceptable only when both facts exist. End: bank **1,071.50 EUR**; PSP/reserve/in-transit and liabilities are zero. Debit balances `1,071.50 + 25 + 3.50 = 1,100`; credit balances `1,000 + 100 = 1,100`. The buyer has **425 EUR** and the remaining part of the product. The merchant's financial result: `100 − 25 − 3 − 0.50 = 71.50 EUR`.

**Failure.** The response to the capture is lost. We do not create a new payment or a new PSP route for `A-1`: we look up `PA-1` and read its state and the reports. Stripe separately warns about the indeterminate result of a `500` and possible effects of the original request. Its idempotency keys may be removed once they are at least 24 hours old, so a single key gives no permanent protection. [P09-C013–C014; Advanced error handling, Server errors](https://docs.stripe.com/error-low-level), [Idempotent requests](https://docs.stripe.com/api/idempotent_requests).

**Refund and success.** Two webhooks for one refund do not create two journal entries or two payouts: the economic transaction is identified by the refund ID and the merchant account context. In Stripe, an insufficient available balance can leave a card refund pending; a request is not the same as a credit to the buyer. Check the provider's result and the designated payment reference, and in a dispute, the issuer's confirmation. [P09-C015; Refund and cancel payments, opening / Refund destinations / Handle failed refunds](https://docs.stripe.com/refunds). In this exercise, success is proven by the delivery, the PSP statement, the merchant's bank and a confirmed refund; an authorization on its own replaces none of these outcomes.

### Case B. Local A2A/QR: the amount matched, but the order got lost

**Roles and boundaries.** Indonesian merchant B receives payment through a QRIS PJP; the buyer chooses their bank account as the source of funds. We consider exactly this variant rather than claiming that the entire QRIS system is pure A2A. The PJP services the merchant agreement; the bank and payment participants perform their part. The store is responsible for the digital product, and the developer for matching data within the scope of its contract.

BI reports the approval of PSP/switching participants for QRIS. In a legal review you cannot rely only on the old PJP categorization: the official summary of PBI 10/2025 states that the new regulatory system applies from **2026-03-31**, covers related and supporting participants and describes the transition. What was read here is precisely the regulator's summary, not the full set of implementing conditions for a specific PJP. [P09-C016; BI QRIS, Parties in Transaction Processing](https://www.bi.go.id/en/fungsi-utama/sistem-pembayaran/ritel/kanal-layanan/QRIS/default.aspx); [P09-C017; PBI 10/2025, Materi Pengaturan / Transisi / Penutup](https://www.bi.go.id/id/publikasi/peraturan/Pages/PBI_102025.aspx).

**Purchase.** Order `B-1` costs 1,600,000 IDR. The teaching dynamic QR is linked to a PJP request; the buyer checks the payee name and the amount in the banking app. Our contract provides for a fee of 0.7%, or **11,200 IDR**, with no separate charge to the buyer. This is a given condition of the example, not a promise of pricing for any merchant category. The PJP recognizes a debt to the merchant of 1,588,800 IDR, then pays it out. The merchant's opening bank balance is 2,000,000 IDR, the buyer's 3,000,000 IDR.

| Step | Dr | Cr | IDR |
|---|---|---|---:|
| Confirmed purchase | Receivable from PJP | Delivery obligation | 1,600,000 |
| Fee withheld | Expenses | Receivable from PJP | 11,200 |
| Product delivered | Delivery obligation | Revenue | 1,600,000 |
| Payout started | Money in transit | Receivable from PJP | 1,588,800 |
| Bank received the money | Bank | Money in transit | 1,588,800 |
| Refund of one quarter accepted | Sales returns | Refund payable | 400,000 |
| Agreed return transfer confirmed | Refund payable | Bank | 400,000 |
| Teaching fee for the return transfer | Expenses | Bank | 2,500 |

The refund here is a **separate bank transfer agreed in the contract**, made after checking the recipient's account and that no parallel PJP refund exists; we do not attribute it to a universal QRIS refund API. The merchant keeps the link `B-1 → refund RB-1 → bank reference`. While the transfer is in transit, the obligation is not declared finally closed without an established criterion. In the figures of the table, both ends of the transfer are confirmed.

The merchant's bank at the end is **3,186,300 IDR**, the buyer's **1,800,000 IDR**. Payment costs are 13,700 IDR; the result is `1,600,000 − 400,000 − 13,700 = 1,186,300`. Check of closing balances: debits `3,186,300 + 400,000 + 13,700 = 3,600,000`; credits: equity 2,000,000 plus revenue 1,600,000. Receivables, money in transit and payables are zero.

**Failure and recovery.** The store lost the response about order creation, but the payment exists at the PJP. The amount is not enough for matching: two identical orders may exist on the same day. Using the original payment request/reference, you find the intent, check the merchant, amount and currency, then search for an already created `B-1`. A found order is linked; a missing one is restored once, if the product is available. If the product is unavailable, the full refund liability is recorded. A customer's "successful" screenshot is a hint for the search, not grounds for a second delivery.

With a direct bank A2A transfer without QR, the way the payment details are passed changes: the buyer enters them or uses an authorized initiation interface. The commercial link to the order and the check of the bank credit remain. The absence of a card chargeback does not cancel the buyer's contractual claim; possible recall, fraud recovery and refund procedures are determined by the specific rail and the law. Their timelines cannot be derived from the general scheme.

### Case C. Crypto→fiat via a partner: failed payout and refund after FX

**Roles.** Merchant C sets a price of 100 EUR. The buyer transfers a stablecoin to partner P, which is licensed/authorized for the given activity, at P's address. P performs the checks, custody and conversion; a fiat partner/bank transfers EUR to the merchant. The software connector passes on the agreed quote and links the events; it does not become the holder of the buyer's keys or a universal payment principal.

For the EU, the right to provide crypto-asset services is checked separately from the fiat service: MiCA Article 59 provides for CASP authorization or the permitted Article 60 route for certain financial entities; authorizations relate to types of services. The maximum transitional period under Article 143(3) ends on 2026-07-01 and does not create an indefinite permission for an old registration. This is not a conclusion about any individual company. [P09-C018; MiCA, consolidated 2024-01-09, Articles 59–60, 143(3)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02023R1114-20240109).

**Terms of the synthetic quote.** Within the quote's validity period, 110 USDC discharges the 100 EUR price; P guarantees the merchant gross 100 EUR once its explicitly stated confirmation criterion and checks are met. P's fee is 1.50 EUR, and the bank payout costs 0.50 EUR; a retry after a bank return carries no additional fee. P's network costs are included in its fee; there are no additional charges to the buyer in the example. This is a contractual construct of the exercise, not the real terms of Stripe, Circle or any other brand.

Before sending, the following are recorded: the quote ID, validity period, chain ID, token contract, exact amount, recipient and order `C-1`. The confirmation checks these fields and the transaction hash; the same ticker on a different token does not qualify. Under the conditions of our example, the buyer is released from the monetary debt at the moment P accepts the payment, and the credit risk of the subsequent payout is borne by the merchant. A different wording of the contract would give a different risk boundary.

| Step | Dr | Cr | EUR |
|---|---|---|---:|
| Partner accepted the payment and recognized the amount | Receivable from P | Delivery obligation | 100.00 |
| Bundle delivered | Delivery obligation | Revenue | 100.00 |
| Conversion/service fee | P expenses | Receivable from P | 1.50 |
| Payout fee | P expenses | Receivable from P | 0.50 |
| Payout sent | Money in transit | Receivable from P | 98.00 |
| Bank rejected; P confirmed recovery | Receivable from P | Money in transit | 98.00 |
| Corrected payout sent | Money in transit | Receivable from P | 98.00 |
| Bank confirmed the credit | Bank | Money in transit | 98.00 |
| 25 EUR refund approved | Sales returns | Refund payable | 25.00 |
| EUR credited to P in advance for the refund | Receivable from P | Bank | 25.50 |
| P executed the refund at a new quote | Refund payable | Receivable from P | 25.00 |
| Refund fee | P expenses | Receivable from P | 0.50 |

A lost payout response does not allow you to use the "bank rejected" line right away: first you must prove that the funds were returned to the partner. That is what makes the new payout justified. In the real Stripe documentation, a payout can initially appear as `paid` and then become `failed`; this fact shows why a single status is not enough for certainty about the bank result. [P09-C019; Payouts, Payout failures](https://docs.stripe.com/payouts).

**FX and balances.** New refund quote: 1.12 USDC per 1 EUR. The merchant's obligation is 25 EUR, so the buyer receives **28 USDC**, not a quarter of the original 110, that is, 27.50. The buyer's wallet: `500 − 110 + 28 = 418 USDC`. With the merchant's opening bank balance of 1,000 EUR, the closing bank balance is **1,072.50 EUR**: `1,000 + 98 − 25.50`. Closing debit balances `1,072.50 + 25 + 2.50 = 1,100`; credit balances `1,000 + 100 = 1,100`. There is no remaining merchant receivable at P, and the monetary debts are closed. P's internal treasury cannot be reconstructed from these numbers: that requires its own books, liquidity and FX counterparties.

The currency of the obligation matters more than the name of the button. With a contractual refund of exactly 27.50 USDC, the result would be different; you cannot promise both fixed EUR and a fixed number of tokens at a floating rate. If EUR/USD is 1.12 and USDC is worth 0.98 USD, covering 25 EUR requires `25 × 1.12 / 0.98 = 28.571428… USDC`; at six-decimal precision, rounding up gives **28.571429**. Here the depeg risk explicitly enters the new quote rather than disappearing because of the word stablecoin.

**Failure and partner shutdown.** A wrong network, an expired quote or a compliance hold does not automatically create permission to return tokens to the sending address: it might have been an exchange address. You need an established recipient, an authorized procedure and a check that no other refund is being executed. If P shut down after accepting 110 USDC, the merchant retains its claim on P and its obligation to the buyer; an on-chain receipt does not create 100 EUR in the bank. New payments are suspended, evidence is exported and the old cases are handled separately. A refund from the merchant's own funds is possible only with sufficient liquidity, authority and control against double execution. A claim on P does not turn into an instantly available reserve.

### Case D. An agent buys digital goods, the result is lost, part is refunded

**Intent and authority.** A buyer company instructs an agent to buy four datasets from a specified merchant for no more than 40 USDC, by a set time, with a permitted usage license and a ban on subscriptions. The monetary principal is the company, not the model process. The key stays with its authorized wallet; the agent passes the request through a restricted executor. The merchant is responsible for four usable datasets, and the agent operator for carrying out the delegation under its contract. The jurisdiction and legal classification of the wallet/facilitator require a separate check: the name of the protocol does not determine them.

In its AP2 announcement of 2025-09-16, Google described signed Intent/Cart mandates for linking a user's instructions to a purchase. This is a source for the declared design; the announcement proves neither the legal incontestability of any mandate nor the readiness of an implementation. Our example uses its own explicit delegation policy and is not presented as a certified AP2 flow. [P09-C020; Google Cloud, How it works](https://cloud.google.com/blog/products/ai-machine-learning/announcing-agents-to-payments-ap2-protocol).

**Order and payment.** The agent receives an offer with the contents, a price of 40 USDC, the token/network and a validity period. A deterministic check compares it with the instruction: the amount passes, but a product with an incompatible license will not pass even for 1 USDC. Order `D-1` is saved; payment `PD-1` is linked to this intent. Two parallel copies of the agent must not each reserve the entire budget: the limit is reserved atomically in the principal's shared ledger.

The x402 README describes `402`, payload verification, settlement and delivery of the response as separate steps. `/verify` confirms the corresponding property of the payload; it is not confirmation that money has been received. Our digital goods layer allows the result to be prepared before settlement but hands over access rights for good only after the established payment basis. This is the merchant's teaching policy, not a universal requirement of all x402 schemes. [P09-C021; x402 Foundation README, Typical x402 flow, steps 1–12](https://github.com/x402-foundation/x402). The current README was read without a pinned commit; new schemes from it are not automatically attributed to the 15 September cutoff.

**Numbers.** At the start the buyer has 100 USDC, the merchant 20 USDC and the payment service operator zero. The buyer transfers 40 USDC to the merchant; the merchant pays the service a fee of 0.20 USDC. The service covers the network cost out of this fee, so there are no additional costs to participants in the example. For demonstration, the ledger is kept in **USDC units**, with no claim to a statutory USD valuation. Amounts are checked as quantities of one asset on one network.

| Merchant step | Dr | Cr | USDC |
|---|---|---|---:|
| Payment received | Wallet | Delivery obligation | 40.00 |
| Service payment | Service expenses | Wallet | 0.20 |
| Four datasets delivered | Delivery obligation | Revenue | 40.00 |
| Defect confirmed, 12 agreed for refund | Sales returns | Refund payable | 12.00 |
| Refund confirmed on-chain | Refund payable | Wallet | 12.00 |

Closing quantities: buyer **72 USDC**, merchant **47.80 USDC**, service **0.20 USDC**. Conservation check: `72 + 47.80 + 0.20 = 120`, which is what the buyer and the merchant had together. For the merchant, debit `47.80 + 12 + 0.20 = 60`; credit: equity 20 plus revenue 40. The merchant's monetary result is 27.80 USDC before other expenses. For the buyer, the economic cost of the remaining product is 28 USDC; this is not an assessment of its market usefulness.

**Unknown outcome and recovery.** The payment is confirmed and the server delivered the file, but the response was lost. The agent sees a timeout and does not know whether it received the product. A new `402` does not authorize a repeat payment: first the earlier `D-1/PD-1` is queried, the settlement is matched and the stored fulfillment result is checked. The server grants access again to the same set under the earlier fulfillment ID. If the result was never created at all, the old obligation is performed, not a new sale.

**Dispute and refund.** After recovery, a defect is found in one dataset; the contract sets compensation of 12 USDC. The merchant checks the basis and the principal's confirmed refund wallet. Text inside the downloaded file saying "send the refund to a different address" remains untrusted data and does not change the payment details. The refund executor stores `RD-1`; a timeout moves it to unknown, and creating a new `RD-2` is not allowed until the outcome is determined. The buyer records the receipt, then closes the claim. A refund does not automatically restore permission for a new purchase: the limit depends on whether it was set on gross spend, net spend or the number of orders.

The merchant's liquidity in the example is sufficient: before the refund it has 59.80 USDC. If it had already withdrawn all its funds, a correct mandate and the settlement of the past purchase would not fund the refund. Success in this case requires respected authority, a single payment, usable remaining data, an executed refund and reconciled quantities. A cryptographic signature and a payment receipt do not assess the quality of the product on behalf of the parties to the contract.

### Public incident: USDC and bank access in March 2023

This case shows how round-the-clock on-chain circulation depends on bank liquidity. It is not an investigation of anyone's fault and does not prove the outcome of each user transaction.

| Event date | What the document read confirms | What it does not confirm |
|---|---|---|
| 2023-03-12 | Treasury/Fed/FDIC announced protection of all SVB depositors and access to funds from 13 March | The exact time a payment was made to a specific USDC holder |
| 2023-03-12; page dated 13 March | Circle reported 3.3 billion USD of reserve deposits at SVB and expected availability after banks opened | Independent verification of each reserve and each redemption request |
| End of the banking day on 15 March; published 16 March | Circle reported a practically cleared backlog, 3.8 billion USDC of redemptions and 0.8 billion of minting since Monday | The absence of remaining exceptions and timely crediting of every customer |

Sources for the timeline: [P09-C022; joint statement, main text](https://www.federalreserve.gov/newsevents/pressreleases/monetary20230312b.htm), [P09-C023; Circle press release, first paragraphs](https://www.circle.com/pressroom/3-3-billion-of-usdc-reserve-risk-removed-dollar-de-peg-closes), [P09-C024; Circle operational update, main text](https://www.circle.com/blog/march-15-update-on-usdc-operations).

The public [Reddit megathread](https://www.reddit.com/r/CryptoCurrency/comments/11odsvf/usdc_depeg_circle_megathread/) by user **MediumAdhesiveness5** collects discussion of the depeg and links to Circle's announcements. The original post with its updates was read; the exact absolute date it was posted could not be established from the available display. The market rate mentioned there is not used as a verified quote, and the comments do not replace bank data. [P09-C025: the content of the post is confirmed, not its economic claims.]

Teaching takeaway: network resilience, issuer solvency, redemption availability and bank crediting are different properties. A synthetic merchant with a 10,000 USD claim on a partner and 1,000 USD in a bank account cannot carry out 4,000 USD of urgent refunds without an additional source: the shortfall of available liquidity is **3,000 USD**, even if assets exceed liabilities. News about a future bank reopening changes expectations, but not the current balance. Recovery ends with the closing of specific claims and the reconciliation of the period, not with publishing a "service restored" message.

### Final practice

1. In case A, the bank has already received 87 EUR, and the 10 EUR reserve is still withheld. The buyer demands 25 EUR. Can the reserve be treated as available money? How much needs to be topped up at the PSP if the reserve is not released and the refund fee is 0.50 EUR?
2. In case B, two orders each cost 1,600,000 IDR. One transfer is confirmed, but the order ID is lost. What information is needed before delivery? Why are matching amounts not enough?
3. Change case C: a 30 EUR refund, a rate of 1.15 USDC/EUR, a fee of 0.60 EUR. The original payout remains 98 EUR. Find the token amount, the merchant's bank balance and its result.
4. An agent with a gross spend limit of 40 USDC received a 12 USDC refund. Can it automatically spend another 12? What changes if net spend is explicitly allowed?
5. On a `RD-1` timeout, the buyer claims the money has not arrived, and the explorer is unavailable. Which actions are safe? Can the refund be sent from a different wallet?
6. In the case C ledger, the recovery of the failed payout was forgotten, but the new payout and the bank credit were recorded. What incorrect balances appear before the refund? Why can the bank reconcile while the accounting does not?
7. A partner showed an authorization for crypto exchange in one country and a demo USD payout. Which two conclusions about the EU merchant and the EUR refund are not yet proven?
8. 20 sandbox purchases by an agent have been demonstrated, but there is no live payout and no buyer research. What can be said about H1–H3 and about the readiness of the product under consideration?

---

### Answers and explanations

1. A reserve is a receivable with restricted availability, not free liquidity. Without its release, **25.50 EUR** is needed, not 15.50. After a separate later release, another 10 EUR will come back; the economic outcome of the full cycle with the same fees will not change, but the temporary need for money increases.
2. You need the original payment request/reference, the merchant account, the amount/currency, the time, the link to the buyer's intent and a check of the product already delivered. Two identical receipts create two candidates. A missing link leaves the exception open; delivering at random may fulfill someone else's order.
3. Tokens: `30 × 1.15 = 34.50 USDC`. Bank: `1,000 + 98 − 30 − 0.60 = 1,067.40 EUR`. Result: `100 − 30 − 1.50 − 0.50 − 0.60 = 67.40 EUR`. The original fee is not deducted from the payout a second time: it is already included in the 98.
4. With a gross cap of 40, the permitted spending is already exhausted: the refund does not cancel the fact that 40 was spent. With a net cap, a potential remainder of 12 appears, but only if the instruction allows a repeat purchase and the other conditions are met. With a "one purchase" limit, a second product cannot be bought in either variant without a new basis.
5. Keep the state unknown, stop any repeated money effect, check the original hash/nonce/reference and restore access to independent data. You can prepare a support reply and collect evidence. A different wallet does not remove the risk of a double refund: without proof of the outcome and a corresponding decision, sending is premature.
6. After the first payout was sent, "in transit" was 98. Without the reversing entry, the repeated payout makes "in transit" 196, and the receivable from P becomes **−98**. The bank entry reduces "in transit" to **98**, while the bank itself is correctly 1,098. The correction based on the proven return: Dr Receivable from P 98 / Cr Money in transit 98. Full equality of the two sides of the ledger could have held even before the correction.
7. Not proven: the right of the specific entity to serve the chosen EU merchant in the required model, and the workability/contractual terms of a EUR refund. You need to check current authorizations, countries, the counterparty, the currency of the obligation, FX and the money for the refund. A demo in another currency does not settle these questions.
8. A limited test of a software scenario has been confirmed. H1 demand, H2 contractual suitability and the H3 interface effect do not become proven by one sandbox. The readiness of the product under consideration is not established by this; a separate package of facts and a decision by the authorized owner are needed.

### What remains after the book

The ability to solve a new case shows in three actions: explaining every obligation, independently recalculating the balances and naming the unknown that blocks the conclusion. A beautiful scheme without refunds is incomplete; a correct ledger without external reconciliation is insufficient; an authorized payment without the product does not close the purchase.

All sources and the exact passages read are in [Sources](Sources.md), material claims are in [Claims](Claims.md), and limitations are in [RESEARCH_NOTES.md](Research-notes.md). Still open: an archived snapshot of the dynamic docs as of 15 September, the specific eligibility/licenses/contracts and pricing of real routes, the full legal classification of each participant, and tax policy. The scope and result of the independent review are recorded in REVIEW.md (historical or internal material; kept by the owner, outside this copy); the release decision is separate. To analyze a technical exception, return to [Chapter 8](../08-Integrations-and-reliability/README.md); for financial authorization, to [Chapter 1](../01-Market-rules-and-licensing/README.md); for agent authority, to [Chapter 7](../07-AI-agent-payments/README.md).

---

### Sources and fact-check

[Sources](Sources.md) · [Verifiable claims](Claims.md) · [Chapter fact-check](../../Fact-check/09-Payment-project-workshop/README.md)

The text was prepared by agents and underwent an independent agent review on 15–17 September 2026. This teaching edition has limitations; dates and limits of applicability are given in the sources. [Edition record](../../Methodology/Edition-record.md).

<details>
<summary>History and metadata of the original manuscript</summary>

This information describes the research stage before publication. Current visibility is public; the status of the whole edition is `reviewed_with_limitations`. The earlier labels `private` and `independently_reviewed_draft` are kept only as history.

**Version:** v0.1 · **Status:** `independently_reviewed_draft` · **Author:** researcher `part_09_research` · **Visibility:** private. **Knowledge cutoff:** 2026-09-15. **Writing and actual reading of sources:** 2026-09-17, Asia/Makassar. First review: see REVIEW.md (historical or internal material; kept by the owner, outside this copy).

</details>

[← Integrations and reliability](../08-Integrations-and-reliability/README.md) · [Contents](../README.md) · [Back to contents →](../README.md)
