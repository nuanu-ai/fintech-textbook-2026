---
title: "FinTech 2026 — knowledge map and payments specialization · v02"
date: "2026-09-15"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Public edition of 2026-09-18. Verification dates and source limitations are preserved. Hashes in historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](Edition-record.md).

> Historical table of contents as of 2026-09-15. Mentions of unwritten chapters describe the state on that date; the current 10 chapters and the final audit are available from the knowledge base's table of contents.

# FinTech 2026 — knowledge map and payments specialization · v02

**Date:** 2026-09-15. **Visibility:** private. **Status:** working editorial structure; the chapters have not yet been filled in.

**Purpose:** a knowledge base for self-study by people and agents: explanations, verifiable sources, examples, exercises and separate PDF chapters. A general overview of fintech + an in-depth block on payments, accounts, stablecoins and agentic commerce is the recommended scope; this is not an approval of a new Lab product direction.

**Basis:** v01.1 (10 parts, 58 modules), preserved unchanged. Three independent reviews were carried out: subject coverage, learning and sources. The outcome and the grounds for the edits are in STRUCTURE_REVIEW (historical or internal material; kept by the owner, outside this copy).

**What changed:** added money/accounting basics, an overview of the other areas of fintech, issuing, a detailed ledger and reliability; expanded bank rails/open banking, end-to-end cases and the source schema. The numbers of existing modules are preserved. The reading order of chapters is set out separately from the topic IDs.

**Working boundary:** the map makes it possible to start collecting sources; it does not mean that all 2026 rules and products have already been verified. This is a historical plan as of 2026-09-15; the state of the public edition is described in the edition record.

---

## How to read this structure

| Layer | What it is |
|---|---|
| **Part** | A large block of the big picture (0–9) |
| **Module** | A learning question with its own prerequisites and outcome; several modules can form one PDF chapter |
| **Subtopic** | An atom: one question / one mechanism / one risk |
| **Depth** | The "deep enough" criterion for the module |
| **→ dataset** | Types of artifacts for the source corpus (not a URL dump) |

**Fill statuses:** `outline_only` · `sources_in_progress` · `sources_ready` · `draft` · `reviewed` · `pdf_verified`. The status refers to a specific module/version; a teaching chapter being ready does not change the Lab's canon of decisions.

**Knowledge base rule:** first we explain the mechanism and its limits, then apply it to a task. Lab cases are moved to an applied layer; general theory must not be used to prove a product chosen in advance. Geographies and brands are dated examples. Each mechanism has one main module; other chapters link to it.

---

## Part 0. Course map and method

### 0.1 How to use this textbook
- The big picture vs a product portfolio (mandatory vs optional)
- The boundary: theory / working_hypothesis / execution ticket
- Linking with other research through sources; a company's internal decision and a legal rule are different kinds of documents. Internal approval does not turn research into law.

### 0.2 The "textbook from research" method
- Primary vs secondary sources vs vendor marketing
- Claim → evidence → confidence; no citation theater
- For payment mechanisms — diagrams of money and liability; for methodology and comparisons — a suitable table, concept map or source analysis
- "Deep enough" = role + money + risk + regulatory lever, without a vendor slide

**Depth:** distinguish a product claim from a legal rule and from market practice.  
**→ dataset:** source checklist; evidence row template.

### 0.3 Glossary and units
- Money movement vs payment instruction vs settlement vs clearing
- MoR / PayFac / PSP / acquirer / issuer / scheme / processor / gateway / ISO
- Fiat rail / crypto rail / stablecoin / EMT / e-money / CBDC
- Custody / control of funds / AML trigger points
- Dual-message vs single-message; APM; QR as a way of presenting payment data, while the underlying scheme/rail is a separate question

**Depth:** term = definition + "what it is not" + a card example + a crypto example.  
**→ dataset:** glossary seed; forbidden trap synonyms.

---

### 0.4 Basics of money, banks and financial risk
- Cash, central bank reserves, bank deposits, e-money and stablecoins: whose obligation the holder receives.
- Assets, liabilities and equity; a bank's balance sheet and a customer's balance in a simple example.
- Credit, deposit creation, liquidity and solvency — the teaching minimum.
- Interest, basis points, FX quote, spread, time and the value of money; units and rounding.
- Credit, liquidity, market, operational and legal risk: where they arise in a single payment.

**Depth:** explain a transfer between two banks on their balance sheets; show why a customer's balance and the banks' settlement asset are different entries.  
**→ dataset:** central bank materials on money, BIS/CPMI, an open introductory course in finance.

### 0.5 Accounting for money: a first ledger
- Double-entry bookkeeping, the journal of transactions and accounts; debit/credit depend on the account type.
- Ledger balance, available balance, hold/pending; customer money and platform revenue.
- Purchase, fee, payout and refund with synthetic numbers; currencies are counted separately.
- Internal accounting, the bank statement and provider data: reconciliation, not choosing the convenient version.

**Depth:** build a small journal and find a mismatch without losing money; the complex multi-currency case is in 8.5.  
**→ dataset:** open accounting courses, primary documents of ledger/reconciliation systems with their model stated.

### 0.6 A map of fintech beyond payments
- Digital banking / neobanks / BaaS: interface, balance and regulated principal.
- Lending / BNPL / credit scoring: origination, servicing, delinquency, collection; funding and credit risk.
- Investing / wealthtech / capital markets: broker, exchange, custody, clearing; payment and the purchase of an asset.
- Insurtech: insurance risk, underwriting, distribution, premium and claim payout.
- RegTech / SupTech / open finance / financial data: data, consent, models and oversight.
- Financial inclusion, competition, safety and customer protection as criteria of fintech's usefulness.

**Depth:** for each area, name the customer's problem, the business model, the risk holder and the link to payments. This is an overview map; in-depth volumes on these areas are not yet part of the payments specialization.  
**→ dataset:** IMF/World Bank/BIS, the relevant regulators and university courses; empirical studies with methodology.

---

## Part 1. Legal / regulation / licenses / geographies

### 1.1 The regulator's logic (not a list of abbreviations)
- What it protects: client money, AML/CFT, the consumer, the payments market, stability
- Activity-based vs entity-based
- When "software" becomes a payment service
- Extraterritoriality and "where the service takes place"
- B2C vs B2B: where consumer law kicks in

**Depth:** for any setup — 2–3 regulatory questions (who holds the money / who the customer is / which geography).  
**→ dataset:** statutes / guidance; an activity→license matrix.

### 1.2 Types of licenses and roles (a map of authorizations)
- Distinguish a license, a registration, a type of activity and a commercial name: bank / EMI / PI / MSB / VASP / CASP / current BI categories and local equivalents. SSP is a label for a business role, not a universal license.
- Actions: accept / hold / transfer / convert / payout / issue
- Outsourcing vs agent vs white-label
- When a partner "covers" the license and when you are inside the perimeter

**Depth:** a table "action × license × whose balance sheet × who is liable to the customer".  
**→ dataset:** license taxonomy; official glossaries.

### 1.3 Five teaching models for organizing payment acceptance
1. Software connector (you don't touch the money)
2. Direct merchant–PSP
3. Platform / PayFac
4. Merchant of Record / reseller
5. Own payment stack / custody

This is a working typology, not an exhaustive legal classification: a platform is not always a PayFac, an MoR is not always a simple reseller, own technology is not always custody. Check the seller, the regulated principal, control of funds and the role in the card scheme separately.

For each: the contracting parties, the money flow, the claims flow (refund/chargeback/consumer redress), AML ownership, what must not be promised in the offer.

**Depth:** two diagrams per model (contracts + money) + pitch prohibitions.  
**→ dataset:** public ToS/Connect/PayFac disclosures as reading benchmarks.

### 1.4 Geographies — screening (mandatory minimum)
The same template for each geography:
(1) regulator(s) (2) activity→permission (3) crypto/stablecoin/CBDC status (4) card acquiring (5) local fiat payout / APM/QR (6) permissible partner models and their limits (7) open questions for counsel

#### 1.4.1 USA
- FinCEN MSB registration; state money transmitter licensing; bank partnership; the current federal stablecoin framework — check official acts and dates, without drawing conclusions from the name of a registration
- Cards vs stablecoin vs crypto broker
- Interstate; custodial wallet; consumer protection hooks (federal/state)

#### 1.4.2 EU / EEA
- Payment services framework: distinguish rules in force from the PSD3/PSR reforms; record adoption, entry into force, transitional periods; EMI/PI and SCA
- MiCA: EMT, ART, CASP × payments law
- Passporting / host; consumer / distance selling overlays

#### 1.4.3 UK
- PSRs, EMI, FCA perimeter; post-Brexit differences

#### 1.4.4 Singapore
- MAS PS Act (majors/standards); DPT / stablecoin; the hub/OpCo pattern

#### 1.4.5 Indonesia
- Current BI classification and authorizations, the BI/OJK boundary for assets and services; QRIS and local APMs; foreign PSP constraints; local payout. Do not present historical abbreviations as the current taxonomy without checking.

#### 1.4.6 UAE
- Mainland vs DIFC/ADGM; the separate remits of CBUAE / DFSA / FSRA / VARA and exceptions; check the type of activity, location and crypto perimeter against the primary rules

#### 1.4.7 Expansion (short cards)
- HK, JP, KR, AU, BR, TR, CIS-adjacent — only risk flags + license type, without false completeness

**→ dataset:** primary acts + FAQ + registers; geo matrix CSV.

### 1.5 AML / KYC / sanctions / travel rule
- CDD / EDD; UBO
- Travel Rule (VASP) × bank rails
- Sanctions on the on/off-ramp and address screening limits
- Who screens whom in models 1–5
- Monitoring after onboarding: alerts, case management, SAR/STR, recordkeeping, escalation and data quality; specific requirements depend on the jurisdiction

**Depth:** on a crypto→fiat chain — the screening points + who bears a false negative.  
**→ dataset:** FATF; local AML rules of the selected geographies.

### 1.6 Data, PCI, operational resilience
- PCI DSS scope with token / SPT / vault
- GDPR / PDPA and payment logs
- Incident / operational resilience (DORA level as the EU benchmark)

**Depth:** show how the integration changes the PCI scope, the applicable checks and the merchant's remaining obligations; outsourcing does not make liability disappear.  
**→ dataset:** PCI SSC; privacy guidance for payments.

### 1.7 Link to the teaching project: "no license of our own"
- Partner setup vs own stack
- Partner due diligence: permissions, geo, assets, dispute ownership
- The myth "license = product"; the truth: activity + geo + asset + client type

**Depth:** a 1-page partner DD checklist.  
**→ dataset:** public license disclosures; questions for counsel (not answers).

### 1.8 Anatomy of contracts (MSA / acquiring / processing / sponsorship)
- Parties and hierarchy: scheme membership ↔ sponsor bank ↔ acquirer/PSP ↔ sub-merchant ↔ buyer
- Typical packages: MSA, acquiring agreement, payment processing terms, BIN sponsorship, ISA/ISO, marketplace addendum, MoR supply terms
- Key clauses: settlement timing, reserve, chargeback liability, termination for risk, data use, audit, indemnity, flow-down of scheme rules
- "Who signs what" in models 1–5
- What engineers read vs what counsel reads (and where the team gets it wrong)

**Depth:** for the PayFac and MoR models, draw the contract tree + 5 clauses without which a pilot cannot be promised.  
**→ dataset:** public templates/ToS of major PSPs (as a teaching analysis); redacted clause maps.

### 1.9 Consumer redress / distance selling / digital goods
- Chargeback (scheme) ≠ statutory withdrawal / refund right (law)
- EU consumer / distance / digital content overlays (a benchmark; not EU-only thinking)
- Digital goods: delivery proof, access revocation, partial performance
- Crypto/stablecoin checkout: where consumer law "does not fit" with finality
- Complaint handling / ADR as ops, not as PR

**Depth:** a table "type of claim → basis (scheme/law/policy) → who pays → deadline".  
**→ dataset:** consumer regs of the selected geographies; scheme vs statute comparison notes.

---

## Part 2. How transactions work today (fiat / card / bank / APM)

### 2.1 Participants and roles
- Issuer, acquirer, merchant, cardholder, scheme, processor, gateway, ISO
- Sponsor bank / BIN sponsor
- Clearing vs settlement vs funding

**Depth:** an E2E purchase — who sees the money / data / risk at each hop.

### 2.2 Authorization → clearing → settlement
- Auth request/response; soft vs hard decline
- Capture / void / partial capture / incremental auth
- Batch clearing; net settlement; cut-off; float; FX at settlement
- Prefund vs postfund (where it occurs)

**Depth:** a timeline of one tx with T+ and who owes whom.

### 2.3 Bank payments, instant payments and open banking
#### 2.3.1 Basic mechanics
- Credit transfer vs direct debit: who initiates, mandate/consent, returns and recalls.
- RTGS vs deferred net settlement; settlement asset, participant access, cut-off and liquidity.
- ACH, SEPA, Faster Payments and local instant systems: comparison classes with regional exceptions.

#### 2.3.2 Cross-border and messages
- Correspondent banks, nostro/vostro; the chain of fees and FX, pre-funding, corridor availability.
- SWIFT as messaging; the movement/finality of money is checked separately.
- ISO 20022: business message, identifiers, remittance information, status and matching against the statement.
- DvP/PvP as ways to link two legs of execution; the teaching meaning of settlement risk.

#### 2.3.3 Open banking / open finance
- Data access vs payment initiation; the roles of account provider, data recipient and initiator.
- Consent, authentication, authorization, duration and revocation of access; API profile and security profile.
- Pay-by-bank UX: redirect, callbacks, pending, refunds; a transfer can also exist without an open banking API.

#### 2.3.4 Instant payments and choosing a payment method
- Availability, speed, liquidity, confirmation of payee, mistaken transfers and authorized push payment scams.
- A transfer authorized by the customer under deception and an unauthorized payment are different scenarios; the remedies depend on the system.
- Rail selection: full cost, speed, risk, access restrictions, customer experience.

**Depth:** trace a credit transfer and a direct debit, compare an instant payment with a card transaction, explain the separate roles of API/messaging/settlement.  
**→ dataset:** CPMI/PFMI, official rulebooks of the selected systems, ISO 20022, Open Banking standards and security profiles.

### 2.4 Acquiring and pricing
- MDR, interchange, scheme fees, acquirer markup
- IC++ vs blended; non-qualified; cross-border; FX markup
- Chargeback fees / fines as P&L

**Depth:** break "2.9% + $0.30" down into its components without the marketing.

### 2.5 Fraud, 3DS, risk engines
- Liability shift; 3DS2; SCA exemptions
- Velocity, device fingerprint, network tokens
- False positive economics; account takeover, scam/APP fraud, mule accounts and merchant fraud — compare the controls with 2.3.4
- ML/rules: labels, precision/recall, drift, explainability and human review; check effectiveness claims against data

**Depth:** who bears the fraud loss before/after 3DS in typical scenarios.

### 2.6 Refunds, disputes, chargebacks
- Reason codes; representment; arbitration; friendly fraud
- Refund (policy) vs chargeback (scheme) vs statutory redress (1.9)

**Depth:** the dispute state machine + who pays at each step.

### 2.7 Message-level card tech (how auth really "travels")
#### 2.7.1 Dual-message vs single-message
- Which mode is used where; consequences for capture/refund
- Regional / product exceptions (without false global symmetry)

#### 2.7.2 ISO 8583 as a language (teaching minimum)
- MTI; bitmap; key fields (PAN/token, amount, MCC, STAN, RRN, auth code)
- DE55 / EMV data where relevant
- What the gateway hides and what matters for support/recon

#### 2.7.3 AVS, CVV/CVC, 3DS payload in auth
- What is checked at the issuer; how it affects liability
- Network token cryptogram vs PAN+CVV

#### 2.7.4 Response codes and diagnosing declines
- Issuer vs switch vs acquirer decline
- Soft decline → retry / SCA step-up
- How to read a decline without "the bank just doesn't like it"

#### 2.7.5 Clearing presentment / presentment files (overview)
- What goes to clearing after capture
- Partial / multiple presentment pitfalls

**Depth:** using one live decline and one capture, the team explains the fields/roles without a vendor dashboard.  
**→ dataset:** ISO 8583 primers; scheme tech overviews (public); acquirer response-code guides.

### 2.8 APM, device wallets, QR, BNPL
#### 2.8.1 Device wallets
- Apple Pay / Google Pay: the specific mode and source of credentials; do not assume that network/device token, PAN and cryptogram are the same in all integrations; merchant decryption vs host
- How this changes PCI and 3DS

#### 2.8.2 Account / bank APM
- iDEAL-like, Sofort-like, pay-by-bank — classes, not a brand catalog
- Redirect vs embedded; return URL hell; reconciliation

#### 2.8.3 QR and local rails (especially SEA)
- Consumer-presented vs merchant-presented QR
- The QRIS class (ID) and equivalents: who is the operator, who is the acquirer, settlement in local fiat
- Why a foreign PSP often runs into the need for a local partner

#### 2.8.4 BNPL as a credit product at checkout
- Who lends; who is the MoR; chargeback/refund oddities
- Funding, underwriting, repayment, delinquency and borrower protection; delayed capture on a card is not the BNPL credit model
- Check the availability of a BNPL/crypto-in combination with the specific provider

#### 2.8.5 A rail selection map for the merchant
- Ticket size, geo, dispute need, agent-compatibility, cost

**Depth:** for ID/SEA and the EU, be able to choose a rail and name the dispute gap vs cards.  
**→ dataset:** national QR scheme docs; APM provider primary docs (marketing_risk tag); device wallet merchant guides.

**→ dataset for sections 2.1–2.6:** scheme regs excerpts; NPSO docs; interchange tables; EMVCo 3DS; chargeback guides.

---

## Part 3. Visa, Mastercard and scheme nuances

### 3.1 The scheme as an institution
- Rules vs local law
- Membership: issue / acquire rights
- Brand vs network vs processor
- Why "connecting to Visa" ≠ "becoming Visa"

**→ dataset:** membership overviews.

### 3.2 Visa — in detail
#### 3.2.1 Product map
- Consumer debit/credit/prepaid; commercial / fleet / virtual
- Product ID / interchange qualification basics

#### 3.2.2 Network and messages
- VisaNet overview; dual-message dominance and exceptions
- Auth → clearing → settlement timing (teaching version)

#### 3.2.3 Tokenization
- VTS; PAR; cryptogram; device vs merchant COF tokens
- Guest checkout vs COF

#### 3.2.4 Push / original credit / payout-adjacent
- Visa Direct / the OCT class: use cases, risk, compliance overlays
- How it differs from an ordinary purchase auth

#### 3.2.5 Cross-border, DCC, multicurrency
- Who sets FX; merchant vs cardholder DCC conflict
- Cross-border interchange / scheme fee hooks

#### 3.2.6 Fees and economics (scheme)
- Interchange categories (high-level map, not memorizing the whole table)
- Scheme fees / assessments; acquirer pass-through

#### 3.2.7 Disputes flavor (Visa)
- Reason code families; timeframes; compelling evidence patterns
- Collaboration / pre-dispute tools; Verifi / Order Insight as a specific example from the Visa ecosystem, with a separate check of supported schemes and terms

#### 3.2.8 Compliance / MCC / programs
- MCC risk; registration programs; brand protection

**Depth 3.2:** the team distinguishes purchase vs OCT, token vs PAN, and names 3 Visa-specific cost/risk levers.

### 3.3 Mastercard — in detail (without false symmetry)
#### 3.3.1 Product map
- Debit/credit/prepaid/commercial; regional brands where relevant

#### 3.3.2 Messages and settlement
- Dual vs single-message reality; what changes for capture/refund
- Clearing/settlement differences that integrations trip over

#### 3.3.3 Tokenization
- MDES; differences from VTS at the merchant integration level

#### 3.3.4 Push / Mastercard Send / payout-adjacent
- Use cases; compliance; when it is not "just a refund"

#### 3.3.5 Cross-border / FX
- Parallels with and differences from Visa (as an explicit list, not "similarly")

#### 3.3.6 Fees / interchange map (high-level)
- Where qualification breaks; digital goods pitfalls

#### 3.3.7 Disputes flavor (Mastercard)
- Reason families; arbitration path differences worth knowing
- Ethoca / Consumer Clarity-class tools: the owner, supported schemes, integration and current availability are checked separately

#### 3.3.8 Compliance / MCC / programs
- High-risk registration; brand rules impacting crypto-adjacent

**Depth 3.3:** compare Visa/MC along the same axes; record confirmed differences and similarities with their product consequences. There is no quota on the number of differences; the absence of a public specification is a gap, not a reason to invent a difference.

### 3.4 Adjacent schemes
- Amex / Discover / UnionPay / JCB
- Local debit schemes; when a local scheme is mandatory
- Co-badging

**Depth 3.2–3.4:** a table of auth model / token / push / dispute / geo strength.

### 3.5 Network tokens, COF, subscriptions
- COF / MIT / CIT; stored credential framework
- Account updater
- Agentic / delegated auth preview → Part 7
- Recurring + SCA exemptions (where applicable)

### 3.6 MCC, prohibited, high-risk
- Who assigns the MCC; mismatch risk
- Crypto, adult, gaming, digital goods
- Scheme vs acquirer vs sponsor policy blocks
- Registration programs

**Depth:** digital goods + crypto-adjacent — where exactly the stop is.  
**→ dataset for Part 3:** operating regs public excerpts; product rules; token docs; MCC/prohibited lists; chargeback guides.

---

## Part 4. PSPs, platforms, PayFac, MoR

### 4.1 Classifying providers
- Gateway-only vs full-stack PSP
- PayFac; marketplace/platform; MoR/SoR
- Orchestration / smart routing layers

**Depth:** who is the MoR for the scheme and who for the buyer.

### 4.2 Underwriting and onboarding
- KYB / UBO; rolling reserve; delayed payout
- Matching MCC / URL / product / geo

### 4.3 Settlement to the merchant
- Gross vs net; schedules; split; failed payout / return

### 4.4 PSP economics
- Take rate stack; IC++ pass-through
- Loss rates (fraud + CB + credit)
- Low-ticket digital traps; APM mix effects

**Depth:** all-in cost of card / A2A / QR / crypto-ramp on a single ticket.

### 4.5 Link to the teaching project: ordinary PSP + crypto acceptance
- A matrix of the verified capabilities of a specific PSP: fiat, crypto-in, delegation, settlement, eligibility and geographies
- Connector vs SSP/VASP partner vs MoR
- The offer: "we accept USDT" ≠ "we are a VASP everywhere"
- Decision tree crypto-in/fiat-out → models 1–5

### 4.6 Sponsorship and bank partnership economics
- Issuing BIN sponsorship, acquiring/PayFac sponsorship and BaaS bank partnership: separate roles and contracts; the shared term sponsor does not make them interchangeable
- Scheme access and settlement bank; an allocation of control, not a universal "compliance umbrella"
- Who underwrites sub-merchants in acquiring; who is responsible for cardholders/the program in issuing (see 5.5)
- Economics: sponsor fee, residuals, reserve, termination risk
- Risk concentration: one sponsor switches you off — the volume dies
- How bank partnership (a US pattern) differs from EU EMI/PI passporting
- Due diligence: audit rights, flow-down, notification of scheme programs

**Depth:** explain the P&L and the kill-switch dependence on the sponsor in simple terms.  
**→ dataset:** public sponsor/PayFac disclosures; partnership program overviews.

---

## Part 5. Wallets, accounts, money storage

### 5.1 Types of wallets and accounts
- Bank / e-money / payment account
- Custodial crypto / non-custodial / smart account
- Closed-loop vs open-loop; stored value / gift / payroll

### 5.2 Control of keys and balance
- Custody spectrum; MPC / MPC-aaS
- "Not your keys" vs regulator view
- Safeguarding / bankruptcy remoteness (EMI)

### 5.3 On-ramp / off-ramp
- Card→crypto; bank→crypto; crypto→bank/fiat
- Liquidity, spread, Travel Rule on the ramp
- Stablecoin as a unit vs a speculative asset

### 5.4 Refunds and reversibility
- Settlement finality; card refund/chargeback and bank recall as different processes. A claim for a refund does not mean that the finality of the original settlement is undone
- The UX lie "just like a card" on an irreversible rail

**Depth:** wallet model → safeguarding / AML / consumer redress. Analyze deposit insurance, safeguarding and insolvency treatment separately; the mechanism and limitations depend on the specific jurisdiction.  
**→ dataset:** wallet disclosures; e-money safeguarding rules.

---

### 5.5 Issuing and the card product lifecycle
- Issuer, program manager, processor, BIN sponsor and cardholder: role and responsibility.
- Debit / prepaid / credit, funding source, virtual/physical card, provisioning and the credential lifecycle.
- Balance/hold, authorization controls, card freeze, replacement, disputes and program closure.
- Issuing economics: interchange revenue, processor/sponsor fees, fraud, service cost; the link to acquiring is in 2.4.

**Depth:** draw a card program from the cardholder's and the issuer's side, without substituting a diagram of merchant payment acceptance for it.  
**→ dataset:** scheme issuing docs and public cardholder/program agreements.

---

## Part 6. Crypto rails, stablecoins, CBDC (the payments angle)

### 6.1 Assets for payments
- Separate the network, the settlement asset and the unit of account: Bitcoin/Ethereum are examples of networks, BTC/ETH/USDT/USDC are examples of assets; current issuers/networks are checked against the source
- EMT / regulated stablecoin vs unregulated
- Bridged vs native stablecoin risk
- Depeg, freeze, blacklist — ops risk
- Issuer vs distributor vs merchant acceptor roles

### 6.2 On-chain payment mechanics
- Address / memo / invoice; confirmation depth
- Gas, batching, L2; watchers; recon; double-pay
- Reorgs, bridge/sequencer/RPC dependencies; observed/confirmed/finalized and the specific network parameters; recovery when the result is uncertain
- Invoice protocols vs "just an address"

### 6.3 Stablecoin settlement services
- SSP / treasury partners
- Mint/redeem vs secondary liquidity
- Reserve, the right to claim and redeem, access to redemption, issuer and custodians; attestation vs audit, disclosure scope and insolvency risk
- Corporate treasury vs consumer checkout

### 6.4 Crypto→fiat for the merchant (payment project)
- Accept → convert → settle fiat
- The client: agent / end-user / merchant
- Rate lock timing; spread; refunds after conversion
- Accounting/tax flags (a map of questions, not advice)
- Dispute gaps vs card world

**Depth:** the full chain of roles/balances/AML/refund gap.

### 6.5 Compliance on crypto rails
- VASP/CASP triggers; Travel Rule patterns
- Address sanctions; chain analytics limits

### 6.6 Myths to kill
- "Stablecoin = e-money everywhere"
- "On-chain receipt = chargeback"
- "One license = the world"
- "CBDC = USDT from the state" (see 6.8)

### 6.7 Treasury / FX / nostro in crypto→fiat ops
- Where the liquidity sits: crypto inventory vs fiat float
- Rate sources; slippage; weekend/gap risk
- Nostro/vostro and settlement banks in the off-ramp
- Pre-funding the partner vs just-in-time convert
- Hedging (only a map of ideas; not a trading desk textbook)
- Ops controls: exposure limits, break-glass halt, recon of gas+FX+fee
- P&L stack: network fee + convert spread + payout fee + failure cost

**Depth:** draw the daily treasury cycle for merchant settlement without "exchange-rate magic".  
**→ dataset:** SSP/treasury partner docs; bank payout SLAs; internal pilot assumptions as secondary.

### 6.8 CBDC — a 2026 card
- What CBDCs promise (retail vs wholesale)
- What a CBDC is not: not a market stablecoin, not "crypto is free", not a universal API
- Status: pilots / live / none — by geography from 1.4 (without a fake global map)
- Payments angle: merchant acceptance, offline, privacy, intermediary role
- Impact on PSP/agentic: hypotheses for now, not a Lab product roadmap

**Depth:** explain the differences between CBDC / EMT / bank deposit / cash on a single diagram.  
**→ dataset:** central bank papers of the selected geographies; BIS overviews; tag `status=pilot|live|research`.

**→ dataset 6.1–6.6:** MiCA EMT; MAS stablecoin; vendor settlement docs; public primary sources and the author's teaching examples.

---

## Part 7. Agentic / machine payments and protocols

### 7.1 Why agents break checkout
- API-only, browser-driven and human-assisted agents: different capabilities; the absence of a browser cannot be assumed to be a property of all agents
- Delegated intent, authentication/3DS, human confirmation and an unreachable challenge are separate questions
- Credentials delegation; spend limits
- Principal vs agent confusion (detail in 7.6)

### 7.2 The card market's responses
- Shared Payment Tokens / network tokens for agents
- Agentic commerce products: announcement / private preview / public preview / GA — the date, geo and eligibility of each; product maturity and standard status are different axes
- UCP / ACP and their neighbors: the task level, publisher/governance, version, implementation and specification status are checked against the original

### 7.3 Machine-native protocols
- HTTP 402 / x402: the idea, the flow, what is standardized
- MPP and other named protocols: the expansion of the name, the publisher, the version and a working primary URL are mandatory; mark an unknown status as open
- Agent accounts, micropayments, prepaid credits

**Depth:** protocol ≠ PSP product ≠ license.

### 7.4 Crypto-native agent pay → merchant fiat
- Stablecoin in → convert → fiat out
- MoR vs direct merchant vs PSP connector
- Catalog/order API ≠ payment rail

### 7.5 Risk & liability
- Unauthorized agent spend; replay; prompt injection → payment instruction
- Who is MoR when agent buys
- Threat model → mapping onto the models in 1.3

### 7.6 Agent identity vs principal
- Who is the subject of KYC/KYB: the user, the agent operator, the platform, the wallet
- Agent authentication: keys, attested runtime, OAuth-like delegation — classes of mechanisms
- Authorization: spend policy, merchant allowlist, velocity, geo, asset allowlist
- Audit trail: who instructed the payment (human intent evidence)
- Liability allocation: principal / agent vendor / PSP / merchant
- When an agent = "a new fraud channel" rather than "a new UX"
- Link to Travel Rule / sanctions: whose wallet?

**Depth:** a one-page RACI for KYC + spend control + dispute for agentic crypto→fiat.  
**→ dataset:** security/delegation notes; scheme agentic pilots; the author's teaching notes as secondary material.

---

## Part 8. Integrations, product and operations

### 8.1 Commerce platforms
- WooCommerce REST / Store API: catalog, order, webhooks
- Shopify / custom headless
- What the platform does / does not provide in payments

### 8.2 Connector design
- Idempotency; webhooks; reconciliation keys
- Internal ledger vs PSP statements; the basic model is in 0.5, detailed accounting in 8.5
- Partial failures (paid on-chain, order not created)

### 8.3 Reporting, reconciliation, ops
- Daily settlement files; exception queues
- Support: "the money left, the goods were not delivered"
- Treasury break-glass (link to 6.7)

### 8.4 Go-to-market claims hygiene
- Claims by models 1–5; geo without "worldwide"
- Preview ≠ GA; APM list hygiene

**Depth:** pilot checklist = legal model + rail + geo + claims + kill criteria.

---

### 8.5 Ledger, reconciliation and financial invariants
- Journal/subledger/general ledger; an event log and an accounting entry are different objects.
- Pending/posted/available, fees, reserve, refund, chargeback and negative balance; correction by a reversing entry.
- Identifiers for the order, the payment attempt, settlement and payout; idempotency and the duplicate boundary.
- Three-way reconciliation: internal ledger, PSP/network, bank/on-chain; discrepancies, aging and close.
- Multi-currency: amount/currency, decimal precision, FX and separate accounting for fees/conversion.
- Unknown result: query/reconcile, then decide; do not create a second payment with a blind retry.

**Depth:** go through one cycle of sale → fee → payout → partial refund, then find a missing/duplicate event. Totals reconcile with an external source; a balanced ledger by itself does not prove that the money is in the bank.  
**→ dataset:** primary accounting/reconciliation docs, synthetic teaching statements and a journal.

### 8.6 Reliability, security and recovery
- Duplicate/out-of-order webhooks, timeout after sending, retries, idempotency window, confirmation of the result.
- Webhook authentication, replay protection, permissions, secrets and control over changes to payment details.
- Availability vs safety of funds; monitoring and alerts on lost/duplicated execution.
- Incident response, recovery, backup/restore, an exit plan if a provider is lost; user support.
- Moving from declared success to proof: ledger + external settlement + order fulfillment.

**Depth:** analyze a provider failure in the middle of a payment with a known and an unknown result; show safe recovery and the link to 1.6.  
**→ dataset:** API/security specifications, public postmortems, regulator resilience guidance.

---

## Part 9. End-to-end practice and application to the payment project

### 9.1 End-to-end map "money × contract × data × license"
- A matrix for typical payment scenarios (incl. QR/APM and agentic)

### 9.2 Working hypotheses (not canon)
- A crypto-in / fiat-out layer for an ordinary PSP
- A partner rail (classes: Bridge-like SSP, Triple-A-like, Coinbase Business-like, CoinGate-like) — not a shortlist without an evidence refresh
- Agentic storefront — separate from the settle stake

### 9.3 What is NOT in textbook v1
- Trading / DeFi yield / token design
- A full tax treatise; in-depth lending / capital markets / insurance — for now only the overview in 0.6
- POS card-present as the core of the course
- Organizations' internal HR and budgeting; third-party environments without the owner's permission

### 9.4 The path structure → dataset → lessons
1. Source registry + claim/evidence links according to the source schema.
2. Three reference modules: **0.5** (accounting), **2.2** (lifecycle), **1.3** (models and liability); test the method on related topics.
3. The next end-to-end module is **6.4**, which builds on wallets, AML, accounting and settlement.
4. Independent review of meaning, sources and exercises; then the PDF and a visual check.
5. Expansion by the packages below. The teaching status reviewed does not mean permission for real operations.

---

### 9.5 End-to-end cases and final review
- One order across different mechanisms: card / bank transfer / QR / stablecoin; the same questions about money, liability and the result.
- A partial refund after FX, failed payout, duplicate webhook and provider shutdown.
- An agent buys digital goods: intent → delegation → order → payment → reconciliation → fulfillment; a disputed/unknown outcome.
- A public incident: timeline, available documents, participants' claims, unknown details; do not infer blame from Reddit/X.
- Application to the teaching project is a separate teaching analysis with working_hypothesis, without carrying it over to the current status of projects.

**Depth:** solve a new case, show the evidence and name the questions for which there is not enough data.  
**→ dataset:** public postmortems/decisions/documents and explicitly synthetic exercises; no production credentials or payments for training.

---

## "Deep enough" criteria (summary)

| Part | Deep enough if the team can… |
|---|---|
| 0 | Explain the kinds of money, simple balance sheets and double-entry bookkeeping; find their way around fintech; check a source |
| 1 | Choose a model 1–5 + geo flags; name the key clauses and consumer vs scheme redress |
| 2 | Break down auth–clear–settle; read a simple decline at the field level; choose APM/QR vs card |
| 3 | Explain the scheme as an institution; compare confirmed Visa/MC similarities/differences; token/push/MCC risk |
| 4 | Build the all-in cost; say who the MoR is; explain the dependence on the BIN sponsor |
| 5 | Classify a wallet and the protection of funds; explain the roles and lifecycle of issuing |
| 6 | Run crypto→fiat with AML/refund/treasury; distinguish CBDC/EMT/deposit |
| 7 | Separate protocol/product/license; RACI for agent identity |
| 8 | Trace money in the ledger, reconcile external data and restore execution after a failure |
| 9 | Solve a new end-to-end case and separate confirmation from unknowns and hypotheses |

**Quality:** definition → mechanism → example → limitations → check of understanding. Formulas with units and meaning; a company name with a specific role; a disputed claim with the limits of knowledge. The diagram is chosen to fit the task; volume and the number of references are not in themselves criteria of depth.

---

## Dataset and knowledge base format

Full schema — [SOURCE_DATASET_SCHEMA.md](Working-with-sources.md); chapter format — [MODULE_TEMPLATE.md](Lesson-template.md).

- Separately: law/regulator, scheme, standard, vendor, research, course, analysis, social (Reddit/X), internal.
- A Source ID describes a specific source and version; a Claim ID is a verifiable claim with links to exact locations.
- Full text, abstract, snippet and a blocked page have different access/review statuses.
- The dates of publication, of a rule being in effect, of the version and of actual reading do not substitute for one another.
- Reddit/X provide practical cases and questions; official announcements on social media are evidence of the announcement, not independent proof of the result.
- The PDF is the readable edition of a chapter; Markdown and the registers preserve editability and the provenance of the material. Other people's PDFs remain sources, not automatically chapters of our book.

## Learning order and future PDF packages

Part numbers are permanent topic addresses. The reading order starts with money and mechanisms, then moves on to roles/law and specializations. No PDF has been created yet; the titles below are a packaging plan, and the volume is determined by how the material hangs together.

| Package | Chapter | Modules | Read first |
|---|---|---|---|
| CH-00 | A map of fintech and working with sources | 0.1, 0.2, 0.3, 0.6 | — |
| CH-01 | Money, balances and a first ledger | 0.4, 0.5 | CH-00 |
| CH-02 | One purchase from request to settlement and refund | 2.1, 2.2, 2.6 | CH-01 |
| CH-03 | Bank transfers and open banking | 2.3 | CH-01, CH-02 |
| CH-04 | Wallet checkout, QR and BNPL | 2.8 | CH-02, CH-03 |
| CH-05 | Roles, business models, contracts and sponsorship | 1.1, 1.2, 1.3, 1.7, 1.8, 4.1, 4.6 | CH-02, CH-03 |
| CH-06 | Six geographies: how to read the rules | 1.4 | CH-05 |
| CH-07 | AML, data, security and customer rights | 1.5, 1.6, 1.9 | CH-05, a selected CH-06 card |
| CH-08 | The card transaction: price, risk, messages and tokens | 2.4, 2.5, 2.7, 3.1, 3.5 | CH-02, CH-05, CH-07 |
| CH-09 | Visa | 3.2 | CH-08 |
| CH-10 | Mastercard | 3.3 | CH-08 |
| CH-11 | Other schemes and MCC | 3.4, 3.6 | CH-08; CH-09/10 for comparisons |
| CH-12 | PSP: onboarding, payouts and economics | 4.2, 4.3, 4.4, 4.5 | CH-05, CH-07, CH-08; 4.5 again after CH-15 |
| CH-13 | Accounts, custody, ramps and issuing | 5.1, 5.2, 5.3, 5.5 | CH-01, CH-05, CH-07, CH-08 |
| CH-14 | Crypto rails, stablecoins and refunds | 5.4, 6.1, 6.2, 6.3, 6.5, 6.6 | CH-03, CH-07, CH-13 |
| CH-15 | Crypto→fiat, treasury and FX | 6.4, 6.7 | CH-12, CH-14 |
| CH-16 | CBDC compared with deposits and stablecoins | 6.8; comparative links to 0.4, 6.1 | CH-01, CH-14 |
| CH-17 | Agentic and machine payments | 7.1–7.6 | CH-05, CH-07, CH-11, CH-15 |
| CH-18 | Integration, accounting, reconciliation and recovery | 8.1–8.6 | CH-01, CH-02, CH-05, CH-07, CH-12; crypto examples after CH-14/15 |
| CH-19 | End-to-end cases and application to the payment project | 9.1–9.5 | selected rails + CH-18; agent case after CH-17 |

Introductory route: CH-00 → CH-01 → CH-02 → CH-03 → CH-05 → one CH-06 card → CH-07. Then specializations by interest. Geographies are separate comparative cards inside CH-06; the first six are kept, and additional ones are not assigned automatically.

Introductory definitions of SCA/3DS in early chapters are given in place; the in-depth technical details are in CH-08. The early 4.5 is only a map of roles; the detailed analysis of crypto→fiat comes after CH-15.

## Order of filling by agents

1. **A limited batch of sources:** for 0.4/0.5, 2.2 and 1.3; a source registry and a list of open questions.
2. **Three sample modules:** 0.5, 2.2, 1.3 using a single template. For each, a researcher/author and a different agent as reviewer; the lead editor aligns terms across modules.
3. **Learning and PDF check:** a new exercise with an answer, verifiable links and a review of the rendered pages. After that, 6.4 as a test of end-to-end coherence.
4. **Filling by packages:** foundations; rails/cards; models/geographies/compliance; accounts/crypto/treasury; agentic; ops/cases. Prerequisites that are discovered are covered before the text that depends on them.
5. **Version index:** each package has a date, status, link to the PDF/source file, gaps and reasons for the next update. Do not confuse sources_ready with a finished chapter.

We do not set the number of pages and references until the three samples exist. The structure describes the content; the result of the current stage is a review and a prepared framework, not a finished textbook.

## Working assumptions

- Recommended scope: an overview of all of fintech and an in-depth payments specialization. Full volumes on lending/investing/insurance would require a separate expansion of the table of contents.
- Geographies: keep US/EU/UK/SG/ID/UAE; for the first practical chapter, pick one specific geography and activity, and do not write a universal legal conclusion.
- CBDC remains a short comparative module; ISO 8583 is an advanced branch after the lifecycle, not the entry point to the course.
- Use previous internal research through evidence rows and external primary sources; do not import unverified text wholesale.

## Review materials

- Final analysis (historical or internal material; kept by the owner, outside this copy).
- Subject-matter review (historical or internal material; kept by the owner, outside this copy).
- Learning review (historical or internal material; kept by the owner, outside this copy).
- Sources and verified inputs (historical or internal material; kept by the owner, outside this copy).
- v01.1 (historical or internal material; kept by the owner, outside this copy) and v01 (historical or internal material; kept by the owner, outside this copy) are the preserved versions.
