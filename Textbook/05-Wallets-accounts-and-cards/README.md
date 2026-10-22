[← Payment providers](../04-Payment-providers/README.md) · [Contents](../README.md) · [Crypto and stablecoins →](../06-Crypto-and-stablecoins/README.md)

<a id="часть-5-счета-кошельки-хранение-денег-и-выпуск-карт"></a>
# Chapter 5. Wallets, accounts and cards

> Where money is held, who controls it and how card issuing works.

**5 lessons** · Knowledge cutoff: **15 September 2026** · [Sources](Sources.md) · [Fact-check and limitations](../../Fact-check/Results.md)

## In this chapter

- [5.1 · Types of wallets and accounts](#module-5-1)
- [5.2 · Who controls the keys and the balance](#module-5-2)
- [5.3 · How to exchange ordinary money for crypto and back](#module-5-3)
- [5.4 · Refunds and reversibility of transactions](#module-5-4)
- [5.5 · Issuing a card: from creation to closure](#module-5-5)
- [Exercises](#exercises)
- [Answers and grading criteria](#answers-and-grading-criteria)
- [Summary, connections and limits of this version](#summary-connections-and-limits-of-this-version)

---

**Scope:** how a customer balance, asset control, fiat↔crypto transitions, refunds and a card product work on the cardholder's side. Legal examples are limited to the jurisdictions named; descriptions of providers are limited to the public documents that were read. This is a teaching analysis, not a legal opinion or a check of whether a product is available to a particular business.

After reading, you will be able to:

- use the contract to tell apart a bank deposit, electronic money, prepaid and crypto custody;
- map keys, authority and recovery without concluding "there is MPC, so there is no custody";
- calculate the result of an exchange and spot the gap between the purchased asset and the availability of withdrawal;
- separate the refund claim, the refund over the payment rail and the credit to the recipient;
- explain card issuing, authorization, settlement funding, card replacement and program economics.

Prerequisites: [0.3–0.5: units, money and ledger](../00-Money-and-fintech-basics/README.md), [1.2, 1.5, 1.8–1.9: authorizations, AML, contracts and buyer rights](../01-Market-rules-and-licensing/README.md), [2.2 and 2.6: payment states and disputes](../02-How-a-payment-works/README.md). P05-S links lead directly to the primary source; the exact reading scope and limitations are in [Sources](Sources.md), and verifiable statements are in [Claims](Claims.md).

<a id="module-5-1"></a>
<a id="51-типы-кошельков-и-счетов"></a>
## 5.1 Types of wallets and accounts

**Question:** what does a person get when an app shows "balance 100"?

**Short answer:** the number means something only together with the asset, the obligated party, the rules of use and the way to get the money back. The word wallet by itself determines neither banking status, nor who owns the keys, nor protection in bankruptcy.

### First the claim, then the interface

A **bank deposit** is the customer's claim on the bank in a specified currency and on the terms of the account. The customer disposes of the claim through the instruments provided; an entry in the app does not mean that the bank keeps a separate stack of banknotes with the depositor's name on it. Here one should distinguish the bank's credit risk, the availability of payments and whether deposit insurance applies. The latter depends on the specific institution and the ownership category; the brand of a non-bank app does not create it by itself. [P05-S004, Banking with third-party apps](https://www.fdic.gov/consumer-resource-center/2024-06/banking-third-party-apps).

**E-money**, as defined in the EU EMD2, is electronically stored monetary value that represents a claim on the issuer, is issued on receipt of funds for the purpose of making payments, and is also accepted by other persons. The EBA/European Commission answer additionally examines the significance of contractual consent to the issuance of such a separate monetary asset. So receiving money and showing a figure in an app do not yet give the right to automatically call the product e-money. [P05-S001, Final answer, Article 2(2), C-661/22 §§47–48](https://www.eba.europa.eu/single-rule-book-qa/qna/view/publicId/2022_6336).

A **payment account** describes a function: an account in the user's name used to execute payment transactions. It is not a fourth kind of currency. In the PSD2 clarification, what matters is the ability to send and receive funds directly, including from third parties; the existence of a linked reference account does not settle the question by itself. The bank or non-bank status of the provider is examined separately. [P05-S002, Final answer, Article 4(12)](https://www.eba.europa.eu/single-rule-book-qa/qna/view/publicId/2018_4272).

**Stored value / prepaid** means a model in which use is funded in advance. It is a product characteristic, not a universal legal exemption. A **gift card** defines a purpose; a **payroll card** defines a way of receiving wages. **Closed-loop** limits acceptance to a store, a group of stores or another defined environment; **open-loop** uses a wider acceptance network. A gift card can also be open-loop. The CFPB stresses that gift and ordinary prepaid products may have a different set of protections even though they look alike. [P05-S003, Choose the right card: card types; open/closed loop; protections](https://www.consumerfinance.gov/consumer-tools/prepaid-cards/choose-the-right-card/).

This gives a useful matrix:

| Question | What you need to name |
|---|---|
| What does the balance measure? | USD, EUR, a specific token, points or a right to receive goods |
| Who must fulfill the claim? | Bank, EMI, another issuer, custodian, merchant |
| Where does the product work? | Network, territory, permitted recipients and transactions |
| How do you get the value back? | Withdrawal, transfer, repayment, redemption or only purchases |
| What happens if a participant fails? | Contract, refund procedure, insurance, safeguarding, priority of claims |

The matrix is the author's way of reading documents. It does not assign licenses based on a product's name. For example, a "USD wallet" can at the same time involve an internal account with the app, a pooled bank account at a partner and an access card. These are three linked objects, not three independent sums of money.

### Crypto wallet: access to the asset and records at an intermediary

With a **custodial wallet**, an intermediary provides custody or control of the means of access. The user usually sees an individual balance in the intermediary's records; the assets may sit at shared addresses. With a **non-custodial wallet**, the access mechanism may allow the user to dispose of the asset without the consent of such a custodian. But technical independence has to be checked: who signs, who recovers, who changes the policy, and whether there is a way out if the app disappears.

A **smart account** is a programmable account that validates transactions with code. In ERC-4337, the user's instruction, a `UserOperation`, passes through a bundler and the EntryPoint; a paymaster can pay for network execution. The signature rules are set by the account implementation. So a smart account can be convenient for limits and recovery, but the term itself does not tell you who actually controls the code and the roles. [P05-S009, Abstract; Motivation; Definitions](https://eips.ethereum.org/EIPS/eip-4337).

A crypto balance should be recorded as a combination of **asset and network**, and for tokens also of a verified contract or other network identifier. Circle publishes different USDC identifiers for different mainnets and testnets. A matching name does not confirm that a supported asset was sent: someone else's token can also display the string USDC. Having an address on one network does not confirm that the receiving service supports it on another. [P05-S028, USDC contract addresses, introduction and network tables](https://developers.circle.com/stablecoins/usdc-contract-addresses).

### Synthetic example: one money pool, two customer balances

Consider a **teaching operational sub-ledger** of a payment service. It shows customer claims and the corresponding bank position; it is not a prescription for how safeguarded assets should be presented in the accounts under IFRS. There are no fees.

| Event, USD | Customer bank position | Anna's claim | Boris's claim | Anna: available / held |
|---|---:|---:|---:|---:|
| 600 and 400 deposited | 1,000 | 600 | 400 | 600 / 0 |
| 120 reserved for Anna's purchase | 1,000 | 600 | 400 | 480 / 120 |
| Anna transferred 50 to Boris | 1,000 | 550 | 450 | 430 / 120 |
| Boris withdrew 200 to an external account | 800 | 550 | 250 | 430 / 120 |

The internal transfer changed how the claims are distributed, but not the balance of the bank pool. The hold restricted the availability of 120 without creating an expense or revenue. After the withdrawal, 800 = 550 + 250 holds. If the service separately has 90 of its own, the total teaching balance sheet equals 890 = 800 of customer liabilities + 90 of equity. The customers' 800 does not become the service's revenue.

**What breaks:** the interface adds up the available 430 and the full balance of 550, shows Anna 980 and lets her spend it. Another mistake is to count the tokens at a shared address and the internal claims on the same pool as two different assets. The fix is to establish the link between each record and its economic object, not to pick a nice-looking total. An additional check: a right to a balance of 550 does not yet mean the ability to withdraw all 550 now, because 120 remain reserved.

<a id="module-5-2"></a>
<a id="52-контроль-ключей-и-остатка"></a>
## 5.2 Who controls the keys and the balance

**Question:** how do you tell who controls the money and what saves the customer when something fails?

**Short answer:** technical control, legal rights and recovery must be checked separately. Strong cryptography helps protect the signature, but it does not establish ownership and does not make up for a shortfall in the money pool.

### MPC is not a legal form of custody

**Multi-party computation (MPC)** lets participants jointly compute a result without revealing certain secrets to one another. In a threshold signature, the key is represented by shares; a sufficient set of participants creates a signature without necessarily reconstructing the whole key in one place. This differs from simply splitting a backup copy and later reassembling the secret. NIST examines such schemes through the threat model, security properties and verifiability of participation. [P05-S008, Executive summary; §1; §2.5](https://nvlpubs.nist.gov/nistpubs/ir/2020/NIST.IR.8214A.pdf).

**Synthetic 2-of-3 scheme:** share A is held by the user, B by the operator, C by a separate recovery party. An ordinary payment needs A+B. Losing the phone allows B+C, if such recovery is permitted. Two different questions follow: can one participant steal the asset, and can two participants exclude the third? If B and C answer to the same administrator, there are fewer organizationally independent parties than cryptographic shares.

With **MPC-as-a-service**, the technical service is outsourced to a provider. It does not automatically answer who legally holds the assets in custody. The list of things to clarify is short: placement of the shares, the threshold, the rules for replacing a signer, the administrator's authority, the backup path and the terms of the contract. You cannot carry the 2-of-3 scheme over to any brand: the public Fireblocks Vault overview describes its own placement of shares and separate recovery options for lost devices or the provider shutting down. This is a description of capabilities, not evidence that recovery for a specific customer has already been set up and tested. [P05-S011, Overview; Recovery Tools](https://developers.fireblocks.com/docs/perform-drs-process).

**Administrative rights** matter especially in a smart account: who changes the validation module, the threshold, the permitted recipients or the recovery party? If the administrator can replace the restricting code, today's limit does not yet prove the customer's independence. If the code cannot be changed, a faulty recovery mechanism may turn out to be permanent. The ERC-4337 specification singles out EntryPoint security separately; conformance to the operation format does not replace an audit of the specific account. [P05-S009, Security Considerations](https://eips.ethereum.org/EIPS/eip-4337).

A telling language risk: in Privy custodial wallets, the `owner` field means the authorized controller of requests and configuration. The documentation explicitly separates it from the ability to export the private key or to execute a transaction alone, without the custody provider. So the name of an API field cannot be turned into the legal conclusion "the asset is in the user's self-custody". [P05-S010, Meaning of owner for custodial wallets](https://docs.privy.io/wallets/custodial-wallets/advanced/authorization-controls).

### "Not your keys" and the regulator's view

The slogan is a reminder of dependence on an intermediary, but it is not a legal test. The FATF treats control functionally: the ability to hold, transfer or spend an asset, or to change its position. The 2021 guidance states explicitly that control need not be exclusive: a multi-signature scheme does not rule it out. At the same time, software itself is not considered a VASP merely because it exists; what is examined is the activity of the relevant persons. This is international guidance, not a ready-made national license; the authors warn that the document does not include later changes to the standards. [P05-S012, §§67, 72–75; publisher caveat](https://www.fatf-gafi.org/content/dam/fatf/documents/recommendations/Updated-Guidance-VA-VASP.pdf).

For the customer, a map of four capabilities is useful: **send**, **block sending**, **change the rules**, **restore access**. These actions may have different owners. The technical ability to dispose of an asset, the right to act on the customer's behalf and the obligation to answer for a loss are different columns of the contract.

### Three protections that must not be lumped together

**Deposit insurance** applies to a defined event and object. In the US, the FDIC does not insure against the failure of the non-bank app itself. When funds are placed through an intermediary, pass-through coverage requires certain conditions to be met: actual ownership by the principal, the intermediary nature of the account being reflected, and records of the owners' identities and their shares. This is a mechanism for recognizing depositors, not a separate category of additional insurance. [P05-S004](https://www.fdic.gov/consumer-resource-center/2024-06/banking-third-party-apps), [P05-S005, §§I, III, V](https://www.fdic.gov/financial-institution-employees-guide-deposit-insurance/pass-through-deposit-insurance-coverage).

**US teaching calculation:** a person has 240,000 USD through an app and 40,000 directly at the same insured bank, in one single-account ownership category. With the pass-through conditions met, the combined position is 280,000; with a limit of 250,000, 30,000 is not covered. A new app does not create a new limit. If only the intermediary failed, this calculation does not by itself trigger an FDIC payout. The example is hypothetical and does not determine coverage for a real customer.

**Safeguarding** is the set of rules protecting certain customer funds. In the UK, the FCA describes, for the relevant EMIs/APIs, a segregated bank account or suitable insurance/guarantee. This is not direct FSCS protection in the failure of a non-bank provider; getting the money back may take time, and the administrator's costs can reduce the amount. The Supplementary Regime under PS25/12 applies from 7 May 2026 to the specified categories of firms. It must not be confused with the post-repeal end-state under discussion. [P05-S006, How safeguarding works](https://www.fca.org.uk/consumers/using-payment-service-providers), [P05-S007, Who this applies to; Background; Next steps](https://www.fca.org.uk/publications/policy-statements/ps25-12-changes-safeguarding-regime-payments-and-e-money-firms).

**Insolvency segregation (often discussed as bankruptcy remoteness)** concerns whether the provider's own creditors can lay claim to customer assets. It is not a promise of no loss, of an immediate payout or of the token's price being preserved. For EU crypto custody, MiCA Article 75 requires legal and operational segregation of assets, a customer register and return procedures; liability for loss is tied to an incident attributable to the provider and is subject to a set cap. This is a specific CASP regime, not a worldwide guarantee for any wallet. [P05-S013, Article 75(1–3),(6–8)](https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/mica/article-75-providing-custody-and).

### Recovery is a separate route to the money

**Synthetic failure:** the segregated pool holds 100,000, and the customer register contains liabilities of 102,000. Isolating the account does not explain the shortfall of 2,000. And if the bank shows 100,000 but the breakdown by customer has been lost, the arithmetic completeness of the pool does not settle the distribution. Likewise, 100 tokens at an address do not help if a sufficient set of signers is missing.

A recovery test must reach an observable result: restored identity → restored authority → access to the correct asset and network → ability to form a valid transaction → reconciled records. In a teaching project, this can be tested on test data and a test network. You also need instructions and records that do not depend on the provider that has stopped. A signed transaction without a working RPC, gas or a valid recipient does not yet mean a successful exit.

<a id="module-5-3"></a>
<a id="53-on-ramp--off-ramp"></a>
## 5.3 How to exchange ordinary money for crypto and back

**Question:** why can't exchanging money for a crypto-asset and back be presented as a single "top up the wallet" step?

**Short answer:** the operation crosses different systems, contracts and timelines. Successful receipt of fiat, purchase of the asset, permission to withdraw and crediting at the bank are each confirmed separately.

An **on-ramp** moves value from the fiat environment into a crypto-asset; an **off-ramp** moves it back. The user interacts with the exchange provider, its payment partners, a custodian or a blockchain address and, on the way out, the recipient's bank. If an app merely routes the user to a ramp partner, that does not make the app the exchange counterparty itself. The defining documents are the customer contract, the exchange instruction, the payment terms and the confirmations of each stage.

### Three routes and their gaps

| Route | Sequence | Gap that must not be hidden |
|---|---|---|
| Card → crypto | Customer check → card authorization/capture → exchange → delivery/withdrawal of the asset | A card dispute can arise after the asset has been delivered |
| Bank → crypto | Bank receipt/waiting → credit at the ramp → exchange → permission to withdraw | Available for trading does not necessarily mean available for sending |
| Crypto → bank | Deposit of a supported asset → checks → sale → fiat payable → bank payout | The sale went through, but the bank has not yet received or credited the money |

The table is a generalized model; a specific provider may combine stages or fund them in advance. Coinbase, for example, describes cash deposits on hold: crypto bought with such funds can sometimes be traded within the platform, while sending it out remains restricted. The period depends on account factors; it is not a universal number of days for all customers. [P05-S014, Cash deposits on hold; Hold periods; Sends and withdrawals](https://help.coinbase.com/en/coinbase/trading-and-funding/sending-or-receiving-cryptocurrency/available-balance-faq).

The marketing claim "no chargebacks" for a ramp integration should be read as a question of how the contract allocates risk: who takes the dispute on the funding leg, and is it entitled to recover losses from the partner? It does not mean that the card network has technically lost its dispute mechanism. This conclusion follows from the separation between card funding and the subsequent transfer of the asset, while the specific allocation of liability requires the text of the contract.

**Redemption with the issuer** differs from selling a token through an exchange off-ramp. For example, the Circle Europe policy provides a separate path for EEA Retail Holders via a form, identity and transaction checks, and a bank IBAN in the EEA. So the institutional Mint requirement cannot be declared common to every direct redemption of USDC. Geography, holder category and the applicable terms matter; for more, see [6.3](../06-Crypto-and-stablecoins/README.md). [P05-S033, §§1.4, 2.1–2.3, 3](https://www.circle.com/legal/mica-redemption-policy). On a repeat reading on 2026-09-17, the page was marked as the version of 2026-09-15; the author had originally recorded 2026-07-13. Without a saved copy, it cannot be confirmed that the page did not change between readings.

### Price: rate, spread and fees

**Spread** is the difference between the exchange price used and a chosen benchmark. **Slippage** is the deviation of the actual execution price from the expected one. These measures must not be treated as one and the same charge. You need to record the asset pair, the direction of the quote, the moment, the benchmark source and the size of the transaction. A rate of "1" without currencies and conditions does not describe a trade.

**Synthetic on-ramp:** a customer spends 1,000 USD by bank transfer. The service fee is 5 USD; 995 remains for the exchange. The hypothetical quote is 1.005 USD per 1 USDC. The purchase is 995 / 1.005 ≈ **990.049751 USDC**. If the withdrawal fee is withheld as 0.50 USDC, the customer receives **989.549751 USDC**; rounded to six decimal places for the example.

Check: 990.049751 × 1.005 ≈ 995 USD; 995 + 5 = 1,000. The 0.50 USDC withdrawal charge should not also be subtracted a second time as 0.50 USD. The all-in cost of obtaining one unit is approximately 1.01056 USD/USDC. If the benchmark was 1 USD/USDC, the total difference relative to the hypothetical parity is approximately 10.450249 USD. This is not a statement about market pricing and not proof of a peg.

**Synthetic off-ramp:** 1,000 USDC are sold at 0.998 USD. The gross fiat result is 998 USD. The exchange fee is 3 USD and the bank payout fee 2 USD; **993 USD** should arrive in the account. The network cost is paid separately and estimated at 0.20 USD, so the overall economic result after it is 992.80 USD. The bank statement should still show 993, not 992.80: do not confuse the cash flow with the full cost.

The Coinbase Offramp Quote API requires the asset, network, amount, fiat currency, payout method and country. At the same time, the document explicitly calls the returned price an estimate, not a guarantee of execution at that price. So a `quote_id` does not yet prove a rate lock. If a guarantee is needed, separate confirmation of how long it lasts and on what conditions is required. [P05-S015, Offramp Quote; Limitations; Request Parameters; Response Fields](https://docs.cdp.coinbase.com/onramp/offramp/generating-quotes).

### Liquidity and data accompany value

**Liquidity** is the ability to meet the required obligation in the required asset and place on time. Even if a ramp has enough tokens, paying out 993 USD requires available USD at the relevant banking partner. Valuing assets in dollars does not turn them into bank liquidity. On a non-business day, the local fiat pool may run out before the company's overall capital does.

The **Travel Rule** concerns information about the sender and recipient that accompanies the relevant transfers. It is a separate data flow, not a name written to a public blockchain. The EBA describes requirements for PSPs/CASPs to detect missing information and the application of the guidelines from 30 December 2024; national thresholds and the full list of procedures are not reproduced here without a separate check of the legal provision. [P05-S016, Background; Legal basis](https://www.eba.europa.eu/publications-and-media/press-releases/eba-issues-travel-rule-guidance-tackle-money-laundering-and-terrorist-financing-transfers-funds-and).

**Edge case:** a deposit is visible on-chain, but the network or contract is not supported; or the receiving party is waiting for information about the recipient. The status should report a specific fact: "deposit detected, credit pending review". The promise "the money is already in the bank" is false until the bank confirms. A stable unit of account reduces one kind of price uncertainty, but does not remove custody, settlement, depeg, freeze and operational risks; for details, see [Chapter 6](../06-Crypto-and-stablecoins/README.md).

<a id="module-5-4"></a>
<a id="54-refunds-и-reversibility"></a>
## 5.4 Refunds and reversibility of transactions

**Question:** if the original payment is final, can the merchant still owe the buyer money?

**Short answer:** yes. Finality relates to a particular settlement. The ground for a refund relates to the contract, the law and the circumstances of the purchase. A new transfer can discharge the refund obligation without rewriting the old transaction.

### Separating grounds and methods

A buyer may have a right to demand money because of non-performance, an error, an unauthorized transaction or an applicable right of withdrawal. For example, EU consumer guidance covers withdrawal from certain distance purchases and, separately, exceptions for services and digital content. You cannot declare all digital content non-refundable just because it is digital; the conditions of consent and of the start of performance matter. The payment rail itself does not set these conditions. [P05-S031, Returns and right of withdrawal; Exceptions](https://europa.eu/youreurope/citizens/consumers/shopping/returns/index_en.htm).

| Mechanism | Who initiates it and what happens | What the result does not prove |
|---|---|---|
| Authorization reversal / void | Release or reduction of a previously placed hold | That a separate payment that has already gone through has been returned |
| Card refund | The merchant sends a credit through the acquiring chain to the original card relationship | That the customer already sees the money or that a dispute is closed |
| Chargeback | The issuer and acquirer take part in the scheme procedure on a specific ground | That any claim is automatically justified |
| Bank recall | A PSP requests the return of a specific transfer | That the recipient must agree in every scenario |
| Bank return | A reverse movement under the rail's rules / for a return reason | That this is a dispute about the quality of goods |
| Crypto refund | A new transfer of the asset to a verified destination | That the original blockchain transaction has been canceled |

The basic card distinctions are covered in detail in [2.6](../02-How-a-payment-works/README.md). A practical example from Stripe: after a successful payment, a refund is created; if the available balance is insufficient, a card refund may wait for funding. References for tracing (ARN/STAN/RRN) are supported. Neither the merchant's message nor such a reference equals the recipient's statement. [P05-S030, Refund requests; Refund destinations; Trace a refund](https://docs.stripe.com/refunds).

For SEPA Credit Transfer, the EPC separately distinguishes a Recall for specified reasons and a **Request for Recall by the Originator** on other grounds. For the latter, the rulebook explicitly requires warning the originator: getting the funds back is not guaranteed and depends on the beneficiary's consent. This is the rule of a specific procedure, not a statement that any bank transfer can be freely reversed. [P05-S018, 2025 v1.1, §4.3.2.4, p.35](https://www.europeanpaymentscouncil.eu/sites/default/files/kb/file/2025-09/EPC125-05%202025%20SCT%20Rulebook%20version%201.1.pdf).

The interface should reflect the difference too. If a blockchain payment is final, a "refund" button usually creates a new transaction with its own fee and recipient check. A promise of "protection like a card" requires a specific dispute mechanism, a responsible party and terms of reimbursement. A familiar wallet screen does not create a chargeback, and the absence of a chargeback does not extinguish a contractual claim.

### Refund in which currency, and to whom?

**Synthetic purchase:** an item costs 100 USD; 100 USDC was accepted at the time of payment. The merchant converted it and received 99 USD after charges. Later, a full refund obligation of **100 USD** is recognized, and the hypothetical current rate is 0.98 USD/USDC.

If the agreement and the applicable law allow settlement in the token at the current price, 100 / 0.98 ≈ **102.040816 USDC** will be needed, rounding to the nearest value with six decimal places. If the debt must be covered in full with no underpayment allowed, round up to **102.040817 USDC**, plus network costs on the agreed terms. The calculation precision, the token precision and the rounding rule for the debt amount must be set separately in the ledger. Refunding only 100 USDC transfers 98 USD of value. If, however, the obligation was originally expressed as 100 USDC, a different result is to be expected: the debt is fixed in the token. You cannot pick the unit that favors the merchant after the rate has changed. The fee for the original acceptance also does not automatically reduce the established debt to the buyer.

The source address is not a universal refund detail. Coinbase explicitly warns that a transfer back to the original sending address may go to Coinbase instead of the customer; you should obtain the customer's current address or use a supported internal route. This is especially clear with shared exchange wallets. [P05-S017, Return a cryptocurrency transaction](https://help.coinbase.com/en/coinbase/trading-and-funding/sending-or-receiving-cryptocurrency/how-do-i-refund-a-digital-currency-transaction).

The opposite extreme is to trust any new address from an email. A study by McCorry, Shahandashti and Hao, published at Financial Cryptography 2016 and available in the authors' version, examined the lack of a reliable binding between the refund destination and the buyer who authorized the payment in the BIP70 process of that time. The authors described experiments, limitations and the processors' response. From this historical study we derive a requirement for proof of authority to change the destination; it does not prove that today's products have the earlier vulnerabilities. [P05-S026, §§2.2–5.2, 6](https://eprint.iacr.org/2016/024.pdf).

### A refund as a managed obligation

The author's state model:

```text
claim received → ground and amount confirmed
→ destination verified → money reserved
→ instruction sent → execution confirmed
→ credit/receipt verified → obligation closed
```

`failed`, `awaiting_information`, `unknown` and a partial result are separate branches. Between "sent" and "received", the rail reference, asset, network, amount, fee and link to the original purchase are kept. If there is no confirmation, the previous transaction is checked again; a new transfer is acceptable only after the result of the previous one has been established and a decision has been made on the risk of a duplicate.

**Double reimbursement example:** a store acknowledged a debt of 80 EUR. Support created a refund of 80, and in parallel the customer's bank credited 80 under a dispute. The 160 received does not mean the item cost 160. The two processes must be matched, the status of each established, and the difference resolved through the designated procedure. Simply deleting the refund record from the local books does not bring the money back. Stripe separately notes the possibility of a double credit when a refund and a dispute combine, for bank debit methods. [P05-S030, Bank debit payment methods](https://docs.stripe.com/refunds).

### Public case: pending for the customer

In a Reddit thread that archive navigation ties to 16 July 2024, **u/RandyMachoManSavage** reported months of waiting for a refund on a Coinbase Card. **u/radman430** linked the problem to the split between the bank and the app; **u/OhmazingJ** objected that contacting the bank sends a person back to card support. These are attributed messages, not a proven diagnosis or a measurement of the failure rate. [P05-S027, original post and first comments](https://www.reddit.com/r/Coinbase/comments/1e50vp4/do_not_use_coinbase_debit_card_they_arent/).

The teaching question from the case: which participant has already received the refund, and in which record did it stop? You need the merchant's confirmation, the network reference, the issuer's record and the record of the linked customer account. Knowing the bank's name is useful, but it does not replace an owner of the investigation and proof of the last completed step. The contract available today cannot silently be declared the version that applied to the author of the post in 2024.

<a id="module-5-5"></a>
<a id="55-issuing-и-жизненный-цикл-карточного-продукта"></a>
## 5.5 Issuing a card: from creation to closure

**Question:** what needs to be built so that a customer gets a working card and correct servicing of the whole money cycle?

**Short answer:** issuing the card details is one stage. The program has to allocate contracts, identification, funding, authorization decisions, settlement, cardholder protection and the wind-down of old obligations after replacement or closure.

### Roles on the cardholder side

| Role | Main function | What to find out in the contract |
|---|---|---|
| Cardholder | Uses the card and seeks protection | Who owns the account, who is an authorised user, who is liable for the credit |
| Issuer | Issues the payment instrument and takes part in issuer obligations | Legal entity, authorizations, cardholder agreement, settlement liability |
| BIN sponsor | Gives the program access through its BIN/relationship with the scheme | Who approves the program and can stop it |
| Program manager | Organizes the product, partners and servicing within the delegated scope | KYC, support, oversight, reporting, complaints, termination |
| Issuer processor | Processes messages, accounts/events in its model | Auth endpoint, clearing, reconciliation, SLA, fallback |
| Scheme / network | Sets the rules and connects issuer/acquirer | Participation, standards, obligations, tokens, disputes |

Roles can be combined, but a label does not replace obligations. In Stripe's processor-only setup, the program works with the BIN sponsor on its own, maintains cardholder balances and arranges funding; the issuer holds the settlement account with the scheme. There is no central Stripe Issuing Balance in this configuration. [P05-S022, Overview; Funding responsibilities; BIN sponsor settlement](https://docs.stripe.com/issuing/processor-only-issuing).

On the network side, VisaNet Connect — Issuing describes separate messages for authorization, completion, return and token provisioning; the issuer receives reports for settlement. API access by itself does not create an approved card program. [P05-S025, How it Works; APIs Used](https://developer.visa.com/capabilities/visanet-connect-issuing).

**A diagram drawn up for this chapter:**

```text
Cardholder ↔ app/program servicing ↔ issuer and its agreement
                         ↓ data/controls
Merchant → acquirer → network → issuer processor → auth decision
                         ↓ settlement obligation
        settlement account issuer → network/settlement infrastructure

Funding source: deposit / prepaid pool / credit line / other contractual source
```

The top line is servicing and responsibility, the middle one is purchase messages, the bottom one is settlement funding. Pressing "issue card" in the app does not create money on the last line.

### Debit, prepaid, credit and card details

**Debit** usually lets you spend funds tied to an account; **prepaid**, value funded in advance; **credit**, a limit set by the lender, with subsequent debt. This is a useful teaching classification, but the specific contractual terms and legal categories take priority. With a corporate card, the cardholder (an employee) and the debtor (the company) may be different persons.

There is a documented example of differing labels. Coinbase Help calls the US Coinbase Card a debit card. The copy of the **Pathward Cardholder Agreement** available via the legal page describes it in §1 as prepaid, not checking/savings, gift or credit; Pathward is named as the issuer and Marqeta as the program manager. This is a specific American consumer program, not a description of all Coinbase cards or all crypto cards. [P05-S032, overview](https://help.coinbase.com/en/coinbase/trading-and-funding/coinbase-card/cb-card), [P05-S019, definitions; §1](https://assets.ctfassets.net/q5ulk4bp65r7/6DSLCW5dxZXmHKCEcofI0g/469cad84c4d773e86b784892d053f7f0/Coinbase_Pathward_Cardholder_Agreement.pdf).

A **virtual** and a **physical** card describe the form in which card details are provided. **Provisioning** adds a suitable card representation, such as a network token, to a device/wallet after verification. The card number, the card object, the underlying account and the device token must be told apart: deleting a token from a phone does not necessarily close the account, and successfully generating a PAN does not confirm activation or the presence of spendable funds. Visa treats checking token provisioning as a separate function. [P05-S025, Inquiries API; Card Services API](https://developer.visa.com/capabilities/visanet-connect-issuing).

A program's lifecycle starts with an agreed target audience, country, funding and underwriting; then come the cardholder agreement, identification, issuing/delivery, activation and access to support. After the first purchase come clearing, settlement, reconciliation, periodic data updates, handling of complaints and replacements. The detailed list depends on the product; physical delivery and a successful purchase require different evidence.

### Authorization and funding: two checks of ability to pay

In **authorization**, the decision is whether to allow the attempt. The checks cover availability of funds/limit, card status, amount, merchant category, geography and risk signals. A **hold** reserves availability until the result is clarified. In **clearing**, a monetary claim is presented that may differ from the original authorization: partial capture, an increased hotel bill, tips, FX. Stripe describes separate states, incremental authorizations and changes to the final amount. [P05-S020, Authorization lifecycle; Purchases in different currencies; Incremental authorization](https://docs.stripe.com/issuing/purchases/authorizations).

**Just-in-time funding (JIT)** is loading funds during the transaction according to a predefined model. With Marqeta Gateway JIT, the program takes part in the funding decision and then receives an asynchronous notification of the actual result. This is not a promise that you can first approve any purchase and then look for the money. The threshold and the funding source must be defined before the response. [P05-S023, Concepts: JIT Funding; Card product configuration](https://www.marqeta.com/docs/developer-guides/configuring-gateway-jit-funding).

**Synthetic prepaid scenario**, USD, no charges and no FX. The customer has 500; the program has a corresponding cash position of 500. A hotel authorizes 150, later adds 30, the final presentment is 170, and the unused hold is released.

| Moment | Liability to the customer | Held | Available | Program's settlement payable | Cash position |
|---|---:|---:|---:|---:|---:|
| Before the purchase | 500 | 0 | 500 | 0 | 500 |
| Auth 150 | 500 | 150 | 350 | 0 | 500 |
| Incremental +30 | 500 | 180 | 320 | 0 | 500 |
| Clearing 170 and release of the remainder | 330 | 0 | 330 | 170 | 500 |
| Settlement 170 | 330 | 0 | 330 | 0 | 330 |
| Final refund of 20 received | 350 | 0 | 350 | 0 | 350 |

After clearing: 500 of assets = 330 of customer balance + 170 of settlement obligation. In the teaching books, the customer liability is reduced and settlement payable is increased by 170; at settlement, cash and payable are reduced by 170. The same spending should not be debited from the customer a second time when the network settles. The refund of 20 increases cash and the customer liability once the corresponding money has been received. This is a simplified model; real programs may show separate receivables, reserves and recognition timing.

In a credit model, the starting quantity is different: a limit of 1,000, previously posted debt of 200 and a hold of 150 give available credit of 650. After the final charge of 170 and release of the hold, the debt becomes 370 and the available limit 630. Here 630 is not the customer's money asset but the remaining ability to borrow under the product's terms. Closing the card credential does not repay the debt of 370.

### Where a controlled card stops being controlled

A **card freeze** is a card usage setting. It does not cancel all previously accepted obligations. Stripe states explicitly: spending controls, real-time controls and card status do not apply to capture. A refund can be credited even to an inactive/canceled card; the link between an incoming credit and the earlier authorization is sometimes incomplete. [P05-S021, introduction; Handling other transactions: Refunds](https://docs.stripe.com/issuing/purchases/transactions).

So a program limit of "no more than 100" needs clarification: is it the amount of one new authorization, a total for a period, the available balance or the final spend including FX/adjustments? An MCC shows the merchant's category, not a reliable list of the specific items in the basket. A limit is one control, not proof that the whole policy is enforced. New authorizations can be restricted, but funds and a process must be kept for permissible later presentments.

**JIT failure:** the program responded approve, but the response did not arrive in time. The local log shows an approval, while the processor declined the attempt. Marqeta requires reconciling notifications against responses; there are also informative events for stand-in and forced funding in certain clearing scenarios. So a local HTTP 200 should not automatically become a debit to the customer. [P05-S024, JIT Funding notifications; method table](https://www.marqeta.com/docs/core-api/gateway-jit-funding-messages).

When a card is lost, the credential is replaced separately and the linked tokens/subscriptions are checked. In Stripe, replacing a damaged/expired card can keep the number, while a lost/stolen one gets new card details. Old authorizations may clear on the original card. The program has its own obligation to arrange replacement; the documentation does not promise automatic reissue of expiring cards. [P05-S029, replacement scenarios; All replacements; Card-on-file updating](https://docs.stripe.com/issuing/cards/replacements).

### Disputes, program termination and economics

Support must distinguish an unauthorized transaction, a problem with goods, a duplicate and a delayed credit. Temporary reimbursement during an investigation is not always final: a separate record of the provisional credit and of the case outcome is needed. Legal deadlines, grounds and liability depend on geography and the type of card product; consumer prepaid and corporate credit cannot be served with one blind template.

In the US Coinbase Card Agreement that was read, under §9(b) a card refund, once received, is transferred to the **Coinbase Wallet**, which the same agreement defines as a linked account at Coinbase. This term cannot automatically be equated with the self-custody app of the same name or with any Coinbase account. §10(b) separately preserves previously accrued rights and obligations when the card is closed. The version date of this copy has not been established; a real cardholder needs their own applicable agreement. [P05-S019, definitions; §9(b); §10(b)](https://assets.ctfassets.net/q5ulk4bp65r7/6DSLCW5dxZXmHKCEcofI0g/469cad84c4d773e86b784892d053f7f0/Coinbase_Pathward_Cardholder_Agreement.pdf).

**Terminating a partnership** requires two clocks: when new purchases stop and when old settlements/obligations end. The author's wind-down plan includes preserving the register and statements, handling late clearing/refund/dispute items, returning unused funds, managing the residual reserve and an accessible complaints channel. Migrating to a new sponsor may require new contracts and card details; having a second API does not prove the program is portable.

**Synthetic monthly economics**, excluding taxes, interest and customer acquisition. The program has 2,000 active cards, each with 10 purchases at an average ticket of 50 USD: volume **1,000,000 USD**, count **20,000**. Suppose gross interchange of 1.4% yields 14,000 USD; under the contractual split the program gets 70%, that is **9,800**. These are made-up teaching parameters, not a scheme tariff and not a rate in any jurisdiction.

| Item | Teaching calculation | USD |
|---|---|---:|
| Program's interchange share | 14,000 × 70% | 9,800 |
| Processor | 20,000 × 0.08 | −1,600 |
| Sponsor/program fee | Hypothetical fixed amount | −1,500 |
| Fraud losses | 0.20% of volume | −2,000 |
| Support and disputes | 2,000 × 0.75 | −1,500 |
| Cards, delivery, token services | Hypothetical expenses recognized for the month | −800 |
| Result before other costs | 9,800 − 7,400 | **2,400** |

If fraud losses rise to 0.50%, that is 5,000, and the result becomes **−600**. If the sponsor requires a collateral reserve of 30,000, placing the reserve should not immediately be treated as an expense of 30,000: it is a separate linked cash position with restricted use. But it has to be funded; a positive margin of 2,400 does not ensure that 30,000 is available today. A credit program additionally bears the cost of funding and credit losses. Issuing interchange also must not be equated with the full merchant fee from acquiring — see [2.4](../02-How-a-payment-works/README.md).

## Exercises

1. An app says "EUR wallet, money at a partner bank". What three groups of information are missing before you can call it the customer's insured bank account?
2. In the 5.1 example, Boris withdraws another 100, and Anna's 120 hold is lifted. Calculate the customer pool, the claims and Anna's available balance.
3. In a 2-of-3 MPC, the operator controls shares B and C. What can you conclude about the independence of user A, and what can you not conclude about the license?
4. At one insured US bank, a customer has 180,000 USD directly and 90,000 through a correctly structured pass-through arrangement, in one single-account category. In the teaching model, how much is outside the 250,000 limit?
5. An on-ramp receives 202 USD, takes 2 USD, sells the token at 1.01 USD and withholds 0.25 tokens for the withdrawal. How much will the customer receive?
6. The refund debt is 75 EUR. The buyer earlier paid 80 USDC; the permissible agreed refund quote is 0.90 EUR/USDC. How many tokens discharge the debt, excluding the network fee? Why do the original 80 not give the answer?
7. A card is frozen after an auth of 90, then a clearing of 85 arrives. Can you delete the 90 from the books and ignore the 85?
8. Credit limit 2,000, debt 600, hold 250. After a capture of 230 and full release of the hold, what are the debt and the available amount?
9. In the 5.5 economics, fraud is 0.35% and all other numbers are unchanged. What is the result? Will it change by the full amount when a refundable reserve of 30,000 is placed?
10. A customer sent a new refund address and proved control of it with a signature. Is that enough for a refund on that specific old order?

## Answers and grading criteria

1. You need the legal debtor/contract and the actual product type; the bank and the ownership/register structure; the applicable insurance conditions, the event and aggregation. Where the money sits does not give all three answers.
2. Pool 700; Anna 550, Boris 150; Anna available 550 / held 0. Releasing the hold did not increase the total owed to customers.
3. B+C can reach the threshold without A unless the mechanism has other restrictions. Recovery/admin rights need to be examined. National legal status does not follow from a threshold formula alone.
4. The combined position is 270,000; 20,000 is outside the limit under the given assumptions. The app's failure on its own is not the same as the bank's failure.
5. 200 / 1.01 − 0.25 ≈ **197.769802 tokens**, rounded to six decimal places. The exchange fee is in USD, the withdrawal fee in the token.
6. 75 / 0.90 ≈ **83.333333 USDC**, rounding to the nearest value with six decimal places; for full coverage with no underpayment allowed, **83.333334 USDC**, rounding up. The debt is set in EUR; the past token amount does not determine the current cost of discharging it. That this refund method is permissible is deliberately assumed here.
7. No. You need to link the clearing to the authorization, recognize the 85 under the appropriate model and release the unused 5. A card freeze does not prove the absence of an old obligation.
8. Before capture, 1,150 is available; after it, the debt is 830, available is 1,170, hold 0. No credit repayment took place.
9. Losses 3,500; expenses 8,900; result **900 USD**. A refundable reserve changes free liquidity and the structure of assets, not automatically profit by 30,000; possible expenses/impairment are considered separately.
10. No. The signature confirms control of the new destination, but by itself does not link the person to the right to a refund for the earlier purchase. You need a verifiable principal↔order↔refund instruction link and valid authority.

## Summary, connections and limits of this version

An account is defined by the obligation and the contract; a wallet, by the asset, access management and recovery. A ramp connects several money stages. A refund discharges a separate obligation. A card program services a much longer cycle than the lifetime of its card details.

Next: [Chapter 3](../03-Visa-and-Mastercard-cards/README.md) — the scheme and the credential; [4.6](../04-Payment-providers/README.md) — sponsorship; [Chapter 6](../06-Crypto-and-stablecoins/README.md) — stablecoins, networks and treasury; [Chapter 7](../07-AI-agent-payments/README.md) — agent authority; [8.5–8.6](../08-Integrations-and-reliability/README.md) — ledger, reconciliation and recovery.

Limitations: part of the EBA/FDIC material is accessible through a search index; this way of reading is explicitly marked. The full text of the EBA Travel Rule Guidelines was not read, so no specific thresholds/procedures are stated here. There is no national insolvency opinion on a specific EMI/CASP, and no audit of custody or of recovery for a specific wallet. Public APIs and contracts do not establish commercial availability, SLAs or the applicable terms for a specific customer. Dynamic documents have not been pinned to a verified commit/hash. The 2016 academic example and the 2024 Reddit case are historical cases with the stated limits. All money calculations are synthetic; real financial and legal decisions require review by qualified professionals.

---

### Sources and fact-check

[Sources](Sources.md) · [Verifiable claims](Claims.md) · [Chapter fact-check](../../Fact-check/05-Wallets-accounts-and-cards/README.md)

The text was prepared by agents and passed an independent agent review on 15–17 September 2026. The teaching edition has limitations; dates and limits of applicability are given in the sources. [Edition record](../../Methodology/Edition-record.md).

<details>
<summary>History and metadata of the original manuscript</summary>

This information describes the research stage before publication. Current visibility is public; the status of the whole edition is `reviewed_with_limitations`. The earlier labels `private` and `independently_reviewed_draft` are kept only as history.

**Version:** v0.1. **Status:** independently_reviewed_draft. **Author:** researcher part_05_research. **Knowledge cutoff and date written:** 2026-09-15. **Visibility:** private. First review: see REVIEW.md (historical or internal material; kept by the owner, outside this copy).

</details>

[← Payment providers](../04-Payment-providers/README.md) · [Contents](../README.md) · [Crypto and stablecoins →](../06-Crypto-and-stablecoins/README.md)
