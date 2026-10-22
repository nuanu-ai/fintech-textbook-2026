---
title: "Chapter 5 — research log"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Wallets, accounts and cards](README.md) · [Contents](../README.md) · [All sources and fact-checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Chapter 5 — research log

An internal organizational link from the historical author's note has been removed from the public edition; the research methodology and external sources are preserved.

## Read and agreed

- RESEARCH_BRIEF, the learning base README, SOURCE_DATASET_SCHEMA, MODULE_TEMPLATE, RESEARCH_RUN, Chapter 5 and the boundaries of Chapters 4/6 in the v02 structure.
- Chapters 0/1/2 were reviewed for terms and connections: safeguarding is not deposit insurance; a refund operation does not undo the finality of the original settlement; an operational sub-ledger is not a mandatory form of financial reporting.
- The editor's hypotheses from the working notes were checked against the originals. Data on Lab products and clients is not used.

## Access limitations

- FDIC: opening the two pages directly returned HTTP 403. The index representation was used: S004 — substantive excerpts, S005 — the full text of §§I–VI. This is not a direct reading of the pages, and the extent of access differs. The terms of any specific bank/account were not checked.
- EBA Q&A 2022_6336 and 2018_4272: a direct fetch gave an internal error; the final answers are available through the index. The substantive extent and the publication date are recorded in SOURCES.
- EBA Travel Rule Guidelines PDF: direct open internal error; the main text of the guidelines is not used for thresholds or for the list of mandatory checks. The official announcement that was read is used; it sets out the scope and the date of application; a detailed country-by-country analysis is in Chapters 1/6.
- Reddit: the thread about pending refunds is readable; threads 1dpqzb9 and 1lm0hul are not directly accessible. Their snippets are not included as evidence. The exact dates of comments in the accessible thread were not reconstructed from the relative ‘2y ago’. The post date is tied to the visible Reddit archive pointer 2024-07-16; its precision is stated separately.
- X was not needed for a separate independent case once a substantive Reddit thread had been found. No social-media quota was set.
- Fireblocks: the public backup/recovery overview was read. The closed support-portal procedure and actual recovery were not checked. The existence of documentation is not treated as a successful recovery of a specific wallet.
- Provider documentation is dynamic; exact commits and immutable snapshots were not obtained. Snapshot IDs mark the date of reading, not a saved copy or hash.

## Key distinctions for review

1. Coinbase Card: the available copy of the US agreement names Pathward as issuer, Marqeta as program manager, and the product as prepaid. The Help overview uses debit. The contractual term Coinbase Wallet is not equated with the self-custody app of the same name.
2. Stripe processor-only: there is no central Issuing Balance; the funding model differs from the standard integrated product. API controls apply to auth, not to the subsequent capture.
3. EIP/ ERC4337 is marked Final on the page that was read. The creation date 2021-09-29 is not the finalization date. The EntryPoint deployment/version/SHA were not established.
4. UK supplementary safeguarding regime: the application date 2026-05-07 was checked against PS25/12; the future post-repeal end-state is not declared to be already in force.
5. MiCA Art75 — regulated EU custody within its own scope; not a global guarantee of compensation, not insurance of the token price.
6. The 2016 academic paper is studied as historical research on authentication of the refund destination; no conclusion is drawn about a current vulnerability at Coinbase/BitPay.

## Not done and not claimed

No real transfers, signatures, private keys, wallet connections, legal opinion, vendor audit or check of product availability for a specific user. No third-party PDFs/illustrations are copied into the deliverable. The author does not carry out independent acceptance of their own chapter.

Addition after alignment: the Circle Europe MiCA Redemption Policy, updated 2026-07-13 (P05-S033), was read independently. In 5.3 a distinction between an exchange off-ramp and issuer redemption was added, without generalizing institutional-only. In 5.4 and exercise 6 the approximate result and rounding up for full discharge of the debt at six decimal places are shown.

## Manuscript check before handoff

The five module headings match the v02 structure; 33 source IDs and 33 explicit snapshot IDs are linked to 45 claims. The money tables, the arithmetic and both round-ups were checked; there are no placeholders. Local links within this chapter and to the finished Chapters 0–4 are valid. Links to Chapters 6/7/8 use future paths allowed by the brief: those files are still being written by other authors; this is a build dependency, not a broken name. The status remains draft_for_review.
