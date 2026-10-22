---
title: "Independent factual audit — Chapter 8"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Sources and fact-check](../README.md) · [Read the chapter](../../Textbook/08-Integrations-and-reliability/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Independent factual audit — Chapter 8

2026-09-17 · Asia/Makassar (UTC+8) · auditor deep_audit_06_07_08_09 · private

## Result

The full CHAPTER/SOURCES/CLAIMS were read. All 30 claims and 28 source cards got separate rows. No confirmed errors requiring changes to the chapter were found. 28 claims verified within the limits of the cited documents, 2 verified_as_reported (Monzo and Reddit). This does not mean an operational check of all APIs.

## What was independently checked

The Woo Store API/customer context is kept separate from REST administrative keys; classic gateway success/on-hold is not called a completed payment. Blocks requires its own integration. Shopify payment extension approval and Plus restrictions were checked against specific sections; the delivery ID differs from the business event ID. Adobe command/request/client/validator/handler are not reduced to a single HTTP response.

Stripe idempotency was checked together with its exceptions: initial execution/500, pruning ≥24h, validation/concurrency, network versus server errors. The safe-retry recommendation uses the previous operation identity/parameters; no new payment is inferred from a timeout. Webhooks can repeat and arrive out of order; new signature timestamps on retry do not mean a new economic event. The Shopify receiving guide was read with the 1s/5s distinction and persistent deduplication/reconciliation.

The Adyen settlement report, Stripe payout reconciliation, available_on and currency encoding were read directly. available_on was additionally clarified via the official .md: it is availability in the Stripe balance, not a bank balance. The Modification Reference is not unique across capture/chargeback type. Automatic payouts, manual/instant payouts and platform exceptions are not mixed up.

RIFL was read within the scope of its architecture, assumptions, durable completion/effects/retry rendezvous and limitations. It is not a universal exactly-once guarantee for a payment through external systems. The AWS outbox gives atomicity of the local write; it does not remove the need for an idempotent consumer. BCBS Principles 3–6 apply to banks; the merchant checklist is an explicitly editorial adaptation.

## Reading the chapter beyond CLAIMS, and arithmetic

The full chapter was checked for important unregistered leaps success→payment, payment→fulfillment, balance→bank and balanced journal→correct accounting. No such unjustified leaps were found; the teaching examples use precisely these limitations.

In §8.5 the payout of 173.40, the subsequent refund/fee/reserve/dispute movements and the PSP total of −106 were independently recalculated; bank 1067.40 and expenses 22.60 give a consistent total. The counterexample with a missing refund/duplicate fee keeps a formal balance but misrepresents the outside world. Synthetic fees/reserves/FX are not attributed to Stripe/Adyen pricing.

## Social, metadata and limitations

Monzo is a dated engineering self-report by Daniel Chatfield/Andrew Lawson about an outage of about an hour in August 2024 and Stand-in; actual production logs were not obtained. The original body of the Reddit post by IndicationOne9495 was read via web extraction after the HTML shell. Relative time and crawl age were not used to invent an absolute date. The causes, frequency and scale of the problems are not considered established.

Dynamic API docs were read on 2026-09-17. Visible current versions do not prove that nothing changed since 15 September. The full metadata check is limited to information actually visible in the document read; unknown publication/effective dates remain unknown. There were no payments, provider account tests, conformance execution or replication of RIFL. The previous review was not used as evidence.

## Coverage and verdict counts

Claims: 30; source cards: 28. Every ID has one matrix row.

- verified: 28
- verified_as_reported: 2

## Final recheck and hashes

The final text was read after the editor's provisional freeze. Hashes were calculated from the actual content of the final files. The previous review was used only as a risk pointer, not as evidence.

final_verdict: reviewed_with_limitations

open_critical: 0

open_major: 0

| File | SHA-256 |
|---|---|
| [CHAPTER.md](../../Textbook/08-Integrations-and-reliability/README.md) | 43b7ec2eccae6a9aab29c11906ce0cf1851f07e4538cabb4c60918d6d43fabd4 |
| [Sources](../../Textbook/08-Integrations-and-reliability/Sources.md) | 0df23aedfb6afdea18806844c2ccb79a5343f437d6d0de41583025c0f9987e24 |
| [Claims](../../Textbook/08-Integrations-and-reliability/Claims.md) | c974dd62d210ff4e70ef3ff7220761b493935cde895304777db248ff3ff67149 |
