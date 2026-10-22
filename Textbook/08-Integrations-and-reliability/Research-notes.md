---
title: "Chapter 8 — research log"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Integrations and reliability](README.md) · [Contents](../README.md) · [All sources and checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Chapter 8 — research log

Status: draft_for_review; author: part_08_research; cutoff: 2026-09-15; private.
An internal organizational link from the historical author's note has been removed from the public edition; the research methodology and external sources are preserved.

## Inputs read

RESEARCH_BRIEF.md, README.md, SOURCE_DATASET_SCHEMA.md, MODULE_TEMPLATE.md, RESEARCH_RUN_2026-09-15.md, the full modules 8.1–8.6 of STRUCTURE_v02. Also reviewed: the boundaries with 7/9, the terminology of models 1–5 in Chapter 1, and accounting in 0.5. These are editorial inputs, not external evidence.

## Access and version limitations

- WooCommerce: dynamic docs, Store API namespace v1. The full commit of the current docs and the installed version of any specific store are unknown; no store runtime is examined.
- Shopify: the latest webhook reference shows selector 2026-07; the direct /2026-07 URL did not open in the web tool. Keep the latest URL actually read, the selector and the date; do not call it an immutable snapshot.
- Stripe: the current docs include preview API examples; the general webhook rules do not confirm GA of all new event destinations. The chapter must not assert a rollout of preview features.
- Reddit /r/shopifyDev/1vtcxj0: the main text and public authors were read; the relative time 22h ago and the crawl metadata of 3 weeks do not give a reliable absolute day. Use it as an attributed question, not as evidence of frequency/throughput. /1wh16t3 was not opened and is not used as evidence.
- Monzo 2025-02-13: the operator's engineering account of the August 2024 outage and Stand-in; not an independent SLO audit and not a full investigation of causes.
- RIFL: the authors' Stanford PDF, SOSP 2015; the mechanism in §§2–4 and the limits of leases were read; do not claim a payment benchmark based on RAMCloud.
- Third-party full texts, screenshots and illustrations are not copied into the folder. Snapshot ID means the access date; there are no retained copies and no SHA.

## Outcome and editorial decisions

- CHAPTER: all modules 8.1–8.6 from v02; two original Mermaid state diagrams; 8 exercises with explained answers; a full synthetic journal J0–J15, an external PSP/bank statement and an FX example.
- SOURCES: 28 sources actually opened; CLAIMS: 30 material claims. Research basis: RIFL; teaching accounting source: the official ACCA examiner report; public experience: Monzo and Reddit.
- OpenStax §3.6 was opened as a candidate; the final accounting statement is tied to the official ACCA FA2 report that was read, pp.2–3. OpenStax texts/illustrations are not carried over.
- Stripe Payout reconciliation was refined: the case of a manual-payout platform with automatic-payout connected accounts is taken into account; an instant payout requires its own reconciliation. The single word manual without account scope would be too broad.
- The visible Shopify selector 2026-07 is kept as the version of the surface read; the stable URL is not declared an immutable copy.
- Stripe preview examples are not used to claim GA. Shopify UCP-specific order webhooks from the leads are not needed for the generic webhook contract and are not used in its place.

## Author checks — 2026-09-15

The checks were run locally, with no money or production actions. This is author verification, not an independent review.

1. All 16 journal entries J0–J15 were extracted from the Markdown table; Decimal arithmetic gave bank 1067.40 USD, fees 22.60 USD, and zeros for pending/reserve/PSP position/in-transit/customer obligations. The totals of each side of the final trial balance: 1200.00 USD.
2. The counterexample with a missing refund of 30.00 and a duplicate fee of 6.60 gives an internal PSP balance of 23.40 USD versus an external 0; fees 29.20; refund payable 30. Both sides of the erroneous trial balance: 1230.00 USD. Correcting entries restore the correct balances.
3. FX exercise: gross 90.00 USD, initial net 87.50 USD, refund debit 23.70 USD, result 63.80 USD.
4. All 6 module headings are kept exactly as in v02; sources P08-S001–S028 and claims P08-C001–C030 are continuous; no unknown ID references were found.
5. All existing local links were checked. ../part-09/CHAPTER.md is an expected editorial dependency on the next chapter; at the time of the check the file did not yet exist; the lead editor should check it once that chapter is assembled. The other links resolve.
6. The research directory is not a Git checkout; no commit/push was made. Only the four permitted part-08 files were changed. REVIEW.md was not created.

## Remaining limits

There is no specific merchant agreement, bank statement, store runtime or producer SLO audit. The ledger is a teaching operational subledger of the merchant, not an approved reporting policy. Final classification in a real business requires a contract and an accountant; the legal model requires specialist review. The research does not create an owner for publication/launch.

Handoff to the independent reviewer: the final balances and the erroneous balance, Stripe idempotency scope, Shopify permissions and IDs, the Woo Blocks boundary, the Monzo attribution and the unknown Reddit date. Status remains draft_for_review.
