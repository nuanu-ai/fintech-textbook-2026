---
title: "Chapter 8 — source catalog"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Integrations and reliability](README.md) · [Contents](../README.md) · [All sources and checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Chapter 8 — source catalog

**v0.1 · independently_reviewed_draft · private.** Author: `part_08_research`. Knowledge cutoff: **2026-09-15**. All originals listed were actually opened on 2026-09-15, Asia/Makassar (UTC+08), during the research session; `date_precision=day` for the access date. A search on its own is not recorded as reading.

The fact-check of the original edition was completed on 2026-09-17. The relationship between the original version and the public copy, the scope of adaptation and the current navigation are described in the edition record.

## Common values and method

The following fields apply to every card unless overridden: `supersedes=none`; `updated_at=unknown`; `effective_from/effective_to=not_applicable` for technical/teaching materials (this is not the date a law enters into force); `language=en`; `locale=publisher original`; `access_status=partial_text` and `access_method=direct_page` for selected HTML sections, `official_pdf` for publisher PDFs, `author_pdf` for Stanford; the actual `reviewed_scope` is given separately. `accessed_at=2026-09-15+08:00`, day precision. `reviewer=see_REVIEW.md`; `review_status=see_REVIEW.md`.

`Snapshot ID` is an identifier of a reading, **not a claim that a copy was saved**. For all sources `local_path=not_saved`, `sha256=not_computed`; public pages and third-party images were not copied into this folder. Where only sections were read, the full document is not declared checked in its entirety. `origin_source_id=self`; the independence group shows common origin — several Stripe pages do not count as several independent confirmations of Stripe's reliability.

Default rights: copyright of the publisher/author; permission to reprint the full text or illustrations, or to distribute commercially, is **unknown** and is not assumed. Direct links and an original, limited synthesis are used, without long quotations. `rights_basis_url` is the card's URL and the notices explicitly shown there; no separate license was checked except where noted below. This is not a legal assessment of rights. Publisher/locator data serve traceability and are not a vendor recommendation.

For vendor sources, the shared `interests`: the publisher describes its own product and has an interest in its use; the docs confirm the stated API scope, not independent operational effectiveness. For technical sources, `jurisdiction` is determined by the product/account scope below, not by the word worldwide. Detailed merchant agreements and geographic legal authorizations were not researched. The research source describes its own method and experiment, and the social post describes the author's experience; individual limits are listed in the corresponding cards. The BCBS principles do not by themselves establish national application to a specific operator.

## P08-S001

**Title:** WooCommerce Store API

- **Snapshot:** `P08-S001-20260915`; **author/publisher:** WooCommerce / Automattic.
- **URL / canonical:** [WooCommerce Store API](https://developer.woocommerce.com/docs/apis/store-api/).
- **Class / kind:** `vendor` / API documentation; **independence_group:** `woo`.
- **Published:** unknown; **updated:** unknown; **version/status:** Store API namespace v1; docs commit unknown. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Introductory section; Requirements and limitations; Store API Namespace; Extensibility.
- **Activity / audience / jurisdiction scope:** public customer-facing API; actual store version unknown.
- **Limitations / interests:** Do not read unauthenticated as permission to access other people's orders.
- **Rights:** The Woo docs footer states GPLv3; only links and our own synthesis are used here, no code/images were carried over; license scope was not separately audited. Rights basis: the original at the URL above; no local copy/hash.

## P08-S002

**Title:** WooCommerce REST API

- **Snapshot:** `P08-S002-20260915`; **author/publisher:** WooCommerce / Automattic.
- **URL / canonical:** [WooCommerce REST API](https://developer.woocommerce.com/docs/apis/rest-api/).
- **Class / kind:** `vendor` / API documentation; **independence_group:** `woo`.
- **Published:** unknown; **updated:** unknown; **version/status:** wc/v3 in the example read; installed WC version unknown. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Generate keys; Make a basic request; Request/Response format; API version history.
- **Activity / audience / jurisdiction scope:** authenticated merchant administration.
- **Limitations / interests:** Examples for old versions and tips for localhost are not a safe production configuration.
- **Rights:** The Woo docs footer states GPLv3; only links and our own synthesis are used here, no code/images were carried over; license scope was not separately audited. Rights basis: the original at the URL above; no local copy/hash.

## P08-S003

**Title:** WooCommerce Payment Gateway API

- **Snapshot:** `P08-S003-20260915`; **author/publisher:** WooCommerce / Automattic.
- **URL / canonical:** [WooCommerce Payment Gateway API](https://developer.woocommerce.com/docs/features/payments/payment-gateway-api/).
- **Class / kind:** `vendor` / integration guide; **independence_group:** `woo`.
- **Published:** unknown; **updated:** unknown; **version/status:** dynamic docs; version/commit unknown. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Creating a basic payment gateway; process_payment; Order Status Best Practice; Working with Payment Gateway Callbacks.
- **Activity / audience / jurisdiction scope:** classic/default checkout; incoming gateway callback.
- **Limitations / interests:** A classic gateway does not prove Blocks support; the historical callback example that replaces https with http is not reproduced.
- **Rights:** The Woo docs footer states GPLv3; only links and our own synthesis are used here, no code/images were carried over; license scope was not separately audited. Rights basis: the original at the URL above; no local copy/hash.

## P08-S004

**Title:** Payment method integration

- **Snapshot:** `P08-S004-20260915`; **author/publisher:** WooCommerce / Automattic.
- **URL / canonical:** [Payment method integration](https://developer.woocommerce.com/docs/block-development/extensible-blocks/cart-and-checkout-blocks/checkout-payment-methods/payment-method-integration/).
- **Class / kind:** `vendor` / integration guide; **independence_group:** `woo`.
- **Published:** unknown; **updated:** unknown; **version/status:** dynamic Blocks docs; commit unknown. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Client Side integration; Server Side Integration; Processing Payments (legacy support); Processing Payments via the Store API.
- **Activity / audience / jurisdiction scope:** WooCommerce Checkout Blocks.
- **Limitations / interests:** UI and server registration is separate from the payment processing API; the full source code of the examples was not audited.
- **Rights:** The Woo docs footer states GPLv3; only links and our own synthesis are used here, no code/images were carried over; license scope was not separately audited. Rights basis: the original at the URL above; no local copy/hash.

## P08-S005

**Title:** Working with webhooks in WooCommerce

- **Snapshot:** `P08-S005-20260915`; **author/publisher:** WooCommerce / Automattic.
- **URL / canonical:** [Working with webhooks in WooCommerce](https://developer.woocommerce.com/docs/best-practices/urls-and-routing/webhooks/).
- **Class / kind:** `vendor` / operations documentation; **independence_group:** `woo`.
- **Published:** unknown; **updated:** unknown; **version/status:** dynamic docs; default configurable. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `full_text` / `direct_page`.
- **Reviewed scope / locator:** What are webhooks; Creating webhooks; Webhook logs.
- **Activity / audience / jurisdiction scope:** outgoing WooCommerce notifications.
- **Limitations / interests:** Five retries is the stated default behavior and can be changed with a filter; this is not the contract for an incoming PSP callback.
- **Rights:** The Woo docs footer states GPLv3; only links and our own synthesis are used here, no code/images were carried over; license scope was not separately audited. Rights basis: the original at the URL above; no local copy/hash.

## P08-S006

**Title:** Extensions for payments

- **Snapshot:** `P08-S006-20260915`; **author/publisher:** Shopify.
- **URL / canonical:** [Extensions for payments](https://shopify.dev/docs/apps/build/payments).
- **Class / kind:** `vendor` / platform documentation; **independence_group:** `shopify`.
- **Published:** unknown; **updated:** unknown; **version/status:** dynamic docs; stable commit unknown. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Introductory section; How it works; Build options; Considerations; Supported features.
- **Activity / audience / jurisdiction scope:** Shopify Payments Platform; approved Partners; custom extensions eligibility.
- **Limitations / interests:** The platform description does not confirm access for a specific app/merchant.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S007

**Title:** Checkout UI extensions

- **Snapshot:** `P08-S007-20260915`; **author/publisher:** Shopify.
- **URL / canonical:** [Checkout UI extensions](https://shopify.dev/docs/api/checkout-ui-extensions/latest).
- **Class / kind:** `vendor` / API reference; **independence_group:** `shopify`.
- **Published:** unknown; **updated:** unknown; **version/status:** selector 2026-07 latest; latest URL mutable. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Introductory section; Shopify Plus notice; Building your extension.
- **Activity / audience / jurisdiction scope:** information/shipping/payment checkout steps.
- **Limitations / interests:** The Plus requirement applies to the listed steps; a UI extension does not replace Payments Platform approval.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S008

**Title:** Webhooks

- **Snapshot:** `P08-S008-20260915`; **author/publisher:** Shopify.
- **URL / canonical:** [Webhooks](https://shopify.dev/docs/api/webhooks/latest).
- **Class / kind:** `vendor` / API reference; **independence_group:** `shopify`.
- **Published:** unknown; **updated:** unknown; **version/status:** selector 2026-07 latest; immutable SHA unavailable. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Headers; Example request headers; Getting started; not the whole topics catalog.
- **Activity / audience / jurisdiction scope:** general shop webhook deliveries.
- **Limitations / interests:** Webhook-Id and Event-Id are different; the direct /2026-07 URL did not open, so the latest version that was actually read was used.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S009

**Title:** Verify webhook deliveries

- **Snapshot:** `P08-S009-20260915`; **author/publisher:** Shopify.
- **URL / canonical:** [Verify webhook deliveries](https://shopify.dev/docs/apps/build/webhooks/verify-deliveries).
- **Class / kind:** `vendor` / integration/security guide; **independence_group:** `shopify`.
- **Published:** unknown; **updated:** unknown; **version/status:** dynamic docs; version unknown. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** HMAC verification; Ignoring duplicates; HTTPS delivery considerations; Queue webhooks to handle traffic bursts.
- **Activity / audience / jurisdiction scope:** Shopify HTTPS webhook receiving.
- **Limitations / interests:** The original URL /subscribe/https redirected here; the rules do not carry over to other platforms.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S010

**Title:** Commerce payment provider gateway

- **Snapshot:** `P08-S010-20260915`; **author/publisher:** Adobe.
- **URL / canonical:** [Commerce payment provider gateway](https://developer.adobe.com/commerce/php/development/payments-integrations/payment-gateway/).
- **Class / kind:** `vendor` / conceptual integration documentation; **independence_group:** `adobe`.
- **Published:** unknown; **updated:** unknown; **version/status:** dynamic Commerce PHP docs; deployed product version unknown. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `full_text` / `direct_page`.
- **Reviewed scope / locator:** What is Adobe Commerce payment provider gateway; operations; component list; Terms used.
- **Activity / audience / jurisdiction scope:** Adobe Commerce payment gateway abstraction.
- **Limitations / interests:** The page is short and conceptual; the whole related chapter was not read, and the capabilities of any specific PSP are not confirmed.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S011

**Title:** Idempotent requests

- **Snapshot:** `P08-S011-20260915`; **author/publisher:** Stripe.
- **URL / canonical:** [Idempotent requests](https://docs.stripe.com/api/idempotent_requests).
- **Class / kind:** `vendor` / API reference; **independence_group:** `stripe`.
- **Published:** unknown; **updated:** unknown; **version/status:** API v1 idempotency surface; dynamic docs; request version not pinned. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `full_text` / `direct_page`.
- **Reviewed scope / locator:** Main text after the example: saved result, key lifetime, parameters, execution start, POST scope.
- **Activity / audience / jurisdiction scope:** Stripe API contract.
- **Limitations / interests:** 24h is the minimum age before possible pruning, not a promise that the key stays valid forever.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S012

**Title:** Receive Stripe events in your webhook endpoint

- **Snapshot:** `P08-S012-20260915`; **author/publisher:** Stripe.
- **URL / canonical:** [Receive Stripe events in your webhook endpoint](https://docs.stripe.com/webhooks).
- **Class / kind:** `vendor` / integration/security documentation; **independence_group:** `stripe`.
- **Published:** unknown; **updated:** unknown; **version/status:** dynamic docs; inspected generic/v1 behavior; v2 preview examples not evidence of GA. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Create a handler; Event delivery behaviors; Event ordering; Preventing replay attacks.
- **Activity / audience / jurisdiction scope:** Stripe event delivery; live versus sandbox distinctions.
- **Limitations / interests:** Not all example code was read; delivery time limits, signature freshness and economic deduplication are different parameters.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S013

**Title:** Advanced error handling / Low-level error handling

- **Snapshot:** `P08-S013-20260915`; **author/publisher:** Stripe.
- **URL / canonical:** [Advanced error handling / Low-level error handling](https://docs.stripe.com/error-low-level).
- **Class / kind:** `vendor` / API error contract documentation; **independence_group:** `stripe`.
- **Published:** unknown; **updated:** unknown; **version/status:** dynamic docs; v1 HTTP/idempotency scope. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Errors in HTTP; Network errors; Server errors; Idempotency.
- **Activity / audience / jurisdiction scope:** Stripe mutating requests.
- **Limitations / interests:** A 500 may have a side effect; a new key is not a safe way to investigate an old operation.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S014

**Title:** Making retries safe with idempotent APIs

- **Snapshot:** `P08-S014-20260915`; **author/publisher:** Malcolm Featonby / Amazon Web Services.
- **URL / canonical:** [Making retries safe with idempotent APIs](https://aws.amazon.com/builders-library/making-retries-safe-with-idempotent-APIs/).
- **Class / kind:** `vendor` / engineering article; **independence_group:** `aws`.
- **Published:** unknown; **updated:** unknown; **version/status:** AWS Builders Library; article version unknown. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Retries and semantic equivalence; Late arriving requests; Same client request ID, different intent.
- **Activity / audience / jurisdiction scope:** AWS distributed API design examples.
- **Limitations / interests:** Not a PSP contract and not proof of exactly-once between independent companies.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S015

**Title:** Transactional outbox pattern

- **Snapshot:** `P08-S015-20260915`; **author/publisher:** Amazon Web Services.
- **URL / canonical:** [Transactional outbox pattern](https://docs.aws.amazon.com/prescriptive-guidance/latest/cloud-design-patterns/transactional-outbox.html).
- **Class / kind:** `vendor` / architecture guidance; **independence_group:** `aws`.
- **Published:** unknown; **updated:** unknown; **version/status:** AWS Prescriptive Guidance; dynamic edition. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Intent; Motivation; Issues and considerations; Implementation using AWS services.
- **Activity / audience / jurisdiction scope:** database + event publication pattern.
- **Limitations / interests:** Queue guarantees do not automatically extend to the effect of an external payment service.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S016

**Title:** Implementing Linearizability at Large Scale and Low Latency

- **Snapshot:** `P08-S016-20260915`; **author/publisher:** Collin Lee; Seo Jin Park; Ankita Kejriwal; Satoshi Matsushita; John Ousterhout / Stanford University, NEC, ACM SOSP.
- **URL / canonical:** [Implementing Linearizability at Large Scale and Low Latency](https://web.stanford.edu/~ouster/cgi-bin/papers/rifl.pdf).
- **Class / kind:** `research` / peer-reviewed conference paper, author-hosted PDF; **independence_group:** `rifl`.
- **Published:** 2015; conference 2015-10-04/07; **updated:** unknown; **version/status:** SOSP 2015; DOI 10.1145/2815400.2815416. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `author_pdf`.
- **Reviewed scope / locator:** Abstract/introduction; §§2–4, PDF pp. 2–6: requirements, architecture, completion records, leases.
- **Activity / audience / jurisdiction scope:** distributed storage/RPC; RAMCloud implementation.
- **Limitations / interests:** Not a financial field study. Selected sections were read; the performance evaluation was not reviewed in full, and its figures were not carried over.
- **Rights:** PDF p.1 permits personal/classroom copies subject to notice and noncommercial use; no copy was saved and no images were carried over. Rights basis: the original at the URL above; no local copy/hash.

## P08-S017

**Title:** Settlement details report

- **Snapshot:** `P08-S017-20260915`; **author/publisher:** Adyen.
- **URL / canonical:** [Settlement details report](https://docs.adyen.com/reporting/settlement-reconciliation/transaction-level/settlement-details-report/).
- **Class / kind:** `vendor` / financial reporting documentation; **independence_group:** `adyen`.
- **Published:** unknown; **updated:** unknown; **version/status:** dynamic report schema; generated schema depends on account/settings. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Report structure; Transactions; Deposit corrections; Merchant payout; Columns 6–8, 15–17.
- **Activity / audience / jurisdiction scope:** Adyen merchant settlement reconciliation.
- **Limitations / interests:** The example rows are historical; the Modification Reference can be the same for a capture and a chargeback; it is not a universal unique key.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S018

**Title:** Payout reconciliation report

- **Snapshot:** `P08-S018-20260915`; **author/publisher:** Stripe.
- **URL / canonical:** [Payout reconciliation report](https://docs.stripe.com/reports/payout-reconciliation).
- **Class / kind:** `vendor` / financial reporting documentation; **independence_group:** `stripe`.
- **Published:** unknown; **updated:** unknown; **version/status:** dynamic docs; account/report eligibility. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Overview; Balance summary; Payout reconciliation; Failed payouts; Ending balance reconciliation.
- **Activity / audience / jurisdiction scope:** automatic payouts; stated platform/connected-account exception.
- **Limitations / interests:** Manual/instant payout scopes differ; the report does not substitute for a bank statement.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S019

**Title:** The Balance Transaction object

- **Snapshot:** `P08-S019-20260915`; **author/publisher:** Stripe.
- **URL / canonical:** [The Balance Transaction object](https://docs.stripe.com/api/balance_transactions/object).
- **Class / kind:** `vendor` / API object reference; **independence_group:** `stripe`.
- **Published:** unknown; **updated:** unknown; **version/status:** dynamic API v1 reference; account request version unknown. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Attributes: amount, available_on, currency, exchange_rate, fee, net, status, source.
- **Activity / audience / jurisdiction scope:** Stripe balance movements.
- **Limitations / interests:** available_on refers to the Stripe balance; it is not a universal bank settlement timestamp.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S020

**Title:** Supported currencies

- **Snapshot:** `P08-S020-20260915`; **author/publisher:** Stripe.
- **URL / canonical:** [Supported currencies](https://docs.stripe.com/currencies).
- **Class / kind:** `vendor` / API currency documentation; **independence_group:** `stripe`.
- **Published:** unknown; **updated:** unknown; **version/status:** dynamic docs; product/region-dependent. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Specify amounts in API requests; Zero-decimal currencies; Special cases, ISK/HUF; conversion context.
- **Activity / audience / jurisdiction scope:** Stripe amount encoding and currencies.
- **Limitations / interests:** The ISO exponent is not always sufficient for API encoding. The chapter uses ISK; the currency eligibility of any specific account was not checked.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S021

**Title:** Examiner’s report: FA2 Maintaining Financial Records, July–December 2016

- **Snapshot:** `P08-S021-20260915`; **author/publisher:** ACCA examining team / Association of Chartered Certified Accountants.
- **URL / canonical:** [Examiner’s report: FA2 Maintaining Financial Records, July–December 2016](https://www.accaglobal.com/content/dam/acca/global/PDF-students/fia/examreports/fa2/fa2-examreport-jul-dec2016.pdf).
- **Class / kind:** `course` / professional accounting teaching/exam report; **independence_group:** `acca`.
- **Published:** publication exact date unknown; exam period 2016-07/12; **updated:** unknown; **version/status:** FA2 Jul–Dec 2016; 3-page PDF. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `official_pdf`.
- **Reviewed scope / locator:** Examples 2–3, pp. 2–3; especially Example 3 discussion.
- **Activity / audience / jurisdiction scope:** elementary double-entry and trial balance education.
- **Limitations / interests:** Historical teaching material for a stable accounting mechanism; not current IFRS policy. IAS 2 Example 1 is not used.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S022

**Title:** Payment method support

- **Snapshot:** `P08-S022-20260915`; **author/publisher:** Stripe.
- **URL / canonical:** [Payment method support](https://docs.stripe.com/payments/payment-methods/payment-method-support).
- **Class / kind:** `vendor` / product eligibility documentation; **independence_group:** `stripe`.
- **Published:** unknown; **updated:** unknown; **version/status:** dynamic support matrix; snapshot date only. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Introductory limitations; Country and currency support; Connected accounts notice; Product/API support structure.
- **Activity / audience / jurisdiction scope:** Stripe payment method eligibility by scope.
- **Limitations / interests:** Not all individual method terms were read; the chapter does not declare any specific method available to any specific merchant.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S023

**Title:** Verify payment status

- **Snapshot:** `P08-S023-20260915`; **author/publisher:** Stripe.
- **URL / canonical:** [Verify payment status](https://docs.stripe.com/payments/payment-intents/verifying-status).
- **Class / kind:** `vendor` / integration documentation; **independence_group:** `stripe`.
- **Published:** unknown; **updated:** unknown; **version/status:** PaymentIntents; dynamic docs. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Monitor a PaymentIntent with webhooks; client-side fulfillment warning.
- **Activity / audience / jurisdiction scope:** Stripe PaymentIntent lifecycle and fulfillment trigger.
- **Limitations / interests:** Payment success does not confirm that fulfillment was completed and does not prove a payout.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S024

**Title:** Tolerating full cloud outages with Monzo Stand-in

- **Snapshot:** `P08-S024-20260915`; **author/publisher:** Daniel Chatfield; Andrew Lawson / Monzo.
- **URL / canonical:** [Tolerating full cloud outages with Monzo Stand-in](https://monzo.com/blog/tolerating-full-cloud-outages-with-monzo-stand-in).
- **Class / kind:** `vendor` / operator engineering incident/resilience account; **independence_group:** `monzo`.
- **Published:** 2025-02-13; **updated:** unknown; **version/status:** article dated; described incident August 2024. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Architecture; Syncing state from Stand-in; Correlating data; Enabling Stand-in; You might have seen Monzo Stand-in.
- **Activity / audience / jurisdiction scope:** UK bank operator experience.
- **Limitations / interests:** The operator's self-report; not an independent SLO audit and not a full root-cause postmortem. Costs and marketing estimates were not carried over.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S025

**Title:** Principles for operational resilience

- **Snapshot:** `P08-S025-20260915`; **author/publisher:** Basel Committee on Banking Supervision / Bank for International Settlements.
- **URL / canonical:** [Principles for operational resilience](https://www.bis.org/publications/202103-guidelines-principles-operational-resilience.pdf).
- **Class / kind:** `regulator` / international supervisory principles; **independence_group:** `bcbs`.
- **Published:** 2021-03-31 per publisher page; PDF March 2021; **updated:** unknown; **version/status:** final principles, March 2021. Effective dates: not_applicable; for BCBS, national application is not established.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `official_pdf`.
- **Reviewed scope / locator:** Principles 3–6; printed pp. 5–7, PDF pp. 9–11.
- **Activity / audience / jurisdiction scope:** banks; international principles, national legal implementation not assessed.
- **Limitations / interests:** Not a standalone law for all commerce operators. The principles on testing, dependencies and recovery are used.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S026

**Title:** API6:2023 Unrestricted Access to Sensitive Business Flows

- **Snapshot:** `P08-S026-20260915`; **author/publisher:** OWASP API Security Project / OWASP Foundation.
- **URL / canonical:** [API6:2023 Unrestricted Access to Sensitive Business Flows](https://api-security.owasp.org/editions/2023/en/0xa6-unrestricted-access-to-sensitive-business-flows/).
- **Class / kind:** `standard` / security awareness guidance; **independence_group:** `owasp`.
- **Published:** 2023 edition; exact page publication date unknown; **updated:** unknown; **version/status:** OWASP API Security Top 10 2023. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Is the API Vulnerable?; Example Attack Scenarios; How To Prevent.
- **Activity / audience / jurisdiction scope:** API business-flow abuse; global technical guidance.
- **Limitations / interests:** Not a binding industry law and not evidence of a real attack on a named product.
- **Rights:** OWASP open guidance; the page's exact license was not separately checked, and full reuse is not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S027

**Title:** Do you process Shopify webhooks inline or always queue them?

- **Snapshot:** `P08-S027-20260915`; **author/publisher:** IndicationOne9495 / r/shopifyDev on Reddit.
- **URL / canonical:** [Do you process Shopify webhooks inline or always queue them?](https://www.reddit.com/r/shopifyDev/comments/1vtcxj0/do_you_process_shopify_webhooks_inline_or_always/).
- **Class / kind:** `social` / developer question and public thread; **independence_group:** `reddit_indication`.
- **Published:** unknown; page displays 22h ago; crawl metadata inconsistent; **updated:** unknown; **version/status:** mutable post; no immutable archive. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Main post; context of several top comments; benchmark comments not used.
- **Activity / audience / jurisdiction scope:** public developer anecdote.
- **Limitations / interests:** Self-selection, unobserved configuration, unknown absolute date; frequency, cause and throughput are not proven.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

## P08-S028

**Title:** Resolve webhook signature verification errors

- **Snapshot:** `P08-S028-20260915`; **author/publisher:** Stripe.
- **URL / canonical:** [Resolve webhook signature verification errors](https://docs.stripe.com/webhooks/signature).
- **Class / kind:** `vendor` / security troubleshooting documentation; **independence_group:** `stripe`.
- **Published:** unknown; **updated:** unknown; **version/status:** dynamic docs; selected signing contract. Effective dates: not_applicable.
- **Access:** 2026-09-15, Asia/Makassar, day precision; `partial_text` / `direct_page`.
- **Reviewed scope / locator:** Intro; Check the endpoint secret; Check the request body; Retrieve the raw request body.
- **Activity / audience / jurisdiction scope:** Stripe signed webhook body.
- **Limitations / interests:** The signature verifies the message, not a business right to take an arbitrary action. The instruction to print the secret is not carried over into the chapter.
- **Rights:** See the common terms; rights to full reprinting/illustrations are not assumed. Rights basis: the original at the URL above; no local copy/hash.

