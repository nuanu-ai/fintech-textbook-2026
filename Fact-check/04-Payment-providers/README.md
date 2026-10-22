---
title: "Independent fact-check results — Chapter 4"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Sources and fact-check](../README.md) · [Read the chapter](../../Textbook/04-Payment-providers/README.md)

> Public edition of 2026-09-18. Verification dates and source limitations are preserved. Hashes in historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Independent fact-check results — Chapter 4

2026-09-17 · Asia/Makassar (UTC+08) · auditor: `deep_audit_02_03_04` · private. Knowledge cutoff: 2026-09-15; new accesses on 2026-09-17. The exact historical bytes of the rolling documentation were not recovered.

## Result and coverage

CHAPTER.md, CLAIMS.md and SOURCES.md were read in full. All 44 claim IDs and 24 source IDs have their own rows: [CLAIM_AUDIT.md](Claim-check.md), [SOURCE_AUDIT.md](Source-check.md). All original URLs were requested independently. The relevant substantive fragments were obtained for all 24 sources; where there was a 403 or an empty shell, the web original was used, and for Stripe also its official Markdown, which is noted separately in the matrix. This does not mean that every large rulebook was read in full.

**New fixable findings: 0 critical, 0 major, 0 minor.** The remaining issues below are evidence limitations that are explicitly preserved in the chapter. The two contradicted verdicts concern claims about a license/passport that the author rejected; the six non_factual verdicts concern models and proposals, not proven market facts. The final three root files differ from the baseline only in updated links to the audit and the designation of the first review; these changes were checked.

| Verdict | Claims |
|---|---:|
| verified | 33 |
| verified_as_reported | 2 |
| partial | 0 |
| contradicted | 2 |
| unverifiable | 1 |
| non_factual | 6 |
| **Total** | **44** |

## High-risk areas checked

- **PayFac and MoR liability:** Mastercard §7.6.5–7.6.5.1, pp.172–174, Stripe MoR charge types and on_behalf_of, and Paddle MSA §2.1 and §§8,10.4 were read directly. Delegation does not remove the acquirer's responsibility; the reseller role does not exclude supplier recourse for refunds/chargebacks. For Paddle, the date 8 October 2025 and the different applicability to new/existing suppliers were checked; there is no individual order form.
- **Payout and reconciliation:** the Stripe payout schedule does not shorten pending availability; paid can later turn into failed. In the Adyen settlement report, commission and the component columns 11–14 are not added up twice. The meaning of the separate fee/reserve/merchant payout entries was read; a provider's report is not proof that the bank has credited the funds.
- **Split payments:** the full relevant text of the official Markdown for Separate charges and transfers confirmed that the objects are separate and that there is no automatic reverse transfer on refund. The assumption of 10 available against a refund obligation of 80 is not masked by a formally successful charge.
- **Pricing and eligibility:** Stripe Connect 2 USD per active account plus 0.25% + 0.25 USD per payout were checked in the US offer, separately from payment processing. The stablecoin page and its Markdown were read for tokens, networks, local-currency settlement and refunds to the original wallet. US merchant eligibility is kept separate from the private preview for EU/HK/MX/CH and from the broader country-code list.
- **License and sponsorship:** the FCA marketplace guidance, VisaNet Connect Issuing eligibility/risk review/production steps, the US interagency guidance of 6 June 2023 and CBI passporting were checked directly. Sandbox/API/the word BIN do not amount to permission to operate in any country. The general third-party guidance has not been turned into a standalone BaaS license.

## Papers: versions, method and assumptions

- [FEDS 2009-23](https://www.federalreserve.gov/pubs/feds/2009/200923/): Prager, Manuszak, Kiser and Borzekowski, 13 May 2009; the executive summary and the main theoretical distinctions were read. This is a literature review, not a causal estimate of a 2026 tariff; the conclusion about efficient interchange depends on the assumptions.
- [Rochet–Tirole](https://tse-fr.eu/sites/default/files/medias/doc/wp/2002/platform.pdf): author draft of 13 December 2002, §2/§2.1, pp.8–10. Checked: linear usage prices, the absence of fixed participation costs in the stated model, exogenous benefits and the joint-volume profit formula. Neither current empirical accuracy nor equivalence of this version to the journal version is claimed.
- [Aurazo, BIS WP1163](https://www.bis.org/publications/working-paper-1163-interchange-fees-access-pricing-and-sub-acquirers-payment-markets.pdf): January 2024, sole author; the model in §3 and the niche case in §6, physical PDF pp.18–20, were read. Checked: six types of participants, no membership fees, every consumer holds a card, no direct bypass, and separate benefit/cost assumptions for the niche case. The direction of the access-price incentive is not turned into an observation about all banks. A full mathematical replication of all propositions was not performed.

## The whole chapter and arithmetic outside individual claims

In addition to the register, the full models of loss, reserve, Friday T+2, delivery split, conversion-adjusted contribution and the partner-exit checklist were read. No new significant unsupported facts were found outside the register. The simple architecture diagram and the connector role do not prove a license, legal consent or permission for a specific launch.

The arithmetic was rechecked independently:

- With GMV of 1 million, revenue of 32000 and the stated disjoint cost/loss rows, contribution = 6100, margin = 0.61%, and after a fixed cost of 15000 profit = −8900. Break-even = 15000 / 0.0061 = 2,459,016.39; at GMV of 2 million profit = −2800. With additional losses of 0.4%, break-even = 7,142,857.14. Constant mix and margin are a condition of the model.
- Connect: 100 accounts, 100000 volume, 400 payouts → 550; 100 payouts → 475. Payment processing is not included in these sums.
- Fixed-plus-percentage fee: for 2 USD the amount is 0.358 (17.9%); for 20 USD it is 0.88 (4.4%). The amount before rounding is kept separate from actual currency minor-unit rounding.
- The four hypothetical cost rows 0.69/0.29/0.70/0.40 become 0.89/0.49/0.90/0.60 after the additional 0.20. With the stated conversions, contribution is 80 × (8 − 0.69) = 584.80 and 70 × (8 − 0.29) = 539.70.
- Delivery 60 + 8 + 2 + 10 = 80. Fee, principal loss, reserve and transfer receivable are not combined into one number and are not counted twice.

## Limitations

- **C029 unverifiable:** the discrepancy between Stripe's preview prose and the broader country-code list has not been resolved by primary confirmation from the provider or by account evidence. Eligibility of a specific non-US merchant remains open; the chapter does not promise access.
- The Triple-A FAQ confirms the published offering and the stated automatic withdrawal threshold of 3000 USD equivalent. No individual SLA, contract or evidence of a license or of an actual withdrawal was obtained.
- Reddit u/songtu-staygold was read together with the author's clarification about acquiring. This confirms the question and the confusion of terms, not network rules, an actual contract or the author's identity. The exact date was not established from the relative age.
- The Mastercard global base rules were checked in the relevant places; no exhaustive audit of all regional supplements was carried out. BOE/CBI/FCA and US guidance do not replace an analysis of a specific legal entity and of all legislation in force.
- There is no check of production, merchant accounts, the ledger, bank credit, actual conversion, customer consent or an overall legal opinion. The synthetic calculations check internal arithmetic, not how realistic the commercial model is.

## Final version check

An independent check of the sources and the final text was carried out within the research scope; this entry describes the audit of 2026-09-17. Changes to the canonical files were made by root; this auditor writes only the reports for its own chapter.

`final_verdict=reviewed_with_limitations` · `open_critical=0` · `open_major=0` · `open_minor=0`.

The actual final CHAPTER/SOURCES/CLAIMS were rechecked after root reported that the edits were complete. The SHA-256 values below refer to these files, not to the old REVIEW and not to the bytes of external sites. Any later edit requires the check and the hashes to be updated.

| Final canonical file | SHA-256 |
|---|---|
| [chapters/part-04/CHAPTER.md](../../Textbook/04-Payment-providers/README.md) | `820c833732c1e70d7dfdeea1b21dab5835291fbadb631aca06d6ecdf93d90407` |
| [chapters/part-04/SOURCES.md](../../Textbook/04-Payment-providers/Sources.md) | `adaca25348b531b671891072ad3be75d89f9b7bd8f650ea32293c39db3ac2c03` |
| [chapters/part-04/CLAIMS.md](../../Textbook/04-Payment-providers/Claims.md) | `e75ef4d8a87cc17a2715f58c1b564fd09d7ef8f76c35f78ccde3376f8b1f3664` |

