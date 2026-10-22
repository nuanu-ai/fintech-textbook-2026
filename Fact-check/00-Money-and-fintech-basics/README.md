---
title: "Detailed independent audit — Chapter 0"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Sources and fact-check](../README.md) · [Read the chapter](../../Textbook/00-Money-and-fintech-basics/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Detailed independent audit — Chapter 0

2026-09-17 · Asia/Makassar · private · auditor `deep_audit_00_01_05`.
The book's knowledge cutoff is 2026-09-15. The sources were accessed for this audit on 2026-09-17.

## Summary

All 48 registered claims and all 24 source cards were checked; CHAPTER, CLAIMS, SOURCES and the relevant part of the structure were read in full. Each claim received a separate assessment in [CLAIM_AUDIT.md](Claim-check.md); the auditor's own access attempt and the scope read for each source are recorded in [SOURCE_AUDIT.md](Source-check.md). No open material errors were found. This does not mean that all external claims have been independently proven.

| Verdict | Count |
|---|---:|
| verified | 19 |
| verified_as_reported | 9 |
| partial | 8 |
| unverifiable | 1 |
| non_factual | 9 |
| contradicted | 2 |
| Total | 48 |

`contradicted` for C045 and C046 refers to the literal content of **myths explicitly rejected by the author**. Their refutation in the book is correct. These two rows are not two errors found in the chapter. `verified_as_reported` confirms the content of the vendor's document, not how the product works, its availability to an account or the actual receipt of money.

## Method and scope of the check

[AUDIT_BRIEF.md](../Method.md) and the source schema were applied. The previous review and the editor's general URL check were not used as evidence. URLs repeated across the assigned chapters were used after the auditor had obtained the text independently; each ID is kept as a separate row.

The decisive areas were checked directly: PFMI 8–9, bank deposit creation, balance limitations and payment states, MiCA definitions and FATF §73. The financial examples were assessed as synthetic models with given assumptions. The Stripe and Modern Treasury documentation was read within the scope of the relevant states and formulas; it does not prove the movement of money in a specific transaction.

For each source, the audit distinguished direct reading, an official search index, a recovered original and unavailability. Where only part of a document was obtained, no check of the full law, study or whole page is claimed. Publication, application of a regime and individual access were not equated with one another.

## Findings and corrections

The new pass found no confirmed critical/major/minor errors that required a change to the mechanism or wording of this chapter.

**Observation P00-O001 — access recovered, no error in the original entry.** P00-S004 previously had an index-only limitation. On new independent access, the full section relevant to the claim could be read, [Modern Treasury Ledger Account Balances object](https://docs.moderntreasury.com/platform/reference/ledger-balances-object), including the table and formulas. C006–C009 were assessed against the current documentation. This does not cancel the actual reading limitation of 15 September and does not restore the historical version of the page.

**Observation P00-O002 — a weak source was not silently replaced.** For P00-S021, the official index [BIS executive summary](https://www.bis.org/fsi/publ/insights19_summary.pdf) was recovered. It is linked to the original study but is not passed off as a direct reading of the full PDF. C033–C034 are left as `partial`. The original and recovered URLs are shown in the matrices.

## Significant statements outside the register, and calculations

- Re-examined: the differences between a legal claim, a technical record and a monetary resource; the scenario of an uncertain transfer outcome and subsequent reconciliation. The synthetic example of a possible duplicate payment is not presented as an observed error rate.
- Checked the bank balance sheets before and after the loan was issued and transferred: initial equalities 1000 = 900 + 100 and 600 = 540 + 60, subsequent 1000 = 900 + 100 and 700 = 640 + 60; total reserves 350, deposits grow from 1440 to 1540. A loss of 120 with equity of 100 gives −20; a liquidity loan of 50 does not by itself restore equity.
- In the eight journal entries, each side totals 422. Final assets 128 = liabilities 105 + equity 23; client money 105 and own money 23 are not commingled. A refund of 20 gives cash 115, merchant payable 15 and assets 138 in the stated model.
- Recalculated: 25 bps of 20,000 = 50; interest 1000 × 12% × 30/365 ≈ 9.863; the FX, BNPL (114 paid out, 90 collected, loss 24) and insurance (15,000 and −45,000) examples. No material arithmetic errors were found.
- The neobank/BaaS definitions and participant maps are treated as an educational classification. They do not establish the regulatory status of any specific business.

## Remaining limitations

- C018–C019: the relevant EBA answer is available via the official index; the full primary statutory/judicial context was not obtained again.
- C024: the BIS section on the monetary claim and tokenization was read; the whole passage on retail/wholesale access was not confirmed in this pass. C031: the full set of SEC paragraphs on all intermediaries was not reread. C037: the exact ISO subsection in the OCC handbook was not fully checked. These compound claims therefore have `partial`.
- C032 — NAIC index; C033–C034 — BIS index, without a full independent reading of the study. The causal effectiveness of suptech cannot be inferred from the description of a survey of 39 authorities and supplementary materials.
- C029: the substantive FDIC original on third-party apps was not obtained. This is `unverifiable`, not established falsity. Another FDIC document on pass-through has a narrower subject and is not used as a silent substitute.
- Current dynamic pages do not confirm that the text was unchanged as of 2026-09-15. Real bank entries, user contracts, current account pricing and the suitability of the scheme for a specific jurisdiction were not checked.

## Recheck and version binding

On 2026-09-17, after the editorial freeze, the pointers to the new audit and the relevant current excerpts were reread; the original cards and claims were reconciled with the individual rows of the matrices. No row inherited a verdict automatically from the previous REVIEW. Substantive limitations were preserved at the final check. The old REVIEW and its hashes refer to a historical snapshot.

final_verdict: `reviewed_with_limitations`  
open_critical: `0`  
open_major: `0`  
final_recheck: `2026-09-17 Asia/Makassar`

| File relative to chapters/part-00 | SHA-256 of the final checked version |
|---|---|
| CHAPTER.md | `30315980fc4cfd8f269aafec93de223a932233745880dff002c0f5bafe0885b9` |
| SOURCES.md | `1425d21ad7b42982ad6eec5c547d4389f5d676c2328555da05cd879ae5d6efac` |
| CLAIMS.md | `ac36cb5b28b72161db6bd4479a02615937f782d085464c8e3d1b6ef2f759358c` |
