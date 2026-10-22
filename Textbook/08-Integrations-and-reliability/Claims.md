---
title: "Chapter 8 — register of material claims"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Integrations and reliability](README.md) · [Contents](../README.md) · [All sources and checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Chapter 8 — register of material claims

**v0.1 · independently_reviewed_draft · private.** Author: `part_08_research`; independent review: see REVIEW.md. Cutoff for all current technical statements: **2026-09-15**; `last_checked_at=2026-09-15, Asia/Makassar`, day precision. No status here means operational acceptance of a product.

The fact-check of the original edition was completed on 2026-09-17. The relationship between the original version and the public copy, the scope of adaptation and the current navigation are described in the edition record.

## How to read this

`confirmed` means consistency with the source as read **within the stated scope**. For vendor docs, what is confirmed is the described contract, not the client's actual configuration; for a social/operator account, it is the content of the attributed statement, not the independent truth of every observation. Each evidence ID has a snapshot by the actual date; no copy of the document was saved. Shared metadata and URLs: [Sources](Sources.md).

For all cards: `as_of=2026-09-15`, except for explicitly dated historical experience; `reviewer=see_REVIEW.md`, `review_status=see_REVIEW.md`; `effective_from/effective_to=not_applicable` for technical explanations; the national applicability of BCBS is not established. `review_trigger`: a new version of the API/document, a change of account/country/model, a release of a specific plugin, or new contradicting evidence. Not finding a conflict does not prove that no conflicts exist.

The author's diagrams, internal state names, pilot/kill criteria, queue rules and numerical examples are a **proposed teaching construct**, not the documented API of any specific company. The arithmetic was checked separately; no fictitious external source is created for synthetic amounts. Applying the financial classification and models 1–5 in practice requires specialist review.

## P08-C001

- **module_ids:** 8.1; **claim_kind:** `mechanism`; **status:** `confirmed` within the scope below.
- **Claim:** The Store API serves the customer context and does not give administrative access to other people's data.
- **Evidence:** [P08-S001 / P08-S001-20260915](Sources.md#p08-s001); **locator:** Introduction; Requirements and limitations; Store API Namespace; **relation:** supports.
- **Scope / conditions:** WooCommerce Store API v1.
- **Reasoning / limits:** Unauthenticated does not mean there are no nonce/session constraints. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C002

- **module_ids:** 8.1; **claim_kind:** `product`; **status:** `confirmed` within the scope below.
- **Claim:** The Woo REST API uses API keys with permissions; the documentation shows the administrative route wc/v3/orders.
- **Evidence:** [P08-S002 / P08-S002-20260915](Sources.md#p08-s002); **locator:** Generate keys; Make a basic request; **relation:** supports.
- **Scope / conditions:** WooCommerce REST API, the example described.
- **Reasoning / limits:** The version and permissions of a specific store were not checked. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C003

- **module_ids:** 8.1; **claim_kind:** `mechanism`; **status:** `confirmed` within the scope below.
- **Claim:** A gateway can return success for checkout processing while payment is still pending; the classic guide refers separately to Blocks.
- **Evidence:** [P08-S003 / P08-S003-20260915](Sources.md#p08-s003); **locator:** Creating a basic payment gateway; process_payment example; **relation:** supports.
- **Scope / conditions:** Classic Woo checkout; cheque example.
- **Reasoning / limits:** Do not extend the success of the returned array to settlement. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C004

- **module_ids:** 8.1; **claim_kind:** `product`; **status:** `confirmed` within the scope below.
- **Claim:** Checkout Blocks requires a separate integration of the payment method; reusing the gateway on the server side does not prove full compatibility.
- **Evidence:** [P08-S004 / P08-S004-20260915](Sources.md#p08-s004); **locator:** Server Side Integration; Processing Payments (legacy support); Processing Payments via the Store API; **relation:** supports.
- **Scope / conditions:** WooCommerce Blocks.
- **Reasoning / limits:** A specific extension needs to be checked; the claim is not about all plugins. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C005

- **module_ids:** 8.1; **claim_kind:** `product`; **status:** `confirmed` within the scope below.
- **Claim:** Woo outgoing webhooks have a documented default of being disabled after five failed retries.
- **Evidence:** [P08-S005 / P08-S005-20260915](Sources.md#p08-s005); **locator:** Creating webhooks, paragraph after activation ping; **relation:** supports.
- **Scope / conditions:** WooCommerce outgoing notifications.
- **Reasoning / limits:** Configurable behavior; not the contract for an incoming PSP callback. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C006

- **module_ids:** 8.1,8.4; **claim_kind:** `product`; **status:** `confirmed` within the scope below.
- **Claim:** Shopify Payments extensions require an approved Partner; custom payment extensions have a separate Plus eligibility.
- **Evidence:** [P08-S006 / P08-S006-20260915](Sources.md#p08-s006); **locator:** Introduction; How it works; Considerations; **relation:** supports.
- **Scope / conditions:** Shopify Payments Platform as read.
- **Reasoning / limits:** Does not confirm approval of a specific app or merchant. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C007

- **module_ids:** 8.1; **claim_kind:** `product`; **status:** `confirmed` within the scope below.
- **Claim:** Checkout UI extensions on the information/shipping/payment steps are described as Plus-only.
- **Evidence:** [P08-S007 / P08-S007-20260915](Sources.md#p08-s007); **locator:** Shopify Plus notice; selector 2026-07; **relation:** supports.
- **Scope / conditions:** The listed checkout steps.
- **Reasoning / limits:** Does not automatically apply to all Shopify surfaces; not a payments approval. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C008

- **module_ids:** 8.1; **claim_kind:** `mechanism`; **status:** `confirmed` within the scope below.
- **Claim:** The Adobe gateway separates payment commands and request/client/validation/handling layers.
- **Evidence:** [P08-S010 / P08-S010-20260915](Sources.md#p08-s010); **locator:** What is Adobe Commerce payment provider gateway; operations; chapter components; **relation:** supports.
- **Scope / conditions:** Adobe Commerce conceptual gateway.
- **Reasoning / limits:** The existence of the abstraction does not guarantee every method/operation at a specific PSP. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C009

- **module_ids:** 8.2,8.5; **claim_kind:** `product`; **status:** `confirmed` within the scope below.
- **Claim:** The Adyen Modification Reference can be the same for a capture and a chargeback.
- **Evidence:** [P08-S017 / P08-S017-20260915](Sources.md#p08-s017); **locator:** Columns, Modification Reference; **relation:** supports.
- **Scope / conditions:** Adyen Settlement details report.
- **Reasoning / limits:** Build the key with the type and account scope; do not assume the field is unique on its own. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C010

- **module_ids:** 8.2,8.6; **claim_kind:** `mechanism`; **status:** `confirmed` within the scope below.
- **Claim:** Stripe idempotency saves the result of a request that has begun execution, including a 500; a key may be removed once it is at least 24h old.
- **Evidence:** [P08-S011 / P08-S011-20260915](Sources.md#p08-s011); **locator:** Saved status/body; key removal; execution start; **relation:** supports.
- **Scope / conditions:** Stripe API v1 mutating request contract.
- **Reasoning / limits:** After pruning, the old key can produce a new request; validation/concurrency exceptions are separate. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C011

- **module_ids:** 8.2; **claim_kind:** `mechanism`; **status:** `confirmed` within the scope below.
- **Claim:** AWS treats a semantically equivalent response, late retries and changed intent as parts of the idempotency contract.
- **Evidence:** [P08-S014 / P08-S014-20260915](Sources.md#p08-s014); **locator:** Retries and semantic equivalence; Late arriving requests; Same client request ID, different intent; **relation:** supports.
- **Scope / conditions:** AWS design explanation.
- **Reasoning / limits:** This is design context, not a financial provider's contract. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C012

- **module_ids:** 8.2; **claim_kind:** `mechanism`; **status:** `confirmed` within the scope below.
- **Claim:** RIFL ties exactly-once RPC to a durable completion record, atomic recording of effects and finding the result after migration.
- **Evidence:** [P08-S016 / P08-S016-20260915](Sources.md#p08-s016); **locator:** §3 Architecture; §4.1 ResultTracker; PDF pp. 3–5; **relation:** supports.
- **Scope / conditions:** RIFL distributed storage model.
- **Reasoning / limits:** Not exactly-once for an arbitrary PSP/shop/bank chain; leases/client failures limit the model. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C013

- **module_ids:** 8.2,8.6; **claim_kind:** `mechanism`; **status:** `confirmed` within the scope below.
- **Claim:** A Stripe 500 may have user-visible side effects; a new idempotency key is not recommended for such a retry.
- **Evidence:** [P08-S013 / P08-S013-20260915](Sources.md#p08-s013); **locator:** Server errors, especially indeterminate result paragraphs; **relation:** supports.
- **Scope / conditions:** Stripe 500 and unknown outcomes.
- **Reasoning / limits:** The chapter's query/reconcile scheme is a design adaptation; a network retry with the same key is allowed by the contract. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C014

- **module_ids:** 8.2,8.6; **claim_kind:** `mechanism`; **status:** `confirmed` within the scope below.
- **Claim:** A transactional outbox ties a local database change to the recording of an outgoing event; the consumer needs protection against duplicates.
- **Evidence:** [P08-S015 / P08-S015-20260915](Sources.md#p08-s015); **locator:** Intent; Issues and considerations; Implementation; **relation:** supports.
- **Scope / conditions:** Database and message publication boundary.
- **Reasoning / limits:** Does not make the external PSP part of the local atomic transaction. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C015

- **module_ids:** 8.3,8.5; **claim_kind:** `product`; **status:** `confirmed` within the scope below.
- **Claim:** The Adyen settlement report separates financial row types and gives a payout reference/batch for matching against the bank.
- **Evidence:** [P08-S017 / P08-S017-20260915](Sources.md#p08-s017); **locator:** Report structure; Merchant payout; **relation:** supports.
- **Scope / conditions:** Adyen merchant reporting.
- **Reasoning / limits:** The chapter's synthetic statement is not a copy of Adyen's actual format. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C016

- **module_ids:** 8.3; **claim_kind:** `product`; **status:** `confirmed` within the scope below.
- **Claim:** Stripe Payout reconciliation is oriented toward automatic payouts; manual/instant payouts have limitations and a separate reconciliation path.
- **Evidence:** [P08-S018 / P08-S018-20260915](Sources.md#p08-s018); **locator:** Overview paragraphs 1–4; Report sections; **relation:** supports.
- **Scope / conditions:** Stripe reports; includes manual-platform/automatic-connected exception.
- **Reasoning / limits:** Apply the report's exact eligibility; no report replaces the bank. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C017

- **module_ids:** 8.3,8.6; **claim_kind:** `mechanism`; **status:** `confirmed` within the scope below.
- **Claim:** Stripe warns against triggering fulfillment on the client side: the buyer may leave after paying.
- **Evidence:** [P08-S023 / P08-S023-20260915](Sources.md#p08-s023); **locator:** Monitor a PaymentIntent with webhooks; **relation:** supports.
- **Scope / conditions:** PaymentIntents integration.
- **Reasoning / limits:** A webhook trigger does not prove that the goods were successfully delivered. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C018

- **module_ids:** 8.4; **claim_kind:** `product`; **status:** `confirmed` within the scope below.
- **Claim:** Payment method support depends on business location, customer country, currency and product/API scope; Connect eligibility may differ.
- **Evidence:** [P08-S022 / P08-S022-20260915](Sources.md#p08-s022); **locator:** Country and currency support; Connected accounts notice; Product support; **relation:** supports.
- **Scope / conditions:** Stripe support matrix.
- **Reasoning / limits:** A list of countries does not mean that all combinations are available; individual terms were not researched in full. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C019

- **module_ids:** 8.5; **claim_kind:** `definition`; **status:** `confirmed` within the scope below.
- **Claim:** A trial balance that balances does not rule out erroneous double entries.
- **Evidence:** [P08-S021 / P08-S021-20260915](Sources.md#p08-s021); **locator:** Example 3, p. 3, explanatory paragraphs; **relation:** supports.
- **Scope / conditions:** ACCA teaching: double-entry bookkeeping.
- **Reasoning / limits:** Not current accounting policy; the chapter's monetary counterexample is synthetic. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C020

- **module_ids:** 8.5; **claim_kind:** `product`; **status:** `confirmed` within the scope below.
- **Claim:** A Stripe Balance Transaction stores gross/fee/net and the time of availability in the Stripe balance separately.
- **Evidence:** [P08-S019 / P08-S019-20260915](Sources.md#p08-s019); **locator:** Attributes: amount, fee, net, available_on, status; **relation:** supports.
- **Scope / conditions:** Stripe balance transactions.
- **Reasoning / limits:** available_on does not mean the funds have arrived at the bank. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C021

- **module_ids:** 8.5; **claim_kind:** `product`; **status:** `confirmed` within the scope below.
- **Claim:** Stripe amount encoding has special cases; 5 ISK is sent as 500, with no way to send fractional ISK.
- **Evidence:** [P08-S020 / P08-S020-20260915](Sources.md#p08-s020); **locator:** Specify amounts; Special cases, ISK; **relation:** supports.
- **Scope / conditions:** Stripe currency contract.
- **Reasoning / limits:** Not a universal encoding for all APIs; the chapter's FX figures are synthetic. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C022

- **module_ids:** 8.6; **claim_kind:** `product`; **status:** `confirmed` within the scope below.
- **Claim:** Stripe does not guarantee the order of webhook events; live retries are described as lasting up to three days.
- **Evidence:** [P08-S012 / P08-S012-20260915](Sources.md#p08-s012); **locator:** Event delivery behaviors: Automatic retries; Event ordering; **relation:** supports.
- **Scope / conditions:** Stripe live webhook delivery.
- **Reasoning / limits:** Not a guarantee that every event reaches the application or is processed by it. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C023

- **module_ids:** 8.6; **claim_kind:** `product`; **status:** `confirmed` within the scope below.
- **Claim:** The Shopify Webhook-Id identifies a delivery; the Event-Id groups the deliveries of a single merchant action.
- **Evidence:** [P08-S008 / P08-S008-20260915](Sources.md#p08-s008); **locator:** Headers; Example request headers; **relation:** supports.
- **Scope / conditions:** Shopify webhook reference selector 2026-07.
- **Reasoning / limits:** Event-ID does not replace consumer-specific and economic-operation deduplication. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C024

- **module_ids:** 8.6; **claim_kind:** `product`; **status:** `confirmed` within the scope below.
- **Claim:** The Shopify HTTPS receiving guide describes persistent deduplication, a fast response and reconciliation; timeout 1s/5s.
- **Evidence:** [P08-S009 / P08-S009-20260915](Sources.md#p08-s009); **locator:** Ignoring duplicates; HTTPS delivery considerations; **relation:** supports.
- **Scope / conditions:** Shopify HTTPS, the guide as read.
- **Reasoning / limits:** Do not carry the parameters over to Woo/PSPs; the durable inbox scheme is a design elaboration. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C025

- **module_ids:** 8.6; **claim_kind:** `mechanism`; **status:** `confirmed` within the scope below.
- **Claim:** Stripe signature verification requires the original, unmodified request body and the correct endpoint secret.
- **Evidence:** [P08-S028 / P08-S028-20260915](Sources.md#p08-s028); **locator:** Intro; Check endpoint secret; Check request body; **relation:** supports.
- **Scope / conditions:** Stripe webhook verification.
- **Reasoning / limits:** Not permission to execute arbitrary payload text; secrets are not logged in the proposed scheme. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C026

- **module_ids:** 8.6; **claim_kind:** `mechanism`; **status:** `confirmed` within the scope below.
- **Claim:** Stripe signs the delivery timestamp; on a retry it signs a new time, so recency and the newness of the event are different things.
- **Evidence:** [P08-S012 / P08-S012-20260915](Sources.md#p08-s012); **locator:** Preventing replay attacks; **relation:** supports.
- **Scope / conditions:** Stripe signature contract.
- **Reasoning / limits:** Freshness does not replace durable deduplication; another PSP's specific replay policy is checked separately. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C027

- **module_ids:** 8.6; **claim_kind:** `mechanism`; **status:** `confirmed` within the scope below.
- **Claim:** OWASP API6:2023 describes the abuse of sensitive business flows through automation.
- **Evidence:** [P08-S026 / P08-S026-20260915](Sources.md#p08-s026); **locator:** Is the API Vulnerable?; Example Attack Scenarios; **relation:** supports.
- **Scope / conditions:** OWASP awareness guidance.
- **Reasoning / limits:** The chapter's limits on reservations/amounts are a design conclusion; no real attack on a product is claimed. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C028

- **module_ids:** 8.6; **claim_kind:** `experience`; **status:** `confirmed` within the scope below.
- **Claim:** Monzo engineers reported an outage of about an hour in August 2024 and how Stand-in worked; they described how effects were carried over, and correlation IDs.
- **Evidence:** [P08-S024 / P08-S024-20260915](Sources.md#p08-s024); **locator:** Syncing state; Correlating data; You might have seen Monzo Stand-in; **relation:** supports.
- **Scope / conditions:** Monzo operator account published 2025-02-13.
- **Reasoning / limits:** The content of the publication is confirmed; an independent SLO and the exact cause are not established. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C029

- **module_ids:** 8.6; **claim_kind:** `mechanism`; **status:** `confirmed` within the scope below.
- **Claim:** BCBS Principles 3–6 include continuity testing, mapping, third-party dependencies and incident recovery.
- **Evidence:** [P08-S025 / P08-S025-20260915](Sources.md#p08-s025); **locator:** Principles 3–6, printed pp. 5–7; **relation:** supports.
- **Scope / conditions:** Banks; international supervisory principles, 2021.
- **Reasoning / limits:** Whether these are legally binding nationally for a specific entity was not researched; not a rule for every store. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

## P08-C030

- **module_ids:** 8.6; **claim_kind:** `experience`; **status:** `confirmed` within the scope below.
- **Claim:** IndicationOne9495 publicly describes difficulties with inline webhook processing and asks about queues.
- **Evidence:** [P08-S027 / P08-S027-20260915](Sources.md#p08-s027); **locator:** Original post body; **relation:** supports.
- **Scope / conditions:** Reddit public question; absolute date unknown.
- **Reasoning / limits:** The text/author as displayed is confirmed, not the frequency/cause of the problems, and it is not a benchmark. The statement is limited to the locator read, with no extrapolation to the whole market.
- **Conflicts / resolution:** no material contradiction with the locator read was found; contentious generalization is excluded by the stated conditions.

