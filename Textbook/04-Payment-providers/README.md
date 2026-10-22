[← Cards: Visa and Mastercard](../03-Visa-and-Mastercard-cards/README.md) · [Contents](../README.md) · [Wallets, accounts and cards →](../05-Wallets-accounts-and-cards/README.md)

<a id="часть-4-psp-платформы-payfac-и-mor"></a>
# Chapter 4. Payment providers

> PSPs, platforms, PayFacs and Merchant of Record: liability and economics.

**6 lessons** · Knowledge cutoff: **15 September 2026** · [Sources](Sources.md) · [Fact-check and limitations](../../Fact-check/Results.md)

## In this chapter

- [4.1 · Types of payment providers](#module-4-1)
- [4.2 · How a provider vets and onboards a merchant](#module-4-2)
- [4.3 · When and how the merchant gets paid](#module-4-3)
- [4.4 · The economics of a payment provider](#module-4-4)
- [4.5 · Practice: a regular PSP and accepting crypto](#module-4-5)
- [4.6 · The economics of bank partnership and sponsorship](#module-4-6)
- [Exercises](#exercises)
- [Answers with explanations](#answers-with-explanations)
- [Summary, connections and gaps](#summary-connections-and-gaps)

---

This chapter explains how the business around payment acceptance is organized: who signs the contract with the merchant, who bears the loss, why money is delayed and how much of the fee is actually left. The main context is e-commerce and platforms. Product examples are tied to the stated country and configuration; legal explanations are limited to the US, UK and EU materials that were read. No company's specific terms are treated here as a universal permission to operate in all countries.

Useful prerequisites are [0.5: money and accounting](../00-Money-and-fintech-basics/README.md), [1.3: five models](../01-Market-rules-and-licensing/README.md) and [2.2: the payment lifecycle](../02-How-a-payment-works/README.md). After reading, you will be able to map contracts and liability, explain reserves and payouts, calculate profit and the cash gap, check a crypto acceptance claim and assess dependence on a bank partner.

**All numerical examples, except explicitly named public tariffs, are synthetic.** They are exercises, not market statistics or vendor offers. Real-world operation requires the specific contracts, licenses and financial model to be checked by qualified specialists. The evidence catalog is [Sources](Sources.md); material claims are in [Claims](Claims.md).

<a id="module-4-1"></a>
<a id="41-классификация-провайдеров"></a>
## 4.1 Types of payment providers

### One interface can hide several different roles

A payment **gateway** passes data between checkout and the next participants in processing. An **acquirer** organizes card acceptance on the merchant side. **Payment service provider, PSP**, is a name that must be read in context: in commercial conversation it refers to a broad package of services, while in legislation it has a specific definition and a defined set of entities. **Full-stack PSP** signals a promise to combine more functions, but does not explain which legal entities perform them in a given country.

So it helps to fill in five lines first: who sells the goods; who accepts the payment instruction; who is the scheme participant; on whose balance sheet the debt to the merchant appears; who receives the complaint. A company can play several roles, and one brand can represent different legal entities.

| Model | What the merchant gets | Where to look for the contract and liability |
|---|---|---|
| Gateway-only | A payment form, request transmission, tokenization or integration | Separate relationships with the gateway and the acquirer; owning the interface does not mean receiving the proceeds |
| Full-stack PSP | A bundle of processing, risk control, reporting and payouts | The product terms plus the terms of the actual financial partners |
| PayFac | Onboarding and servicing of sponsored merchants through an acquirer | The acquirer–PayFac agreement, the merchant agreement, scheme rules and applicable law |
| Marketplace/platform | Organization of trade, orders or relationships between sellers and buyers | A platform can be a software intermediary, a seller, or have payment functions; the word marketplace does not give the answer |
| MoR/reseller | Selling through a party that acts as the seller to the buyer | The supply/resale agreement, buyer terms, refunds, taxes and the right of recourse |
| Orchestration | Selection and combination of several payment integrations | An agreement for the software layer plus separate authorized relationships with each downstream provider |

**Payment facilitator, PayFac**, is a role in organizing card acceptance, not a universal financial license. Under the Mastercard Rules, the acquirer is responsible for the actions of the PayFac and its sponsored merchants, although it can delegate business vetting, retention of vetting materials, payouts and monitoring. This is a division of work that preserves the acquirer's liability to the scheme. It does not turn the PayFac into the seller of all goods. [P04-S002, §§7.6.5–7.6.5.1](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-rules.pdf)

The legal boundary is determined by activity. For example, the FCA warns UK marketplaces that receiving buyers' money before passing it on to the seller, including through an account in the platform's name at an acquirer, may be a payment service. Whether an exclusion is available requires a separate assessment. Registering the company as a marketplace does not settle this question. [P04-S001, “If your business receives customer money…”](https://www.fca.org.uk/firms/consider-if-you-provide-payment-services)

### Who is the MoR for the scheme and who is the seller to the buyer

**Merchant of record, MoR**, is a term about liability for the sale/transaction; **seller of record, SoR**, is also used to denote the seller. They should not be treated as standard licenses in their own right, or as terms that mean exactly the same thing in every contract. Two pictures are checked for consistency: whom the card transaction represents, and with whom the buyer makes the deal. The name on the statement helps identification, but does not by itself change the sales contract.

In the Stripe Connect documentation, a direct charge makes the connected account the MoR; an indirect charge with `on_behalf_of` also assigns the MoR role to the connected account, but covering its negative balance may remain with the platform. With an indirect charge without this parameter, the MoR is the platform. The document requires the website, checkout, receipt and descriptor to be consistent with the actual selling party. These are the rules of a specific integration, not a way to designate the seller with a single arbitrary API field. [P04-S003, “Define the merchant of record”](https://docs.stripe.com/connect/merchant-of-record)

Paddle uses a different contractual structure: the company is appointed reseller of the agreed software/digital content; the supplier provides the product, while Paddle sells to the buyer and handles sales tax as set out in the agreement. At the same time, the supplier remains obliged to provide accurate product information, and refunds and chargebacks can be passed on to it for reimbursement. So "the MoR takes on liability" does not mean "the supplier never bears losses again." [P04-S004, §§2–4, 9.4, 10](https://www.paddle.com/legal/terms)

**Example.** A buyer purchases access for 120 USD, which includes a notional 20 USD of tax. In the teaching reseller model, the MoR must remit the tax of 20 and retains the agreed 8, and 92 is owed to the supplier. Check: 20 + 8 + 92 = 120. The buyer claims the refund from the MoR, and the MoR applies its agreement with the supplier. In the direct merchant model, the same 120 enters the merchant's own settlement flow, and its tax obligation does not disappear because a PSP is involved. A numerically similar payout does not prove the same legal model.

### What orchestration actually does

Routing selects a processor by rules: currency, card type, region, share of traffic. For example, Spreedly describes static, split-volume and conditional routing. Its claims of an improved approval rate reflect the vendor's interest; the mere existence of selection rules does not prove an economic effect. [P04-S005, “Types of Routing”](https://developer.spreedly.com/docs/routing-rules-1)

In the teaching example, a store has authorized connections A and B. Switching from A to B changes the technical path of new payments, but does not move old settlements and disputes to B. A timeout at A means an uncertain result: first find the original attempt and its status; otherwise B may charge the customer a second time. The orchestrator must remember the contractual scope of each route and keep the link between the order, the attempt, the charge and the payout. Its API does not replace a new acquirer's underwriting.

<a id="module-4-2"></a>
<a id="42-underwriting-и-onboarding"></a>
## 4.2 How a provider vets and onboards a merchant

### Why checks do not end with uploading a passport

**Onboarding** is connecting a client to a service. **Underwriting** is deciding whether its risk is acceptable and on what terms. **KYB, know your business**, checks the legal entity, its activity and control; **UBO, ultimate beneficial owner**, denotes the person who is the final beneficial owner. Checking that a company exists does not answer the question of whether it will fulfill the obligations it has already been paid for.

Stripe explicitly links Connect requirements to the jurisdiction, capabilities, business type, agreement and risk level. Additional information may be required later; if it is missing, charges or payouts can be paused. Even a successful Stripe verification does not replace the platform's own legal obligations and fraud monitoring. [P04-S006, “Verification requirements”, “Onboarding flows”](https://docs.stripe.com/connect/identity-verification)

A practical questionnaire has to combine four layers. The first is the entity: registration, the representative's authority, owners, bank details. The second is the product: what exactly is sold, whether it may be sold, who fulfills it and within how many days. The third is the buyers: countries, acquisition channels, ticket size, subscription or one-off purchase. The fourth is the cash forecast: volume, refunds, disputes, liquidity if new sales stop. This is an analytical framework, not a complete list of a specific regulator's requirements.

A mismatch between the **MCC** (the merchant category in the card system), the website and the actual product makes the risk picture unreliable. A template store and a marketplace that, after onboarding, started accepting advance payments for tourist trips have different obligations to buyers. What must be checked is the actual activity, the URL, the contractual seller and the territory; choosing a convenient category instead of the correct one is not allowed. At Mastercard, reporting on a sponsored merchant includes its name/URL, MCC, volume and chargebacks. [P04-S002, §7.6.5.1(5)](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-rules.pdf)

### Merchant risk resembles credit risk

In a sale with future delivery, the money has already been accepted, but the obligation to the buyer still exists. If the merchant has spent the proceeds and stopped fulfilling orders, refunds may arrive after it has disappeared. A PSP assesses not only the average fraud rate but also a large correlated loss: many buyers demanding their money at the same time for one cancelled concert or a shut-down service.

**Example.** A company sells a future service for 100 USD: 1,000 buyers, 100,000 USD in total. Before delivering, it has spent 70,000. Everyone needs a refund, and it has 30,000 of its own money left. The shortfall is 70,000 USD even before dispute costs. Flawless registration and a zero chargeback history in the first week do not eliminate this shortfall. The faster advance sales grow, the more unfulfilled obligations have to be funded if the business stops.

### Reserve, hold and delayed payout are different restrictions

A **reserve** is a defined amount of funds held back as cover for potential obligations. A **rolling reserve** holds back a share of each eligible sale and releases it as the corresponding cohort ages. A **hold** is broader: a stop on availability or payout, for example during a review; its duration cannot be inferred from the word reserve. A **delayed payout** sets a time lag before money is released, and a **payout schedule** is the calendar for sending funds that are already available.

In its US help article, Square describes a rolling reserve: a share of card payments is set aside and then released; the factors include prepayment, the nature of the industry, disputes, irregular activity and a new processing history. The exact terms must be taken from the notice to the client, not from a general FAQ. [P04-S007, “About reserves”, “Before you begin”](https://squareup.com/help/us/en/article/6832-reserves-faq)

**Reserve calculation.** Conditions: 10% of gross sales is held for 90 calendar days; sales are 1,000 USD per day for 90 days in a row; there are no refunds. Each day 100 USD is added. Before the first release, 9,000 USD will have accumulated. On the next day the first hundred is released and a new one comes in: at constant volume, the balance stabilizes. This is not "a 10% fee." The merchant's balance still includes a claim to 9,000, but it cannot be spent now.

If the goods cost 850 USD for every 1,000 of sales and the fee is 30, then 870 of the first cohort remains available to spend: 1,000 − 30 − 100. After paying for the goods, 20 USD is left. The economic margin before other costs is 120, but 100 of it is tied up in the reserve. The cost of financing 9,000 USD at an illustrative 12% per year is 1,080 USD per year at a constant balance. Interest is an expense, the reserve is a liquidity constraint; a final debit from the reserve is accounted for separately.

**Edge case.** A merchant passed initial onboarding but did not provide new UBO documents. Charges are allowed, payouts are paused. This can be treated neither as a confirmed confiscation nor as proof of full readiness: you need the reasons for the restriction, the deadline and the available actions for the specific account. Working around it through someone else's account does not correct the information about the real seller.

<a id="module-4-3"></a>
<a id="43-settlement-к-мерчанту"></a>
## 4.3 When and how the merchant gets paid

### Four points in time instead of a single "paid"

A merchant needs to distinguish settlement between the participants of the rail, crediting to the PSP's internal balance, the amount moving into the available balance, and the payout arriving at the bank. **Settlement** in different providers' interfaces can denote different segments of this sequence. So a contractual T+2 is incomplete without defining T, business/calendar days, the cutoff and the currency.

Stripe explains that changing the payout schedule does not speed up the conversion of the pending balance into the available balance. A daily schedule means regularly sending money that has already matured. Bank crediting time and country specifics apply separately. [P04-S008, “Payout schedule”, “Settlement timing”](https://docs.stripe.com/payouts)

**Timing example.** Capture takes place on Friday; the agreement specifies T+2 business days, and there is no holiday. Monday is the first business day, Tuesday the second. With daily sending, the payout can go out on Tuesday; with weekly sending on Fridays, only on Friday. If the bank credits on the next business day, the money will be accessible at the bank even later. This illustrates the given conditions, not a promised timeline of any PSP.

### Gross and net: what exactly was deducted

With **net settlement**, fees are withheld from payouts. With **gross settlement**, the agreed fees can be invoiced separately. Gross does not necessarily mean paying out the full sales amount, though: refunds, reserves and adjustments also change the settlement balance. A provider may use its own definitions, so you need to read the statement formula.

Adyen's Settlement details report distinguishes transactions, fee entries, changes to the deposit/reserve, invoice deductions and MerchantPayout, with details for reconciliation with the bank. In an IC++ breakdown, the overall Commission may be empty, while Markup, Scheme Fees and Interchange are filled in separately. You must not add the total fee to its own components. [P04-S009, “Entries”, “Standard columns”](https://docs.adyen.com/reporting/settlement-reconciliation/transaction-level/settlement-details-report/)

**Synthetic statement, USD.** The opening balance is zero; all listed sales are available for settlement.

| Movement | Change in the PSP's obligation to the merchant |
|---|---:|
| Sales | +10,000 |
| Refunds | −400 |
| Chargeback principal | −100 |
| Fees | −300 |
| Transfer to a separate reserve balance | −500 |
| Available for payout | 8,700 |

After the payout, the merchant's bank has received 8,700, and 500 remains in the reserve. Check of how the original money was allocated: 8,700 + 500 + 400 + 100 + 300 = 10,000. If the same fees are collected through a separate invoice, the payout will be 9,000 and the merchant still owes 300: the economic result is the same. This is no reason to recognize 9,000 as revenue instead of the value of actual sales: revenue recognition, taxes and the agent role are checked separately.

A PSP's simplified management accounting first records a settlement-flow asset of 10,000 and an obligation to the merchant of 10,000. Moving 500 into the reserve changes the availability of part of the debt, but does not create profit. The payout entry reduces the asset and the debt by 8,700. This presentation helps reconcile amounts; the actual chart of accounts depends on who is the principal, who legally owns the funds and how safeguarding is arranged.

### A split is not yet a payout

Distributing money among recipients can be an entry in PSP balances. Paying each recipient out to a bank is the next operation. In Stripe separate charges and transfers, the platform creates a charge and, separately, transfers; fees, refunds and chargebacks debit the platform's balance. A refund of the original charge should not be treated as an automatic reversal of all previously completed transfers. [P04-S024, introductory section; “Issue refunds”, “Reverse transfers”](https://docs.stripe.com/connect/separate-charges-and-transfers)

In the teaching delivery example, out of 80 USD the restaurant is allocated 60, the courier 8, processing costs 2, and 10 is left for the platform. If the order is fully refunded, the customer must get 80. Before the refund, only 10 is available to the platform; it must recover the remaining amounts contractually and technically, or cover the gap with its own money. Having a split field does not guarantee successful recovery from a restaurant that has already withdrawn the money.

With a failed payout, the original debit from the available balance must be linked to the return movement and then to a new attempt. Stripe warns that a payout may first have the status `paid` and then move to `failed`; receiving the bank return takes time. [P04-S008, “Payout failures”](https://docs.stripe.com/payouts) Until the return is confirmed, you must not create an independent second payout just because the recipient does not see the money. You need the payout ID, the amount/currency, the bank reference, the failure code and the movement back into the balance.

<a id="module-4-4"></a>
<a id="44-экономика-psp"></a>
## 4.4 The economics of a payment provider

### Volume is not revenue, and a fee is not profit

**GMV, gross merchandise value**, here means the gross value of processed sales per month, as we define it. Other reports may use TPV, processed volume and other bases. Before comparing, you need to establish whether refunds, taxes, FX, payouts and internal transfers are included. **Take rate** is the ratio of a chosen revenue figure to a chosen volume. Without the numerator and the denominator, a figure of "3%" cannot be verified.

In **IC++, interchange++**, interchange, scheme fees and the servicing party's markup are shown separately. Pass-through means passing a specific cost on to the client under the agreement; it is not a promise of zero markup on everything. Authorizations, refunds, FX, minimums and account maintenance may be charged separately. Adyen explicitly describes fees on some non-settled events and the need to reconcile the monthly invoice, not only the settlement report. [P04-S010, “Processing Fees”, “Authorisation Scheme Fees”](https://help.adyen.com/knowledge/finance/invoices/how-do-i-reconcile-my-invoice)

Why does part of the money go to the issuer? In a four-party card system, interchange redistributes revenue between the issuing and acquiring sides. The economics of two-sided markets takes into account that a card works only if both the buyer and the merchant agree to use it. This is an explanation of the mechanism from FEDS 2009/23; the rates cited in that older paper do not describe 2026. [P04-S016, §§II–III](https://www.federalreserve.gov/pubs/feds/2009/200923/)

In the authors' version of Rochet–Tirole dated 2002-12-13, demand in the model depends on the prices for both sides, and profit depends on the joint volume and the total price minus costs. A useful conclusion follows: a low price for one side can be rational if it attracts the other side. This is a theoretical result with assumptions, not proof that any subsidy will pay off. [P04-S017, §2, PDF pp.8–11](https://tse-fr.eu/sites/default/files/medias/doc/wp/2002/platform.pdf)

### A full model of revenue and losses

For a simple month, let: G be the volume in USD; N the number of successful payments; t the share of volume charged; r the costs proportional to G; f the costs per successful payment; L other expected losses; O variable operational support; F fixed costs. Then:

**Fee revenue = G × t.**  
**Contribution = G × (t − r) − N × f − L − O.**  
**Operating result = Contribution − F.**

If the processing fee is charged per attempt, a separate count of attempts A is needed instead of N. Fees on payouts are calculated on the number/volume of payouts, and fees on accounts on the number of active accounts. A single overall rate works only after these bases have been correctly converted to volume.

**A fully synthetic PayFac, one month, USD.** G = 1,000,000; N = 20,000; average ticket 50; client price 3.2% with no fixed component. The rates below are not taken from any company's agreement.

| Item | Calculation | USD |
|---|---:|---:|
| Fee charged | 1,000,000 × 3.2% | 32,000 |
| Interchange + network pass-through | 1,000,000 × 2.1% | −21,000 |
| Processing | 20,000 × 0.08 | −1,600 |
| Sponsor fee, in addition to the lines above | 1,000,000 × 0.1% | −1,000 |
| Unrecovered principal fraud-loss | 1,000,000 × 0.10% | −1,000 |
| Other lost disputes, excluding the fraud above | 1,000,000 × 0.05% | −500 |
| Other credit loss, excluding the amounts above | 1,000,000 × 0.03% | −300 |
| Dispute handling fees | Given monthly total | −200 |
| Variable support | Given monthly total | −300 |
| Contribution | Difference | 6,100 |
| Fixed costs | Team, systems, audit | −15,000 |
| Operating result | 6,100 − 15,000 | **−8,900** |

Fraud and chargebacks often describe the same loss from different angles: fraud is the cause, a chargeback is the mechanism for the claim. In the table, the loss categories deliberately do not overlap. If a 100 USD fraudulent payment is already included in fraud-loss, you cannot deduct the same 100 again as chargeback principal. An additional dispute fee can be deducted separately. If the merchant reimburses the loss, the final loss is reduced; using the merchant's reserve is not a second loss for the PSP.

With an unchanged average ticket, mix and proportionality of the other variable costs, contribution equals 0.61% of G. **Break-even G = 15,000 / 0.0061 ≈ 2,459,016 USD per month.** Above this threshold, the model turns an operating profit only if the assumptions hold. Doubling volume to 2 million still gives −2,800. If non-overlapping losses rise by 0.4 percentage points, the margin shrinks to 0.21%, and break-even becomes about 7.14 million. A positive take rate does not save a negative contribution.

Some companies report revenue net of pass-through. Then, for our example, the starting revenue may be 11,000 instead of 32,000. You cannot subtract 21,000 again from 11,000. Recognizing revenue gross or net for accounting purposes requires a principal–agent analysis; here we show two presentations of the same management economics.

### One ticket, four ways to pay

Let us compare a payment of **20 USD equivalent**: one domestic market, the same product, with no sales tax, no cross-border element and no mandatory FX. All costs below are invented for teaching; they are not actual price quotes for these rails. In the crypto option, the merchant pays the stated network cost; if the buyer pays it, the distribution of costs changes, but the cost does not disappear.

| Component, USD per payment | Card | A2A, bank transfer | QR leading to the same card | Stablecoin via a partner into fiat |
|---|---:|---:|---:|---:|
| Acceptance/processing | 0.46 + 0.10 | 0.20 | 0.46 + 0.10 | 0.12 |
| Blockchain network | — | — | — | 0.06 |
| Conversion spread | — | — | — | 0.08 |
| Bank payout, per payment | included | included | included | 0.04 |
| Expected non-overlapping loss | 0.08 | 0.03 | 0.08 | 0.05 |
| Support/reconciliation | 0.03 | 0.05 | 0.03 | 0.02 |
| Cost of tied-up liquidity | 0.02 | 0.01 | 0.02 | 0.03 |
| Additional QR interface | — | — | 0.01 | — |
| **Variable all-in cost** | **0.69 / 3.45%** | **0.29 / 1.45%** | **0.70 / 3.50%** | **0.40 / 2.00%** |

Here QR is a way to pass checkout data, so it keeps the card economics. If the QR initiates a local A2A payment, you have to count that A2A, its tariff and the additional interface costs. Comparing "QR 0%" with "card 3%" without the underlying rail is meaningless. A crypto transaction may have no card chargeback, but it still carries mistaken transfers, refunds, compliance review, and counterparty and exchange-rate risk.

For the **full** cost to the business, add the allocated share F/N. With F = 2,000 USD per month and 10,000 successful payments, that is another 0.20 per payment: the final figures are 0.89; 0.49; 0.90; 0.60. This compares four alternative architectures with the same F; it is not the cost of four systems with F counted once. If all four run at the same time and new fixed costs arise, the model has to be rebuilt.

**The low-ticket trap.** A notional 2.9% + 0.30 costs 0.358 USD on a 2 USD purchase, that is 17.9%; on 20 USD it costs 0.88, that is 4.4%. Issuing prepaid credits can combine many small uses into one payment, but it adds an obligation to the customer, refunds and possible questions about a stored-value regime. This is a new product that cannot be justified by fee savings alone.

The cost of platform payouts changes too. On the US Stripe Connect page that was read, the “You handle pricing” model includes 2 USD per monthly active account and 0.25% + 0.25 USD per payout; payment processing is paid for separately. [P04-S011, “You handle pricing”](https://stripe.com/connect/pricing) With 100 active sellers, a total payout of 100,000 and four payouts to each seller, these components cost 200 + 250 + 100 = 550 USD. One payout to each seller would reduce the last part to 25, for a total of 475, but the sellers would wait longer.

### Mix and quality of sales

If half of payments go by card at a cost of 0.69 and half by A2A at 0.29, the average is 0.49. But you cannot simply move everyone to A2A and declare savings: some buyers may abandon the purchase. For 100 checkout visits, a 20 USD ticket and an 8 USD gross contribution from the product: 80 successful card purchases give 80 × (8 − 0.69) = 584.80; 70 A2A purchases give 70 × (8 − 0.29) = 539.70. The cheaper payment method brought the business less money. This is a teaching causal scheme, not experimental estimates of conversion rate.

<a id="module-4-5"></a>
<a id="45-связка-с-учебным-проектом-ordinary-psp--crypto-acceptance"></a>
## 4.5 Practice: a regular PSP and accepting crypto

### What exactly is being studied

The module title preserves its address in the structure, but what follows is neither a launch decision nor a description of an internal Lab product. **Ordinary PSP + crypto acceptance** is a hypothesis about combining a merchant interface, a crypto service provider and fiat settlement. Whether it is permissible depends on the roles and contracts. You cannot accept crypto from a buyer and then covertly present a downstream PSP with an ordinary merchant payment from a different person, treating the mere fact of conversion as permission.

**SSP**, if a provider uses it to mean stablecoin service provider, is a commercial label that needs to be decoded. **VASP** and **CASP** belong to specific regulatory frameworks for crypto services; the name SSP does not prove such a status. The detailed legal classification and the path of the money are covered in [Chapter 6](../06-Crypto-and-stablecoins/README.md).

### A matrix of the public documentation actually read

This is a comparison of evidence as of 2026-09-15, not a shortlist. "Not established" means there is no confirmation in the cited source, not that the product is proven to be absent.

| Check | Stripe Stablecoin payments | Triple-A, help pages read |
|---|---|---|
| Crypto-in | USDC on the listed networks; USDP and USDG have US-only caveats; USDT is not on the list | Crypto payments and invoice payments are described; the exact token/network matrix is not established in these pages |
| Fiat outcome | Credit to the Stripe balance in local currency; this is not yet a bank payout | For invoice payments, fiat or crypto settlement at the business's preference is stated |
| Merchant geography | US is stated explicitly; EU/HK/MX/CH are named as private preview | Eligibility of a specific merchant/entity/geo is not established by these FAQs |
| Delegation to an agent | Customer-authenticated wallet flow; the document does not prove an autonomous agent's right to spend from someone else's wallet | Not established |
| Refund | Stablecoin to the buyer's original wallet | Detailed refund terms not checked |
| Eligibility | Capability and business restrictions; whether the account has the method is checked separately | The specific client's contract and underwriting are required |
| Reading limitation | No version number/commit; the country-code list is broader than the preview text | No update date and no individual contract |

Grounds: [P04-S012, “Payment method properties”, “Business locations”, “Limitations”, “Connect support”](https://docs.stripe.com/payments/stablecoin-payments); [P04-S014, “What services…”](https://support.triple-a.io/knowledge/what-services-does-triple-a-provide). General availability in additional countries cannot be inferred from the Stripe country-code list: this is a specific contradiction on the page, left open.

The payout threshold is also part of the product. At Triple-A, a separate FAQ describes an automatic local-currency withdrawal once 3,000 USD equivalent is reached, followed by bank processing time. This is a general help-center condition that was read; its applicability to a specific contract is unknown. [P04-S015, “Bank account settlements…”](https://support.triple-a.io/knowledge/i-didnt-receive-my-payment-what-can-i-do) For a teaching-example merchant receiving 100 USD a day, such a setup means about a month of accumulation before the threshold is reached, even if each payment is confirmed quickly.

### Decision tree for models 1–5

1. **Only a catalog, an order and a redirect?** This is a candidate for a software connector, model 1. The buyer makes the deal with the merchant, who is itself connected to the required provider. The connector does not gain the right to dispose of client funds.
2. **Does the merchant itself connect a supported crypto method?** This is direct merchant–provider, model 2. You need a permitted product, an eligible merchant country, a conversion/settlement agreement and a clear refund process.
3. **Does the platform onboard merchants and distribute their proceeds?** This is model 3; you have to determine separately the payment role, the seller, control over balances and liability. A platform is not automatically a PayFac, and PayFac registration does not permit any crypto flow.
4. **Does the operator actually resell the goods to the buyer?** This is a candidate for MoR/reseller, model 4. You need real resale rights, buyer terms, fulfillment, taxes and refunds. Calling yourself the MoR at checkout is not enough.
5. **Does the operator itself accept/hold/exchange client funds?** This is a candidate for its own payment/custody stack, model 5, with a separate analysis of the regulated activity. Using your own code does not yet prove custody; what matters is actual control.

Stripe separately classifies crypto exchanges/wallets and a number of financial services as restricted businesses that require additional review; approval applies to a specific service and may be changed. This confirms the need to describe the real model rather than extend an ordinary merchant account to an adjacent business. [P04-S013, “Restricted Businesses”](https://stripe.com/legal/restricted-businesses)

**End-to-end example.** Merchant M sells its own digital service for 50 USD. The buyer chooses a permitted crypto method offered by partner X. X provides a quote, accepts the agreed asset on the correct network, confirms the payment and must transfer 49 USD to M after a notional fee of 1. The connector stores the order ID and payment ID, and M delivers the service after the agreed proof of payment. In this model there may be no card charge at another PSP at all: fiat arrives by bank transfer. If the arrangement assumes such a charge, you must separately disclose who pays it, its economic basis and its contractual support.

**Failure.** The crypto has been received, but the fiat payout is delayed by a review. The order may count as paid under X's rules, X's obligation to M exists, but M does not yet have the money in the bank. You must not automatically issue a new crypto invoice. You need to reconcile the original transaction, the review status and the terms for fulfillment/refund. A full refund of 50 USD may require M to also give back the notional 1 USD fee if the agreement does not refund it; which asset and which rate the buyer receives is determined by the specific refund mechanism.

<a id="module-4-6"></a>
<a id="46-sponsorship-и-bank-partnership-economics"></a>
## 4.6 The economics of bank partnership and sponsorship

### Sponsor: who, and for which function

**Sponsorship** means a relationship of access/participation and control in a specific system. The word sponsor without qualification is dangerous: people may be discussing card issuing, merchant acquiring or a banking product while meaning different contracts.

| Relationship | What the partner provides | Main parties and risk |
|---|---|---|
| Issuing BIN sponsorship | Access to issuing a card program through a scheme participant and the relevant BIN/account ranges | Issuer, program manager, cardholder; spending limits, cardholder obligations, fraud and settlement |
| Acquiring/PayFac sponsorship | Acceptance of merchant transactions and the link between the PayFac and the acquirer/scheme | Acquirer, PayFac, sponsored merchant; business underwriting, chargebacks, payouts and reserve |
| BaaS bank partnership | A banking product offered through a fintech's interface/distribution | Bank, fintech, depositor/borrower/user; specific accounts, lending, payments and control |
| Settlement bank | Accounts and the execution of monetary settlement obligations | The payment system participant and its settlement bank; timing, liquidity and availability |

One bank can appear in several rows at once, but that does not make the services interchangeable. In VisaNet Connect–Issuing, a non-member implementation requires a sponsor from among licensed members; production requires additional checks, and the issuer is responsible for transaction decisions and for the KYC of cardholders. This is a specific issuing product, not an instruction for becoming an acquirer. [P04-S020, “Eligibility”, “Next Steps”, “Best Practices and Tips”](https://developer.visa.com/capabilities/visanet-connect-issuing/docs-getting-started)

On the acquiring side, Mastercard leaves liability for the PayFac and its merchants with the acquirer, even when part of the work is delegated. Settlement funds available to the PayFac must be used for payouts to sponsored merchants under the agreements. [P04-S002, §7.6.5.1(2–3)](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-rules.pdf) A partner bank does not sell a universal "compliance umbrella": it sets boundaries, requires evidence and can stop unsupported activity.

In the US, the joint Fed/FDIC/OCC guidance of 2023-06-06 emphasizes that using a third party does not reduce the bank's responsibility. It covers planning, due diligence, contract negotiation, monitoring and termination. This is supervisory guidance, not a new license or a law creating a separate "BaaS" regime. [P04-S019, A; C; footnote 2](https://www.federalreserve.gov/frrs/guidance/interagency-guidance-on-third-party-relationships.htm)

### Why a sponsor is not interested in just any growth

For a bank, additional volume creates revenue, but also operational, compliance and credit obligations. **Residuals** are a contractual share of ongoing revenue from a portfolio, for example an agent's commission after agreed costs. You need to establish the base: gross fees, net revenue or profit after losses. Rates and the right to residuals after termination usually require reading the specific commercial agreement; no market "average price of sponsorship" is claimed here.

**Example.** A PayFac portfolio brings in 100,000 USD in client fees per month. Scheme/processing costs are 75,000; the remainder is 25,000. The sponsor receives 20% of exactly this remainder, that is 5,000. The PayFac keeps 20,000 before its own risk/operations costs. The mistake of taking 20% of 100,000 would overstate the sponsor fee by 15,000. If there is an additional minimum of 6,000 and the agreement specifies **max(6,000; revenue share)**, the sponsor receives 6,000, not 11,000. If the agreement says minimum **plus** share, the arithmetic is different.

BIS WP1163 views the acquirer as both an access provider and a competitor of the sub-acquirer. In the model, the incentives differ: entry into a new niche brings the acquirer additional revenue, while the poaching of its existing merchants can make a high access price worthwhile. This is a useful question for negotiations: do we complement the bank's distribution or compete with it? The model assumes the acquirer's market power, no bypass and a number of cost simplifications; it is not an accusation of collusion against any bank and not an empirical estimate of tariffs. [P04-S018, §§3, 6; PDF pp.9–12, 19–20](https://www.bis.org/publications/working-paper-1163-interchange-fees-access-pricing-and-sub-acquirers-payment-markets.pdf)

### Concentration and real replacement of a partner

A **kill switch**, in the economic sense, is a critical partner's ability to stop what the volume depends on. It can affect new merchants, a particular MCC, new payments, card issuing or payouts; these states must be told apart. Stopping new payments does not erase past refunds, disputes and reserve claims.

A hypothetical PSP earns a contribution of 0.6% on 5 million USD of monthly volume, that is 30,000; fixed costs are 24,000, and profit is 6,000. One sponsor handles 80% of the flow. If its flow stops, the remaining 1 million brings 6,000 of contribution, and the result is minus 18,000 per month. Meanwhile, the 150,000 USD withheld earlier does not automatically become available. A business can be profitable in a normal month and insolvent during the transition.

A backup integration helps only after real approval. In acquiring, a replacement usually requires new underwriting of the portfolio, permitted territories/categories, agreements, settlement details, a check of token availability and reporting. In issuing, you may need agreement on transferring the program, BIN/account ranges or reissuing cards; whether migration is possible is checked separately. This belongs in an exit plan; it is not a guaranteed technical feature.

Before signing an agreement, it is useful to get verifiable answers:

- Which types of transactions and territories are approved; who changes the limits, and how?
- Who collects KYB/KYC, makes the risk decision, stores the evidence and must hand it over during an examination?
- What audit rights do the bank and the scheme have; which requirements must be passed down to subcontractors and merchants, that is, **flow-down obligations**?
- How is inclusion in scheme monitoring programs reported, and who is responsible for remediation?
- How are fees, residuals, reserve and collateral calculated; when are they reviewed and released?
- What are the grounds for restriction/termination, the notice periods and the cure period; which exceptions allow an immediate stop?
- Who handles refunds/disputes after new sales stop; how is data handed over and how are final balances reconciled?

This is the author's checklist for contract analysis. Its logic follows the third-party risk lifecycle: the US guidance separately addresses access to information, audit, responsibilities, default/termination and orderly transition. [P04-S019, C.3, C.5](https://www.federalreserve.gov/frrs/guidance/interagency-guidance-on-third-party-relationships.htm) It does not follow from the checklist that a specific partner must agree to all desirable terms.

### US bank partnership and European passporting

In European **passporting**, an entity uses the authorization of its home-state regulator for certain services in other EU countries, subject to the required notifications. The Central Bank of Ireland describes this route separately for payment institutions and electronic money institutions, including branches, agents and cross-border services. [P04-S021, “Passporting In/Out”, “Cross Border”](https://www.centralbank.ie/regulation/industry-market-sectors/electronic-money-institutions/passporting); [P04-S022, “Cross Border / Freedom of Services”](https://www.centralbank.ie/regulation/industry-market-sectors/payment-institutions/passporting)

The distinction is fundamental: a commercial partnership with a US bank is not an EU PI/EMI passport; a PI/EMI passport is not a bank license, a permission to operate worldwide or automatic card scheme membership. What is confirmed here is the mechanism, based on the Irish regulator's guidance. The full current consolidated PSD2 and national applicability were not independently checked in this chapter because of access limitations; detailed deadlines and exceptions are not asserted.

### A practical question from Reddit

In the public r/fintech thread **“BIN sponsorship vs Payment Facilitator”**, the author **songtu-staygold** first asks about the difference between the models and then clarifies that they mean acquiring. The first reply discusses issuing; the later ones discuss ISOs, PayFacs and contractual liability. This is a good example of how the same word leads to a conversation about different things. The interface that was read shows `4y ago`; the exact day is not established. [P04-S023, original post and the clarification thread](https://www.reddit.com/r/fintech/comments/10kwnbp/bin_sponsorship_vs_payment_facilitator/)

The thread proves that the question exists, not that every comment is right. The generalizations found there about a master MID, "renting a BIN" and how easy it is to obtain the status must not be turned into a rule. The right first answer to a prospective partner: which side of the payment, which scheme, country, product and contractual liability are we discussing?

## Exercises

**1. Sale and risk.** A platform uses an indirect charge with `on_behalf_of` set to the merchant. A colleague claims: "The MoR is the merchant, so the platform never covers its negative balance." Find the mistake and name the documents to check.

**2. Reserve.** Every calendar day the merchant processes 2,000 EUR; rolling reserve 5%, term 60 days; no refunds. What is the balance before the first release? Is it a fee? What happens if the daily volume doubles?

**3. Payout.** For the period: sales 24,000 USD, refunds 1,000, chargeback principal 200, fees 720, new reserve 1,200. The opening available balance is 300. How much should be sent under net settlement? Separately state the new reserve that remains.

**4. Break-even.** A PSP charges 2.8% of volume. Non-overlapping variable costs are 2.35% of volume, fixed costs are 9,000 USD per month. Find the break-even point. What if variable costs become 2.9%?

**5. Low ticket.** Rail A costs 0.8% + 0.20 USD, rail B costs 1.8% with no fixed component. At what ticket size are the fees equal? Name two reasons why this calculation does not determine the final choice.

**6. Crypto and the promise.** Stripe has a stablecoin method. Can you conclude from this and write: "we accept USDT for any merchants worldwide, and an autonomous agent pays without the owner's involvement"? Analyze each part of the sentence.

**7. Unknown payout.** The interface shows `paid`, but the amount is not in the bank statement; the money has not yet been returned to the PSP balance. An employee suggests paying it out again from another bank. What is the correct next step?

**8. Sponsor shutdown.** With a volume of 4 million USD, contribution of 0.5% and fixed costs of 16,000, sponsor A handles 75%. Calculate the normal result and the result after A stops completely. Why does a working API from a second provider not prove that a replacement is ready?

---

## Answers with explanations

**1.** The MoR and the party that covers a negative balance are different questions. In the Stripe Connect documentation that was read, an indirect charge with `on_behalf_of` may leave such coverage with the platform. Check the charge type, the account configuration, the platform/connected-account agreements and the disclosure to the buyer; the promise "never" is unfounded.

**2.** 2,000 × 5% × 60 = **6,000 EUR**. These are tied-up funds, not a fee; the economic expense may be the cost of financing them. If volume doubles permanently, the target rolling balance becomes 12,000, but not instantly: old cohorts of 100 are released while new ones of 200 come in. Without tracking the movement of cohorts, it is easy to get the required capital wrong.

**3.** 300 + 24,000 − 1,000 − 200 − 720 − 1,200 = **21,180 USD** payout. The new reserve of 1,200 remains in a separate balance. Check: 21,180 + 1,200 + 1,000 + 200 + 720 = 24,300 of original funds, including the opening balance.

**4.** The margin is 0.45 percentage points = 0.0045. Break-even = 9,000 / 0.0045 = **2 million USD per month**. With costs of 2.9%, contribution is negative: each additional dollar of volume makes the result worse. Increasing scale does not create a positive break-even point without a change in price or costs.

**5.** 0.008x + 0.20 = 0.018x, so **x = 20 USD**. Below that, B is cheaper on the fee alone; above it, A is. But there are also conversion/approval, losses, refunds, geography/eligibility, fixed costs and the speed of receiving the money. Any two correctly explained reasons are enough.

**6.** USDT is not listed on the page that was read; merchant geography is limited and some regions are in preview; a customer having access from a country is not the same as a business from that country being eligible. The wallet flow requires customer authentication, and this source contains no evidence of an agent's delegated authority. Every part of the universal promise needs other evidence; it cannot be published on the basis of this page.

**7.** Reconcile the original payout: the ID, the bank trace/reference, the date and currency, the reason the money is missing, the external status and the return to the balance. `Paid` may later change to `failed`. A new independent execution before the matter is clarified creates a risk of a double payout; proceeding is acceptable once the outcome has been established, following the rules for recovering the original operation.

**8.** Normally 4,000,000 × 0.5% − 16,000 = **4,000 USD**. 25% of the volume remains, that is 1 million: 5,000 − 16,000 = **−11,000 USD** per month. An API does not prove underwriting of the whole portfolio, limits, agreements, or the portability of data and reserves. Old claims continue to live on separately.

## Summary, connections and gaps

A PSP is chosen based on the combination of role, eligibility, outcome for the buyer, cost, liquidity and the ability to survive a partner shutdown. For a single transaction, the merchant agreement, the data in the payment system, the movements of funds and the liability for refunds must all line up at the same time. Profit is measured after costs and non-overlapping losses; available money, after reserves and delays.

Further reading: [Chapter 3](../03-Visa-and-Mastercard-cards/README.md) — specific scheme rules; [Chapter 5](../05-Wallets-accounts-and-cards/README.md) — accounts, custody and issuing; [Chapter 6](../06-Crypto-and-stablecoins/README.md) — the full crypto→fiat path, FX and treasury; [Chapter 8](../08-Integrations-and-reliability/README.md) — ledger, reconciliation and recovery; [Chapter 9](../09-Payment-project-workshop/README.md) — end-to-end tasks.

**Specific gaps:** private sponsor contracts and real buy rates were not researched; the full PSD2 is not available through the channel used; a specific client's eligibility is not established; the Stripe country-code list/preview contradiction is left open; Triple-A's crypto licenses by country were not checked in registers and are not claimed here; no absolute date was extracted for the Reddit thread; the scope of the independent review is stated in REVIEW.md. Only the cited sections of long documents were read, not the entire body of market rules.

Sources and access limitations: [Sources](Sources.md), [Claims](Claims.md), [RESEARCH_NOTES.md](Research-notes.md). Update product cards before use, and legal conclusions whenever the country, activity, agreement or version of a rule changes.

---

### Sources and fact-check

[Sources](Sources.md) · [Verifiable claims](Claims.md) · [Chapter fact-check](../../Fact-check/04-Payment-providers/README.md)

The text was prepared by agents and passed an independent agent review on 15–17 September 2026. This teaching edition has limitations; dates and limits of applicability are stated in the sources. [Edition record](../../Methodology/Edition-record.md).

<details>
<summary>History and metadata of the original manuscript</summary>

This information describes the research stage before publication. Current visibility is public; the status of the whole edition is `reviewed_with_limitations`. The former labels `private` and `independently_reviewed_draft` are kept only as history.

**Version:** v0.1 · **Status:** `independently_reviewed_draft` · **Cutoff:** 2026-09-15 · **Author:** researcher `part_04_research` · **Language:** Russian · **Visibility:** private. First review: see REVIEW.md (historical or internal material; kept by the owner, outside this copy).

</details>

[← Cards: Visa and Mastercard](../03-Visa-and-Mastercard-cards/README.md) · [Contents](../README.md) · [Wallets, accounts and cards →](../05-Wallets-accounts-and-cards/README.md)
