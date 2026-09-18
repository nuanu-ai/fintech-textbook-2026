---
title: "Источники части 7"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Публичная редакция от 18.09.2026. Даты проверки и ограничения источников сохранены. Хеши в исторических аудитах относятся к исходной рукописи; публичные изменения и текущие хеши — в [паспорте издания](../../edition.md).

# Источники части 7

**v0.1 · 15.09.2026 · private · independently_reviewed_draft; independent_review=see_REVIEW.md.**

Фактчек исходной редакции завершен17.09.2026. Связь исходной версии с публичной копией, область адаптации и текущая навигация описаны в паспорте издания.

## Общие поля карточек

Каждая карточка ниже наследует: `accessed_at=2026-09-15, Asia/Makassar (UTC+08:00)`, `accessed_precision=day`, `language=en`, `as_of=2026-09-15`, `effective_from/effective_to=not_applicable` (это не каталог действующих законов), `supersedes=none`, `doi=unknown`, `reviewer=part_07_research`, `review_status=author_checked; independent_scope=see_REVIEW.md`. Неуказанные точные даты обновления — `unknown`, не дата выдачи поиском. Прочитанные объемы указаны явно: `partial_text` означает ограниченный scope, даже когда весь документ технически доступен.

Для GitHub URLs использовано прямое HTTPS-чтение raw blob по указанному SHA; дополнительно публичный API для HEAD/tag/release. `access_method=direct_raw_https+github_api`, `access_status=partial_text` кроме явно полностью прочитанных файлов. SHA — идентификатор исходного репозитория, не hash локально сохраненного документа. Для прочих источников метод — `direct_page via web extraction`, кроме явно названных Chrome UI и SPT Markdown HTTPS. `local_path=none_in_dataset`, `sha256=not_recorded`: временное чтение в /tmp не обещается как архив. Снимок ID фиксирует дату обращения и версию, а не сохраненную полную копию.

`canonical_url` совпадает с URL карточки; source independence group — издатель/проект. Несколько документов одной компании не являются независимыми подтверждениями ее эффективности. Интерес вендора в продвижении продукта предполагается для vendor/scheme announcements и указан отдельно, где влияет на вывод. Для стандартов это интерес авторов в принятии конструкции. Для research независимая репликация не выполнялась; финансирование не проверялось. Для social существует самоотбор.

Права на хранение/цитирование/распространение разделяются: здесь собственный учебный синтез и ссылки; полные чужие тексты, скриншоты и иллюстрации в поставку не включены. Указание Apache относится к прочитанному LICENSE соответствующего repo; права на товарные знаки не выводятся из лицензии. Иные права на распространение — unknown, если прямо не указано.

<a id="p07-s001"></a>

## P07-S001 — HTTP Semantics

- **snapshot_id:** `P07-S001-20260915`; **author/publisher:** Roy Fielding, Mark Nottingham, Julian Reschke / IETF, RFC Editor; **source_class/document_kind:** standard / Internet Standard.
- **URL:** [Оригинал](https://www.rfc-editor.org/rfc/rfc9110.html#name-402-payment-required).
- **publication/update/version/status:** RFC 9110 / STD 97; 2022-06; accepted Internet Standard.
- **reviewed_scope / locator / access:** §15.5.3 целиком; соседние HTTP status definitions для контекста. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** HTTP; global technical scope. **limitations/interests:** Не определяет конкретный платежный протокол; дата month.
- **rights/basis:** IETF Trust BCP78; ссылка и короткий оригинальный синтез; полное воспроизведение не выполнялось.

<a id="p07-s002"></a>

## P07-S002 — X402 Protocol Specification v2

- **snapshot_id:** `P07-S002-20260915`; **author/publisher:** x402 Foundation contributors / x402-foundation; **source_class/document_kind:** standard / open protocol specification.
- **URL:** [Оригинал](https://github.com/x402-foundation/x402/blob/6b9302737f16eea7de90b3bf617c045cef23e032/specs/x402-specification-v2.md).
- **publication/update/version/status:** v2; repo 6b9302737f16eea7de90b3bf617c045cef23e032; HEAD 2026-09-15T14:04:22Z.
- **reviewed_scope / locator / access:** §§1–6.1, §7 verify/settle/supported, §9 errors, §10 security, §11 implementation; схемы и основные поля. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** x402 v2; зависит от scheme/network/facilitator. **limitations/interests:** HEAD не SDK release и не deployment; слово standard принадлежит проекту, не признание IETF.
- **rights/basis:** Apache-2.0; https://github.com/x402-foundation/x402/blob/6b9302737f16eea7de90b3bf617c045cef23e032/LICENSE.

<a id="p07-s003"></a>

## P07-S003 — Transport: HTTP

- **snapshot_id:** `P07-S003-20260915`; **author/publisher:** x402 Foundation contributors / x402-foundation; **source_class/document_kind:** standard / transport specification.
- **URL:** [Оригинал](https://github.com/x402-foundation/x402/blob/6b9302737f16eea7de90b3bf617c045cef23e032/specs/transports-v2/http.md).
- **publication/update/version/status:** v2; тот же pin, 2026-09-15.
- **reviewed_scope / locator / access:** Весь документ; Payment Required Signaling, Payment Payload Transmission, Settlement Response Delivery, Header Summary, Response Body. access_status=full_text (документ или основная короткая страница).
- **jurisdiction/activity/product:** HTTP transport v2. **limitations/interests:** Не описывает весь lifecycle товара; base64 не шифрование.
- **rights/basis:** Apache-2.0; https://github.com/x402-foundation/x402/blob/6b9302737f16eea7de90b3bf617c045cef23e032/LICENSE.

<a id="p07-s004"></a>

## P07-S004 — Scheme exact on EVM

- **snapshot_id:** `P07-S004-20260915`; **author/publisher:** x402 Foundation contributors / x402-foundation; **source_class/document_kind:** standard / scheme binding.
- **URL:** [Оригинал](https://github.com/x402-foundation/x402/blob/6b9302737f16eea7de90b3bf617c045cef23e032/specs/schemes/exact/scheme_exact_evm.md).
- **publication/update/version/status:** pin 6b9302737f16eea7de90b3bf617c045cef23e032; 2026-09-15.
- **reviewed_scope / locator / access:** Summary; EIP-3009 phases 1–3 полностью; Permit2 setup и payload; сравнительная таблица ERC-7710; settlement_pending. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** EVM exact; asset capabilities differ. **limitations/interests:** Permit2/ERC-7710 не проверены тестом; не обобщать EIP-3009 на все схемы.
- **rights/basis:** Apache-2.0; https://github.com/x402-foundation/x402/blob/6b9302737f16eea7de90b3bf617c045cef23e032/LICENSE.

<a id="p07-s005"></a>

## P07-S005 — Extension: payment-identifier

- **snapshot_id:** `P07-S005-20260915`; **author/publisher:** x402 Foundation contributors / x402-foundation; **source_class/document_kind:** standard / optional extension.
- **URL:** [Оригинал](https://github.com/x402-foundation/x402/blob/6b9302737f16eea7de90b3bf617c045cef23e032/specs/extensions/payment_identifier.md).
- **publication/update/version/status:** pin 6b9302737f16eea7de90b3bf617c045cef23e032; 2026-09-15.
- **reviewed_scope / locator / access:** Полностью; Idempotency Behavior, Request Binding, Responsibilities. access_status=full_text (документ или основная короткая страница).
- **jurisdiction/activity/product:** Advertised extension only. **limitations/interests:** Реализация обязана хранить состояние; само поле ID не гарантирует exactly-once.
- **rights/basis:** Apache-2.0; https://github.com/x402-foundation/x402/blob/6b9302737f16eea7de90b3bf617c045cef23e032/LICENSE.

<a id="p07-s006"></a>

## P07-S006 — The Payment HTTP Authentication Scheme / MPP

- **snapshot_id:** `P07-S006-20260915`; **author/publisher:** Brendan Ryan, Jake Moxey, Tom Meagher (Tempo Labs), Jeff Weinstein, Steve Kaliski (Stripe) / IETF draft; MPP repo Tempo/Stripe; **source_class/document_kind:** standard / Internet-Draft work in progress.
- **URL:** [Оригинал](https://www.ietf.org/ietf-ftp/internet-drafts/draft-httpauth-payment-01.html).
- **publication/update/version/status:** draft-httpauth-payment-01; published 2026-09-09; expires 2027-03-13; intended Standards Track, not RFC; repo a938bfdd443a9683aa0fcbeae487ed4ffadfe4be.
- **reviewed_scope / locator / access:** IETF metadata/Status/Copyright; raw core Introduction, Terminology, Protocol Overview, challenge binding/body digest, security §§Transport, Replay, Idempotency, Concurrency, Amount, Caching; README maintenance. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** MPP core; method-agnostic. **limitations/interests:** Repo README still links earlier draft name; exact current IETF 01 opened. Publication is not adoption; specific method specs may use earlier citations.
- **rights/basis:** IETF Trust BCP78/noModification notice; original limited discussion, no republished spec. Repo source: https://github.com/tempoxyz/mpp-specs/blob/a938bfdd443a9683aa0fcbeae487ed4ffadfe4be/specs/core/draft-httpauth-payment-01.md.

<a id="p07-s007"></a>

## P07-S007 — Stripe Charge Intent for HTTP Payment Authentication

- **snapshot_id:** `P07-S007-20260915`; **author/publisher:** Brendan Ryan (Tempo), Steve Kaliski (Stripe) / tempoxyz/mpp-specs; **source_class/document_kind:** standard / informational method draft.
- **URL:** [Оригинал](https://github.com/tempoxyz/mpp-specs/blob/a938bfdd443a9683aa0fcbeae487ed4ffadfe4be/specs/methods/stripe/draft-stripe-charge-00.md).
- **publication/update/version/status:** draft-stripe-charge-00; version 00; repo a938bfdd443a9683aa0fcbeae487ed4ffadfe4be, HEAD 2026-09-09; document date unknown.
- **reviewed_scope / locator / access:** Introduction, Stripe Charge Flow, Relationship, Terminology; payment request/credential relationship. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** stripe charge + SPT. **limitations/interests:** Draft method is not Stripe account eligibility; no live execution.
- **rights/basis:** Source ipr noModificationTrust200902; limited original synthesis and links; redistribution permission not inferred.

<a id="p07-s008"></a>

## P07-S008 — Tempo Session Intent for HTTP Payment Authentication

- **snapshot_id:** `P07-S008-20260915`; **author/publisher:** Liam Horne, Georgios Konstantopoulos, Dan Robinson, Brendan Ryan, Jake Moxey / Tempo Labs; **source_class/document_kind:** standard / informational method draft.
- **URL:** [Оригинал](https://github.com/tempoxyz/mpp-specs/blob/a938bfdd443a9683aa0fcbeae487ed4ffadfe4be/specs/methods/tempo/draft-tempo-session-00.md).
- **publication/update/version/status:** draft-tempo-session-00; version 00; pinned 2026-09-09 repo; publication day unknown.
- **reviewed_scope / locator / access:** Abstract, Introduction, Use Case: LLM Token Streaming, Session Flow; headings for channel lifecycle; cumulative-voucher mechanism. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** Tempo session; escrow and vouchers. **limitations/interests:** Not full contract audit; illustrative arithmetic is author's, not protocol pricing.
- **rights/basis:** Source ipr noModificationTrust200902; limited synthesis, no redistributed figures.

<a id="p07-s009"></a>

## P07-S009 — Solana Charge Intent for HTTP Payment Authentication

- **snapshot_id:** `P07-S009-20260915`; **author/publisher:** Ludo Galabru, Ilan Gitter / Solana Foundation; publisher tempoxyz/mpp-specs; **source_class/document_kind:** standard / informational method draft.
- **URL:** [Оригинал](https://github.com/tempoxyz/mpp-specs/blob/a938bfdd443a9683aa0fcbeae487ed4ffadfe4be/specs/methods/solana/draft-solana-charge-00.md).
- **publication/update/version/status:** draft-solana-charge-00; version 00; pinned repo 2026-09-09; publication day unknown.
- **reviewed_scope / locator / access:** Verification Procedure outline; Replay Protection fully; Pull Mode Settlement fully; Push Mode heading/description; Confirmation/Finality heading scan only. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** Solana charge pull/push. **limitations/interests:** Confidential transfers not fully reviewed; no SDK test; not proof all SPL/Token2022 variants interoperable.
- **rights/basis:** Source ipr noModificationTrust200902; limited synthesis, no redistributed figures.

<a id="p07-s010"></a>

## P07-S010 — Agentic Commerce Protocol repository README

- **snapshot_id:** `P07-S010-20260915`; **author/publisher:** OpenAI and Stripe, founding maintainers / agentic-commerce-protocol; **source_class/document_kind:** standard / open specification overview.
- **URL:** [Оригинал](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/7fdd78df677a94dce04c770644b0fbbb1401272b/README.md).
- **publication/update/version/status:** beta; latest stable spec 2026-04-17; repo HEAD 7fdd78df677a94dce04c770644b0fbbb1401272b, 2026-07-18.
- **reviewed_scope / locator / access:** Full README; Repo Structure, Versioning, Quick Links, Governance, License; release tree via GitHub API. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** ACP governance and version lineage. **limitations/interests:** README claim production-ready references not accepted as our own readiness conclusion; unreleased excluded.
- **rights/basis:** Apache-2.0; https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/7fdd78df677a94dce04c770644b0fbbb1401272b/LICENSE.

<a id="p07-s011"></a>

## P07-S011 — ACP Agentic Checkout OpenAPI

- **snapshot_id:** `P07-S011-20260915`; **author/publisher:** ACP contributors / OpenAI and Stripe; **source_class/document_kind:** standard / OpenAPI contract.
- **URL:** [Оригинал](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/7fdd78df677a94dce04c770644b0fbbb1401272b/spec/2026-04-17/openapi/openapi.agentic_checkout.yaml).
- **publication/update/version/status:** released API snapshot 2026-04-17; repo 7fdd78df677a94dce04c770644b0fbbb1401272b.
- **reviewed_scope / locator / access:** Checkout operation headers/path structure, status and order schema locations; changelog release headings and architecture website. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** ACP released checkout REST contract. **limitations/interests:** Not every schema/example read; no API invocation; optionality and implementation assessed only for named fields.
- **rights/basis:** Apache-2.0; https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/7fdd78df677a94dce04c770644b0fbbb1401272b/LICENSE.

<a id="p07-s012"></a>

## P07-S012 — ACP Delegate Payment OpenAPI

- **snapshot_id:** `P07-S012-20260915`; **author/publisher:** ACP contributors / OpenAI and Stripe; **source_class/document_kind:** standard / OpenAPI contract.
- **URL:** [Оригинал](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/7fdd78df677a94dce04c770644b0fbbb1401272b/spec/2026-04-17/openapi/openapi.delegate_payment.yaml).
- **publication/update/version/status:** released 2026-04-17; pin 7fdd78df677a94dce04c770644b0fbbb1401272b.
- **reviewed_scope / locator / access:** POST delegated payment description; IdempotencyKey (lines 251–255 in read blob); Allowance (lines 520–559); required list. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** Delegated credentials; merchant PSP. **limitations/interests:** Tokenization contract is not independent proof PSP enforces every allowance in production.
- **rights/basis:** Apache-2.0; https://github.com/agentic-commerce-protocol/agentic-commerce-protocol/blob/7fdd78df677a94dce04c770644b0fbbb1401272b/LICENSE.

<a id="p07-s013"></a>

## P07-S013 — Universal Commerce Protocol Official Specification

- **snapshot_id:** `P07-S013-20260915`; **author/publisher:** UCP Authors / Universal-Commerce-Protocol organization; **source_class/document_kind:** standard / open specification.
- **URL:** [Оригинал](https://github.com/Universal-Commerce-Protocol/ucp/blob/cd78fb38e819de77d9b527d110476eccb876f1bd/docs/specification/overview/index.md).
- **publication/update/version/status:** release v2026-08-25; tag cd78fb38e819de77d9b527d110476eccb876f1bd; published 2026-08-25T13:53:03Z.
- **reviewed_scope / locator / access:** Discovery, Governance, Negotiation headings and named concepts; profile/version definitions; full short docs/versioning and release metadata. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** UCP profiles/capabilities/handlers. **limitations/interests:** Large specification only selected sections; main was separately pinned 8e600b0, but claims use released tag; no product certification.
- **rights/basis:** Apache-2.0; https://github.com/Universal-Commerce-Protocol/ucp/blob/cd78fb38e819de77d9b527d110476eccb876f1bd/LICENSE.

<a id="p07-s014"></a>

## P07-S014 — UCP Checkout Capability

- **snapshot_id:** `P07-S014-20260915`; **author/publisher:** UCP Authors / Universal-Commerce-Protocol; **source_class/document_kind:** standard / capability specification.
- **URL:** [Оригинал](https://github.com/Universal-Commerce-Protocol/ucp/blob/cd78fb38e819de77d9b527d110476eccb876f1bd/docs/specification/shopping/checkout/index.md).
- **publication/update/version/status:** v2026-08-25, cd78fb38e819de77d9b527d110476eccb876f1bd.
- **reviewed_scope / locator / access:** Overview; Checkout Status Lifecycle and Status Values; Continue URL; Complete Checkout headings/contract; state semantics fully read. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** UCP shopping checkout. **limitations/interests:** completed is placement of order in this contract; no inference of delivery/payout.
- **rights/basis:** Apache-2.0; https://github.com/Universal-Commerce-Protocol/ucp/blob/cd78fb38e819de77d9b527d110476eccb876f1bd/LICENSE.

<a id="p07-s015"></a>

## P07-S015 — UCP Payment Handler Specification Guide

- **snapshot_id:** `P07-S015-20260915`; **author/publisher:** UCP Authors / Universal-Commerce-Protocol; **source_class/document_kind:** standard / implementation guide.
- **URL:** [Оригинал](https://github.com/Universal-Commerce-Protocol/ucp/blob/cd78fb38e819de77d9b527d110476eccb876f1bd/docs/specification/payment/guide.md).
- **publication/update/version/status:** v2026-08-25; cd78fb38e819de77d9b527d110476eccb876f1bd.
- **reviewed_scope / locator / access:** Introduction/Purpose/Scope/Core Concepts/Participants; Processing logical flow. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** Payment handlers. **limitations/interests:** Guide vocabulary is logical data flow, not callable API; not payment license.
- **rights/basis:** Apache-2.0; https://github.com/Universal-Commerce-Protocol/ucp/blob/cd78fb38e819de77d9b527d110476eccb876f1bd/LICENSE.

<a id="p07-s016"></a>

## P07-S016 — UCP Payment Authentication Extension

- **snapshot_id:** `P07-S016-20260915`; **author/publisher:** UCP Authors / Universal-Commerce-Protocol; **source_class/document_kind:** standard / extension specification.
- **URL:** [Оригинал](https://github.com/Universal-Commerce-Protocol/ucp/blob/cd78fb38e819de77d9b527d110476eccb876f1bd/docs/specification/payment/extensions/authentication.md).
- **publication/update/version/status:** v2026-08-25; cd78fb38e819de77d9b527d110476eccb876f1bd.
- **reviewed_scope / locator / access:** Overview, Discovery and Negotiation, Runtime Shape initial example. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** Browser interactions for DDC/3DS challenge. **limitations/interests:** Extension does not replace EMV 3DS or provider processing; only selected sections read.
- **rights/basis:** Apache-2.0; https://github.com/Universal-Commerce-Protocol/ucp/blob/cd78fb38e819de77d9b527d110476eccb876f1bd/LICENSE.

<a id="p07-s017"></a>

## P07-S017 — AP2 Agentic Payment Protocol v0.2

- **snapshot_id:** `P07-S017-20260915`; **author/publisher:** Google Agentic Commerce/AP2 contributors / google-agentic-commerce; **source_class/document_kind:** standard / open protocol specification.
- **URL:** [Оригинал](https://github.com/google-agentic-commerce/AP2/blob/e1ea56db72a6385bce3e5c1112b3a56ce60acb43/docs/ap2/specification.md).
- **publication/update/version/status:** v0.2; CHANGELOG 0.2.0 dated 2026-04-28; HEAD e1ea56db72a6385bce3e5c1112b3a56ce60acb43 dated 2026-04-29.
- **reviewed_scope / locator / access:** Roles; Agentic vs Non-Agentic; Mandates; Direct/Autonomous; Agent-to-Agent Delegation; Dispute Evidence; full flows.md read. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** AP2 authorization within commerce. **limitations/interests:** No GA/production claim; a2a delegation and dispute retention/retrieval details out of scope.
- **rights/basis:** Apache-2.0; https://github.com/google-agentic-commerce/AP2/blob/e1ea56db72a6385bce3e5c1112b3a56ce60acb43/LICENSE.

<a id="p07-s018"></a>

## P07-S018 — AP2 Agent Authorization

- **snapshot_id:** `P07-S018-20260915`; **author/publisher:** AP2 contributors / Google Agentic Commerce; **source_class/document_kind:** standard / authorization framework.
- **URL:** [Оригинал](https://github.com/google-agentic-commerce/AP2/blob/e1ea56db72a6385bce3e5c1112b3a56ce60acb43/docs/ap2/agent_authorization.md).
- **publication/update/version/status:** AP2 v0.2 repo pin e1ea56db72a6385bce3e5c1112b3a56ce60acb43.
- **reviewed_scope / locator / access:** Introduction; Mandate Delegation; User Credential/Trusted Agent Provider; User Credential model; initial OpenID4VP description. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** Consent trust models. **limitations/interests:** Not identity proofing/KYC standard; not full credential issuance implementation review.
- **rights/basis:** Apache-2.0; https://github.com/google-agentic-commerce/AP2/blob/e1ea56db72a6385bce3e5c1112b3a56ce60acb43/LICENSE.

<a id="p07-s019"></a>

## P07-S019 — AP2 Checkout Mandate

- **snapshot_id:** `P07-S019-20260915`; **author/publisher:** AP2 contributors / Google Agentic Commerce; **source_class/document_kind:** standard / mandate specification.
- **URL:** [Оригинал](https://github.com/google-agentic-commerce/AP2/blob/e1ea56db72a6385bce3e5c1112b3a56ce60acb43/docs/ap2/checkout_mandate.md).
- **publication/update/version/status:** AP2 v0.2; vct mandate.checkout.1 / mandate.checkout.open.1; repo pin e1ea56d.
- **reviewed_scope / locator / access:** Usage/Type/Mandate Schema; Constraints; Allowed Merchants; Line Items including no splitting note. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** What purchase is authorized. **limitations/interests:** Template macros for expanded schemas not read as expanded JSON; claims use explicit prose, not inferred missing fields.
- **rights/basis:** Apache-2.0; https://github.com/google-agentic-commerce/AP2/blob/e1ea56db72a6385bce3e5c1112b3a56ce60acb43/LICENSE.

<a id="p07-s020"></a>

## P07-S020 — AP2 Payment Mandate

- **snapshot_id:** `P07-S020-20260915`; **author/publisher:** AP2 contributors / Google Agentic Commerce; **source_class/document_kind:** standard / mandate specification.
- **URL:** [Оригинал](https://github.com/google-agentic-commerce/AP2/blob/e1ea56db72a6385bce3e5c1112b3a56ce60acb43/docs/ap2/payment_mandate.md).
- **publication/update/version/status:** AP2 v0.2; vct mandate.payment.1 / mandate.payment.open.1; repo pin e1ea56d.
- **reviewed_scope / locator / access:** Usage/Type; Payment Mandate Constraints; Agent Recurrence; Allowed Payees; Allowed Instruments. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** Payment constraint classes and state tracking. **limitations/interests:** Expanded schema macros not independently expanded; no conformance test.
- **rights/basis:** Apache-2.0; https://github.com/google-agentic-commerce/AP2/blob/e1ea56db72a6385bce3e5c1112b3a56ce60acb43/LICENSE.

<a id="p07-s021"></a>

## P07-S021 — AP2 Security and Privacy Considerations

- **snapshot_id:** `P07-S021-20260915`; **author/publisher:** AP2 contributors / Google Agentic Commerce; **source_class/document_kind:** standard / threat model.
- **URL:** [Оригинал](https://github.com/google-agentic-commerce/AP2/blob/e1ea56db72a6385bce3e5c1112b3a56ce60acb43/docs/ap2/security_and_privacy_considerations.md).
- **publication/update/version/status:** AP2 v0.2; pin e1ea56db72a6385bce3e5c1112b3a56ce60acb43.
- **reviewed_scope / locator / access:** Whole document; manipulated checkout/payment, credential theft, discovery, double spend, privacy. access_status=full_text (документ или основная короткая страница).
- **jurisdiction/activity/product:** AP2 declared threat model. **limitations/interests:** Normative wording does not prove implementation compliance; double-spend guidance contains deployment assumptions.
- **rights/basis:** Apache-2.0; https://github.com/google-agentic-commerce/AP2/blob/e1ea56db72a6385bce3e5c1112b3a56ce60acb43/LICENSE.

<a id="p07-s022"></a>

## P07-S022 — Shared payment tokens — Sellers and Agents variants

- **snapshot_id:** `P07-S022-20260915`; **author/publisher:** Stripe / Stripe Documentation; **source_class/document_kind:** vendor / product documentation.
- **URL:** [Оригинал](https://docs.stripe.com/agentic-commerce/concepts/shared-payment-tokens.md?agent-seller=seller).
- **publication/update/version/status:** Live document 2026-09-15; publication/update unknown; examples Stripe-Version 2026-04-22.preview.
- **reviewed_scope / locator / access:** Seller variant fully; agent variant intro/onboarding and payment collection; geographic country list; usage limits; PaymentIntent; deactivation events. Agent URL: https://docs.stripe.com/agentic-commerce/concepts/shared-payment-tokens.md?agent-seller=agent. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** US, CA and listed European countries; SPT participants. **limitations/interests:** Live docs may drift; no access check for any account; geography claims limited to displayed list.
- **rights/basis:** Stripe copyright; links and short synthesis only; copies not redistributed.

<a id="p07-s023"></a>

## P07-S023 — Machine payments

- **snapshot_id:** `P07-S023-20260915`; **author/publisher:** Stripe / Stripe Documentation; **source_class/document_kind:** vendor / product documentation.
- **URL:** [Оригинал](https://docs.stripe.com/payments/machine).
- **publication/update/version/status:** Live read 2026-09-15; publication/update unknown; no inferred GA label.
- **reviewed_scope / locator / access:** Full 66-line page; Features, Availability, networks/currencies, approval process, directory listing. access_status=full_text (документ или основная короткая страница).
- **jurisdiction/activity/product:** Stripe machine payments; US exclusions and request-based other geography. **limitations/interests:** Provider-specific minimums and rails; not all MPP/x402 implementations; no live payment.
- **rights/basis:** Stripe copyright; limited synthesis only.

<a id="p07-s024"></a>

## P07-S024 — Agentic commerce

- **snapshot_id:** `P07-S024-20260915`; **author/publisher:** Stripe / Stripe Documentation; **source_class/document_kind:** vendor / product documentation.
- **URL:** [Оригинал](https://docs.stripe.com/agentic-commerce).
- **publication/update/version/status:** Live read 2026-09-15; Agents section Private preview.
- **reviewed_scope / locator / access:** Full 58-line page; seller/agent integration table and private preview label. access_status=full_text (документ или основная короткая страница).
- **jurisdiction/activity/product:** Stripe agent integrations. **limitations/interests:** Preview label scoped to agents; not automatically every seller feature.
- **rights/basis:** Stripe copyright; limited synthesis only.

<a id="p07-s025"></a>

## P07-S025 — Get Started — Agentic Commerce

- **snapshot_id:** `P07-S025-20260915`; **author/publisher:** OpenAI / OpenAI Developers; **source_class/document_kind:** vendor / product onboarding documentation.
- **URL:** [Оригинал](https://developers.openai.com/commerce/guides/get-started).
- **publication/update/version/status:** Live read 2026-09-15; publication/update unknown.
- **reviewed_scope / locator / access:** Actual content lines 821–852; approved-partner notice, Overview, Integration path. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** ChatGPT product-feed onboarding. **limitations/interests:** Feed/indexing is not checkout acceptance or distribution guarantee; no account eligibility verification.
- **rights/basis:** OpenAI copyright; short synthesis and link only.

<a id="p07-s026"></a>

## P07-S026 — Visa Intelligent Commerce Overview

- **snapshot_id:** `P07-S026-20260915`; **author/publisher:** Visa / Visa Developer; **source_class/document_kind:** scheme / product documentation.
- **URL:** [Оригинал](https://developer.visa.com/capabilities/visa-intelligent-commerce/overview).
- **publication/update/version/status:** Live read 2026-09-15; development/deployment disclaimer; publication/update unknown.
- **reviewed_scope / locator / access:** Full short page; tokenization, authentication, instructions, signals, How It Works, sandbox/production. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** Listed Visa regions; actual market availability qualified. **limitations/interests:** Potential features; may not all markets; no production onboarding or fee agreement inspected.
- **rights/basis:** Visa copyright and applicable product terms; no specification redistribution.

<a id="p07-s027"></a>

## P07-S027 — Trusted Agent Protocol — Merchant Specifications

- **snapshot_id:** `P07-S027-20260915`; **author/publisher:** Visa / Visa Developer; **source_class/document_kind:** scheme / protocol specification.
- **URL:** [Оригинал](https://developer.visa.com/capabilities/trusted-agent-protocol/trusted-agent-protocol-specifications).
- **publication/update/version/status:** Live page; explicit numbered version not established; Product Terms linked.
- **reviewed_scope / locator / access:** Introduction/Audience/Participants; Trust Model; Agent Recognition Signature and replay discussion. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** Merchant/site protection and approved agent providers. **limitations/interests:** Not legal advice about accepting Product Terms; public read only; no whole-spec copy in dataset; full validation examples not audited.
- **rights/basis:** Visa Product Terms linked in source; limited synthesis; reproduction rights not inferred.

<a id="p07-s028"></a>

## P07-S028 — Visa Opens the Door to AI-Driven Shopping for Businesses Worldwide

- **snapshot_id:** `P07-S028-20260915`; **author/publisher:** Visa / Visa UK Newsroom; **source_class/document_kind:** scheme / announcement.
- **URL:** [Оригинал](https://www.visa.co.uk/about-visa/newsroom/press-releases.3442048.html).
- **publication/update/version/status:** Published 2026-04-09; pilot at announcement.
- **reviewed_scope / locator / access:** Full short release; pilot bullet, product scope, named partner context. access_status=full_text (документ или основная короткая страница).
- **jurisdiction/activity/product:** Intelligent Commerce Connect; select pilot partners. **limitations/interests:** Historical announcement does not establish September GA; vendor promotional interest.
- **rights/basis:** Visa copyright; limited synthesis only.

<a id="p07-s029"></a>

## P07-S029 — Scaling agentic commerce with trust

- **snapshot_id:** `P07-S029-20260915`; **author/publisher:** Pablo Fourez, Chief Digital Officer / Mastercard; **source_class/document_kind:** scheme / explanatory announcement.
- **URL:** [Оригинал](https://www.mastercard.com/us/en/news-and-trends/stories/2025/agentic-commerce-framework.html).
- **publication/update/version/status:** Published 2025-10-14.
- **reviewed_scope / locator / access:** Main article from title through framework registration/tokenization and merchant interaction sections. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** Mastercard Agent Pay Acceptance Framework. **limitations/interests:** No closed rulebook or product eligibility terms read; promotional interest; not performance evidence.
- **rights/basis:** Mastercard copyright; limited synthesis only.

<a id="p07-s030"></a>

## P07-S030 — Mastercard launches Agent Pay for Machines

- **snapshot_id:** `P07-S030-20260915`; **author/publisher:** Mastercard / Mastercard Newsroom; **source_class/document_kind:** scheme / announcement.
- **URL:** [Оригинал](https://www.mastercard.com/us/en/news-and-trends/press/2026/june/mastercard-launches-agent-pay-for-machines.html).
- **publication/update/version/status:** Published 2026-06-10.
- **reviewed_scope / locator / access:** Main release through How It Works/Partnering; quote sheet not used as independent evidence. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** AP4M; proposed network participants and supported rails. **limitations/interests:** Guaranteed settlement is publisher claim, terms not reviewed; partner validation not universal GA.
- **rights/basis:** Mastercard copyright; limited synthesis only.

<a id="p07-s031"></a>

## P07-S031 — OAuth 2.0 Token Exchange

- **snapshot_id:** `P07-S031-20260915`; **author/publisher:** Michael B. Jones et al. / IETF, RFC Editor; **source_class/document_kind:** standard / Standards Track RFC.
- **URL:** [Оригинал](https://www.rfc-editor.org/rfc/rfc8693.html).
- **publication/update/version/status:** RFC 8693; 2020-01.
- **reviewed_scope / locator / access:** §1 scope; §1.1 Delegation vs Impersonation; §4.1 act; Appendix A.2 context. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** OAuth token exchange. **limitations/interests:** Not complete authorization policy, regulated identity proofing or legal delegation.
- **rights/basis:** IETF Trust BCP78; limited synthesis.


<a id="p07-s032"></a>

## P07-S032 — OAuth 2.0 Demonstrating Proof of Possession (DPoP)

- **snapshot_id:** `P07-S032-20260915`; **author/publisher:** Daniel Fett et al. / IETF, RFC Editor; **source_class/document_kind:** standard / Standards Track RFC.
- **URL:** [Оригинал](https://www.rfc-editor.org/rfc/rfc9449.html).
- **publication/update/version/status:** RFC 9449; 2023-09.
- **reviewed_scope / locator / access:** §4 proof meaning and limitation; §4.1 header; §7.1 validation context. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** OAuth DPoP. **limitations/interests:** Does not authenticate/authorize alone; does not prove intent; not payment-specific.
- **rights/basis:** IETF Trust BCP78; limited synthesis.

<a id="p07-s033"></a>

## P07-S033 — AgentDojo: A Dynamic Environment to Evaluate Prompt Injection Attacks and Defenses for LLM Agents

- **snapshot_id:** `P07-S033-20260915` (исходное чтение без закрепленной ревизии); `P07-S033-20260917` (повторная проверка v3); **author/publisher:** Edoardo Debenedetti, Jie Zhang, Mislav Balunović, Luca Beurer-Kellner, Marc Fischer, Florian Tramèr / NeurIPS 2024; authors arXiv; **source_class/document_kind:** research / peer-reviewed Datasets and Benchmarks paper.
- **URL:** [Оригинал](https://arxiv.org/html/2406.13352v3).
- **publication/update/version/status:** arXiv first 2024-06-19; NeurIPS2024 confirmed by proceedings record; повторно открытая 17.09.2026 HTML-версия: arXiv:2406.13352v3, 24.11.2024. Исходный незакрепленный снимок чтения 15.09 не сохранен; его полное тождество v3 не утверждается.
- **reviewed_scope / locator / access:** Main §§1–5: environment design, metrics §3.4, evaluation §4.1–4.3, limitations; selected Appendix benchmark context. Proceedings metadata separately read: https://proceedings.neurips.cc/paper_files/paper/2024/hash/97091a5177d8dc64b1da8bf3e1f6fb54-Abstract-Datasets_and_Benchmarks_Track.html. access_status=partial_text; только указанный объем. Независимый рецензент повторно проверил методы и ограничения v3 17.09; редактор отдельно сверил заголовок и дату v3.
- **jurisdiction/activity/product:** 2024 tested tool agents and synthetic environments. **limitations/interests:** No reproduction; no inference about 2026 live payment loss rate; URL теперь фиксирует v3; исторический снимок чтения 15.09 отсутствует.
- **rights/basis:** Authors retain rights per publication license; no PDF/figures copied, limited synthesis.

<a id="p07-s034"></a>

## P07-S034 — A Formal Analysis of Agent Payment Protocols

- **snapshot_id:** `P07-S034-20260915`; **author/publisher:** Ke Jiang, Mohan Yu, Yuan Chang, Mohit Kumar Jangid, Jianyu Niu, Cong Wang, Yinqian Zhang / arXiv; **source_class/document_kind:** research / preprint.
- **URL:** [Оригинал](https://arxiv.org/html/2609.00060v1).
- **publication/update/version/status:** v1; submitted 2026-08-30 (despite 2609 identifier); peer review not established.
- **reviewed_scope / locator / access:** §III framework/threat model, §IV Tamarin modeling and Cardano trace, §V/VI evidence levels and cases, §VII scope/limitations; abs metadata independently fetched. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** Modeled x402/MPP/AP2/ACP semantics. **limitations/interests:** No Tamarin run; code/contract/symbolic witnesses have different weight; no claim all current implementations vulnerable; corpus commits not reconstructed.
- **rights/basis:** arXiv/author rights; limited synthesis, no reproduced figures.

<a id="p07-s035"></a>

## P07-S035 — Beyond the Mandate: A Systematic Security Analysis of AP2

- **snapshot_id:** `P07-S035-20260915`; **author/publisher:** Avital Aviv, Parth A. Gandh, Ron Bitton, Asaf Shabtai / arXiv; **source_class/document_kind:** research / preprint.
- **URL:** [Оригинал](https://arxiv.org/html/2608.23858v1).
- **publication/update/version/status:** v1; submitted 2026-08-24; peer review not established.
- **reviewed_scope / locator / access:** §3 roles/lifecycle/architectures, §4 threat model/scoring, §5 taxonomy, §6 demonstration overview, §7 scanner/CDSE, §8 ablations, §9 discussion/limitations. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** AP2 v0.2 author-controlled testbed. **limitations/interests:** No live deployment inspected by authors; same testbed for scanner evaluation; no reproduction; PoC details in figures not fully inspected.
- **rights/basis:** arXiv/author rights; limited synthesis, no copied figures.

<a id="p07-s036"></a>

## P07-S036 — Solana now supports the Machine Payments Protocol

- **snapshot_id:** `P07-S036-20260915`; **author/publisher:** Solana @solana / X; **source_class/document_kind:** social / official ecosystem announcement.
- **URL:** [Оригинал](https://x.com/solana/status/2036507994381492326).
- **publication/update/version/status:** UI displayed 2026-03-25 02:18 AM; UI timezone unknown.
- **reviewed_scope / locator / access:** Main post and two visible same-author continuations, read independently by part_07_research via Chrome UI. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** Solana MPP announcement. **limitations/interests:** SDK not run; token compatibility not verified; images/full thread unread; account is ecosystem interested party.
- **rights/basis:** Copyright author; short attributed synthesis and link only; no screenshot republished.

<a id="p07-s037"></a>

## P07-S037 — x402 turns any API endpoint into a paid service

- **snapshot_id:** `P07-S037-20260915`; **author/publisher:** deX402 @deX402_official / X; **source_class/document_kind:** social / product promotional statement.
- **URL:** [Оригинал](https://x.com/deX402_official/status/2043175089198293291).
- **publication/update/version/status:** UI displayed 2026-04-12 11:51 AM; UI timezone unknown.
- **reviewed_scope / locator / access:** Main public post read independently by part_07_research via Chrome UI. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** Claim about eliminating payment processors in author's use case. **limitations/interests:** Product identity/implementation not independently verified; not protocol publisher; no performance or sale evidence.
- **rights/basis:** Copyright author; limited attributed synthesis and link only.

<a id="p07-s038"></a>

## P07-S038 — Shipped against Stripe's Shared Payment Tokens preview

- **snapshot_id:** `P07-S038-20260915`; **author/publisher:** IndianDownUnder / Reddit r/fintech; **source_class/document_kind:** social / self-reported implementation experience.
- **URL:** [Оригинал](https://www.reddit.com/r/fintech/comments/1vtl49r/shipped_against_stripes_shared_payment_tokens/).
- **publication/update/version/status:** Exact publication date unknown; extracted UI says 2d ago; conflicting indexed age not resolved.
- **reviewed_scope / locator / access:** Main post points 1–4 and sandbox-key note via web extraction; title/author read. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** Author test-mode SPT integration. **limitations/interests:** No reproduction; code linked by author not run. AU availability claim not accepted as current fact; official SPT country list prevails for this chapter.
- **rights/basis:** Reddit original author; attributed short synthesis only; no full repost.

<a id="p07-s039"></a>

## P07-S039 — Updated Guidance for a Risk-Based Approach to Virtual Assets and VASPs — publication page

- **snapshot_id:** `P07-S039-20260915`; **author/publisher:** FATF / FATF; **source_class/document_kind:** regulator / intergovernmental guidance overview.
- **URL:** [Оригинал](https://www.fatf-gafi.org/en/publications/Fatfrecommendations/Guidance-rba-virtual-assets-2021.html).
- **publication/update/version/status:** Published 2021-10-28; live warning about later amendments incl. 2025 Recommendation1 revisions.
- **reviewed_scope / locator / access:** Publication page description and six scope topics; explicit outdated-guidance caveat; full PDF not read in this part. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** FATF international guidance, national implementation required. **limitations/interests:** Only scope/context claim, no precise legal obligation established from unread PDF; must read current standards/local law for deployment.
- **rights/basis:** FATF rights; limited summary and link, no PDF copied.

<a id="p07-s040"></a>

## P07-S040 — The PaymentIntent object

- **snapshot_id:** `P07-S040-20260915`; **author/publisher:** Stripe / Stripe API Reference; **source_class/document_kind:** vendor / API contract.
- **URL:** [Оригинал](https://docs.stripe.com/api/payment_intents/object).
- **publication/update/version/status:** Live read 2026-09-15; exact rendered API version not established.
- **reviewed_scope / locator / access:** status enum and its definitions (lines 634–655); object context. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** Stripe PaymentIntents. **limitations/interests:** HTTP status and application status differ; no live test; not a statement that every succeeded means irrevocable bank finality.
- **rights/basis:** Stripe copyright; limited synthesis.

<a id="p07-s041"></a>

## P07-S041 — Remote ATtestation procedureS (RATS) Architecture

- **snapshot_id:** `P07-S041-20260915`; **author/publisher:** Henk Birkholz et al. / IETF, RFC Editor; **source_class/document_kind:** standard / Informational RFC.
- **URL:** [Оригинал](https://www.rfc-editor.org/rfc/rfc9334.html).
- **publication/update/version/status:** RFC 9334; 2023-01; Informational.
- **reviewed_scope / locator / access:** §4.1 Roles; §5.2 background-check flow; §7 trust context; §8.5 appraisal policies. access_status=partial_text; только указанный объем.
- **jurisdiction/activity/product:** Remote attestation architecture. **limitations/interests:** Not a payment authorization or legal identity standard; full implementation/security appendix not audited.
- **rights/basis:** IETF Trust BCP78; limited synthesis.

<a id="p07-s042"></a>

## P07-S042 — UCP Governance

- **snapshot_id:** `P07-S042-20260915`; **author/publisher:** UCP Authors / Universal-Commerce-Protocol; **source_class/document_kind:** standard / project governance policy for open specification.
- **URL:** [Оригинал](https://github.com/Universal-Commerce-Protocol/.github/blob/ced53b98c2064d472b41a5aff1c20b8261e6dd91/GOVERNANCE.md).
- **publication/update/version/status:** public governance policy; repo HEAD `ced53b98c2064d472b41a5aff1c20b8261e6dd91`, commit 2026-09-15T07:55:35Z; effective date of policy unknown. Separate repo from released UCP spec.
- **reviewed_scope / locator / access:** full file: Contributors; Maintainers; Domain Working Groups; Domain Tech Councils; Governing Council; Communication. access_status=full_text; direct raw HTTPS plus GitHub API commit. Read 15.09.2026 at 23:49 Asia/Makassar. MAINTAINERS.md at same SHA also read as context; chapter does not derive deployment/product availability from membership.
- **jurisdiction/activity/product:** governance of UCP project assets and domains. **limitations/interests:** Project's own allocation of governance authority; does not establish regulator status, legal enforceability, implementation conformance, or independent certification. Membership may change.
- **rights/basis:** License coverage of this GOVERNANCE.md has not been independently established. The pinned file contains no copyright/license header; the earlier attribution to Apache-2.0 was unsupported and corrected17.09.2026 after independent full-file reading. Limited original synthesis; full file not redistributed.
