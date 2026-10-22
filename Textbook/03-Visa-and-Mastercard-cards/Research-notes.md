---
title: "Chapter 3 — research log and handoff"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Cards: Visa and Mastercard](README.md) · [Contents](../README.md) · [All sources and fact-checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Check dates and source limitations have been preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Chapter 3 — research log and handoff

**2026-09-15 · private · author: part_03_research · status: draft_for_review.**

## Completed

An internal organizational link from the historical author's note has been removed from the public edition; the research methodology and external sources have been kept.

- CHAPTER.md: 6,686 words by whitespace splitting; all six modules, eight Visa subsections and eight Mastercard subsections, a comparison table of six schemes, synthetic examples, ten exercises and explained answers.
- SOURCES.md: 47 cards with snapshot ID, versions/dates, actual reading limits, access status, independence groups and rights. All 47 IDs are used in the chapter; the metadata source is explicitly labeled.
- CLAIMS.md: 75 sequential unique claims, including open/rejected/working_hypothesis; reviewed_status of all is pending. There is a table of calculations and a resolution of material contradictions.
- Checked: source identifiers, the presence of the six exact module headings, relative links and the arithmetic of the exercises. The three main files contain no TODO/TBD/PLACEHOLDER. No PDF was created, and none is claimed to be ready.

## Material findings for the independent reviewer

1. **Editions:** Visa Core Rules 2026-04-18, 923 PDF pages; Mastercard Rules 2026-06-02, 503; TPR 2026-06-09, 436; Switch Rules 2025-12-16, 114; SPME 2026-08-04, 236; MCC Quick Reference 2026-06-02, 359. Cover dates are not declared to be the effective date of every provision.
2. **GMAP:** SPME §8.2, p. 87 directly says suspension until further notice. ECP §8.3 uses the previous month's transaction count. The exact ECM/HECM thresholds are placed in another manual and were not filled in from memory.
3. **VAMP:** the fact sheet gives 150 bps from 2026-04-01 for AP/Canada/EU/US, plus count ≥ 1,500 and portfolio/country/exclusion conditions. This is not one universal merchant trigger.
4. **Visa disputes:** Table 11-2 for categories 12/13: acquirer pre-arbitration response 30 calendar days from the Processing Date of the attempt; Tanzania domestic 10; issuer arbitration 10 days from the Processing Date of the response. This is not the window for a store's response to its PSP.
5. **Crypto:** MC §9.4.9 uses MCC 6051/TCC U and TTI P70/P76 by type; P76 covers fully fiat-backed stablecoin/CBDC. The CBDC reporting category is not equated with the definition of cryptocurrency. Visa Table 7-9 classifies crypto/NFT cases separately; do not carry over the MC coding.
6. **Rate illustrations:** Visa US effective 2026-04-18: selected rows verified. The MC Canada May 2026 table was read, but the exact effective date of its rows is not confirmed; the chapter explicitly calls this an illustration of the edition named by the file name.
7. **Dispute cycle services:** Verifi Order Insight describes non-Visa direct integration; Ethoca Smart Subscriptions calls Ethoca brand-agnostic. This is not evidence that any specific issuer is connected.
8. **RTS/co-badging:** the EUR-Lex JS challenge was bypassed not by a technical hack but by reading the official BOE originals: RTS DOUE-L-2018-80459, IFR DOUE-L-2015-80958. The English adopted article XML was used to cross-check specific articles. There is no full current consolidation. BOE RTS Analysis contains an erroneous entry date of 2018-11-14; operative article 38 + publication on 2018-03-13 give 2018-03-14; application 2019-09-14. The Spanish corrigendum 2020-80441 was read.
9. **Reddit:** the initial DCC post later opened directly. Author u/gbcox, UI date "2y ago", complaint outcome unknown. The story is not accepted as established fraud; the full transcript/comments were not copied. X is not used.
10. **Scholarship/education:** ECB 2010 textbook for established models; BIS WP 1163 official summary only; Who Pays Whom author version/HAL 2025 read partially, without a claim of verified proofs/experiments. No fictitious course/timecode.

## Explicit limits

- Full VTS/MDES merchant message/lifecycle specs were not obtained. API differences were not invented.
- The full current Mastercard Chargeback Guide was not opened; Chargebacks Made Simple 2025 is a separate introductory document. The Data Integrity Monitoring Program and the Visa Integrity Risk Program Guide were not obtained.
- EMVCo current TF 2.4/new Use Cases — metadata only. The v2.2.1 January 2023 that was read is an illustrative guide with specific pages in SOURCES, not a new full specification.
- EBA Q&A 2018_4031/4048/2019_4794 return fetch/403 errors; the legal scope of any MIT was not reconstructed from snippets. RTS Art. 14 is used for the narrow series of same amount/same payee.
- There is no comparable current 2026 market geography for all schemes, no full operating rulebooks of adjacent brands, and no actual provider contracts/production approval.
- Third-party source PDFs/images/full texts were not saved and are not distributed. A snapshot ID means a reading; no hash was invented.

## What to hand over to the reviewer

Review priority: C021 (exact Visa deadlines), C025 (VAMP scope), C040–C042 (GMAP/ECP), C060 (RTS scope), C068–C070 (crypto), C036 (limited Canada date). Also check the separation of tokens, COF, CIT and MIT. Open items remain open until a sufficient source is obtained. The author does not write REVIEW.md and does not give independent approval.
