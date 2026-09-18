---
title: "Часть 3 — журнал исследования и handoff"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Публичная редакция от 18.09.2026. Даты проверки и ограничения источников сохранены. Хеши в исторических аудитах относятся к исходной рукописи; публичные изменения и текущие хеши — в [паспорте издания](../../edition.md).

# Часть 3 — журнал исследования и handoff

**15.09.2026 · private · author: part_03_research · status: draft_for_review.**

## Выполнено

Внутренняя организационная ссылка из исторической авторской заметки исключена из публичного издания; исследовательская методика и внешние источники сохранены.

- CHAPTER.md: 6 686 слов по разделению пробелами; все шесть модулей, восемь подразделов Visa и восемь Mastercard, сравнительная таблица шести схем, синтетические примеры, десять задач и объясненные ответы.
- SOURCES.md: 47 карточек со snapshot ID, версиями/датами, реальными пределами чтения, access status, группами независимости и правами. Все 47ID используются в главе; metadata source явно обозначен.
- CLAIMS.md: 75 последовательных уникальных тезисов, включая open/rejected/working_hypothesis; reviewed_status всех pending. Есть таблица расчетов и разрешение существенных противоречий.
- Проверены идентификаторы источников, наличие шести точных module headings, относительные ссылки и арифметика задач. В трех основных файлах нет TODO/TBD/PLACEHOLDER. PDF не создавался и не заявляется готовым.

## Существенные findings для независимого reviewer

1. **Редакции:** Visa Core Rules18.04.2026,923PDF-страницы; Mastercard Rules02.06.2026,503; TPR09.06.2026,436; Switch Rules16.12.2025,114; SPME04.08.2026,236; MCC Quick Reference02.06.2026,359. Даты обложки не объявлены effective date каждого пункта.
2. **GMAP:** SPME§8.2,с.87 прямо говорит о suspension until further notice. ECP§8.3 использует число транзакций предыдущего месяца. Точные ECM/HECM thresholds вынесены в другой manual и не подставлены по памяти.
3. **VAMP:** fact sheet дает 150bps с 01.04.2026 для AP/Canada/EU/US, также count≥1500 и portfolio/country/exclusion conditions. Это не один универсальный merchant trigger.
4. **Visa disputes:** Table11-2 для категорий 12/13: acquirer pre-arbitration response30calendar days от Processing Date attempt; Tanzania domestic10; issuer arbitration10days от Processing Date response. Это не окно ответа магазина PSP.
5. **Crypto:** MC§9.4.9 использует MCC6051/TCCU и TTIP70/P76 по виду; P76fullyfiat-backed stablecoin/CBDC. Reporting category CBDC не приравнена к определению cryptocurrency. Visa Table7-9 отдельно классифицирует crypto/NFTcases; не переносить MC кодировку.
6. **Тарифные иллюстрации:** VisaUSeffective18.04.2026 verified selected rows. MC CanadaMay2026table прочитана, но точная effective date строк не подтверждена; глава прямо называет это иллюстрацией редакции по имени файла.
7. **Сервисы спорного цикла:** Verifi Order Insight описывает non-Visa direct integration; Ethoca Smart Subscriptions называет Ethocabrand-agnostic. Это не evidence подключения любого конкретного issuer.
8. **RTS/co-badging:** EUR-Lex JS challenge обойден не техническим взломом, а чтением официальных оригиналов BOE: RTS DOUE-L-2018-80459, IFR DOUE-L-2015-80958. Englishadopted articleXML использован длясверки конкретныхстатей. Полной currentconsolidation нет. BOE RTSAnalysis содержит ошибочную entrydate14/11/2018; operativearticle38+publication13/03/2018 дают 14.03.2018; application14.09.2019. Spanishcorrigendum2020-80441 прочитан.
9. **Reddit:** начальный DCCpost позднее открылся напрямую. Автор u/gbcox, UIdate«2yago», complaintoutcomeunknown. Рассказ не принят как установленное мошенничество; полный transcript/comments не копировался. X не используется.
10. **Наука/обучение:** ECB2010textbook для устойчивыхмоделей; BISWP1163 толькоофициальный summary; WhoPaysWhom authorversion/HAL2025 прочитана частично, без claim о проверенных proofs/experiments. Никакого фиктивного курса/таймкода.

## Явные пределы

- Полные VTS/MDES merchant message/lifecycle specs не получены. Отличия API не придуманы.
- Полный текущий Mastercard Chargeback Guide не открыт; Chargebacks Made Simple2025 — отдельный вводный документ. Data Integrity Monitoring Program и Visa Integrity Risk Program Guide не получены.
- EMVCo current TF2.4/new Use Cases — metadata. Прочитанный v2.2.1January2023 — illustrative guide с конкретными страницами в SOURCES, не новая полная specification.
- EBA Q&A2018_4031/4048/2019_4794 дают fetch/403; правовой scope любого MIT не реконструирован по snippets. RTS ст.14 используется для узкой серии sameamount/samepayee.
- Нет сопоставимой текущей 2026 рыночнойгеографии для всех схем, полного operatingrulebooks смежныхбрендов, actualprovidercontracts/productionapproval.
- Исходные чужие PDF/изображения/полные тексты не сохранены и не распространяются. Snapshot ID означает чтение, hash не выдуман.

## Что передать reviewer

Приоритет проверки: C021 (точные сроки Visa), C025 (VAMP scope), C040–C042 (GMAP/ECP), C060 (RTS scope), C068–C070 (crypto), C036 (ограниченная дата Canada). Также проверить разделение tokens, COF, CIT и MIT. Открытые пункты сохраняются открытыми, пока не получен достаточный источник. Автор не пишет REVIEW.md и не ставит независимое одобрение.
