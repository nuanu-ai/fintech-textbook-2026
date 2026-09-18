---
title: "Итог независимого фактчека — часть 03"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Публичная редакция от 18.09.2026. Даты проверки и ограничения источников сохранены. Хеши в исторических аудитах относятся к исходной рукописи; публичные изменения и текущие хеши — в [паспорте издания](../../edition.md).

# Итог независимого фактчека — часть 03

17.09.2026 · Asia/Makassar (UTC+08) · auditor: `deep_audit_02_03_04` · private. Срез знаний: 15.09.2026; повторный доступ и исправления — 17.09.2026. Более позднее чтение не названо историческим снимком.

## Результат и охват

Полностью прочитаны CHAPTER.md, CLAIMS.md и SOURCES.md. [CLAIM_AUDIT.md](claim-audit.md) содержит 75 индивидуальных verdict; [SOURCE_AUDIT.md](source-audit.md) — 48 индивидуальных записей, включая новый S048. Все оригинальные URL независимо попытался открыть. Для S022, S023 и S040 исходные региональные/глобальные страницы полностью не получены; официальные альтернативы и индекс отделены от оригинала. Остальные оригиналы дали содержательный материал в обозначенном scope. Полное чтение всех 923 страниц Visa или всех закрытых Standards не заявляется.

Предыдущая REVIEW использована только как указатель рисков. Все финальные изменения root сравнены с baseline и отдельно перепроверены по первичкам. Contradicted для C062 относится к явно отклонённому автором универсальному правилу, а не к текущему совету главы.

| Verdict | Claims |
|---|---:|
| verified | 55 |
| verified_as_reported | 7 |
| partial | 2 |
| contradicted | 1 |
| unverifiable | 8 |
| non_factual | 2 |
| **Всего** | **75** |

## Findings и повторная проверка

Новых замечаний: **6 minor, 0 major, 0 critical**. Все шесть закрыты. Исторические версии не заменены молча текущими.

| Finding | Приоритет | Исходная точная фраза / место | Независимое основание | Исправление и итог |
|---|---|---|---|---|
| P03-A01 | minor | S011: `newer Use Cases v2.3` без draft-статуса | [EMVCo landing](https://www.emvco.com/emv-technologies/payment-tokenisation/), документы: Use Cases v2.3_DRAFT 2 April 2026, comments end 1 May; Technical Framework v2.4 final 9 July 2026 | Root явно разделил draft и final. Повторно прочитаны метаданные; полного нового framework не заявлено. Closed. |
| P03-A02 | minor | S019 title: `Evolution of Compelling Evidence: External FAQs` | [Visa PDF](https://usa.visa.com/content/dam/VCOM/regional/na/us/support-legal/documents/evolution-of-compelling-evidence-external-faqs.pdf), October 2022 cover — Client FAQs | Title исправлен; filename с external-faqs отдельно объяснён. Обложка и нужные вопросы прочитаны независимо. Closed. |
| P03-A03 | minor | S024 title: `Visa Stored Credential Transaction Framework` | [Visa PDF](https://usa.visa.com/content/dam/VCOM/global/support-legal/documents/stored-credential-transaction-framework-vbs-10-may-17.pdf), cover | Точный заголовок заменён на Improving Authorization Management for Transactions with Stored Credentials; исторический статус 2017 сохранён. Обложка и определения прочитаны. Closed. |
| P03-A04 | minor | S034 `J/Secure2.0`; C047 и таблица главы `J/Secure 2.0` | [JCB FAQ](https://www.global.jcb/en/products/security/jsecure/faq/), текущий title J/Secure™ FAQ for Merchants, Q1–Q4 | Текст подтверждает механизм EMV3DS, но не точный release 2.0. Root исправил title/audience и убрал неподтверждённую версию из карточки, claim и главы. Текущий C047 verified; механизм не изменён. Closed. |
| P03-A05 | minor | S039: `José Aurazo et al.` | [BIS WP1163 page](https://www.bis.org/publications/working-paper-1163-interchange-fees-access-pricing-and-sub-acquirers-payment-markets), Authors | Указан единственный автор José Aurazo. Блок автора независимо прочитан; модель также проверена по PDF в части 04. Closed. |
| P03-A06 | minor | C012: `PAR ... не является самостоятельным payment credential`; исходные S008/S010 давали linkage/context без достаточно прямого основания для всей фразы | [PCI SSC FAQ1374](https://www.pcisecuritystandards.org/faqs/1374/), полный ответ, особенно ¶3, January 2016 | Root добавил S048, ссылки в C012/главе; мысль о согласии выделена как отдельный учебный вывод. FAQ прочитан независимо целиком: PAR alone не инициирует authorization/capture/clearing/settlement. C012 partial → verified. Closed. |

## Решающие проверки правил, версий и границ

- Visa Rules 18 April 2026: §§1.7.3–1.7.6 разделяют authorization/clearing/settlement; §4.1.7 связывает virtual account с product/program BIN. §11.2.3, pp.671–673, table 11-2 и fn7 непосредственно прочитаны: acquirer pre-arbitration response 30 календарных дней, Tanzania domestic 10; issuer arbitration 10 от processing response. Это не универсальные merchant deadlines.
- VAMP: прочитана вся публичная одностраничная таблица с формулой TC40+TC15 / TC05, исключениями и условиями extraction, merchant count, региона и портфеля. Порог 150 bps с 1 April 2026 не выдан за единственное условие для любого мерчанта.
- Mastercard Rules 2 June 2026, TPR 9 June 2026, SPME 4 August 2026 и Switch Rules 16 December 2025 проверены по применимости, лицензии/Area of Use, single/dual, C/M taxonomy, GMAP/ECP и settlement. Текущие ECM/HECM thresholds по отсутствующему Data Integrity manual не восстановлены из старых цифр.
- MCC5815–5818 сверены по Quick Reference Booklet pp.162–164: 5818 требует как минимум две указанные категории; условие размера не добавлено. Visa table 7-9 crypto/NFT и Mastercard §9.4.9 проверены отдельно; MCC, TCC и registration не заменяют местную лицензию.
- Visa USA exempt/regulated debit строки и fraud-prevention footnote проверены в таблице 18 April 2026. Mastercard Canada — именно May 2026 edition, Core Digital Commerce 1.67% / Standard 1.96%, с оговоркой publisher о договорных условиях. Эти строки не стали ценой PSP или универсальным тарифом.
- EMVCo Use Cases v2.2.1: roles, characteristics и guest checkout, включая table 11.12 с Used/Not Used cryptogram, прочитаны в исторической версии. CIT/MIT/COF, token credential и account updater не смешаны с consent. BOE RTS Article 14/38 и Spanish corrigendum прочитаны; IFR Article 8(6) разрешает holder override среди принятых вариантов, с датой применимости Article 18.

## Исследование и факты вне реестра

Прочитана вся глава, включая незарегистрированные примеры funding/payout, FX refund, fee waterfall, сценарии guest checkout, перенос токенов, crypto/off-ramp и вопросы выбора партнёра. Синтетические схемы не доказывают разрешение на доступ, успех rollout или агентское consent. Новых существенных фактов вне реестра, требующих исправления, не найдено.

Пересчитаны 100 + 2 = 102; purchase FX 100 EUR × 1.10 = 110 и refund × 1.08 = 108; Visa 100 USD fee 1.80, regulated 0.26 либо 0.27 при оговорённом условии; Canada difference 0.29 на 100 CAD. Все суммы соответствуют указанным входным предпосылкам, не прогнозу.

Для Who Pays Whom прочитаны abstract/introduction, §3.3 threat model и comparison table. Авторская версия с HAL deposit 29 January 2025 содержит модели доверия и ограничение совместной коррупции issuer/proxy; эти предпосылки не превращены в доказанное свойство VTS/MDES. Полные proofs не воспроизведены, deployment не установлен. C064 поэтому verified_as_reported.

Reddit DCC: прочитан исходный пост u/gbcox и последующее сообщение того же автора о зачислении курсовой разницы банком. Это уточняет историю самого высказывания; не подтверждает юридический fraud finding. Глава ограничивает незавершённость именно первоначальным постом, поэтому исправление её узкой формулировки не требуется. C073 — факт публикации, C074 — unverifiable; exact day не установлен по relative UI date.

## Ограничения

- **C038/C039 partial:** Ethoca global pages возвращали 403/timeout. [US Consumer Clarity](https://www.mastercard.com/us/en/business/cybersecurity-fraud-prevention/dispute-management/ethoca-consumer-clarity.html) и [официальный API PDF 4.0.0](https://static.developer.mastercard.com/content/consumer-clarity/uploads/ethoca-merchant-digital-api-integration-guide.pdf), §1, подтверждают ограниченный scope. Smart Subscriptions original полностью не прочитан; индекс не выдан за полный текст. Текущая точная API-версия и coverage каждого issuer не установлены.
- **C032:** [официальная US Move page](https://www.mastercard.com/us/en/business/payments/mastercard-move/payments-to-businesses.html) восстановила публичное предложение с market/product caveats; оригинальная Europe page полностью недоступна. Verified_as_reported подтверждает описание, не работоспособность маршрута.
- **C010, C030, C042, C051, C061, C063, C071, C074 unverifiable:** нет соответствующей статистики, полных контрактов/Standard, полной новой спецификации или первичного решения банка/суда. Открытые вопросы главы остаются открытыми.
- Публичные rules имеют исключения и могут уступать полным member Standards. Это не полный юридический аудит, проверка каждой локальной модификации, тест аккаунта, payout или воспроизведение криптографических доказательств. Меняющиеся страницы не сохранены как полные архивы.

## Финальная проверка версии

Независимая проверка источников и конечного текста выполнена в исследовательском объеме; эта запись описывает аудит 17.09.2026. Изменения канонических файлов вносил root; данный аудитор пишет только отчёты своей части.

`final_verdict=reviewed_with_limitations` · `open_critical=0` · `open_major=0` · `open_minor=0`.

Повторно проверены реальные окончательные CHAPTER/SOURCES/CLAIMS после уведомления root о завершении правок. SHA-256 ниже относится к этим файлам, не к старой REVIEW и не к байтам внешних сайтов. Любая последующая правка требует обновления проверки и хешей.

| Final canonical file | SHA-256 |
|---|---|
| [chapters/part-03/CHAPTER.md](../../chapters/part-03/chapter.md) | `868ad139cde16574406f15626c8de9ed5a70f49bdce94c1059ff2c7940f14e20` |
| [chapters/part-03/SOURCES.md](../../chapters/part-03/sources.md) | `6e9af557851aac41ed517199f3de73bce24f263cfc083eb310cf59a71faf32f5` |
| [chapters/part-03/CLAIMS.md](../../chapters/part-03/claims.md) | `5de7b8a86b091b7cae732f8471664e300d601d2e5b082233cd635631a9c486a7` |

