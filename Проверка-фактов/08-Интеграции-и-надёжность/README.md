---
title: "Independent factual audit — Part 08"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Источники и фактчек](../README.md) · [Читать главу](../../Учебник/08-Интеграции-и-надёжность/README.md)

> Публичная редакция от 18.09.2026. Даты проверки и ограничения источников сохранены. Хеши в исторических аудитах относятся к исходной рукописи; публичные изменения и текущие хеши — в [паспорте издания](../../Методика/Паспорт-издания.md).

# Independent factual audit — Part 08

17.09.2026 · Asia/Makassar (UTC+8) · auditor deep_audit_06_07_08_09 · private

## Результат

Прочитаны полные CHAPTER/SOURCES/CLAIMS. Все30 claims и28 source cards получили отдельные строки. Подтверждённых ошибок, требующих изменения главы, не найдено.28claims verified в границах указанных документов,2verified_as_reported (Monzo и Reddit). Это не означает эксплуатационную проверку всех API.

## Что независимо проверено

Woo Store API/customer context отделён от REST administrative keys; classic gateway success/on-hold не назван completed payment. Blocks требует собственной интеграции. Shopify payment extension approval и Plus ограничения проверены по конкретным разделам; delivery ID отличается от business event ID. Adobe command/request/client/validator/handler не сведены к одному HTTP ответу.

Stripe idempotency проверена вместе с исключениями: initial execution/500, pruning≥24h, validation/concurrency, network versus server errors. Рекомендация безопасного повтора использует прежние operation identity/parameters; из timeout не выведен новый платёж. Webhooks могут повторяться и приходить не по порядку; новые signature timestamps при retry не означают новый economic event. Shopify receiving guide прочитан с1s/5s distinction и persistent deduplication/reconciliation.

Adyen settlement report, Stripe payout reconciliation, available_on и currency encoding прочитаны непосредственно. available_on дополнительно раскрыт через official .md: это доступность в Stripe balance, не банковский остаток. Modification Reference не уникален по capture/chargeback type. Автоматические payouts, manual/instant и platform exceptions не смешаны.

RIFL прочитан в пределах архитектуры, предпосылок, durable completion/effects/retry rendezvous и ограничений. Это не универсальная exactly-once гарантия платежа через внешние системы. AWS outbox даёт атомарность локальной записи, не удаляет необходимость idempotent consumer. BCBS Principles3–6 относятся к банкам; merchant checklist — явно редакционная адаптация.

## Чтение главы вне CLAIMS и арифметика

Полный chapter проверен на важные незарегистрированные переходы success→payment, payment→fulfillment, balance→bank и balanced journal→correct accounting. Таких необоснованных переходов не обнаружено; именно ограничения используются в учебных примерах.

В§8.5 независимо пересчитаны payout173,40, дальнейшие refund/fee/reserve/dispute движения и итогPSP−106; банк1067,40 и расходы22,60 дают согласованный итог. Контрпример с пропущенным refund/повторной fee сохраняет формальный баланс, но неверно отражает внешний мир. Синтетические комиссии/резервы/FX не приписаны тарифам Stripe/Adyen.

## Social, metadata и ограничения

Monzo — датированный инженерный self-report Daniel Chatfield/Andrew Lawson о примерно часовом outage августа2024 и Stand-in; фактические production logs не получены. Reddit original body IndicationOne9495 прочитан через web extraction после HTML shell. Относительное время и crawl age не использованы для выдумывания абсолютной даты. Причины, частота и масштаб проблем не считаются установленными.

Динамические API docs прочитаны17.09.2026. Visible current versions не доказывают неизменность15.09. Full metadata check ограничен сведениями, реально видимыми в прочитанном документе; неизвестные publication/effective dates остаются неизвестными. Платежей, provider account tests, conformance execution и репликации RIFL не было. Previous review не использован как evidence.

## Coverage and verdict counts

Claims: 30; source cards: 28. Every ID has one matrix row.

- verified: 28
- verified_as_reported: 2

## Final recheck and hashes

Финальный текст прочитан после provisional freeze редактора. Хеши рассчитаны по фактическому содержимому окончательных файлов. Previous review использован только как указатель риска, не как evidence.

final_verdict: reviewed_with_limitations

open_critical: 0

open_major: 0

| File | SHA-256 |
|---|---|
| [CHAPTER.md](../../Учебник/08-Интеграции-и-надёжность/README.md) | 43b7ec2eccae6a9aab29c11906ce0cf1851f07e4538cabb4c60918d6d43fabd4 |
| [Источники](../../Учебник/08-Интеграции-и-надёжность/Источники.md) | 0df23aedfb6afdea18806844c2ccb79a5343f437d6d0de41583025c0f9987e24 |
| [Утверждения](../../Учебник/08-Интеграции-и-надёжность/Утверждения.md) | c974dd62d210ff4e70ef3ff7220761b493935cde895304777db248ff3ff67149 |
