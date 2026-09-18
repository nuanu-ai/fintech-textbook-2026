---
title: "Independent factual audit — Part 07"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Публичная редакция от 18.09.2026. Даты проверки и ограничения источников сохранены. Хеши в исторических аудитах относятся к исходной рукописи; публичные изменения и текущие хеши — в [паспорте издания](../../edition.md).

# Independent factual audit — Part 07

17.09.2026 · Asia/Makassar (UTC+8) · auditor deep_audit_06_07_08_09 · private

## Результат и findings

Прочитаны полные CHAPTER/SOURCES/CLAIMS, индивидуально оценен51 claim и42 source cards. Новых ошибок платежного механизма не подтверждено. Один minor по правам источника закрыт.

- **F07-01, minor, closed — S042.** В полном pinned GOVERNANCE.md нет copyright/license header. Ранее приписанный этому файлу Apache-2.0 notice не подтверждается. Редактор убрал атрибуцию и указал license coverage unknown. Итоговая карточка перечитана; содержательный C051 о council/domain/founding seats подтверждён.
- **L07-01, metadata limitation — S036.** X показывает24.03.2026 18:18, прежняя карточка25.03 02:18 с неизвестным timezone. Разница8часов совместима с отображением по поясам, не доказывает иной день события. Сам пост и продолжения прочитаны; SDK не тестировались.
- **L07-02, historical version limitation.** AgentDojo v3 самостоятельно прочитан; NeurIPS2024 Datasets and Benchmarks отдельно подтверждён [официальной записью proceedings](https://proceedings.neurips.cc/paper_files/paper/2024/hash/97091a5177d8dc64b1da8bf3e1f6fb54-Abstract-Datasets_and_Benchmarks_Track.html). Архив15.09 для прежнего незакреплённого чтения отсутствует, что сохранено в S033.

## Версии и проверенные механизмы

GitHub API независимо подтвердил commits: x4026b930…15.09.2026 14:04:22Z; MPPa938…09.09.2026 21:20:04Z; ACP7fdd…18.07.2026 04:51:51Z; UCPcd78…25.08.2026 13:47:10Z; AP2e1ea…29.04.2026 16:51:41Z; governanceced53…15.09.2026 07:55:35Z. UCP tagv2026-08-25 разрешается вcd78…. Полные hashes присутствуют в original URLs матрицы. Exact release publication timestamp не подменялся commit timestamp.

В x402 проверены три порядка resource/settlement, readonly verify, EIP3009 branch, optional payment identifier и non-terminal pending. В MPP прочитаны draft status, Stripe/Tempo/Solana branches и атомарная consumed-signature registry. В ACP/UCP checked session/order/complete states и отдельные payment handlers. В AP2v0.2 проверены текущие Checkout/Payment названия, trusted surface, deterministic validation, checkout hash и cumulative budget presentations. Ни одна спецификация не принята за сертификат совместимости работающего продукта.

## Papers, social и важные незарегистрированные выводы

AgentDojo:97tasks/629security cases, utility и attack success в контролируемом benchmark; не payment-loss rate. Formal Analysis: символические Tamarin traces отделены от проверок реализации;86cases не названы86живыми уязвимостями. Beyond the Mandate: testbed/scanner и raters не эквивалентны production field study. Peer review двух2026preprints не установлен.

Полная глава проверена на незарегистрированные переносы identity→authority, verify→settlement, settlement→delivery, protocol→liability. Такие переходы не утверждаются. Синтетический бюджет6+6>10 и правила reconciliation сформулированы как авторские нормативные конструкции, поэтому C002/C028/C035/C037/C048 имеют non_factual, а не механический verified. Посты X/Reddit подтверждают только публикацию слов авторов.

## Ограничения

Не выполнены live payments, SDK conformance tests, reproduction security papers и отдельное юридическое заключение о liability. Динамические vendor docs наблюдались17.09; historical sameness15.09 не доказана. HTTP200 shell Reddit не считался чтением: оригинальный body получен отдельным web extraction. Рекламные обещания Visa/Mastercard не стали договорными гарантиями.

## Coverage and verdict counts

Claims: 51; source cards: 42. Every ID has one matrix row.

- verified: 38
- non_factual: 5
- verified_as_reported: 8

## Final recheck and hashes

Все перечисленные исправления перечитаны после provisional freeze редактора. Хеши ниже рассчитаны по фактическому содержимому окончательных файлов. Предыдущая рецензия использовалась только как указатель риска, не как evidence.

final_verdict: reviewed_with_limitations

open_critical: 0

open_major: 0

| File | SHA-256 |
|---|---|
| [CHAPTER.md](../../chapters/part-07/chapter.md) | 255aeb73f4b56c114bce54fe29219a3f801e70ed25feeaa298ae8a87e010faf8 |
| [SOURCES.md](../../chapters/part-07/sources.md) | e83e77f5d2da6b4c0465ac9e84e6ad756c0bd6d77227041777df6922ea708f57 |
| [CLAIMS.md](../../chapters/part-07/claims.md) | d997c5631a66b4f2c09650169d92be38ac4dee4ffbf70198b123ad14e1669ea1 |
