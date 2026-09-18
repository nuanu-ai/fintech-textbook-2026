---
title: "Итог независимого фактчека — часть 04"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Публичная редакция от 18.09.2026. Даты проверки и ограничения источников сохранены. Хеши в исторических аудитах относятся к исходной рукописи; публичные изменения и текущие хеши — в [паспорте издания](../../edition.md).

# Итог независимого фактчека — часть 04

17.09.2026 · Asia/Makassar (UTC+08) · auditor: `deep_audit_02_03_04` · private. Срез знаний: 15.09.2026; новые обращения — 17.09.2026. Точные исторические байты rolling documentation не восстановлены.

## Результат и охват

Полностью прочитаны CHAPTER.md, CLAIMS.md и SOURCES.md. Все 44 claim ID и 24 source ID имеют отдельные строки: [CLAIM_AUDIT.md](claim-audit.md), [SOURCE_AUDIT.md](source-audit.md). Все оригинальные URL самостоятельно запрошены. Содержательные нужные фрагменты получены у всех 24 источников; при 403/оболочке использован web original, а для Stripe дополнительно его официальный Markdown, что отдельно отражено в матрице. Это не означает полного чтения каждого большого rulebook.

**Новых исправляемых findings: 0 critical, 0 major, 0 minor.** Оставшиеся вопросы ниже — ограничения доказательства, явно сохранённые в главе. Два contradicted относятся к отвергнутым автором утверждениям о лицензии/паспорте; шесть non_factual — к моделям и предложениям, не к доказанным рыночным фактам. Финальные три файла root отличаются от baseline только актуальными ссылками на аудит/обозначением первой рецензии; эти изменения сверены.

| Verdict | Claims |
|---|---:|
| verified | 33 |
| verified_as_reported | 2 |
| partial | 0 |
| contradicted | 2 |
| unverifiable | 1 |
| non_factual | 6 |
| **Всего** | **44** |

## Проверенные области повышенного риска

- **PayFac и MoR liability:** непосредственно прочитаны Mastercard §7.6.5–7.6.5.1, pp.172–174, Stripe MoR charge types и on_behalf_of, Paddle MSA §2.1 и §§8,10.4. Делегирование не снимает ответственность acquirer; роль reseller не исключает supplier recourse за refunds/chargebacks. У Paddle проверены дата 8 October 2025 и разная применимость к новым/существующим suppliers; индивидуальный order form отсутствует.
- **Payout и reconciliation:** Stripe payout schedule не сокращает pending availability; paid может позже перейти в failed. В Adyen settlement report commission и component columns 11–14 не складываются дважды. Прочитан смысл отдельных fee/reserve/merchant payout entries; отчёт провайдера не доказательство зачисления банком.
- **Split payments:** полный нужный текст официального Markdown Separate charges and transfers подтвердил раздельные объекты и отсутствие автоматического reverse transfer при refund. Предположение о доступных 10 при обязательстве refund 80 не замаскировано формальным successful charge.
- **Pricing и eligibility:** Stripe Connect 2 USD за active account плюс 0.25% + 0.25 USD per payout проверены в US offer, отдельно от payment processing. Stablecoin page и её Markdown прочитаны по токенам, сетям, local-currency settlement и возврату в исходный wallet. US merchant eligibility отделена от private preview EU/HK/MX/CH и более широкого country-code list.
- **Лицензия и sponsorship:** FCA marketplace guidance, VisaNet Connect Issuing eligibility/risk review/production steps, US interagency guidance 6 June 2023 и CBI passporting проверены напрямую. Sandbox/API/слово BIN не являются разрешением работать в любой стране. Общая third-party guidance не превращена в самостоятельную BaaS licence.

## Papers: версии, метод и предпосылки

- [FEDS 2009-23](https://www.federalreserve.gov/pubs/feds/2009/200923/): Prager, Manuszak, Kiser и Borzekowski, 13 May 2009; прочитаны executive summary и основные теоретические различия. Это обзор литературы, не причинная оценка тарифа 2026 года; вывод об эффективном interchange зависит от предпосылок.
- [Rochet–Tirole](https://tse-fr.eu/sites/default/files/medias/doc/wp/2002/platform.pdf): авторский draft 13 December 2002, §2/§2.1, pp.8–10. Проверены linear usage prices, отсутствие фиксированных расходов участия в указанной модели, экзогенные выгоды и joint-volume формула прибыли. Не приписана текущая эмпирическая точность или равенство этой версии журнальной.
- [Aurazo, BIS WP1163](https://www.bis.org/publications/working-paper-1163-interchange-fees-access-pricing-and-sub-acquirers-payment-markets.pdf): January 2024, sole author; прочитаны модель §3 и niche case §6, physical PDF pp.18–20. Проверены шесть типов участников, отсутствие membership fees, карта у всех consumers, отсутствие direct bypass и отдельные предпосылки выгод/расходов для niche case. Направление access-price incentive не превращено в наблюдение за всеми банками. Не выполнена полная математическая репликация всех propositions.

## Вся глава и арифметика вне отдельных claims

Дополнительно к реестру прочитаны полные модели loss, reserve, Friday T+2, delivery split, conversion-adjusted contribution и partner-exit checklist. Новых значимых необоснованных фактов вне реестра не найдено. Простая архитектурная диаграмма и роль connector не доказывают licence, юридическое consent или разрешение на конкретный запуск.

Арифметика перепроверена независимо:

- При GMV 1 млн, revenue 32000 и указанных disjoint cost/loss строках contribution = 6100, margin = 0.61%, после fixed cost 15000 profit = −8900. Break-even = 15000 / 0.0061 = 2 459 016.39; при GMV 2 млн profit = −2800. При дополнительных потерях 0.4% break-even = 7 142 857.14. Постоянство mix и маржи — условие модели.
- Connect: 100 accounts, 100000 volume, 400 payouts → 550; 100 payouts → 475. Payment processing не включён в эти суммы.
- Fixed-plus-percentage fee: для 2 USD сумма 0.358 (17.9%); для 20 USD — 0.88 (4.4%). Сумма до округления отделяется от actual currency minor-unit rounding.
- Четыре условные cost строки 0.69/0.29/0.70/0.40 после дополнительных 0.20 становятся 0.89/0.49/0.90/0.60. При указанных conversions contribution 80 × (8 − 0.69) = 584.80 и 70 × (8 − 0.29) = 539.70.
- Delivery 60 + 8 + 2 + 10 = 80. Fee, principal loss, reserve и transfer receivable не сведены в одно число и не посчитаны повторно.

## Ограничения

- **C029 unverifiable:** расхождение Stripe preview prose и более широкого country-code list не снято первичным подтверждением провайдера или account evidence. Допуск конкретного non-US merchant остаётся open; глава не обещает доступ.
- Triple-A FAQ подтверждает опубликованное предложение и указанный automatic withdrawal threshold 3000 USD equivalent. Не получен индивидуальный SLA, contract или доказательство лицензии/реального withdrawal.
- Reddit u/songtu-staygold прочитан с уточнением автора об acquiring. Это подтверждает вопрос/путаницу терминов, не правила сетей, фактический контракт или личность автора. Exact date не установлен по relative age.
- Mastercard global base rules проверены в нужных местах; не проведён исчерпывающий аудит всех regional supplements. BOE/CBI/FCA и US guidance не заменяют анализ конкретного юрлица и всего действующего законодательства.
- Нет проверки production, merchant accounts, ledger, bank credit, фактической конверсии, согласия клиента или общего правового заключения. Синтетические расчёты проверяют внутреннюю арифметику, не реалистичность коммерческой модели.

## Финальная проверка версии

Независимая проверка источников и конечного текста выполнена в исследовательском объеме; эта запись описывает аудит 17.09.2026. Изменения канонических файлов вносил root; данный аудитор пишет только отчёты своей части.

`final_verdict=reviewed_with_limitations` · `open_critical=0` · `open_major=0` · `open_minor=0`.

Повторно проверены реальные окончательные CHAPTER/SOURCES/CLAIMS после уведомления root о завершении правок. SHA-256 ниже относится к этим файлам, не к старой REVIEW и не к байтам внешних сайтов. Любая последующая правка требует обновления проверки и хешей.

| Final canonical file | SHA-256 |
|---|---|
| [chapters/part-04/CHAPTER.md](../../chapters/part-04/chapter.md) | `820c833732c1e70d7dfdeea1b21dab5835291fbadb631aca06d6ecdf93d90407` |
| [chapters/part-04/SOURCES.md](../../chapters/part-04/sources.md) | `adaca25348b531b671891072ad3be75d89f9b7bd8f650ea32293c39db3ac2c03` |
| [chapters/part-04/CLAIMS.md](../../chapters/part-04/claims.md) | `e75ef4d8a87cc17a2715f58c1b564fd09d7ef8f76c35f78ccde3376f8b1f3664` |

