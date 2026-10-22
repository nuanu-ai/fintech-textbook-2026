---
title: "Claims register for Chapter 2"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← How a payment works](README.md) · [Contents](../README.md) · [All sources and fact-checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Claims register for Chapter 2

v0.1 · `independently_reviewed_draft` · private · 2026-09-15.

Fact-checking of the original edition was completed on 2026-09-17. The relationship between the original version and the public copy, the scope of adaptation and the current navigation are described in the edition record.

Common fields: `as_of=2026-09-15`; `last_checked_at=2026-09-15`; `reviewer=part-02 researcher`; `review_status=see_REVIEW.md`. `confirmed` means confirmation within the stated scope, not independent acceptance of the whole chapter. Each evidence link has snapshot `<source_id>-20260915` and relation `supports` unless the row states otherwise. A snapshot denotes an access, not an immutable copy. Dates/versions and rights/access limitations are disclosed in [Sources](Sources.md).

For each claim, `review_trigger`: a change to the cited document/version/contract, the release of a new edition of the chapter, or a move from the teaching example to a real product. For empirical claims, additionally, a new report or a change in methodology; for source-access gaps, obtaining a readable primary text. Unknown values are not replaced with a probability estimate.

## Confirmed definitions and mechanisms

| claim_id | module_id; kind | Claim and scope | Evidence: source + snapshot + locator | Limitation / basis for the conclusion |
|---|---|---|---|---|
| P02-C001 | 2.1; mechanism | `confirmed`: the merchant, acquirer and intermediary functions may belong to different entities; in the Visa model the acquirer retains responsibility for the participants acting through it | P02-S034 / P02-S034-20260915, Backdrop p.2 | Public role overview 2024; the detailed rules in force and the contract are required for a specific launch |
| P02-C002 | 2.1; definition | `confirmed`: ISO in acquiring sales means Independent Sales Organization and is not the ISO messaging standard | P02-S034 / P02-S034-20260915, Third Party Agents / ISO p.7 | A sales/support role does not prove an independent right to hold settlement funds |
| P02-C003 | 2.1; mechanism | `confirmed`: in the Visa model described, a PF may sign acceptance contracts and/or receive funds for sponsored merchants | P02-S034 / P02-S034-20260915, Payment Facilitator p.3 | Not a universal law about all PSPs; quantitative thresholds from the old overview were not carried over |
| P02-C004 | 2.1,2.2; definition | `confirmed`: authorization, clearing and settlement denote different stages of the card process | P02-S003 / P02-S003-20260915, §§2.1–2.2 pp.4–5; P02-S002 / P02-S002-20260915 §2.18.1 pp.68–69 | Merchant payout/fulfillment cannot be inferred from the authorization response |
| P02-C005 | 2.2; product | `confirmed`: at Stripe, the specific capture_before and the method's limitations determine the manual capture window; there is no universal seven days | P02-S004 / P02-S004-20260915, Authorization validity windows; Capture the funds | Only the Stripe routes described; the tables are rolling, not immutable |
| P02-C006 | 2.2,2.7; product | `confirmed`: in the Stripe model described, a partial capture usually releases the remainder; multiple capture requires support | P02-S004 / P02-S004-20260915, Capture the funds, multicapture paragraph | Not universal across all PSPs and card products |
| P02-C007 | 2.2; product | `confirmed`: Adyen manual capture is asynchronous; request receipt does not equal final financial success | P02-S005 / P02-S005-20260915, Manual capture; Failed capture | Check the exact webhook and settlement record; CAPTURE_FAILED may revise the earlier result |
| P02-C008 | 2.2; mechanism | `confirmed`: changing the authorization amount and extending its validity are different operations; the result affects the original operation according to the route's rules | P02-S040 / P02-S040-20260915, Adjust amount; Extend authorization | One cannot generalize that the original hold necessarily remains after any failed extension |
| P02-C009 | 2.1,2.3; definition | `confirmed`: PFMI requires a clear point of settlement finality | P02-S001 / P02-S001-20260915, Principle 8, key considerations 1–3 | A normative FMI principle, not a statement about the actual architecture of every scheme |
| P02-C010 | 2.3; mechanism | `confirmed`: in direct debit, the payee initiates the collection on the basis of a prior mandate | P02-S010 / P02-S010-20260915, A different scheme; creditor-driven mandate | SEPA is described; another rail may have a different form/holder of the authorization |
| P02-C011 | 2.3; mechanism | `confirmed`: SEPA SDD Core allows a no-questions refund for eight weeks and a request for an unauthorized collection for up to 13 months | P02-S010 / P02-S010-20260915, Main differences, refund bullets | Scope: Core, counted from the debit; do not carry over to A2A credit transfers or to all of B2B |
| P02-C012 | 2.3; mechanism | `confirmed`: SDD B2B does not give the same refund right for an authorized transaction; the payer PSP checks the mandate | P02-S010 / P02-S010-20260915, Main differences, B2B bullets | Does not mean the absence of all returns/legal remedies |
| P02-C013 | 2.3; mechanism | `confirmed`: in Nacha's explanation, an ACH reversal is limited to sender errors and a five-banking-day window after settlement | P02-S008 / P02-S008-20260915, right time; timing; what reversals cannot be used for | US ACH; scam recovery is not an arbitrary reversal; if funds are unavailable, the return may not be executed |
| P02-C014 | 2.3; mechanism | `confirmed`: Faster Payments customer availability 24/7 and interbank net settlement on the RTGS schedule are different events | P02-S006 / P02-S006-20260915, Faster Payments Service; How does net settlement work | The page read shows three cycles per business day; the schedule needs updating before publication |
| P02-C015 | 2.3; mechanism | `confirmed`: FPS prefunding caps a participant's maximum obligation at the funds deposited in advance | P02-S006 / P02-S006-20260915, Prefunded net settlement | Do not equate with a merchant reserve or a specific sponsor-program deposit |
| P02-C016 | 2.3; mechanism | `confirmed`: FedNow distinguishes settlement, a new return transfer and a nonvalue request | P02-S042 / P02-S042-20260917, §§2.39,7.1,9.1.16,9.6–9.8 | Effective 2026-04-01; checked 2026-09-17; the historical S007 is not the basis for the current status; end-customer access is not proven |
| P02-C017 | 2.3; mechanism | `confirmed`: as of the reading date, the SCT Inst landing page designates the 2025 v1.1 rulebook as current and describes the ten-second timeline | P02-S009 / P02-S009-20260915, Current rulebook; Regulatory changes | The full rulebook was not read; exact recall deadlines are not inferred from the summary |
| P02-C018 | 2.3; mechanism | `confirmed`: correspondent banking uses accounts that banks hold with each other; nostro/vostro are different perspectives on the account relationship | P02-S035 / P02-S035-20260915, correspondent banking description; P02-S043 / P02-S043-20260917-deep, §7010.1 Vostro account, PDFp30 | Not evidence of the route of a specific transfer; chain fees/FX in the chapter are synthetic |
| P02-C019 | 2.3; mechanism | `confirmed`: transmission of a Swift message and the beneficiary bank's crediting actions are separate | P02-S011 / P02-S011-20260915, How does Swift work | A delivered message does not confirm beneficiary balance/fulfillment |
| P02-C020 | 2.3; definition | `confirmed`: the ISO20022 catalogue contains message definitions, MDR/MUG, schemas and sometimes examples | P02-S012 / P02-S012-20260915, Which documents can I download | Does not equal access to a bank account or XSD certification |
| P02-C021 | 2.3; definition | `confirmed`: pain.001 is CustomerCreditTransferInitiation; camt.053 is BankToCustomerStatement | P02-S039 / P02-S039-20260915, Payments Initiation; Bank-to-Customer Cash Management | Names/families checked, full schemas not read; a bank's versions may differ from the latest ones in the catalogue |
| P02-C022 | 2.3; mechanism | `confirmed`: in Fedwire, pacs.002/PDNG is intermediate; the next status, ACSC or RJCT, ends the pending state according to the FAQ | P02-S013 / P02-S013-20260915, FAQ PDNG | Scope: Fedwire; ACSC does not confirm fulfillment of the commercial goods |
| P02-C023 | 2.3; mechanism | `confirmed`: in Fedwire, camt.056 requests the return of a previously settled value message | P02-S013 / P02-S013-20260915, FAQ return of funds | A request does not guarantee a completed return |
| P02-C024 | 2.3; product | `confirmed`: in the historical UK OB domestic-payment-consent, Consumed does not reflect the status of the payment itself | P02-S014 / P02-S014-20260915, State Model: Consumed | Historical example v3.1.2/page-path 3.1.3; not asserted to be the current mandatory profile |
| P02-C025 | 2.3; definition | `confirmed`: the FAPI2 Security Profile governs the secure obtaining/use of OAuth tokens, not payment settlement | P02-S015 / P02-S015-20260915, §1 Scope; §5 | General-purpose final standard; adoption by every bank is not proven |
| P02-C026 | 2.3,2.5; legal | `confirmed`: PSR guidance describes local UK APP reimbursement from 2024-10-07, up to GBP 85,000, for eligible customers/transfers | P02-S016 / P02-S016-20260915, protections; eligibility; exclusions | Eligibility of a real claim is not established; a civil dispute is not automatically a scam; the geography is not global |
| P02-C027 | 2.4; definition | `confirmed`: Visa distinguishes interbank interchange from the merchant discount agreed between the merchant and its financial provider | P02-S017 / P02-S017-20260915, interchange/merchant discount explanation | US Visa context; the chapter's synthetic rates are not official schedule rates |
| P02-C028 | 2.4; product | `confirmed`: Adyen reports distinguish interchange, scheme fees and markup | P02-S018 / P02-S018-20260915, Payment method fees | Cost visibility does not guarantee savings; there is no independent comparative assessment of PSPs |
| P02-C029 | 2.5; mechanism | `confirmed`: a 3DS challenge requires additional interaction with the ACS; a frictionless flow can complete without it | P02-S037 / P02-S037-20260915, Business Overview; P02-S041 / P02-S041-20260915, Business Overview | Authentication is not the same as approval/settlement; marketing efficacy claims are not adopted |
| P02-C030 | 2.5; product | `confirmed`: in Stripe's description, the 3DS liability shift applies to qualifying fraud disputes and has exceptions | P02-S020 / P02-S020-20260915, Disputes and liability shift | Cannot be extended to non-delivery; confirm the specific transaction, data and rules |
| P02-C031 | 2.5; mechanism | `confirmed`: temporal validation of fraud ML must account for label delay and drift | P02-S021 / P02-S021-20260915, Validation strategies introduction/hold-out | A methodological conclusion of an academic handbook; no model was tested on store data |
| P02-C032 | 2.5; empirical | `confirmed`: based on EU/EEA data for 2022–2024, EBA/ECB report lower fraud rates for SCA-authenticated card payments overall and a different pattern for credit transfers | P02-S022 / P02-S022-20260915, Executive Summary pp.6–7 | An observational association, selection/transaction mix; not an individual causal effect of 3DS |
| P02-C033 | 2.5; empirical | `confirmed`: according to the same report, manipulation of the payer accounts for more than half of the value of fraudulent credit transfers | P02-S022 / P02-S022-20260915, Executive Summary p.6 | Specific period/geography/value metric; not a share of all payments and not a global estimate |
| P02-C034 | 2.6; product | `confirmed`: a refund can be pending/failed and needs separate tracing; cancellation before capture is a different process | P02-S033 / P02-S033-20260915, pending/failed refunds; cancel; tracing | Scope: Stripe methods, with no general SLA and no claim of actual crediting |
| P02-C035 | 2.6; mechanism | `confirmed`: a chargeback allocates financial liability through a reason-based workflow; second presentment, pre-arbitration and arbitration have conditions | P02-S003 / P02-S003-20260915, §§3,5 pp.6–11 | A simplified teaching diagram; not a substitute for the full Chargeback Guide |
| P02-C036 | 2.6; product | `confirmed`: Stripe debits the disputed amount and the fee separately; an ordinary refund during an open dispute is restricted | P02-S036 / P02-S036-20260915, Receive a dispute; Dispute fees | Fee amounts/refundability depend on the contract/country; the teaching USD 15 is not Stripe's current rate |
| P02-C037 | 2.7; mechanism | `confirmed`: dual-message separates authorization/clearing; single-message combines the data of these stages in one financial format | P02-S003 / P02-S003-20260915, §2.2 p.5 | Single-message does not mean a single network packet and does not eliminate settlement; debit/credit is not a global correspondence |
| P02-C038 | 2.7; mechanism | `confirmed`: the MTI, bitmap and named DEs have the described purposes in Worldpay V2.63 | P02-S024 / P02-S024-20260915, §1.2 p.6; Chapter5 pp.236,241,248,255,276–278,302,310 | Only the published profile; the synthetic trace is not a wire-compatible fixture; the ISO original was not read |
| P02-C039 | 2.7; product | `confirmed`: Adyen raw mapping distinguishes 05 general refusal, 51 insufficient funds and Mastercard 65 authentication required | P02-S023 / P02-S023-20260915, Visa/Mastercard raw responses | Code 65 is not universal across all networks/profiles; do not invent an issuer cause from 05 |
| P02-C040 | 2.7; mechanism | `confirmed`: Mastercard clearing requirements call for acknowledgements, correction of rejects and reconciliation with the net settlement advisement | P02-S002 / P02-S002-20260915, §2.18.1 pp.68–69 | Obligations of a scheme participant, not a guarantee that a specific PSP has met them |
| P02-C041 | 2.8; product | `confirmed`: Google Pay Web PAN_ONLY and CRYPTOGRAM_3DS are tied to different credential sources | P02-S025 / P02-S025-20260915, CardParameters.allowedAuthMethods | One cannot assert a network/device token for every Google Pay payment |
| P02-C042 | 2.8; product | `confirmed`: Apple describes the DAN and a unique security code for the specified Apple Pay card flow | P02-S026 / P02-S026-20260915, payment processing after authentication | Do not generalize to all wallets/all access modes and liability |
| P02-C043 | 2.8; product | `confirmed`: Google PaymentMethodToken is a signed/encrypted envelope containing either a PAN or a device PAN with a cryptogram | P02-S027 / P02-S027-20260915, overview ECv2 | An API token envelope is not necessarily an EMV Payment Token; direct decryption changes the data/security scope |
| P02-C044 | 2.8; mechanism | `confirmed`: the PCI scope exception for a proper EMV Payment Token outside the TSP environment does not remove the scope of PAN/connected systems | P02-S028 / P02-S028-20260915, Applicability of PCI DSS | No assessment of a specific merchant's environment was performed |
| P02-C045 | 2.8; mechanism | `confirmed`: QRIS allows MPM/CPM; PJP/switching processing requires prior BI authorization | P02-S029 / P02-S029-20260915, Para Pihak; Karakteristik | A QR interface is not a license in itself and not proof of foreign PSP access |
| P02-C046 | 2.8; product | `confirmed`: the BI page shows an MDR of 0.7% for UKE/UME/UBE, with other micro/special categories | P02-S029 / P02-S029-20260915, Skema Tarif QRIS | As of 2026-09-15; the category of the specific cafe is not established; its assignment is synthetic |
| P02-C047 | 2.8; definition | `confirmed`: CFPB 2022 defines the pay-in-four studied as a loan with four installments, usually with 25% as the first installment | P02-S030 / P02-S030-20260915, §2.1 p.6 | Historical scope of the study; not all BNPL worldwide and not the current legal classification |
| P02-C048 | 2.8; product | `confirmed`: Klarna has a separate refund operation; a successful request returns a refund_id | P02-S031 / P02-S031-20260915, full/partial refund; Success response | An API receipt is not sufficient for the full outcome of borrower/merchant settlement |

## Social case, open questions and rejected generalizations

| claim_id | module_id; kind/status | Statement | Evidence / locator | Editorial decision |
|---|---|---|---|---|
| P02-C049 | 2.3; experience, `confirmed` only as a fact of publication | Consistent-Virus-959 describes the problem of an XSD-valid pain.001 that a particular bank profile does not accept | P02-S032 / P02-S032-20260915, main post intro/layered validation | The author's experience and the specific banks are not verified; the framing of the question is used, not incident statistics. At the end of the post the author promotes their own validator/explainer (re-read on 2026-09-17, P02-S032-20260917) |
| P02-C050 | 2.5; legal, `open` | The exact thresholds and cumulatives for SCA exemptions under the consolidated RTS in force on 2026-09-15 | P02-S038 / P02-S038-20260915, metadata only, relation=context | The direct text was not obtained; the chapter does not present a legal table based on snippets |
| P02-C051 | 2.8; product, `open` | A specific combination of BNPL and crypto-in is permissible at a specific provider | Evidence absent; P02-S030/P02-S031 only context | Neither support, nor authorization, nor an actual payment is claimed |
| P02-C052 | 2.7; empirical, `open` | The synthetic decline/capture trace reflects a live payment that actually happened | Evidence absent | Such a conclusion is explicitly prohibited by the example's labeling; permitted actual logs are needed for a real case |
| P02-C053 | 2.1–2.8; hypothesis, `rejected` | A successful authorization/callback proves merchant payout and order fulfillment | P02-S003/P02-S005/P02-S007/P02-S013/P02-S014/P02-S036, relation=contradicts, locators above | Stages and objects are kept separate; only the corresponding external confirmation answers a specific question |
| P02-C054 | 2.3; hypothesis, `rejected` | Any instant payment means immediate interbank gross settlement | P02-S006 / P02-S006-20260915, FPS/Net settlement, relation=contradicts | UK FPS is a specific counterexample; do not universalize its design back onto FedNow |
| P02-C055 | 2.5; hypothesis, `rejected` | 3DS makes any merchant dispute losses impossible | P02-S020 / P02-S020-20260915, liability shift exclusions, relation=contradicts | Fraud-liability coverage is limited; delivery/refund remain separate obligations |
| P02-C056 | 2.8; hypothesis, `rejected` | A wallet token always means a network token and automatically takes the entire environment out of PCI scope | P02-S025/P02-S027/P02-S028, locators above, relation=contradicts | Check the credential mode, the actual data and the connected environment |
| P02-C057 | 2.8; hypothesis, `rejected` | BNPL is just card delayed capture | P02-S030 / P02-S030-20260915 §2.1; P02-S004 / P02-S004-20260915 manual capture; relation=contradicts | The lender, funding, underwriting and repayment schedule distinguish the economic model |

## Own synthesis and arithmetic

Synthetic numbers are not empirical claims. Checked separately:

- 80 × 2.9% + 0.30 = 2.62 USD; 80 − 2.62 = 77.38.
- Three-way netting 100/90/80 gives positions −20/+10/+10; sum 0.
- FX 1,000 EUR × 1.10 − 10 − 5 = 1,085 USD.
- Processing 100 × 2.9% + 0.30 = 3.20; 1.70 + 0.25 + 1.25 = 3.20.
- Risk case: precision 80/380 = 21.05%; recall 80/100 = 80%; FPR 300/9,900 = 3.03%; 8,000 − 7,500 = 500 USD before additional costs.
- Dispute case: 96.80 − 100 − 15 = −18.20; after the return of 100 with a non-refundable fee, the result is 81.80.
- QRIS example: 150,000 × 0.7% = 1,050 IDR; net 148,950 IDR.
- BNPL example: 200 − 10 = 190 merchant payout; 190 − 50 = 140 initial funding gap; future principal receipts 150.
- Exercises: netting 200/140/90 → −110/+60/+50; total costs 320 + 75 + 50 = 445 USD; 445/10,000 = 4.45%; precision 40/200 = 20%, recall 40/50 = 80%.

The synthesis on choosing a rail and the practical investigation schemes are teaching methods derived from the differences between confirmed mechanisms; they are not legal advice, a price offer or a product-readiness verdict. The coverage of the independent review of the cards and its limitations are described in REVIEW.md (historical or internal material; kept by the owner, outside this copy).

## Updates after the knowledge cutoff

Rows are appended by the weekly [timeline](../../Timeline/README.md). The lesson text is not changed; the lesson carries a dated note next to the statement. `superseded` means the claim was true at the cutoff but no longer describes the current state; `added` is a new claim introduced by an update note. Each row was checked against its primary source by a second agent.

| Date | Claim / lesson | Change | Status now | Source | Week |
|---|---|---|---|---|---|
| 2026-09-30 | lesson 2.3 (no claim ID; source P02-S009) | The EPC delayed the 2026-11-15 end date for unstructured addresses under all five EPC schemes; no new date set | `superseded` | P02-S044, P02-S045 | [Week 40](../../Timeline/2026-W40.md) |
