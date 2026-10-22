---
title: "Detailed independent audit — Chapter 1"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Sources and fact-check](../README.md) · [Read the chapter](../../Textbook/01-Market-rules-and-licensing/README.md)

> Public edition of 2026-09-18. Check dates and source limitations have been preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Detailed independent audit — Chapter 1

2026-09-17 · Asia/Makassar · private · auditor `deep_audit_00_01_05`.
The book's knowledge cutoff is 2026-09-15. The date of the accesses in this audit is 2026-09-17.

## Summary

All **52 claims and 56 source cards** were checked, including C052, S063 and S064, which were added during the correction. There are gaps in the source numbering: the highest ID, 064, does not mean 64 cards. CHAPTER, CLAIMS, SOURCES and the corresponding part of the structure were read in full. The results for each ID are in [CLAIM_AUDIT.md](Claim-check.md) and [SOURCE_AUDIT.md](Source-check.md).

Two material defects in the evidence base and one inaccuracy in an article reference were fixed by the editor and independently rechecked. No open critical/major findings remain. The scope of the check is not the same as the number of fully proven external claims.

| Verdict | Count |
|---|---:|
| verified | 25 |
| verified_as_reported | 14 |
| partial | 6 |
| unverifiable | 3 |
| non_factual | 4 |
| contradicted | 0 |
| Total | 52 |

## Method and scope of the check

[AUDIT_BRIEF.md](../Method.md) and the source schema were applied. The old REVIEW and the editor's URL check served only as navigation, not as evidence. An independent attempt was made to open each original URL; any alternative original or index is stated explicitly. A date in a PDF file name, an HTTP 200 and a search-result title were not accepted as evidence of the current version or of having read the relevant provision.

Particular attention was paid to separating the dates of adoption, entry into force, application and transition; the license holder and the activity; contractual liability and conditional exemptions. The decisive provisions of PSD2, TFR, MiCA, GENIUS, UK safeguarding, UK stablecoin rules, Singapore PDPC, FinCEN and the vendor terms that were read were checked directly. Checking individual articles is not presented as a full legal audit of all countries and national implementations.

## Findings and closure

### P01-F001 — major, closed: a guest article presented as regulatory guidance

**Original text:** CHAPTER §1.6: "the official PDPC explanation distinguishes the obligations of the organization and of the intermediary", citing P01-S029. The source card also presented the material as a regulator explainer.

**Grounds:** the index of the [original PDPC page](https://www.pdpc.gov.sg/the-distinction-between-organisations-and-data-intermediaries-and-why-it-matters) retains the contributor credit **Wong Wai San, BSA — The Software Alliance**. The original URL itself returned an error/404 on repeat access. Hosting a guest text on the regulator's website does not prove that the agency wrote it. The weak attribution is material for a paragraph about legal obligations.

**Correction:** S029 is kept as guest material with an honest access limitation. S063 and C052 were added; the paragraph is limited to processing on behalf of and for the purposes of an organization under a written contract. Evidence: [PDPC Advisory Guidelines on Key Concepts in the PDPA](https://www.pdpc.gov.sg/-/media/Files/PDPC/PDF-Files/Advisory-Guidelines/AG-on-Key-Concepts/Advisory-Guidelines-on-Key-Concepts-in-the-PDPA-17-May-2022.pdf), cover and printed pp.24–25, Data intermediaries / Obligations / Considerations, including §4(3).

**Independent recheck:** the PDF actually obtained has 165 pages and revision **2026-04-29**, despite "17-May-2022" in the URL. The pp.24–25 that were read confirm Protection, Retention Limitation, Data Breach Notification towards the principal within the scope considered; the organization's own obligations remain, and other actions of the intermediary are analyzed separately. The final CHAPTER, C052 and S063 match this narrow scope. The remaining 163 pages are not declared checked.

### P01-F002 — major, closed: a correct conclusion relied on a document about a different question

**Original text:** CHAPTER §1.2, "Example: registration versus license", and C021: FinCEN MSB registration does not replace a state license/authorizations. The only local basis was S002, FIN-2014-R009.

**Grounds:** [FIN-2014-R009](https://www.fincen.gov/resources/statutes-regulations/administrative-rulings/application-money-services-business), 2014-08-27, analyzes the ISO/payment processor facts and the exemption conditions. It is not a direct clarification of what registration itself means.

**Correction:** S064 was added: [FinCEN Alert on Fraud Schemes Abusing FinCEN’s Name, Insignia, and Authorities for Financial Gain](https://www.fincen.gov/system/files/2024-12/Alert-FinCEN-Scams-FINAL508.pdf), FIN-2024-Alert005, 2024-12-18. C021 and specific sentences of the chapter now rely on printed p.6, Guidance on Avoiding MSB Registration Scams. S002 is kept for the factual ISO/processor exemption conditions.

**Independent recheck:** the cover and printed pp.5–6 of the 11-page PDF were read. P.6 explicitly distinguishes MSB registration, authorization to operate and the applicable separate state/territory licensing. The title of S064 was checked in full, including "for Financial Gain". The corrected text does not claim to have checked all US regional regimes.

### P01-F003 — minor, closed: inaccurate locator for liability under PSD2

**Original text:** CHAPTER §1.2, "Three relationships with a partner": "using an agent and outsourcing important functions do not release the payment institution from liability; control of outsourcing is described in Art. 19 PSD2".

**Grounds:** [official PSD2 text in BOE](https://www.boe.es/buscar/doc.php?id=DOUE-L-2015-82575), art.19(6) governs the conditions for controlling outsourcing; art.20(2) explicitly establishes full liability for the acts of employees, agents, branches and contractors. The actual text of both provisions was read via the official HTTP original.

**Correction and recheck:** the final sentence cites art.19(6) for control and art.20(2) for full liability separately. The original wording did not get the mechanism itself backwards; the precision of the legal reference was corrected.

## Additional checks of text and dates

- TFR: arts.14(4)–(5), 16(2), 17, 25, 26 and 40 were read separately. Data transmission does not have to happen directly on-chain; the self-hosted check threshold does not exempt smaller transfers from all information requirements; five-year retention and possible national extension are not confused with indefinite retention. Application from 2024-12-30 is kept separate from entry into force.
- MiCA: the maximum transition to 2026-07-01, the possibility of an earlier national end and the exact entity were considered separately. Lawful operation before 2024-12-30 is a condition of the relevant transitional regime, not an authorization for an entire brand or group.
- GENIUS: §20 contains a conditional general start; the three-year provision §3(b)(1) has its own subject matter. The OCC NPRM is not equated with a final rule. The actual full register of triggering final rules was not researched exhaustively, so C009 is kept as `unverifiable/open`.
- PSD3/PSR: [Council ST9814/26](https://data.consilium.europa.eu/doc/document/ST-9814-2026-INIT/en/pdf), p.3, rows 5–6, directly confirms the provisional agreement of 2025-11-27 and the COREPER confirmation of 2026-04-22. The document is dated 2026-06-09, state of play 2026-06-12. These stages do not by themselves prove that the new law has started to apply.
- UK supplementary safeguarding from 2026-05-07 and, separately, the future commencement of the UK stablecoin instruments on 2027-10-25 were checked directly. The document with final rules is not presented as a regime already applying at the book's cutoff.
- A material paragraph in §1.5 about OFAC that is not in the claims register was compared with the [official brochure](https://ofac.treasury.gov/system/files/126/virtual_currency_guidance_brochure.pdf), printed p.15: identity/location/IP and other data are material; the list of known addresses does not exhaust the risk.
- The FIDReC limitations were checked against [Terms of Reference v2.1](https://www.fidrec.com.sg/_entity/annotation/63c8379b-6e55-f011-bec2-0022485a9df8), 2024-12-16, Rules 13 and 15, pp.8–9: the internal settlement attempt/period, the six-month limit after the relevant final reply, and eligibility. A check of all categories of claimants is not claimed.
- The synthetic models were recalculated: connector (100 − 3 − 2 = 95), PayFac (87 + 10 + 3 = 100), dispute (115 in costs with 10 retained gives −105), MoR (100 − 3 − 90 − 100 + 90 = −3), wallet (70 + 30 = 100). No arithmetic errors were found; the contractual allocations are not declared universal.

## Remaining limitations

C004–C005 (BI/PBI/TIKMI), C017 (FSRA), C030 (DORA), C043 (Hong Kong) and C047 (BCB) are `partial`: the matrix states which part was read directly and which relies on an official index/another government document. For C042 (QRIS) and C048 (CMB Türkiye) the required original was not obtained; network/TLS errors are not declared evidence that the source is invalid. The author's statuses are not automatically turned into `verified` here.

Not confirmed: the exhaustive stage of Singapore stablecoin implementing legislation, all national transitions/exemptions, the full current package of each country, and the individual legal classification of a specific business. Sources on vendor rules prove only the published terms; actual accounts, signed contracts, underwriting and operations were not checked. Dynamic pages obtained on 17 September do not prove that they were historically unchanged.

## Recheck and version binding

After the corrections, root independently reread all changed passages of the chapter, S029/S063/S064 and C021/C052; after the last PSD2 edit, the final reference to both articles was rechecked. The new IDs are included. The completeness and uniqueness of the matrix rows were checked. The pointer to this audit refers to the current version; the previous REVIEW and its hashes refer to the historical snapshot.

final_verdict: `reviewed_with_limitations`  
open_critical: `0`  
open_major: `0`  
final_recheck: `2026-09-17 Asia/Makassar`

| File relative to chapters/part-01 | SHA-256 of the final checked version |
|---|---|
| CHAPTER.md | `cd2485b7e0c38144757ab6ea0880314c764c94d29752cf0d4730cadb20e3af94` |
| SOURCES.md | `668c76e2f370370ae334294b32f563cd917136c3eaedcc5fae25c711c1a5b74c` |
| CLAIMS.md | `3f2ea69b5f39b174d07ca52f04e92e614bfe36545267e17602a2169cd20ba4dc` |
