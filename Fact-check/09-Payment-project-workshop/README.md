---
title: "Independent factual audit — Chapter 9"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Sources and fact-check](../README.md) · [Read the chapter](../../Textbook/09-Payment-project-workshop/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Independent factual audit — Chapter 9

2026-09-17 · Asia/Makassar (UTC+8) · auditor deep_audit_06_07_08_09 · private

## Result

The full CHAPTER/SOURCES/CLAIMS were read. A total of 26 claims and 21 source cards were assessed individually. No new confirmed critical/major issue was found. Four partial verdicts relate to inaccessible originals/the historical version, and one unverifiable verdict relates to the explicitly open question of whether the dynamic docs stayed unchanged. No inaccessibility has been masked as verified.

## Access to primary sources and limits of the conclusions

- **C001/S001, partial.** EUR-Lex consolidation/original/TXT/PDF returned a JS challenge (HTTP 202). Article 3(j) was independently read directly in the official legislation.gov.uk mirror of the EU directive: the technical services exclusion contains the PIS/AIS carve-out. Identity with the full consolidation of 2025-01-17 is not confirmed. This is a limitation of the version check, not a contradiction found in the mechanism.
- **C002/C016/S003 and C017/S004, partial.** Bank Indonesia original pages/PDF were not obtained because of resets/timeouts. In the official index, QRIS sources of funds/static-dynamic/approved participants and PBI 10/2025 effective 2026-03-31/new framework were read. This cannot be called a direct reading of the whole BI page or of the regulation.
- **C018/S012, verified via an alternative primary source.** The EUR-Lex body is inaccessible, but the ESMA official reproduction of Articles 59, 60, 143 was read directly. The authorisation/financial-entity routes and the maximum transition of 2026-07-01 are confirmed, with earlier grant/refusal and a country's right to shorten the transition. The consolidation metadata is not declared independently confirmed.
- **C026, unverifiable.** There is no archived 15 September snapshot of the dynamic Stripe/x402 documents. The text honestly leaves the identity of the versions open, and the 17 September observation is dated separately.
- **S013/S018, metadata limitations.** Google's structured datePublished 2025-09-16 differs from one HTML display of 17 September; the card's date is not deemed wrong. The current Circle byline, Circle Internet Financial, differs from Team Circle in the card; the historical form of the byline was not established, and this does not change the mechanism/dates of the operational report.

## Full chapter, cases and arithmetic

Material facts outside the register were checked: separate merchant/provider agreements, the moment of debt discharge in the synthetic contract, approvals/licensing and the source of refund liquidity. Stripe terms §5 provide their own contractual debt-discharge trigger; synthetic case C is not passed off as these real terms.

Cases A–D were recalculated from the opening balances and movements:

| Case | Independent numerical check |
|---|---|
| A | Bank 1,000 + 87 − 15.50 = 1,071.50 EUR; trial 1,071.50 + 25 + 3.50 = 1,100; buyer 425 EUR. If the reserve is not released, a full top-up of 25.50 is needed. |
| B | Fee 11,200 IDR; bank 2,000,000 + 1,588,800 − 400,000 − 2,500 = 3,186,300; buyer 1,800,000; expenses 13,700; trial 3,600,000. 0.7% is a condition of the exercise, not a universal QRIS rate. |
| C | Bank 1,000 + 98 − 25.50 = 1,072.50 EUR; refund 25 × 1.12 = 28 USDC; buyer 418. With a depeg, 25 × 1.12 / 0.98 = 28.571428… and rounded up 28.571429. A new payout is allowed after the return of funds is proven, not after a single timeout. |
| D | Buyer 72 USDC, seller 47.80, service 0.20; total 120. Seller journal 47.80 + 12 + 0.20 = 60, credit 20 + 40. The service covers the network cost out of its fee, per the conditions of the example. |
 
The liquidity shortfall with 1,000 cash and 4,000 refunds equals 3,000, despite the 10,000 claim on the partner. Arithmetic does not prove contractual enforceability, sufficiency of reserves or the legality of a real route. H1–H3 remained hypotheses; hypotheses are not a launch decision.

## Historical incident and limits of independence

The Fed/Treasury/FDIC statement of 2023-03-12, the Circle announcement with different body/page dates of 12/13 March, and the operational update of 15/16 March were read separately. Circle's 3.3bn reserve deposit, 3.8bn redemptions/.8bn minting and substantially all backlog are attributed statements. Execution of every request/bank transfer was not established. The Reddit MediumAdhesiveness5 post/Updates confirms that the discussion was published; the price-feed and causality were not checked.

The independent review is not a financial, legal or operational approval.

## Coverage and verdict counts — public edition

Claims: 26; 20 published source cards and 1 exclusion record, P09-S021. Every ID has one matrix row. C008/C009 were replaced with editorial positions on 2026-09-18: verified → non_factual. The rest of the fact-check keeps the date 2026-09-17.

- partial: 4
- verified: 11
- non_factual: 5
- verified_as_reported: 5
- unverifiable: 1

## Final recheck and hashes

The final text was read after the editor's provisional freeze. The hashes were calculated from the actual content of the final files. The previous review was used only as a risk pointer, not as evidence.

final_verdict: reviewed_with_limitations

open_critical: 0

open_major: 0

| File | SHA-256 |
|---|---|
| [CHAPTER.md](../../Textbook/09-Payment-project-workshop/README.md) | 43b39c1c23c142cb72180197c69de9432df54d0643b527eed0aa1dcd8daf2f14 |
| [Sources](../../Textbook/09-Payment-project-workshop/Sources.md) | fc913f90460ec4f751b0b3eef83a48cafb88b05610e2e7e981c6eb1d2ea0ca00 |
| [Claims](../../Textbook/09-Payment-project-workshop/Claims.md) | 2232417ab58af5c2bb90576590a02b8aaf3165645935042f8b3f05f22b2d90e1 |
