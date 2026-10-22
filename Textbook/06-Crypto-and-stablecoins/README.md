[← Wallets, accounts and cards](../05-Wallets-accounts-and-cards/README.md) · [Contents](../README.md) · [AI agent payments →](../07-AI-agent-payments/README.md)

<a id="часть-6-crypto-rails-stablecoins-cbdc-платёжный-угол"></a>
# Chapter 6. Crypto and stablecoins

> Blockchain payments, exchange into ordinary money, liquidity and central bank digital currencies.

**8 lessons** · Knowledge cutoff: **15 September 2026** · [Sources](Sources.md) · [Fact-check and limitations](../../Fact-check/Results.md)

## In this chapter

- [6.1 · Digital assets for payments](#module-6-1)
- [6.2 · How a blockchain payment works](#module-6-2)
- [6.3 · Stablecoin settlement services](#module-6-3)
- [6.4 · The buyer pays in crypto, the merchant receives ordinary money](#module-6-4)
- [6.5 · Rules and checks for crypto payments](#module-6-5)
- [6.6 · Myths about crypto payments](#module-6-6)
- [6.7 · Liquidity, FX risk and settlement accounts](#module-6-7)
- [6.8 · Central bank digital currencies: CBDC](#module-6-8)

---

This chapter explains how a digital asset turns into a fulfilled monetary obligation. It treats public networks, issuers, conversion and bank payout as linked but separate mechanisms. This is a teaching study, not a decision to launch a Lab product. All money examples below are synthetic; real routes require checking the specific contract, the licenses, and the accounting and tax treatment.

After reading it, you will be able to draw up a profile of an accepted asset, determine what counts as sufficient proof of payment, distinguish a reserve from available liquidity, and calculate the economics of crypto→fiat and the need for working capital. You will also be able to read a news item about a CBDC and tell whether it describes research, a technical experiment or money that is actually available.

<a id="module-6-1"></a>
<a id="61-активы-для-payments"></a>
## 6.1 Digital assets for payments

### What exactly the merchant receives

The question "do you accept crypto?" cannot be answered with sufficient technical precision. You need to name the asset, the network, the way the asset is identified on that network, and the recipient. A **network** is a system in which participants agree on records. An **asset** is the thing whose quantity is transferred. A **unit of account** is the unit in which the price of the goods and the obligation are measured. Ethereum is a network; ETH is its native asset; USDC is a separate token. The merchant's account, meanwhile, may be denominated in euros. Bitcoin can denote the system, and BTC the asset transferred within it.

For a token on an EVM network, a ticker is not enough: any developer can give their contract a similar name. An acceptance profile must contain the network and chain ID, the address of the verified contract, the number of decimal places, the recipient address, the permitted transfer method and the version of the confirmation rules. For other architectures the identifier may be a mint or another network object. The wallet address answers the question "where", the contract answers "what", and the network answers "in which ledger". The same address string on two networks does not create a single balance. These distinctions are needed before the payment form is shown, not only when an error is being investigated.

**Stablecoin** is the name of a class of assets that aim to maintain a relatively stable price. It does not define a single legal structure. USDC and USDT have different issuers, contracts, reserve compositions and terms of direct redemption. In an algorithmic project, maintaining the price may rely on exchange into another market token. BTC and ETH have no issuer promise to redeem each token for a fixed number of dollars. Consequently, accepting "100 units" of each of these assets creates different risks.

In the EU, the category **e-money token, EMT** is defined by reference to a single official currency; MiCA separately regulates public offers and issuers. This is a territorial legal classification, not a property of all tokens priced around one dollar. [MiCA, Art. 3(1)(7)](https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/mica/article-3-definitions), [Art. 48](https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/mica/article-48-requirements-offer-public-or) [P06-C001]. Singapore's MAS announced its own framework for certain single-currency stablecoins in August 2023. That announcement by itself does not prove that an arbitrary token has already been recognized as MAS-regulated or that all provisions have entered into force. [MAS primary release](https://www.sgpc.gov.sg/api/file/getfile/Media%20Release_MAS%20Finalises%20Stablecoin%20Regulatory%20Framework.pdf?path=/sgpcmedia/media_releases/mas/press_release/P-20230815-2/attachment/Media+Release_MAS+Finalises+Stablecoin+Regulatory+Framework.pdf) [P06-C002].

### The promise, the market price and the ability to use the promise

It helps to break a stablecoin's stability down into three questions. Are the issuer's assets sufficient? Can money be obtained from them in time? Can this particular holder apply for redemption? A positive answer to the first question does not replace the others. In particular, the USDC Terms for holders outside the EEA distinguish between a token owner and a Circle Mint customer; direct redemption depends on admission to the relevant account. A separate policy applies in the EEA, including a procedure for retail holders. [Circle USDC Terms](https://www.circle.com/legal/usdc-terms), [MiCA Redemption Policy](https://www.circle.com/legal/mica-redemption-policy) [P06-C003; P06-C004]. For the EEA policy, a re-read on 2026-09-17 shows the version of 2026-09-15; the author's original record of 2026-07-13 is not backed by an archived copy. Differences between the versions have not been established.

A synthetic example: a merchant listed goods at 100 USD and agreed to accept 100 tokens at a fixed quote. When the payment arrives, the market values the token at 0.97 USD. An immediate sale will bring 97 USD before fees. The loss relative to the promised price is 3 USD. If instead the contract recalculates the price before payment, the customer will need `100 / 0.97 = 103.092783505…` tokens before rounding and costs. If, under the terms of the example, the amount is rounded up to six decimal places so as not to underpay, the amount sent will be 103.092784 tokens; costs are accounted for separately. These are two different products: in the first, the accepting side temporarily bears the exchange-rate risk; in the second, the payer does. The word "stable" does not choose between them.

A **depeg** is a deviation of the market price from the target peg. It can arise from doubts about reserves, closed access to redemption, a lack of exchange liquidity or technical fragmentation. **Freeze/blacklist** is a restriction on the circulation of specific tokens or addresses under the rules of the administered contract and the issuer. The existence of a blockchain record during a freeze does not mean the asset can be transferred or exchanged. Circle describes the relevant restrictions in its terms; this is a risk separate from changes in the market rate. [USDC Terms, §§13–17](https://www.circle.com/legal/usdc-terms) [P06-C005].

For an algorithmic structure, imagine a rule: one settlement coin may be exchanged for market tokens worth one dollar. If that second token costs 10 USD, issuing ten of its units makes it formally possible to redeem 100 settlement coins. At a price of 1 USD, a hundred units are needed. Selling the additional issuance can push the price down and require even more issuance. This is an explanation of a possible feedback loop, not a model of all algorithmic projects and not a reconstruction of a specific Terra transaction. A promise of exchange into an endogenous asset cannot be counted as an external dollar reserve.

### Native and bridged: where an additional claim appears

A **native stablecoin** is issued by the issuer directly on a supported network. A **bridged token** usually represents an asset locked on another network. The bridge takes in the original tokens and issues a representation on the target side; the way back requires the bridge to work correctly and the collateral to be unlockable. The user ends up dependent both on the issuer of the original asset and on the design of the bridge.

Circle explicitly separates third-party bridged USDC from its own obligation: a wrapper does not become Circle-issued USDC merely because of a similar name. The fact that some services can first perform an unbridge and then a redemption does not remove the two stages. [Bridged USDC Terms, §§1–2](https://www.circle.com/legal/bridged-usdc-terms) [P06-C006]. Synthetically, 1,000 units of the wrapper may remain in a wallet while withdrawal of 1,000 original USDC is temporarily unavailable. This is an availability shortfall, even if the original issuer's reserve is fully sufficient.

Roles differ too. The issuer creates the token and defines the redemption obligation; a distributor provides access or secondary exchange; a merchant acceptor accepts payment for its own goods. If the latter starts holding customers' assets and transferring them to third parties, the description of its activity changes. Calling an interface a "checkout" does not set the boundaries of liability.

<a id="module-6-2"></a>
<a id="62-on-chain-payment-mechanics"></a>
## 6.2 How a blockchain payment works

### From invoice to proof

A crypto payment starts with an invoice: the order identifier, price, asset, network, address, quote validity period and rules for recognizing the payment. A **memo/tag** is an additional identifier used when the chosen route relies on a shared address and needs to tell recipients apart. It must not be added or ignored out of habit: it is a requirement of a specific network and service. A single permanent address not tied to an order is convenient for a demo, but does a poor job of explaining which of several identical transfers paid for which purchase.

An invoice protocol carries structured payment data. For example, ERC-681 describes a URI for an address, chain ID, function and parameters, suitable for a QR code. The standard has Final status and was created on 1 August 2017, but implementation by a particular wallet is checked separately. The request fields can be edited by the user; a QR code by itself does not authenticate the merchant and is not a receipt. [ERC-681, Syntax and Security Considerations](https://eips.ethereum.org/EIPS/eip-681) [P06-C007].

In a synthetic invoice, the token has six decimal places. The amount 27.35 corresponds to the integer value of 27,350,000 minimal units. Comparing the strings `27.35` and `27.350000` should yield equality, and rounding through binary floating-point arithmetic is out of place here. The network fee, gas, is usually paid separately through a designated route. Holding 27.35 tokens does not prove there are resources to send them. When gas is paid by a service or a sponsorship mechanism, the payer of the fee changes, but the cost does not disappear.

A payment **watcher** matches the network result to the invoice. For a token, it checks the expected network, contract, recipient, the amount actually transferred and successful execution. A contract call that ended in an error can spend gas without transferring the token. A hash identifies an attempt but does not by itself report its outcome. For a batch transaction, one hash is not enough: it helps to link the order to a specific transfer or event inside it. These are design rules for reconciliation, not a universal format for all networks.

### Several clocks, several kinds of finality

The `observed` state means the system has seen the transaction. `confirmed` should be defined per network: for example, inclusion in a block at a chosen depth. `finalized` indicates that the network's finality criterion has been reached. In Bitcoin, confirmation depth reduces the risk of a reorganization, but waiting for a fixed number of blocks is not a guarantee of timing or that history cannot be undone. The Bitcoin guide discusses the choice of confirmations and the price validity period separately. [Bitcoin Developer Guide, Payment Processing](https://developer.bitcoin.org/devguide/payment_processing.html) [P06-C008].

In Ethereum PoS, finality relies on validator votes and checkpoints: this is a different design from a simple count of subsequent blocks. It rests on assumptions about consensus and the behavior of shares of stake. [Ethereum, Gasper: What is finality?](https://ethereum.org/developers/docs/consensus-mechanisms/pos/gasper/) [P06-C009]. Consequently, a "six confirmations for everything" setting should not be carried over mindlessly between networks.

An L2 adds yet another scale. The Base documentation distinguishes a fast preliminary confirmation, an L2 block, publication of the batch to L1, and finality of that batch. The stated benchmarks are roughly 200 ms, 2 seconds, 2 minutes and 20 minutes respectively; these are estimates for the stages, not a contractual deadline under any load. The seven-day wait applies to canonical withdrawal to Ethereum, not to all transfers within Base. [Base, Transaction Finality](https://docs.base.org/specifications/transactions/transaction-finality) [P06-C010].

This leads to an important product decision: when should the goods be released? Cheap digital goods and expensive irreversible fulfillment can have different risk thresholds. Early fulfillment means the merchant accepts credit or network risk. It does not turn a preliminary confirmation into a stronger technical fact. The times of the order, inclusion, reaching the chosen finality, crediting to the internal ledger and release of the goods must be stored separately.

### Uncertainty and recovery

Imagine a payment of 90 USDC. The RPC, that is, the interface for accessing a network node, stopped responding after the payment was sent. The user clicked again, and later the watcher found two successful transfers of 90 each. If these are two independent transactions, economically 180 USDC has been received for one order. The second 90 is an overpayment and a separate obligation to refund or settle. Two notifications about the same transfer, by contrast, do not create two receipts. The uniqueness of the network operation and the idempotency of the internal credit help tell these cases apart.

When the outcome is unknown, the system first looks for the original operation using the stored identifiers and network data. It must not create another outgoing operation just because an HTTP timeout expired. During a reorganization, a previously observed record can disappear or change position. The network evidence is then updated, but goods already released do not disappear: the resulting risk is recorded as a separate incident with its accounting consequence.

Dependencies are best described by point of failure. An RPC can give an incomplete picture while the network is working. A sequencer can delay new L2 transactions. A bridge can fail to deliver a cross-chain message. An issuer can restrict a token. A provider can fail to credit a supported asset sent without the required memo. Resending does not automatically fix any of these cases. A practical runbook records the original request, the identifiers, the expected asset, the confirmed stages and the next person responsible.

A refund is a new operation with a verified destination. You cannot assume that the sender's address is always a safe refund address: it may be an exchange's shared hot wallet. The Bitcoin guide separately discusses obtaining a refund address. [Payment Processing, Refunds](https://developer.bitcoin.org/devguide/payment_processing.html) [P06-C011].

<a id="module-6-3"></a>
<a id="63-stablecoin-settlement-services"></a>
## 6.3 Stablecoin settlement services

### What a settlement partner sells

A settlement service provider, SSP, is a functional description of a settlement intermediary, not a single worldwide license. One partner provides institutional deposits and withdrawals, another provides liquidity, a third handles bank payouts, and a fourth connects all of this with an API. For the client, it is important to identify the legal entity that accepts the asset, becomes the debtor, fixes the rate and is liable for a payout that is not received.

In a **mint**, the issuer receives the funding provided for by the contract and issues tokens. In a **redeem**, tokens accepted for redemption are withdrawn from circulation under the relevant procedure, and the holder receives payment in fiat. In a simple synthetic scheme, the issuer's receipt of 10,000 USD is accompanied by the issuance of 10,000 tokens and a corresponding obligation. The composition of the reserve may then change under the permitted policy; a token is not an individual tag on a specific banknote or bank balance.

Buying 10,000 existing tokens on an exchange from another holder does not require new issuance. The seller receives the buyer's money; the issuer's obligation on the tokens in circulation does not increase by itself. **Secondary liquidity**, the ability to sell an existing asset on the market, differs from **primary redemption**, direct redemption with the issuer. The former may work at night or for small amounts, but at the market price and with counterparty risk. The latter has contractual admission conditions and its own fulfillment process.

### Access to redemption must be read literally

Under the non-EEA USDC Terms, holding a token is not equivalent to having an open and active Circle Mint account. For the EEA, Circle France publishes a separate path: retail holders use a form, non-retail holders use Mint redemption-only; identification, checks and a bank IBAN in the EEA are required. Therefore two universal formulas are equally wrong: "any wallet immediately gets a dollar from Circle" and "a retail holder can never apply to the issuer". [USDC Terms, §§1–4](https://www.circle.com/legal/usdc-terms), [MiCA Redemption Policy, §§1–3](https://www.circle.com/legal/mica-redemption-policy) [P06-C003; P06-C004].

Tether's Relevant Information Document of 20 February 2026 describes the direct primary market as open to verified customers. It states a minimum direct redemption of 100,000 USD and a fee equal to the greater of 1,000 USD and 0.1%. Therefore a synthetic redemption of exactly 100,000 USD yields 99,000 USD before other applicable costs: the minimum fee here equals 1%, not 0.1%. This is not the rate of any exchange service and not the fee on every USDT transfer. [Tether, Relevant Information Document, pp. 13–15](https://tether.to/public/Relevant_Information_Document_-_Tether_International,_S.A._de_C.V..pdf) [P06-C012].

### What a reserve report confirms

A reserve report should be read in this order: the entity examined, the measurement dates, the criteria, the composition of assets, the liabilities, the exclusions and the examiner's opinion. The July USDC report, signed on 27 August 2026, concerns an assertion about reserves and circulation on two July dates. It is useful evidence within the stated limits, not a check of every future moment. [USDC Examination Report, July 2026, pp. 1–5](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/USDCAttestationReports/2026/2026%20USDC_Examination%20Report%20July%2026%20(1).pdf) [P06-C013].

The BDO report on Tether as at 30 June 2026 is a reasonable assurance report on a specific financial statement and criteria. It explicitly distinguishes the subject of the examination from complete financial statements and contains limitations regarding notes and going concern. The assets listed include not only cash and Treasury instruments but also other categories, including gold, BTC and secured loans. They cannot be relabeled as "all dollars in a bank account". [BDO, Independent Auditor’s Report, pp. 1–3; Financial Figures and Reserves](https://assets.ctfassets.net/vyse88cgwfbl/2kYf7r64h3tzwiu6F0CbUB/2997abd2f11ecea74a21528048b50707/Opinion___Report_-_Tether_International_Financial_Figure_30-06-2026.pdf) [P06-C014].

**Attestation/examination** and **audit** cannot be told apart merely by how prestigious the word sounds. You need to find out what information was checked and what conclusion was given. A reserve report is not the same as an audit of the whole company, deposit insurance, a liquidity guarantee or an opinion on the order in which claims are satisfied in bankruptcy. The latter requires the applicable law, the contract, the ownership structure and the limits on creditors' claims. Even a good short-term government instrument has to be sold or held until it settles; cash held with a custodian requires access to that custodian.

The study by Ahmed, Aldasoro and Duley links information disclosure to the risk of a run on a stablecoin. The authors use a theoretical coordination model and empirical comparisons of episodes with counterfactual prices. The conclusion does not boil down to "transparency always saves the day": the reaction depends on prior beliefs about the reserve and on the signal received. The small number of episodes and the assumptions behind the control scenario limit how far the findings carry over to any given token. [BIS Working Paper 1164, version of 2025-01-31, §§2–5](https://www.bis.org/publications/working-paper-1164-public-information-and-stablecoin-runs.pdf) [P06-C015].

### Cross-chain service and corporate treasury

Circle CCTP V2 moves native USDC by burning it on the source side, confirming the message off-chain and minting on the target side. This differs from holding a locked token behind a wrapper. However, dependencies on the networks, the contracts and Circle's attestation service remain. Here the word attestation means confirmation of a cross-chain message, not an accounting report on reserves. [CCTP Technical Guide](https://developers.circle.com/cctp/references/technical-guide) [P06-C016].

A corporate treasury function can accept a delay in a large redemption, manage several counterparties and hold fiat in advance. A consumer checkout must also link payments to orders, show the deadline, handle overpayments and disputes, refund money and ensure delivery. Therefore an API for transfers between corporate accounts is not a ready-made checkout. When choosing a partner, compare the full chain of obligations, not just the promise of a low network fee.

<a id="module-6-4"></a>
<a id="64-cryptofiat-для-мерчанта-платежный-проект"></a>
## 6.4 The buyer pays in crypto, the merchant receives ordinary money

### How money travels along the route

In the basic version, the buyer transfers a permitted asset, the provider converts it, and the merchant receives fiat. This is the economic route **accept → convert → settle fiat**. It requires several contracts and states. Who is the seller of the goods? To whom does the buyer discharge the monetary obligation? Who buys the tokens received? At what stage does a fixed debt to the merchant arise? Whose account holds the money before the payout? The answers determine what the product actually promises.

A software agent may act on behalf of the buyer, a business or the merchant. An API call by itself does not create a new regulated principal and does not prove authority to dispose of money. In the payment record, it is useful to separate the `acting_agent`, the legal client, the payer, the merchant of record and the payout recipient. If one person pays and another receives the goods, this must be consistent with the contract and the checks, not hidden behind a wallet identifier.

Provider documentation shows both the real capabilities and the limits of portability. As of the reading date, Stripe describes stablecoin payments credited to the Stripe balance in local currency and lists the supported assets and networks. Access outside the main geography includes a private preview; a country's presence on the page does not prove availability for a particular account. Limitations are stated, including the absence of manual capture and card chargebacks. [Stripe, Stablecoin Payments](https://docs.stripe.com/payments/stablecoin-payments) [P06-C017]. From this, one cannot infer that accepting all stablecoins is universally lawful for any Lab company.

For a specific route, you need to build a matrix: the provider's legal entity, the client's country, the merchant's country, the purpose of payment, the permitted asset/network, the bank recipient, limits, contractual liability and the time to completion. Technical support for a token answers only one column. It is checked separately whose services are provided to the end customer and whether the chosen model allows accepting funds on behalf of other merchants.

### A quote has a beginning and an end

A synthetic checkout offers to pay 100 USDC for goods priced at 90 EUR. The quote is valid for two minutes and guarantees the merchant 90 EUR gross after proper payment. The provider's fee is 2% of that amount, that is, 1.80 EUR, and the payout costs another 0.20 EUR. The merchant is owed 88 EUR net. The payer's screen shows 100 USDC, the order shows 90 EUR, and the obligation after fees is 88 EUR: these numbers are consistent but denote different quantities.

If a transaction is first detected after the quote has expired, what happens depends on a condition published in advance: the decisive moment may be the time of sending, of inclusion in a block or of reaching the chosen threshold. There must be a reliable way to verify exactly that moment. A rate favorable to the operator may not be chosen retroactively. A late payment may become a request for recalculation or refund, not automatically a new fulfilled order.

Before the price is fixed, the provider can usually pass a market move on into the next quote. Once the obligation is fixed, the risk already sits somewhere: with the provider, its liquidity provider or, under the contract, the merchant. The term rate lock means a contractual price promise on certain conditions, not the fact that hedging has been carried out. The internal calculation must keep the original quote, the time of acceptance, the actual sale of the asset and the difference.

### From the internal balance to the recipient's account

Bridge, for example, distinguishes `awaiting_funds`, `funds_received`, `payment_submitted`, `payment_processed`, as well as refund and error states. For a submitted operation, the hash may be preliminary. In your own system, these statuses must be mapped to the contract and to evidence of final crediting; their names cannot be mechanically declared to mean finality on all bank rails. [Bridge, Transfer States](https://apidocs.bridge.xyz/platform/orchestration/transfers/transfer-states) [P06-C018].

In practice, there are both payouts with a calendar and cutoff and round-the-clock bank routes. Bridge documentation gives a cutoff of 16:45 ET for USD wire; ACH next-day assumes business days. At the same time, FedNow is described as a 24/7 beta by invitation, and SEPA Instant depends on support from the recipient's bank and may fall back to ordinary SCT. Therefore a timing promise is built for a combination of rail, bank, currency and access, not for an abstract "fiat". [Bridge, Cutoffs](https://apidocs.bridge.xyz/platform/orchestration/more/cutoffs) [P06-C019].

If the provider has credited the merchant's internal balance, the merchant may have a claim against the provider. That is not necessarily the merchant's money in a bank yet. If the sender's bank has accepted a payment order, that is not necessarily an entry on the recipient's statement yet. And even a received statement does not confirm that the customer received the ordered goods. The chain needs its own evidence at each step: invoice, network transfer, ledger credit, conversion, payout and fulfillment.

### Refund after conversion

Suppose the goods from the previous example are canceled and the 100 USDC have already been sold. First establish the size of the refund obligation: 100 USDC, 90 EUR, or the value of 90 EUR in tokens at the new rate. At a new price of 1 USDC = 0.88 EUR, refunding a fixed 100 USDC is equivalent to 88 EUR, while refunding the value of 90 EUR requires `90 / 0.88 = 102.27272727… USDC`. If in this teaching example the amount is rounded up to six decimal places so as not to underpay, the result is 102.272728 USDC. Added to this are the costs of buying back, network costs and the possible non-refundability of the original fee. The basis must be chosen in the product terms, taking applicable law into account, not after a loss has occurred.

Stripe describes its own refund in stablecoins to the original wallet. This is the rule of a specific service; an independent operator must check whether a refund to a specific destination is possible, especially if the original transfer was sent by a custodian. [Stripe, Refunds](https://docs.stripe.com/payments/stablecoin-payments) [P06-C020]. The absence of a card chargeback does not remove the buyer's claims under contract and law. It changes the recovery mechanism and the distribution of the operational burden.

The accounting map of questions includes the moment revenue for the goods is recognized, the moment the intermediary's obligation arises, the classification of the token received, the functional currency, the measurement of exchange differences, the fee, the tax document and the refund. Accounting may differ for a merchant of record and for an agent accepting money on behalf of another merchant. Neither an address nor a hash replaces the basis of the transaction, the counterparty and the purpose of payment. §6.7 works through the operational ledger of one explicitly defined variant; it does not prescribe universal financial reporting.

<a id="module-6-5"></a>
<a id="65-compliance-на-crypto-rails"></a>
## 6.5 Rules and checks for crypto payments

### What is regulated is the activity, not the app's name

**VASP**, virtual asset service provider, is the FATF term for covered services involving virtual assets. The FATF sets international standards and guidance; specific obligations arise from national implementation. The guidance explicitly describes itself as non-binding and does not override the powers of national authorities. [FATF Guidance 2021, ¶25–26](https://www.fatf-gafi.org/content/dam/fatf-gafi/guidance/Updated-Guidance-VA-VASP.pdf.coredownload.inline.pdf) [P06-C021]. Therefore "we comply with FATF" is not the name of a license and does not give global permission to operate.

In the EU, a **CASP**, crypto-asset service provider, is defined by MiCA through the professional provision of services to clients. The list includes custody and control of the means of access, exchange, execution and transmission of orders, and transfers on behalf of clients. Article 59 provides for CASP authorization or a statutory route for certain financial entities. The authorization specifies the permitted services; extending the list requires a separate procedure. [MiCA, Art. 3(1)(15–26)](https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/mica/article-3-definitions), [Art. 59](https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/mica/article-59-authorisation) [P06-C022].

Consider two synthetic businesses. Company A sells its own subscription and receives tokens as payment. Company B holds the balances of a hundred merchants, exchanges their assets and remits money to recipients. Having the same checkout button does not make their activities the same. For B, custody, transfer and exchange must be analyzed separately, and for both, the applicable payment, tax and consumer rules. The first description does not automatically imply an exemption from all requirements; from the second, a specific license cannot be chosen without the jurisdiction and the contracts.

The analysis starts with a map of authority: who can sign a transfer, change the recipient, delay a refund, set the rate and use liquidity. If a technical contractor controls the keys or in fact disposes of the funds, a contractual label of "software only" does not settle the question. If an agent merely prepares a request, that does not yet mean it is a financial intermediary. The actual functions need to be examined.

The official summary of the FATF update of 16 July 2026 notes persistent gaps in the practical implementation of licensing, registration and supervision. This is an additional reason to distinguish a framework on paper from its enforcement. The full report of this update was not read here; only the limited conclusion of the published summary is used. [FATF, Seventh Targeted Update](https://www.fatf-gafi.org/en/publications/Fatfrecommendations/targeted-updated-virtualassets-vasps-2026.html) [P06-C043].

### The Travel Rule and address screening solve different problems

The **Travel Rule** concerns the transmission of required information about the sender and the recipient between obligated participants. This information can be transmitted over a separate secure channel and does not have to be placed on a public blockchain. The FATF guidance also covers transfers involving unhosted wallets: the absence of a second VASP does not remove the obligation of the serving VASP to collect the necessary information. Specific thresholds, checks and prohibitions are set by the applicable rules. [FATF Guidance, ¶177–193](https://www.fatf-gafi.org/content/dam/fatf-gafi/guidance/Updated-Guidance-VA-VASP.pdf.coredownload.inline.pdf) [P06-C023].

Imagine a transfer of 2,000 tokens from an exchange customer to a merchant. On the network, the addresses, the amount and the contract are visible. The Travel Rule message may contain the necessary identifying information. The merchant ledger holds the order and the basis for payment. These three data sets are linked through protected identifiers but are not merged into a public profile of the buyer. If the message is delayed, the network may already have completed the transfer while the provider's credit awaits review. This is the state `funds_received / compliance_pending`, not proof that money was lost or that the customer broke the law.

Sanctions screening looks for risks relevant to the applicable regime. OFAC stresses that published crypto addresses help identify sanctioned persons but do not exhaust the associated addresses; customer and geographic data are also used. This guidance relates to the US sanctions context, not automatically to all participants worldwide. [OFAC Guidance, printed pp. 15–17](https://ofac.treasury.gov/media/913571/download?inline=) [P06-C024].

**Chain analytics** infers connections from observed history and additional labels. An address is not a person; a shared exchange serves many customers; a contact in the graph does not determine the legal characterization. Therefore risk scoring requires versioned sources, a clear basis for each flag and a review procedure. Synthetically, a payment may get a high score because of a link to a shared service; this is a reason to check the origin and nature of the transaction, not to publicly declare the buyer guilty. A refund is checked too: automatically moving frozen funds to a new address may create a new violation. The decision is documented by a responsible person; switching networks does not fix a compliance problem.

<a id="module-6-6"></a>
<a id="66-myths-to-kill"></a>
## 6.6 Myths about crypto payments

### Five false shortcuts

**"Stablecoin = e-money everywhere."** The legal regime is tied to the activity, the entity and the territory. Even in the EU, one must distinguish the definition of an EMT, the issuer's authorization and compliance with the offer rules. Article 49 of MiCA establishes the holder's claim against the issuer and redemption at par; this is not a statement about the price in every exchange trade. [MiCA, Art. 49](https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/mica/article-49-issuance-and-redeemability-e) [P06-C025].

**"On-chain receipt = chargeback."** A receipt confirms a specific network result. A chargeback in a card system is a dispute procedure with its own participants and rules. The recipient can make a new refund transaction, but it does not erase the original transfer. Proof of payment also does not prove delivery of the goods and does not deprive the buyer of contractual rights. The confusion is especially dangerous when an agent takes the word `success` as universal permission to close the order.

**"One license = the world."** An authorization has a legal entity, a territory and services. Even within one regime, permission for one function is not the same as permission for the others. Outside that regime, there are other requirements, banks and customer restrictions. Being able to sign up on a website, a public product name and the existence of an API are no substitute for this check.

**"CBDC = USDT from the state."** A CBDC has a fundamentally different debtor: the central bank. A private issuer's token is governed by that issuer's legal and reserve structure. A CBDC does not have to use a public network, interoperate freely with any wallet or allow cross-border transactions without rules. The detailed breakdown is in §6.8.

**"Large on-chain volume proves mass payment for goods."** One economic payment may be accompanied by transfers between wallets, exchanges and networks. Synthetically, a purchase of 100 units, followed by a transfer to treasury and a rebalancing of another 100 each, produces three network movements totaling 300 units, although there is only one sale to a buyer. This is the author's methodological counterexample: a single gross indicator is not enough to establish the volume of purchases; you need to determine the economic purpose of the movements and exclude double counting. The example does not measure the real share of commerce on any network. [P06-C026].

Proving adoption requires a definition of use, a method for removing internal movements, the number of independent payers and merchants, repeat purchases and a link to real orders. Even cleaned-up volume remains a measurement under a chosen methodology. A survey of holders answers a different question than on-chain analysis; neither by itself proves product demand for Lab.

### How to check a promise

The claim "we paid the supplier in a second" should be unpacked: within that second, was the transaction signed, a preliminary confirmation received, the internal balance credited, fiat delivered or the order fulfilled? A synthetic status report can honestly say: "100 USDC finalized; conversion completed; 90 EUR payout submitted; bank credit not yet confirmed". Such a report is already useful and does not need the word "all".

Public complaints are useful as a source of product questions: the wrong network, an unclear refund, a stuck credit. During the research, relevant Reddit threads were found, but their full pages could not be read, and a search of X did not yield a verifiable, substantive case. Therefore neither provider fault nor the outcome of recovery is asserted here on the basis of these fragments. The links and access limits are kept in the [research notes](Research-notes.md).

<a id="module-6-7"></a>
<a id="67-treasury--fx--nostro-на-cryptofiat-ops"></a>
## 6.7 Liquidity, FX risk and settlement accounts

### Why a positive total balance is not enough

**Treasury** manages available money, timing, currencies and counterparty risk. A single aggregate figure such as "we have 50,000 dollars in assets" does not answer whether 8,000 EUR can be paid to a specific recipient today. Some assets may be in tokens, some in another legal entity's account, some in an unfinished transfer, and some with a partner that limits withdrawals. They cannot automatically be netted against each other.

A minimal liquidity map has these dimensions: legal entity, owner of the funds, currency/asset, location, availability, restriction on use, expected time and counterparty. Own funds and client obligations are tracked separately. USDC in one wallet, native USDC on another network and bridged USDC are different operational positions, even if the report values all of them in USD. Moving between them takes time, fees and access to the route.

**Nostro** is our account with another bank, from the point of view of the bank that owns it; **vostro** is another bank's account with us, from the point of view of the servicing bank. These are two views of the corresponding correspondent relationship. Correspondent settlement requires both accounts and message exchange. [CPMI, Correspondent Banking, §2.1 and Annex 2](https://www.bis.org/publications/correspondent-banking-final-report.pdf) [P06-C038]. Not every balance in an API is a nostro: for a non-bank operator, it may be its own bank account, a safeguarded client account, a contractual claim against a provider or merely an informational limit. Calling all these positions "cash" means losing the information about who owes the money and how to obtain payment.

### A fully numerical daily cycle

The following example is a **synthetic operating model of a principal provider P**. P acquires tokens from the payer and takes on an obligation to pay euros to a separate merchant M. All accounts belong to P; client safeguarding is not assumed in this model. For the demonstration, the functional currency is USD and a constant accounting valuation of 1 EUR = 1.10 USD is used. This is a notional subledger, not a recommendation on recognizing assets under IFRS or local standards.

At the start of the day, P has:

| Position | Balance in original units | Value in USD |
|---|---:|---:|
| Own USD bank account | 20,000 USD | 20,000.00 |
| Own EUR account for payouts | 5,000 EUR | 5,500.00 |
| Gas resource, notional fixed valuation | — | 100.00 |
| Tokens and debt to the merchant | 0 | 0.00 |
| Total assets and opening capital | — | **25,600.00** |

P issues a quote: the buyer transfers 10,000 USDC, and merchant gross is 9,000 EUR. The offered rate is 0.90 EUR per USDC. P's fee is 1% of merchant gross, that is, 90 EUR; M will receive 8,910 EUR. This is a fee explicitly agreed with the merchant, not a hidden difference in the price of the goods.

At 09:00, P recognizes proper receipt of 10,000 USDC. In the notional ledger, the tokens received are recorded at 10,000 USD, and the gross payable to the merchant at 9,900 USD. The difference of 100 USD is the quote margin. Withholding the fee reduces the payable by 90 EUR, or 99 USD, and creates fee income. Thus the debt to M is 8,910 EUR, valued at 9,801 USD. The market valuation of tokens and the revenue recognition rules in real financial reporting require separate analysis; here, subsequent prices are given explicitly.

At 09:05, P sells the tokens and receives **9,990 USD net**: the cost of the sale relative to 10,000 USD is 10 USD. At 09:10, it buys 9,000 EUR at 1.10 USD per EUR, spending 9,900 USD. The purchase must actually be executed and become available in the right account. The mere existence of an FX quote does not confirm this. After the euros are confirmed as credited, P pays M 8,910 EUR; a separate bank fee is 2 EUR. Network operations used 4 USD of the gas resource.

The operational journal entries show P's perspective:

| Event | Debit | Credit |
|---|---|---|
| Receipt of tokens | Token inventory 10,000 USD | Merchant gross payable 9,900 USD; quote margin 100 USD |
| Withholding of merchant fee | Merchant payable 99 USD | Fee income 99 USD |
| Sale of tokens | USD bank 9,990 USD; conversion expense 10 USD | Token inventory 10,000 USD |
| Purchase of euros | EUR bank 9,000 EUR = 9,900 USD | USD bank 9,900 USD |
| Payout to M | Merchant payable 8,910 EUR = 9,801 USD | EUR bank 8,910 EUR |
| Payout fee | Expense 2.20 USD | EUR bank 2 EUR |
| Gas | Expense 4 USD | Gas asset 4 USD |

Let us check the closing balances: USD bank = 20,000 + 9,990 − 9,900 = **20,090 USD**. EUR bank = 5,000 + 9,000 − 8,910 − 2 = **5,088 EUR**, or 5,596.80 USD. Gas = **96 USD**. Tokens and payables are zero. Assets: 20,090 + 5,596.80 + 96 = **25,782.80 USD**.

The economics match the change in capital: quote margin 100 + merchant fee 99 − sale 10 − payout 2.20 − gas 4 = **182.80 USD of profit**. The growth in assets relative to the start of the day is also 182.80 USD. The EUR balance grew by 88 EUR, but that is not the whole profit: another 90 USD remained in the dollar account, and 4 USD went on gas. Mixing currencies hides this connection.

### The same deal can miss the deadline

Now M demands the payout at 09:02, while the purchased euros will become available only at 09:10. The payout and fee require 8,912 EUR. The account holds 5,000 EUR. **The intraday gap is 3,912 EUR**, even though the deal is profitable and the tokens have already been received. Possible solutions are to pre-position euros, secure a confirmed credit line, change the promised timing or stop accepting the relevant orders. An unfinished conversion does not substitute for the actual balance.

Additional prefunding of 4,000 EUR covers this gap under the given conditions. Moving one's own money between accounts is not in itself an expense. But capital has a cost and a risk of being locked up. At a notional rate of 12% per year and three days of placement, the cost of 4,000 × 1.10 × 12% × 3 / 365 is about **4.34 USD**. This is a modeled cost of funding, not any provider's tariff. If the prefunding sits with an intermediary, the claim against it and the ability to get the balance back are assessed separately.

**Just-in-time convert** reduces the fiat pre-positioned in advance but increases dependence on current market availability and bank crediting. **Prefunding** improves execution but ties up capital. For a bank or provider with a round-the-clock rail, the delay may be small; another route has a cutoff. You cannot substitute generic "weekends" for the calendar of the chosen payout. Confirmed examples of these differences are given in §6.4.

### Exchange-rate and counterparty stress

Suppose the obligation of 8,910 EUR is already fixed, but instead of 9,990 USD the token sale brings **9,500 USD net** because of a depeg and liquidity. All other conditions stay the same. The loss relative to the base case is 490 USD; the profit becomes **−307.20 USD**. The formal nominal value of 10,000 USDC does not pay for the resulting shortfall.

In another scenario, the tokens are sold as in the base case, but euros can be bought only at 1.12 USD. Buying 9,000 EUR costs 10,080 USD, which is 180 USD more. With the other base-case costs, the operating result of the deal in this model is **2.80 USD**. If both deteriorations happen at once, the result is **−487.20 USD**. This is a comparison of cash flows; the revaluation of other currency balances at a changed reporting rate would be calculated separately.

Slippage is the difference between the expected and the actual execution price. It must be measured on a single basis: time, rate source, volume, available depth, fees and net proceeds. An indicative mid-market rate without available volume is not an executable quote. A hedge, for example an FX deal agreed in advance, can reduce one risk but adds a counterparty, settlement timelines, possible collateral requirements and basis risk. This is a map of questions, not instructions for a trading desk.

When a partner fails, the asset does not necessarily disappear, but it becomes an inaccessible claim. If 9,000 EUR are stuck with an intermediary, they cannot be counted in the cash forecast as immediately available for M. Forced urgent replacement of liquidity costs money; a repeat payout while the outcome of the original one is unclear creates a risk of duplication. First the same operation is reconciled, then the approved recovery scenario is applied.

### Daily control and closing a route

Before the day starts, treasury reconciles the available balances for each legal entity and currency, unfinished operations, bank and counterparty limits, the calendar and expected payouts. During the day, the total unhedged position is limited, as is the money held with any one provider. At the end, invoices, network records, internal journal entries, conversion confirmations and bank statements are matched. Gas, spread and payout fee must not dissolve into a single "fee" line.

The control balance is built as opening + confirmed receipts − confirmed outflows = closing. A separate table explains pending items, blocked funds, the refund reserve and discrepancies. The halt threshold may take into account a depeg, a statement mismatch, unavailability of a key rail or a breach of a counterparty limit. A **break-glass halt** in such a system means a predefined stop to new quotes and new risk-taking, with a responsible owner, not a stop to accounting for obligations already accepted.

In a wind-down, new obligations are stopped first, then pending transfers are closed, amounts due are refunded or paid out, balances are reconciled and evidence is preserved. A remaining token, a stuck refund and a disputed payout do not disappear when the website is switched off. A wind-down plan is needed in advance, because it is precisely during a shutdown that it is harder to top up gas, reach a partner and find out who is authorized to sign an operation.

<a id="module-6-8"></a>
<a id="68-cbdc--карточка-2026"></a>
## 6.8 Central bank digital currencies: CBDC

### Who is the debtor

**Central bank digital currency, CBDC**, is digital money of the central bank. Retail CBDC is intended for access by the public and businesses, wholesale CBDC for certain financial participants and wholesale settlement. The BIS distinguishes these forms by purpose and access, not simply by the size of the transfer. [BIS Papers 159, Definitions and Annex A](https://www.bis.org/publications/paper-159-advancing-tandem-results-2024-bis-survey-central-bank-digital-currencies-and-crypto.pdf) [P06-C027].

| Form of money | Whose liability we are looking at | How the user gets access | Main question when paying |
|---|---|---|---|
| Central bank cash | The central bank's | Physical possession of banknotes | Authenticity and actual handover |
| Bank deposit | A commercial bank's | Account and payment instrument | Account terms, settlement, bank risk |
| EMT | The issuer's, under the relevant legal regime | Token, wallet and issuer procedures | Holder rights, redemption, access |
| Retail CBDC | The central bank's | The wallet/account model of the specific system | Access, privacy, limits, acceptance rules |
| Wholesale CBDC | The central bank's | Access for authorized financial participants | Settlement of wholesale obligations |

This is a conceptual scheme, not a claim that all jurisdictions classify cash in the same way or give holders the same rights. A CBDC may be serviced through intermediaries. The intermediary provides the interface and the checks, but this does not necessarily turn the underlying asset into the intermediary's own liability.

A synthetic balance sheet shows the difference. A customer has 100 monetary units on deposit at a commercial bank. They move 30 into retail CBDC under a model in which the bank redeems the corresponding part of the deposit using its reserves. The customer's deposit becomes 70; the bank's reserve assets decrease by 30; the bank's liability to the customer decreases by 30. At the central bank, the reserve liability to the bank shrinks by 30, and the CBDC liability grows by 30. The customer then pays a merchant 20 CBDC: the customer is left with 10, and the merchant has 20. Neither a private stablecoin nor its issuer's reserve is involved in this example.

### Program status is a separate claim

**Research/design** means study and design; a **PoC** tests a technical idea; a **pilot/trial** tests a limited system, sometimes with real value; **live** requires established availability within a defined perimeter. A real transaction inside a pilot does not prove a generally available retail launch. A BIS study published in August 2025, based on a 2024 survey, reported that 85 of 93 responding central banks were exploring CBDC. This is self-reporting on work on the topic, not the number of currencies launched and not a map as of September 2026. [BIS Papers 159, Introduction, Annexes A–B](https://www.bis.org/publications/paper-159-advancing-tandem-results-2024-bis-survey-central-bank-digital-currencies-and-crypto.pdf) [P06-C028].

Below are the six geographies of the main structure. The status column is limited to the evidence that was read; it does not disguise the absence of later confirmation as a negative fact.

| Geography | Confirmed stage and date of evidence | What remains conditional or unverified |
|---|---|---|
| EU, digital euro | The next stage of the project after the preparation phase, completed in October 2025; the official progress page is available as of the cutoff | The ECB links a possible first issuance in 2029 to the adoption of legislation in 2026; the decision to issue is separate and comes after the law. This is not retail money that has been launched. [ECB](https://www.ecb.europa.eu/euro/digital_euro/progress/html/index.en.html) [P06-C029] |
| United Kingdom, digital pound | Research/design; report of 2026-03-04, page updated 2026-03-12. No decision to introduce it has been taken in this document | The completion of the design phase and a decision on next steps later in 2026 have been announced. A later decision was not established in this research. [Bank of England](https://www.bankofengland.co.uk/the-digital-pound/progress-update-digital-pound-design-phase) [P06-C030] |
| Indonesia, Project Garuda | PoC of an immediate-state wholesale cash ledger completed; BI release of 2024-12-13 | The success of test scenarios as reported by BI does not equal a launch of retail Digital Rupiah. A later live rollout is not confirmed by any primary source that was read. [Bank Indonesia](https://www.bi.go.id/en/iru/highlight-news/Pages/Garuda-Project-Proof-of-Concept,-New-Chapter-of-Digital-Rupiah-Exploration.aspx) [P06-C031] |
| Singapore | Live **trial** of issuing wholesale CBDC for interbank overnight lending, announced by MAS on 2025-11-13 | This is a limited real-world experiment by DBS, OCBC and UOB. A future test of tokenised MAS Bills and a retail CBDC do not follow from this speech as completed projects. [MAS speech, BIS republication](https://www.bis.org/speeches/20251120-creating-future-finance-journey-innovation-and-collaboration) [P06-C032] |
| UAE, Digital Dirham | The CBUAE describes wholesale and retail work; the government transaction of 2025-11-11 is explicitly assigned to the pilot phase | The real value of the payment confirms a pilot event. A generally available retail launch as of this chapter's cutoff has not been separately established. [Ministry of Finance](https://mof.gov.ae/en/news/ministry-of-finance-and-dubai-finance-conduct-first-government-transaction-using-digital-dirham/), [CBUAE primer](https://centralbank.ae/media/lczb23l4/cbdc-short-report_july.pdf) [P06-C033] |
| United States | Policy constraint: the executive order of 2025-01-23 prohibits agencies from establishing, issuing or promoting a CBDC, except where required by law | Old Fed research materials cannot be used as evidence of a current issuance program. The order is not a ban on all private digital payments; subsequent legislative changes have not been separately established here. [White House, §5](https://www.whitehouse.gov/presidential-actions/2025/01/strengthening-american-leadership-in-digital-financial-technology/) [P06-C034] |

### What this could change in payments

Merchant acceptance requires a merchant identifier, a compatible interface, invoice data, and rules for finality and refunds — even if the debtor on the money is the central bank. Wholesale CBDC can be used for the cash leg of settlement against securities or another currency. But the atomicity of a technical exchange does not by itself establish rights to the delivered asset or cross-border legal finality.

An offline payment poses a separate problem: how to transfer value without a constant connection and without allowing the same amount to be spent twice. Options include a secure device, limits, later synchronization and loss allocation. The specific design determines the trade-off between accessibility, privacy and control; a stated offline capability does not mean unlimited anonymous transfer. In the CBUAE primer, offline use and an intermediated architecture are treated as elements of a system under development. [CBUAE Policy Paper 1/2025, design sections](https://centralbank.ae/media/lczb23l4/cbdc-short-report_july.pdf) [P06-C035].

Privacy must also be broken down by participant: what information the central bank, the wallet, the bank and the merchant see, where identifiers are stored and who discloses them on a lawful request. The Bank of England's promise that the state will not program how money is spent relates to a design commitment and a future legislative architecture. User-defined conditional payments are separated there from restrictions built into the money itself. [Digital Pound Progress Update, Annex](https://www.bankofengland.co.uk/the-digital-pound/progress-update-digital-pound-design-phase) [P06-C036].

For PSPs, a new role is possible: interface, customer due diligence, reconciliation and support. For agent payments, one can posit delegated authority, limits and conditional execution. For now, this is a **working_hypothesis**, not a confirmed API available to a specific account, and not a product roadmap. [P06-C037] A verifiable next step for a specific project is to find a published interface, participation terms and a permitted scenario, and then to separate the experiment from production.

### Practice: eight exercises with explained answers

1. **Asset profile.** A buyer showed 500 "USDC", but the contract address is different. Can the payment be recognized? **Answer:** there is not enough proof. The network, the identifier of the accepted asset, the recipient and the amount are checked. The name and the displayed dollar value do not replace these checks. Until clarified, this is a different or unsupported asset, not automatically fraud.

2. **Two webhooks.** For an invoice of 27.35, two identical notifications arrived about one network transfer. What is the income? **Answer:** one receipt of 27.35, while income is determined by the contract and the accounting for the sale. Two notifications do not create a second asset. If, however, two different transfers are found, there is an overpayment, which cannot silently be recognized as revenue from a second order.

3. **USDT direct redemption.** Under the conditions given in §6.3, a customer redeems 250,000 USD. What is the fee? **Answer:** max(1,000; 250,000 × 0.1%) = 1,000 USD, net 249,000 USD before other costs. This is 0.4% of the amount. The terms apply to an admitted primary customer, not to any exchange sale.

4. **Late payment.** The quote expires at 12:02, the transaction was sent at 12:01 and included at 12:03. Is the order paid at the old rate? **Answer:** there is not enough data. An agreed fixing event and proof of it are required. The condition cannot be defined only after the rate movement has become known.

5. **Liquidity.** In §6.7, the account holds 5,000 EUR; the payable is 8,910 EUR and the fee 2 EUR. What is the minimum shortfall? **Answer:** 3,912 EUR. The expected 9,000 EUR are not yet available. The positive profit on the deal of 182.80 USD does not by itself cover the shortfall.

6. **Stress.** Net proceeds from the token sale fell to 9,500 USD, and buying euros became 180 USD more expensive. How did the result change relative to the base case? **Answer:** 182.80 − 490 − 180 = −487.20 USD. This is the cash economics of this deal; revaluation of other balances and the cost of additional funding are not included.

7. **Observability.** The API reports `payment_submitted`, the order has already been handed over, and there is no bank statement. Which facts are proven? **Answer:** submission, in the provider's semantics, and fulfillment, from separate order data. Receipt of fiat is not proven. The original payout is reconciled; a blind resend creates a risk of a double payout.

8. **CBDC maturity.** A central bank reported the first real transfer between three banks. Can buyers be promised acceptance of retail CBDC? **Answer:** no. A limited wholesale trial has been proven. Retail requires its own conditions for issuance, access, wallets, merchant acceptance and operational readiness.

### Connections, evidence and open questions

Basic concepts of obligations and evidence are in [Chapter 0](../00-Money-and-fintech-basics/README.md); the geography of regulation in [Chapter 1](../01-Market-rules-and-licensing/README.md); bank and card settlement in [Chapter 2](../02-How-a-payment-works/README.md); product checkout in [Chapter 4](../04-Payment-providers/README.md); custody, on/off-ramp and reversibility in [Chapter 5](../05-Wallets-accounts-and-cards/README.md). Agent protocols are covered in Chapter 7; this chapter does not assume their availability.

The full reading catalog is in [Sources](Sources.md), the verifiable material claims in [Claims](Claims.md), and gaps in access and further verification in [RESEARCH_NOTES.md](Research-notes.md). As of the 2026-09-15 cutoff, the following have not been established: the current availability of a specific provider for a specific legal entity, individual bank contracts, exact versions of dynamic APIs, the complete latest changes in the stages of individual CBDCs, and the order of bankruptcy claims for a chosen chain of counterparties. These gaps limit operational conclusions but do not invalidate the mechanisms examined or the verified arithmetic.

---

### Sources and fact-check

[Sources](Sources.md) · [Verifiable claims](Claims.md) · [Chapter fact-check](../../Fact-check/06-Crypto-and-stablecoins/README.md)

The text was prepared by agents and passed an independent agent review on 15–17 September 2026. The teaching edition has limitations; dates and limits of applicability are given in the sources. [Edition record](../../Methodology/Edition-record.md).

<details>
<summary>History and metadata of the original manuscript</summary>

This information describes the research stage before publication. Current visibility is public; the status of the whole edition is `reviewed_with_limitations`. The earlier labels `private` and `independently_reviewed_draft` are kept only as history.

**Status:** `independently_reviewed_draft` · **Version:** v0.1 · **Author:** Part 06 researcher, Codex · **Cutoff:** 2026-09-15 · **Sources read:** 2026-09-15 UTC · **Access:** private.

</details>

[← Wallets, accounts and cards](../05-Wallets-accounts-and-cards/README.md) · [Contents](../README.md) · [AI agent payments →](../07-AI-agent-payments/README.md)
