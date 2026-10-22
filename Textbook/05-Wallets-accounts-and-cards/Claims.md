---
title: "Chapter 5 — register of material claims"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Wallets, accounts and cards](README.md) · [Contents](../README.md) · [All sources and fact-checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Chapter 5 — register of material claims

**Version:** v0.1. **Status:** independently_reviewed_draft. **Author:** part_05_research. **Knowledge cutoff:** 2026-09-15. First review: see REVIEW.md (historical or internal material; kept by the owner, outside this copy).

The fact-check of the original edition was completed on 2026-09-17. The link between the original version and the public copy, the scope of adaptation and the current navigation are described in the edition record.

## How to read the register

All rows inherit `as_of=2026-09-15`, `last_checked_at=2026-09-15, Asia/Makassar (UTC+08:00)`, `reviewer=see_REVIEW.md`, `review_status=see_REVIEW.md`. `confirmed` means confirmation **within the stated scope**, not an endorsement of implementation or a claim that the conclusion is universal. For non-normative statements `effective_from/to=not_applicable`; an unknown date of a contract/rule is marked `unknown`.

The evidence column gives the source, snapshot and exact section; full direct URLs, the actual extent of reading, the access method and rights are in [Sources](Sources.md). `supports` means the source supports the statement, `context` means grounds for an explicitly authorial conclusion, `contradicts` means a refutation of a stated myth. The chapter's simplified calculations are synthetic scenarios, not empirical provider data.

**General basis for confidence:** a relevant passage of the primary document that was read; for social-media testimony — only the fact that the statement was published; for the academic case — the authors' result in its historical setting. One company's product documents are not independent confirmation of how well it performs. General trigger for re-checking: a change in a rule, document, program, API or jurisdiction, or a new edition of the chapter. Special triggers are given below.

## 5.1 Types of wallets and accounts

| claim_id / module_ids | claim / kind / status | evidence + locator + relation | Scope, conditions and limitations |
|---|---|---|---|
| P05-C001 · 5.1 | EU e-money is a claim on the issuer and is defined by a combination of features of issuance and use. `definition; confirmed` | P05-S001 · P05-S001-20260915 · Final answer, EMD2 Art. 2(2), C-661/22 §§47–48 · supports | EU; Q&A final 2025-01-17. The answer was read through the index; it is an interpretation, not the full national law in force. The effective date of the rule itself was not checked separately. |
| P05-C002 · 5.1 | Classification as a payment account depends on the payment function; a reference account does not settle the question by itself. `definition; confirmed` | P05-S002 · P05-S002-20260915 · Final answer, PSD2 Art. 4(5),(12), C-191/17 · supports | EU; Q&A final 2021-03-12. Does not determine the license of a specific operator. |
| P05-C003 · 5.1 | A gift card can be open-loop; its protections may differ from those of an ordinary prepaid product. `legal; confirmed` | P05-S003 · P05-S003-20260915 · Card types; open-loop/closed-loop; protections · supports | US consumer guidance. Does not carry over to every territory or every gift certificate. |
| P05-C004 · 5.1 | ERC-4337 uses UserOperation, a bundler and EntryPoint; validation rules are set by the account implementation. `mechanism; confirmed` | P05-S009 · P05-S009-20260915 · Abstract; Motivation; Definitions; account context · supports | Specification with a displayed status of Final. The Final date and commit are unknown; no specific deployment was checked. |
| P05-C005 · 5.1 | Identifying a supported token requires the network and the on-network identifier, not just the name USDC. `mechanism; confirmed` | P05-S028 · P05-S028-20260915 · Introduction; Mainnet/Testnet contract tables · supports | Circle publishes different identifiers. This is not proof of support by a specific ramp, or of redemption or reserves. |

## 5.2 Control of keys and the balance

| claim_id / module_ids | claim / kind / status | evidence + locator + relation | Scope, conditions and limitations |
|---|---|---|---|
| P05-C006 · 5.2 | A threshold signature can be produced without reconstructing the full key in one place. `mechanism; confirmed` | P05-S008 · P05-S008-20260915 · Executive Summary, PDF p.7; §1, PDF p.10 · supports | The threshold cryptography model of NISTIR 8214A, 2020. Not a statement about every MPC implementation. |
| P05-C007 · 5.2 | A cryptographic threshold does not by itself determine legal custody or the independence of administrators. `mechanism; confirmed` | P05-S008 · P05-S008-20260915 · §2.5 Auditability, printed p.10/PDF p.19 · context; P05-S012 · P05-S012-20260915 · §§72–75 · context | Authorial conclusion from the difference between the threat model and the functional legal approach. National classification requires its own analysis. |
| P05-C008 · 5.2 | A Privy custodial `owner` does not get the right to transact alone without the custodian or to export the key. `product; confirmed` | P05-S010 · P05-S010-20260915 · Meaning of owner for custodial wallets · supports | Only the described Privy custodial product; other wallet types are not generalized. Page date/version unknown. |
| P05-C009 · 5.2 | Fireblocks describes separate Vault recovery tools, including a scenario in which the provider ceases operations. `product; confirmed` | P05-S011 · P05-S011-20260915 · Overview; Recovery Tools · supports | Public description of Direct Custody/Vault. The existence and a successful test of a specific client's recovery kit are not confirmed. |
| P05-C010 · 5.2 | The possibility of joint control does not rule out VASP classification under the FATF guidance. `legal; confirmed` | P05-S012 · P05-S012-20260915 · §§72–75, footnote 20, printed p.29/PDF pp.30–31 · supports | International guidance from 2021, not national law. The publisher warns of later updates to the standards; numeric thresholds are not carried over from it. |
| P05-C011 · 5.2 | The FDIC insures the relevant deposit if the bank fails, not against the failure of the nonbank app itself. `legal; confirmed` | P05-S004 · P05-S004-20260915 · fintech/nonbank insolvency and placement paragraphs · supports | US FDIC; the conditions for actual placement and coverage must be met. Direct fetch 403; the index representation was read. |
| P05-C012 · 5.2 | Pass-through requires actual ownership by the principal, a recorded agency relationship and proper records of owners/interests. `legal; confirmed` | P05-S005 · P05-S005-20260915 · §III Requirements for Pass-through Deposit Insurance Coverage · supports | US; the source cites 12 CFR 330.5/330.7. The substantive section was read through the index; no specific arrangement was checked. |
| P05-C013 · 5.2 | Pass-through does not create a separate insurance category: one owner's holdings in the same category and bank are aggregated. `legal; confirmed` | P05-S005 · P05-S005-20260915 · §V Aggregation of Deposits · supports | The examples use the single-account category and the 250,000 USD limit. Other categories are not modeled. |
| P05-C014 · 5.2 | UK safeguarding at nonbank PSPs differs from direct FSCS coverage if they become insolvent. `legal; confirmed` | P05-S006 · P05-S006-20260915 · How you're protected; How safeguarding works; How to make a claim · supports | UK EMI/API, with caveats for SPI; the procedure may involve delay and costs. Not an opinion on any specific insolvency. |
| P05-C015 · 5.2 | The supplementary safeguarding regime under FCA PS25/12 began to apply on 2026-05-07. `legal; confirmed` | P05-S007 · P05-S007-20260915 · Next steps; Who this applies to · supports | UK, the listed categories; `effective_from=2026-05-07`, `effective_to=unknown`. The future Post-Repeal Regime is not declared to be already in force. |
| P05-C016 · 5.2 | MiCA requires legal and operational segregation of clients' crypto-assets held in custody within the scope of Article 75. `legal; confirmed` | P05-S013 · P05-S013-20260915 · Art. 75(7); Art. 149; Art. 143(3) · supports | EU MiCA CASPs. General application from 2024-12-30; a national transition may have ended before the general limit of 2026-07-01. Not proof of compliance by any individual CASP. |
| P05-C017 · 5.2 | MiCA custody liability for loss is tied to an incident attributable to the CASP and is capped at the market value at the time of loss. `legal; confirmed` | P05-S013 · P05-S013-20260915 · Art. 75(8) · supports | EU, a specific article. Not deposit insurance and not protection against a price fall. Causation in any specific incident was not examined. |
| P05-C018 · 5.2 | "MPC automatically means non-custodial and regulated protection of assets." `hypothesis; rejected` | P05-S008 · P05-S008-20260915 · §1, §2.5 · contradicts; P05-S010 · P05-S010-20260915 · Meaning of owner · contradicts; P05-S012 · P05-S012-20260915 · §§72–75 · contradicts | The myth conflates the signing mechanism, actual control and the legal regime; there is no single consequence. |

## 5.3 On-ramp / off-ramp

| claim_id / module_ids | claim / kind / status | evidence + locator + relation | Scope, conditions and limitations |
|---|---|---|---|
| P05-C019 · 5.3 | Coinbase may allow trading with funds on hold while keeping the restriction on external sends/withdrawals. `product; confirmed` | P05-S014 · P05-S014-20260915 · Cash deposits on hold; Sends and withdrawals after a deposit hold clears · supports | The described Coinbase account flows. The period for a specific user is not known; not a self-custody protocol. |
| P05-C020 · 5.3 | A Coinbase Offramp Quote is an estimate that does not guarantee the actual execution price. `product; confirmed` | P05-S015 · P05-S015-20260915 · Offramp Quote; Limitations · supports | A specific quote API; country, asset/network and method are part of the conditions. Not a conclusion about every RFQ/rate-lock product. |
| P05-C021 · 5.3 | The EBA Travel Rule guidance describes sender/recipient information and the handling of missing data. `legal; confirmed` | P05-S016 · P05-S016-20260915 · main announcement; Background; Legal basis · supports | EU PSPs/CASPs within the stated scope; the guidelines apply from 2024-12-30. The main PDF was not read: thresholds and detailed procedures are not claimed. |
| P05-C022 · 5.3 | An on/off-ramp requires tracking funding, exchange, withdrawal availability and final receipt separately. `mechanism; confirmed` | P05-S014 · P05-S014-20260915 · Hold periods · context; P05-S015 · P05-S015-20260915 · Request/Response fields, Limitations · context | Authorial state model; a provider may combine or pre-fund stages. The example is not an audit of its implementation. |

## 5.4 Refunds and reversibility

| claim_id / module_ids | claim / kind / status | evidence + locator + relation | Scope, conditions and limitations |
|---|---|---|---|
| P05-C023 · 5.4 | Finality of the original settlement does not by itself extinguish a separately arising refund obligation. `mechanism; confirmed` | P05-S031 · P05-S031-20260915 · Right of withdrawal; Exceptions · context; P05-S017 · P05-S017-20260915 · Return options · context | Authorial synthesis of the difference between the right to claim and the method of performance. The basis, currency, amount and whether a refund in tokens is permissible are determined separately. |
| P05-C024 · 5.4 | Digital content is not a universal exception to the EU right of withdrawal: the conditions of consent and performance matter. `legal; confirmed` | P05-S031 · P05-S031-20260915 · Exceptions, digital content / fully delivered services · supports | EU consumer guidance, last checked 2026-04-28; not the full text of the directive and not an opinion on a contract. |
| P05-C025 · 5.4 | An SCT Request for Recall by the Originator does not guarantee a return and depends on the beneficiary's consent. `legal; confirmed` | P05-S018 · P05-S018-20260915 · 2025 v1.1 §4.3.2.4, printed/PDF p.35 · supports | SEPA SCT EUR; `effective_from=2025-10-05`, `effective_to=unknown`. Not all kinds of Recall/return and not all bank rails. |
| P05-C026 · 5.4 | An outgoing Coinbase sending address does not necessarily belong to the client and is not a safe automatic refund destination. `product; confirmed` | P05-S017 · P05-S017-20260915 · warning; Return options · supports | Transfers from a Coinbase account under the described model; a supported new address still requires checking the authority to receive the refund. |
| P05-C027 · 5.4 | McCorry et al. studied insufficient authentication of refund details in the historical Bitcoin Payment Protocol. `empirical; confirmed` | P05-S026 · P05-S026-20260915 · §§2.2–3, §4 experiments, §§5–5.2, §6 · supports | Authors' version 2016/024, BIP70/processes of the study period. Not an assessment of current vulnerability, the frequency of losses or the industry as a whole. |
| P05-C028 · 5.4 | Proof of control of a new address does not by itself prove the right to a refund for the earlier order. `mechanism; confirmed` | P05-S026 · P05-S026-20260915 · §§5–5.2, linkage/authentication discussion · context | Authorial defensive conclusion: a principal↔order↔instruction link is needed. Not a prescription of a single technical method of identification. |
| P05-C029 · 5.4 | A Reddit author reported Coinbase Card refunds that stayed pending for a long time; participants argued about the support route. `experience; confirmed` | P05-S027 · P05-S027-20260915 · original post u/RandyMachoManSavage; initial comments u/radman430, u/OhmazingJ · supports | The published account is confirmed, not fault/cause. The day 2024-07-16 was inferred from archive navigation; comments show only "2y ago". |
| P05-C030 · 5.4 | Stripe describes the possibility of a double credit when a refund and a parallel dispute occur on a bank debit payment. `product; confirmed` | P05-S030 · P05-S030-20260915 · Bank debit payment methods · supports | Specific Stripe rails. The synthetic 80+80 example is not a statistic and not a universal procedure for debiting the duplicate. |
| P05-C031 · 5.4 | A Stripe card refund may wait for a sufficient available balance; the reference is needed for tracing but does not replace reconciliation with the recipient. `product; confirmed` | P05-S030 · P05-S030-20260915 · Refund requests; Trace a refund · supports/context | The first part is a product description; the reconciliation requirement is an authorial control of the outcome. No universal refund SLA has been established. |

## 5.5 Issuing and the card product lifecycle

| claim_id / module_ids | claim / kind / status | evidence + locator + relation | Scope, conditions and limitations |
|---|---|---|---|
| P05-C032 · 5.5 | Stripe processor-only does not use a central Issuing Balance; the program and the sponsor arrange funding and the settlement account. `product; confirmed` | P05-S022 · P05-S022-20260915 · Overview; program/funding responsibilities; BIN sponsor settlement · supports | Only the processor-only configuration. Do not carry the model over to integrated Issuing. Availability of the contract to a new client was not checked. |
| P05-C033 · 5.5 | VisaNet Connect Issuing describes separate capabilities for authorization, completion, return and provisioning. `product; confirmed` | P05-S025 · P05-S025-20260915 · How it Works; APIs Used · supports | Official overview, not the full Visa rulebook/access to closed specifications. A capability does not mean program approval. |
| P05-C034 · 5.5 | The available US Coinbase Card Agreement names Pathward as issuer, Marqeta as program manager and the product as prepaid. `product; confirmed` | P05-S019 · P05-S019-20260915 · short form; definitions; §1, PDF pp.1–2 · supports | US personal/family/household program. Date, edition and effective date unknown; no specific user's signed agreement was checked. |
| P05-C035 · 5.5 | Debit in Coinbase Help and prepaid in the agreement describe this product from different angles. `definition; confirmed` | P05-S032 · P05-S032-20260915 · opening; issuer disclosure · context; P05-S019 · P05-S019-20260915 · §1 · context | The apparent mismatch in terms is resolved through the specific agreement, without concluding that it is a deposit account. Not Coinbase One credit and not a worldwide classification. |
| P05-C036 · 5.5 | Stripe Issuing supports holds and incremental/partial authorization; the final amount may differ. `product; confirmed` | P05-S020 · P05-S020-20260915 · Authorization lifecycle; partial/incremental authorization; currency conversion · supports | API states table — 2025-03-31.basil and newer. The teaching journal entry is not the same as an API object or network settlement. |
| P05-C037 · 5.5 | Marqeta Gateway JIT lets the program take part in funding the transaction; the outcome must be reconciled against notifications. `product; confirmed` | P05-S023 · P05-S023-20260915 · Concepts/JIT Funding · supports; P05-S024 · P05-S024-20260915 · JIT Funding notifications · supports | Gateway JIT; a local approve may not reach the processor. Not an unsecured credit line and not a general model for all issuing. |
| P05-C038 · 5.5 | Stripe Issuing card status and spending controls do not apply to a subsequent capture. `product; confirmed` | P05-S021 · P05-S021-20260915 · introduction, capture controls note · supports | Stripe Issuing; a freeze does not cancel a money obligation that arose earlier. For other processors, the rules need to be checked. |
| P05-C039 · 5.5 | Stripe Issuing can accept refunds to inactive/canceled cards. `product; confirmed` | P05-S021 · P05-S021-20260915 · Handling other transactions: Refunds · supports | The described capability does not guarantee a correct bank/internal route for any real refund. |
| P05-C040 · 5.5 | Stripe replacements for lost/stolen cards issue new credentials; authorizations opened earlier may complete on the original card. `product; confirmed` | P05-S029 · P05-S029-20260915 · replacement scenarios; All replacements · supports | Only the described product. Expired/damaged and card-on-file updates have different conditions; actual delivery was not checked. |
| P05-C041 · 5.5 | Under the §10(b) that was read, closing a Coinbase Card preserves rights and obligations that arose earlier. `legal; confirmed` | P05-S019 · P05-S019-20260915 · §10(b), PDF p.5 · supports | The same available US agreement; effective date unknown. Not proof of the version that applied to the Reddit author in 2024. |
| P05-C042 · 5.5 | Coinbase Wallet in this agreement is a defined linked account; the word does not prove self-custody. `definition; confirmed` | P05-S019 · P05-S019-20260915 · definitions, PDF pp.1–2; §9(b), PDF p.5 · supports | Within the US agreement. A received card refund is transferred there; not any Coinbase account or the app of the same name. |

## Open boundaries and authorial models

| claim_id / module_ids | claim / kind / status | evidence + locator + relation | Scope, conditions and further checking |
|---|---|---|---|
| P05-C043 · 5.4 | The proposed refund state model helps avoid closing the debt before performance is verified. `hypothesis; working_hypothesis` | P05-S030 · P05-S030-20260915 · events; failed refunds; tracing · context; P05-S026 · P05-S026-20260915 · §§5–5.2 · context | An authorial teaching control; universal effectiveness not proven. To be tested on test scenarios of a duplicate, unknown and partial refund. |
| P05-C044 · 5.2, 5.5 | The availability and successful recovery of a specific custody/issuing product for a specific user have not been established. `product; open` | P05-S011 · P05-S011-20260915 · Recovery Tools · context; P05-S022 · P05-S022-20260915 · setup/program responsibilities · context | Public documents do not replace the applicable contract, an eligibility check and a technical test. Real transactions were not part of the research. |

## Addendum to 5.3 after aligning the chapters

| claim_id / module_ids | claim / kind / status | evidence + locator + relation | Scope, conditions and limitations |
|---|---|---|---|
| P05-C045 · 5.3 | Circle France provides a separate redemption path for EEA Retail Holders via a form and checks. `product; confirmed` | P05-S033 · P05-S033-20260917 · §§1.4, 2.1–2.3, 3 · supports | When read on 17 September, the policy was marked 2026-09-15; earlier the author recorded 13 July; no historical snapshot exists. EEA IBAN and eligibility matter. Not a worldwide institutional-only rule and not confirmation that a specific request was executed. |

## Author's check before handoff

Checked: consistency of module IDs, linkage of source identifiers, direct links in the chapter and the arithmetic of the synthetic examples. Reddit testimony is not used to draw conclusions about the cause of a failure; the historical paper is not presented as a modern vulnerability assessment. No unresolved contradiction is left hidden behind a universal legal conclusion; the debit/prepaid names and access limitations are stated explicitly. An independent reviewer must re-assess whether the statements match the passages read and whether access was sufficient; the author does not mark their own work `checked`.
