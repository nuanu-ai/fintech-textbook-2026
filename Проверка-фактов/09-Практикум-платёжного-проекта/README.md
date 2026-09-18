---
title: "Independent factual audit — Part 09"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Источники и фактчек](../README.md) · [Читать главу](../../Учебник/09-Практикум-платёжного-проекта/README.md)

> Публичная редакция от 18.09.2026. Даты проверки и ограничения источников сохранены. Хеши в исторических аудитах относятся к исходной рукописи; публичные изменения и текущие хеши — в [паспорте издания](../../Методика/Паспорт-издания.md).

# Independent factual audit — Part 09

17.09.2026 · Asia/Makassar (UTC+8) · auditor deep_audit_06_07_08_09 · private

## Результат

Прочитаны полные CHAPTER/SOURCES/CLAIMS. Отдельно оценены26 claims и21 source card. Нового подтверждённого critical/major не найдено. Четыре partial относятся к недоступным оригиналам/исторической версии, один unverifiable — явно открытому вопросу о неизменности dynamic docs. Никакая недоступность не замаскирована verified.

## Доступ к первичке и ограничения выводов

- **C001/S001, partial.** EUR-Lex consolidation/original/TXT/PDF возвращали JS challenge (HTTP202). Article3(j) самостоятельно прочитан напрямую в официальном legislation.gov.uk mirror EU directive: technical services exclusion содержит исключение PIS/AIS. Идентичность полной consolidation17.01.2025 не подтверждена. Это ограничение проверки версии, не обнаруженное противоречие в механизме.
- **C002/C016/S003 и C017/S004, partial.** Bank Indonesia original pages/PDF не получены из-за resets/timeouts. В официальном индексе прочитаны QRIS sources of funds/static-dynamic/approved participants и PBI10/2025 effective31.03.2026/new framework. Нельзя назвать это прямым чтением всей BI page или нормативного акта.
- **C018/S012, verified по альтернативной первичке.** EUR-Lex body недоступен, но ESMA official reproduction Articles59,60,143 непосредственно прочитан. Authorisation/financial-entity routes и maximum transition01.07.2026 подтверждены, с earlier grant/refusal и правом страны сократить переход. Consolidation metadata не объявлена независимо подтверждённой.
- **C026, unverifiable.** Архивного15.09 снимка динамических Stripe/x402 документов нет. Текст честно оставляет тождество версий open, а17.09 observation отдельно датирован.
- **S013/S018, metadata limitations.** Google structured datePublished16.09.2025 отличается от одного HTML display17.09; дата карточки не признана ошибочной. Current Circle byline Circle Internet Financial отличается от Team Circle в карточке; историческая форма byline не установлена, механизм/даты операционного отчёта этим не меняются.

## Полная глава, кейсы и арифметика

Проверены существенные факты вне реестра: separate merchant/provider agreements, момент погашения долга в синтетическом договоре, approvals/licensing и source of refund liquidity. Stripe terms§5 предусматривают свой contractual debt-discharge trigger; синтетический кейсC не выдан за эти реальные условия.

КейсыA–D пересчитаны по исходным остаткам и движениям:

| Кейс | Независимый числовой контроль |
|---|---|
| A | Bank1000+87−15,50=1071,50EUR; trial1071,50+25+3,50=1100; buyer425EUR. При неосвобождённом reserve нужен полный top-up25,50. |
| B | Fee11200IDR; bank2000000+1588800−400000−2500=3186300; buyer1800000; expenses13700; trial3600000.0,7% — условие задачи, не универсальный QRIS тариф. |
| C | Bank1000+98−25,50=1072,50EUR; refund25×1,12=28USDC; buyer418. При depeg25×1,12/0,98=28,571428… и вверх28,571429. Новый payout допустим после доказанного возврата средств, не после одного timeout. |
| D | Buyer72USDC, seller47,80, service0,20; сумма120. Seller journal47,80+12+0,20=60, credit20+40. Сервис покрывает network cost из тарифа по условию примера. |
 
Нехватка ликвидности при1000cash и4000refunds равна3000, несмотря на требование10000 к партнёру. Arithmetic не доказывает договорную исполнимость, достаточность резервов или законность реального маршрута. H1–H3 остались гипотезами, гипотезы не являются решением о запуске.

## Исторический инцидент и пределы независимости

Fed/Treasury/FDIC statement12.03.2023, Circle announcement с разными body/page dates12/13March и операционный update15/16March прочитаны отдельно. Circle3.3bn reserve deposit,3.8bn redemptions/.8bn minting и substantially all backlog — атрибутированные сообщения. Не установлено исполнение каждой заявки/банковского перевода. Reddit MediumAdhesiveness5 post/Updates подтверждает публикацию обсуждения; price-feed и причинность не проверены.

Независимый review не является финансовым, юридическим или эксплуатационным одобрением.

## Coverage and verdict counts — публичная редакция

Claims: 26; 20 опубликованных карточек источников и 1 запись об исключении P09-S021. Every ID has one matrix row. C008/C009 заменены редакционными положениями 18.09.2026: verified → non_factual. Остальной фактчек сохраняет дату 17.09.2026.

- partial: 4
- verified: 11
- non_factual: 5
- verified_as_reported: 5
- unverifiable: 1

## Final recheck and hashes

Финальный текст прочитан после provisional freeze редактора. Хеши рассчитаны по фактическому содержимому окончательных файлов. Previous review использован только как указатель риска, не как evidence.

final_verdict: reviewed_with_limitations

open_critical: 0

open_major: 0

| File | SHA-256 |
|---|---|
| [CHAPTER.md](../../Учебник/09-Практикум-платёжного-проекта/README.md) | 43b39c1c23c142cb72180197c69de9432df54d0643b527eed0aa1dcd8daf2f14 |
| [Источники](../../Учебник/09-Практикум-платёжного-проекта/Источники.md) | fc913f90460ec4f751b0b3eef83a48cafb88b05610e2e7e981c6eb1d2ea0ca00 |
| [Утверждения](../../Учебник/09-Практикум-платёжного-проекта/Утверждения.md) | 2232417ab58af5c2bb90576590a02b8aaf3165645935042f8b3f05f22b2d90e1 |
