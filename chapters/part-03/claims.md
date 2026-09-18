---
title: "Часть 3 — реестр утверждений"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Публичная редакция от 18.09.2026. Даты проверки и ограничения источников сохранены. Хеши в исторических аудитах относятся к исходной рукописи; публичные изменения и текущие хеши — в [паспорте издания](../../edition.md).

# Часть 3 — реестр утверждений

**v0.1 · 15.09.2026 · private · independently_reviewed_draft · автор: part_03_research.**

Фактчек исходной редакции завершен17.09.2026. Связь исходной версии с публичной копией, область адаптации и текущая навигация описаны в паспорте издания.

`confirmed` здесь означает подтверждение автором **в явно указанной области**, а не независимый reviewer verdict. Все карточки имеют `reviewer=see_REVIEW.md`, `review_status=see_REVIEW.md`. Непрочитанное содержание не получает статус подтвержденного.

## Общие поля каждой строки

- `as_of=2026-09-15`; `last_checked_at=2026-09-15, Asia/Makassar`; `effective_to=unknown`, если речь о норме; `not_applicable` для объяснения/примера. `effective_from` дан в строке для используемого датированного положения; иначе `provision_specific/unknown`, не дата обложки.
- Ссылка вида `S001: §…` в evidence означает `P03-S001 + snapshot_id P03-S001@2026-09-15 + locator + relation=supports`. `context`/`contradicts` указаны отдельно. Название и URL раскрыты в [SOURCES.md](sources.md); ближайшая ссылка в [CHAPTER.md](chapter.md) ведет напрямую в оригинал.
- `reasoning/confidence_basis`: прямое содержание названного первичного раздела в пределах scope; для научного/social/учебного источника предел чтения явно сужен. Поле «Вывод и предел» содержит собственную интерпретацию, если она есть. Синтетические числа не выдаются за эмпирическое наблюдение.
- `conflicts=none_identified_in_reviewed_scope` по умолчанию. Это не заявление, что всех противоречий нет. Особые конфликты описаны в строках и ниже.
- `review_trigger`: новая применимая редакция/bulletin или изменение региона, продукта, участника, activity/route; для product page — новый релиз/договор перед внедрением; для закона — amendment/судебное толкование/локальное применение; для рассказа — новые первичные evidence или установленный outcome.
- `jurisdiction/conditions` и `effective_from` в колонке «Scope и дата» имеют приоритет над общим срезом. Однотипные страницы Visa/Verifi и Mastercard/Ethoca не считаются независимыми подтверждениями, группы в SOURCES.

## 3.1 Институт и права

| claim_id | module_ids / kind / status | Утверждение | Scope и дата | Evidence / locator | Вывод и предел |
|---|---|---|---|---|---|
| P03-C001 | 3.1; definition; confirmed | Card scheme и processing entity — разные роли | ECB report2025, EU | S029: §§1–3 | Объединение в группе не стирает различие правил и обработки |
| P03-C002 | 3.1; definition; confirmed | Четырёхсторонняя модель разделяет issuer и acquirer, трёхсторонняя объединяет эти функции | Учебная модель, не счет всех компаний; effective n/a | S028: с.55–57 | Датированный учебник подходит для модели, не для текущего списка участников |
| P03-C003 | 3.1; mechanism; confirmed | Участие в сети создает взаимную ценность для сторон карточного рынка | Теоретическое объяснение | S028: с.55–57 context; S039: Focus/Contribution context | Пример1млн держателей собственный, не доказательство оптимальности комиссии; BIS прочитан лишь summary |
| P03-C004 | 3.1; legal; confirmed | Mastercard требует соответствующего одобрения и License для Activity | Mastercard global rule with exceptions, edition02.06.2026 | S002: §1.1 с.34 | Участие и API-доступ различаются; не разрешение определенной организации |
| P03-C005 | 3.1; legal; confirmed | Область использования Mastercard license ограничивает Activity с предусмотренными исключениями | §1.7/global plus regional variations | S002: §§1.6–1.7.1 с.42–43 | Для выхода в другой регион нужно проверить применимые права, не переносить старый approval |
| P03-C006 | 3.1; mechanism; confirmed | Публичные копии правил имеют ограничения полноты/актуальности | Visa public edition и Mastercard public index | S041: Rules impacting processors and merchants; S042: introductory caveats | Public URL не удостоверяет исчерпывающий договорный набор |
| P03-C007 | 3.1; mechanism; confirmed | Лицензия схемы не заменяет право регулируемой деятельности | Mastercard eligibility subject to law | S002: §1.1.1 с.34 | Практическая трехслойная проверка — редакторский вывод, не индивидуальное юридическое заключение |

## 3.2 Visa

| claim_id | module_ids / kind / status | Утверждение | Scope и дата | Evidence / locator | Вывод и предел |
|---|---|---|---|---|---|
| P03-C008 | 3.2; product; confirmed | Виртуальная форма карты и продуктовая категория — разные признаки | Visa virtual accounts/product schedule | S001: §4.1.7; S016: product tables | Virtual не равняется отдельному источнику денег; не все combination eligibility проверены |
| P03-C009 | 3.2; mechanism; confirmed | Авторизация, clearing и settlement представлены в правилах как отдельные функции | Visa §1.7, edition18.04.2026 | S001: §§1.7.3–1.7.6 | Учебные часы/суммы не Visa SLA |
| P03-C010 | 3.2; empirical; open | Dual-message доминирует в любом сегменте Visa | Доля по конкретному рынку/периоду не получена | S001/S016 context, not sufficient | В структуре было слово «доминирование», но измерение не найдено; глава не выдает его за установленную долю |
| P03-C011 | 3.2,3.5; product; confirmed | VTS использует token-to-PAN processing с issuer authorization decision | Fact sheet2022 illustrative flow | S009: How it works, с.2 | Общая роль, не текущий полный message contract |
| P03-C012 | 3.2,3.5; mechanism; confirmed | PAR позволяет связывать записи, но не является самостоятельным payment credential | VTS product/PAR Inquiry | S008: PAR Inquiry; S010: §11.3 context; S048: FAQ1374, answer paragraph3, no transaction initiation using PAR alone | Отсутствие PAN у мерчанта не означает анонимность или consent |
| P03-C013 | 3.2; definition; confirmed | AFT и OCT описывают разные стороны funding/push сценария | Visa Direct for Card | S007: Implementation Overview/Getting Started | Двуногий пример102=100+2 синтетический; AFT не обязателен для всякого payout |
| P03-C014 | 3.2; legal; confirmed | Originator Visa Direct должен быть licensed acquirer или работать со sponsor | Visa Direct for Card stated participation | S007: Getting Started | Публичная документация не подтверждает approval конкретной программы |
| P03-C015 | 3.2; product; confirmed | Доступность средств при Visa Direct зависит от принимающего учреждения и других условий | Account/region/type dependent | S007: funds availability qualifications | Нельзя обещать немедленную доступность каждому получателю |
| P03-C016 | 3.2; mechanism; confirmed | DCC требует информации о конвертации и выбора держателя | Visa consumer DCC guidance | S014: What to expect | Не доказательство что DCC всегда дешевле/дороже, social opinion отдельно |
| P03-C017 | 3.2,3.3; mechanism; confirmed | Interchange и merchant discount — разные уровни цены | Visa US merchant explainer | S043: Interchange reimbursement fees | Табличный interchange не полный MDR; конкретные fee pass-through договорные |
| P03-C018 | 3.2; product; confirmed | Выбранная Visa USA exempt debit e-commerce строка равна1.65%+0.15USD | US applicableCPS/e-Commerce Basic Debit, effective18.04.2026 | S016: с.4 | 100USD→1.80USD лишь тарифная иллюстрация, без остальных fees |
| P03-C019 | 3.2; product; confirmed | В выбранной Visa USA regulated колонке0.05%+0.21USD с возможным0.01USD adjustment | US qualified regulated debit, effective18.04.2026 | S016: с.4 and footnote | 0.26/0.27USD на100; не универсальная ставка любого consumer debit |
| P03-C020 | 3.2; definition; confirmed | Visa dispute categories10/11/12/13 разделяют fraud/auth/processing/consumer disputes | Visa public rules18.04.2026 | S001: §§11.2–11.3 | Классификация не диктует один общий deadline |
| P03-C021 | 3.2; legal; confirmed | §11.2.3 содержит 30 дней pre-arbitration response и 10 дней arbitration after response | Категории 12/13: acquirer response от даты обработки attempt; Tanzania domestic — 10 дней; issuer arbitration от даты обработки response; edition 18.04.2026 | S001: §11.2.3, с.669–673 | Это межучастнические сроки, не универсальное окно merchant PSP; применимые исключения обязательны |
| P03-C022 | 3.2; mechanism; confirmed | Историческое Visa CE FAQ описывает доказательства по двум предшествующим неоспоренным операциям | FAQOctober2022, initiativeApril2023 | S019: issuerFAQ1–7 | Не обещание любой спор выиграть поIP; current qualification не восстановлена из старогоFAQ |
| P03-C023 | 3.2; product; confirmed | Order Insight описывает доступ для non-Visa issuers через direct integration | Undated Verifi page as read | S020: concluding paragraphs | Владение Visa не равно исключительной поддержке Visa; конкретные банки не проверены |
| P03-C024 | 3.2; mechanism; confirmed | VAMP ratio используетTC40+TC15 кCNP VisaNet settledTC05 с оговоренными exclusions | Public2025fact sheet | S013: definition/footnotes,с.1 | Не сырой универсальный chargeback ratio; timing data extract влияет |
| P03-C025 | 3.2; legal; confirmed | Excessive Merchant threshold150bps указан с01.04.2026 дляAP/Canada/EU/US при иных условиях | Для AP/Canada/EU/US не менее 1500 учитываемых событий; portfolio/country qualifications apply | S013: threshold table and footnotes | 150bps в одиночку не доказывает program entry; full guide beyond sheet not read |

## 3.3 Mastercard

| claim_id | module_ids / kind / status | Утверждение | Scope и дата | Evidence / locator | Вывод и предел |
|---|---|---|---|---|---|
| P03-C026 | 3.3; product; confirmed | Mastercard/Maestro/ATM и route требуют учета разных applicability rules | Global and MainlandChina/regional exceptions,02.06.2026 | S002: Applicability,с.29–31 | Logo не достаточный маршрутизатор; no current global Maestro issuance claim |
| P03-C027 | 3.3; mechanism; confirmed | Mastercard поддерживает dual- и single-message processing | Defined systems; guide2025/TPR2026 | S021: §§2.1–2.2; S003: §2.2.1 | Нельзя всегда достраивать второй capture; duplicate12+12 пример условный |
| P03-C028 | 3.3; mechanism; confirmed | Switch Rules описывают net/bilateral settlement и отделяют message cutoff от funds-transfer finality | Rulebook16.12.2025 and local transfer law | S004: §§3.1–3.1.2,с.40 | Finality не запрет будущего отдельного компенсационного сообщения |
| P03-C029 | 3.3; product; confirmed | MDES/tokenization описание включает решение эмитента и token/cryptographic data | Mastercard public primer2024 | S012: How does tokenization work/online COF | Public primer not complete merchant MDES API |
| P03-C030 | 3.3,3.5; product; open | VTS и MDES имеют взаимозаменяемые merchant API и lifecycle | Exact implementation/country/provider | S008/S009/S012 context; no complete wire specs | Не установлено, и в главе не утверждается; uniformSDK не доказательство |
| P03-C031 | 3.3; definition; confirmed | Mastercard Payment Transaction не является refund предыдущей покупки | Defined Applicability,02.06.2026 | S002: с.30 | MoneySend/payment semantics нельзя реализовать произвольным refund |
| P03-C032 | 3.3; product; confirmed | Move portfolio включает выплаты бизнесу/мерчантам | Market/product-dependent, page2026read | S040: Use Cases/FAQ/footnotes | Move portfolio шире одного MastercardSend card route; exact coverage not claimed |
| P03-C033 | 3.3; mechanism; confirmed | Mastercard converter допускает issuer fee/rate divergence и fallback к processing rate | Card/bank/transaction dependent | S015: Please Note | Калькулятор не объясняет любую фактическую сумму выписки |
| P03-C034 | 3.3; mechanism; confirmed | Mastercard settlement currency conversion отличается по роли от cardholder FX | Switch Rules16.12.2025 | S004: §3.1.1 | Это разные валютные отношения, не двойная комиссия по определению |
| P03-C035 | 3.3; mechanism; confirmed | Interchange qualification зависит от совокупности характеристик обработки | Mastercard US explanatory page | S017: determination/qualification paragraphs | ОдинdigitalMCC илиproductlabel не гарантирует тариф |
| P03-C036 | 3.3; product; confirmed | В прочитанной канадской таблице DigitalCommerceCore1.67%,StandardCore1.96% | Canada domestic consumer credit May2026edition; exacteffective unknown | S018: с.2 | Разница0.29CAD на100 — иллюстрация edition, не quote текущего контракта |
| P03-C037 | 3.3; mechanism; confirmed | Mastercard dispute overview предусматривает second presentment, pre-arbitration и arbitration | Publicintroguide2025 | S021: §§3–5,с.7–10 | Не исчерпывающие сроки полногоcurrentChargebackGuide |
| P03-C038 | 3.3; product; confirmed | Ethoca Consumer Clarity описывает transaction details/API-интеграцию | Product page, participating network | S022: What makes us different | Эффективность/конкретное issuer coverage не измерены |
| P03-C039 | 3.3; product; confirmed | Ethoca на странице Smart Subscriptions названаbrand-agnostic | Undated public product statement | S023: Powering the global subscription economy | Не означает все карты/банки уже подключены |
| P03-C040 | 3.3; legal; confirmed | GMAP приостановлена до дальнейшего уведомления вSPME04.08.2026 | Scope current public edition, resumptionunknown | S005: §8.2,с.87 | Более поздний применимыйbulletin может изменить статус; сторонний launchpost не перевешивает |
| P03-C041 | 3.3; mechanism; confirmed | ECP bps делит chargebacks текущего месяца наtransactions предыдущего | SPME §8.3 definition | S005: §8.3,с.87–88 | Same-month denominator — другая метрика |
| P03-C042 | 3.3; legal; open | Полные актуальныеECM/HECM числовые thresholds установлены этой главой | RequiredDataIntegrityMonitoringProgram unavailable | S005: §8.3 context/reference | Не установлены; старые100/150/300 thresholds не воспроизведены |

## 3.4 Другие схемы и local routing

| claim_id | module_ids / kind / status | Утверждение | Scope и дата | Evidence / locator | Вывод и предел |
|---|---|---|---|---|---|
| P03-C043 | 3.4; product; confirmed | Amex OptBlue предусматривает стороннего provider, устанавливающего merchant rate | США, eligible merchants | S030: FAQ on provider/pricing | В этом канале договор не обязательно прямой с Amex |
| P03-C044 | 3.4; product; confirmed | Amex публикует COF и digital-wallet tokenization offerings | Зависимость от страны/регистрации | S031: Tokenization Services | Полный implementation guide не прочитан |
| P03-C045 | 3.4; product; confirmed | Discover публикует Stored Token Services с domain controls | DGN public offer | S032: main description | Не доказательство полных push/dispute функций |
| P03-C046 | 3.4; product; confirmed | JCB/Adyen объявили COF-tokenization rollout 13.05.2025 | Объявление для domestic/global merchants | S033: release | Подтверждено объявление; результат и независимый uplift неизвестны |
| P03-C047 | 3.4; product; confirmed | J/Secure описывает 3DS-аутентификацию | Участвующие JCB issuers | S034: FAQ | Аутентификация не является финансовой авторизацией/settlement |
| P03-C048 | 3.4; product; confirmed | MoneyExpress описывает remittance на UnionPay debit в Китае с RMB credit | Destination China, eligible accounts | S035: main paragraphs | Полный worldwide payout scope и гарантированное время не установлены |
| P03-C049 | 3.4; legal; confirmed | IFR ст.8 регулирует co-badging и выбор приложения | ЕС в scope акта; ст.8 применяется с 09.06.2016 | S038: ст.8(6),18 | Merchant priority может существовать; держатель сохраняет предусмотренный выбор среди принимаемых вариантов |
| P03-C050 | 3.4; product; confirmed | Обзор BI связывает GPN logo ATM/debit с PBI 19/8/PBI/2017 | Индонезия, обзор регулятора | S036: ATM/debit/GPN | Не доказательство обязательности GPN для каждого иностранного/e-commerce платежа |
| P03-C051 | 3.4; empirical; open | Есть сопоставимая оценка географической силы всех шести схем на 2026 год | Comparable market share / coverage dataset не получен | S029 исторический context; S030–S035 product context | В таблице указана география документа/сервиса; доли и ранжирование не выдуманы |

## 3.5 Tokens, COF, subscriptions

| claim_id | module_ids / kind / status | Утверждение | Scope и дата | Evidence / locator | Вывод и предел |
|---|---|---|---|---|---|
| P03-C052 | 3.5; definition; confirmed | CIT предполагает активное взаимодействие держателя, MIT — merchant initiation на ранее установленном основании | Visa 2017 definitions; текущие MC identifiers | S024: с.3–6; S003: с.330–333 | Историческое определение не заменяет текущие требования реализации |
| P03-C053 | 3.5; definition; confirmed | Сохраненная карта может использоваться в CIT | Visa COF framework | S024: с.3–6 | COF не синоним MIT; учебная матрица показывает разные признаки |
| P03-C054 | 3.5; mechanism; confirmed | Network token может применяться в guest checkout | EMVCo illustrative guide v2.2.1 | S010: §11.3, с.150–155 | Это не разрешение мерчанту на любые будущие покупки |
| P03-C055 | 3.5; mechanism; confirmed | Token requestor, TSP, issuer и token user — отдельные роли | EMVCo guide v2.2.1, выбранные разделы | S010: §§3–7, с.15–16/19–20/24/27–28/30; §11.3 | Роли могут совмещаться; шаги не исчерпывают все варианты протокола |
| P03-C056 | 3.5; mechanism; confirmed | Domain controls ограничивают token use; применение cryptogram зависит от use case | EMVCo guide, guest/table11.12 | S010: §7; §11.3.4, с.153 | Не утверждается криптограмма в абсолютно каждой MIT-операции |
| P03-C057 | 3.5; hypothesis; working_hypothesis | Миграция provider handle/token требует проверки requestor, domain и lifecycle contracts | Конкретный PSP и маршрут не выбраны | S010/S024 context | Архитектурный вывод и вопросы к договору; обещания портируемости нет |
| P03-C058 | 3.5; product; confirmed | VAU передает обновленные реквизиты и status advices | Участвующие стороны Visa VAU | S026: overview / update types | Не все карты обязательно покрыты; согласие не возобновляется из наличия новых данных |
| P03-C059 | 3.5; product; confirmed | MC ABU privacy notice описывает обработку старых/новых PAN/expiry | Notice effective 01.10.2025 | S027: information types / purposes | Data update не равен consent management; отмена подписки — отдельное событие |
| P03-C060 | 3.5; legal; confirmed | RTS ст.14 описывает SCA при создании/изменении/первой операции серии с одинаковыми суммой и получателем | Scope акта ЕС; общее применение с 14.09.2019 | S037: ст.14,38; S044: Spanish correction | Не универсальное освобождение всех подписок; полная консолидация не прочитана |
| P03-C061 | 3.5; legal; open | Любой MIT автоматически находится вне SCA | Такое всеобщее утверждение не подтверждено | EBA Q&A недоступны; S037 context only | Scope payee-initiated и exemption — разные вопросы; blanket claim не принят |
| P03-C062 | 3.5; legal; rejected | Mastercard требует receipt после каждого billing от любого мерчанта без исключений | Исторический FAQ, обновленный в ноябре 2022 | S025: вопросы1–9 contradicts | Изменение 11.10.2022 делает это best practice с исключением для определенной группы; не универсальная текущая обязанность |
| P03-C063 | 3.5; product; open | Текущий EMVCo TF2.4 полностью прочитан автором | Только metadata новой редакции | S011: metadata only | Глава использует прочитанный старый guide для иллюстрации ролей |
| P03-C064 | 3.5; mechanism; confirmed | Who Pays Whom предлагает отдельные privacy-протоколы; это не доказательство их VTS/MDES deployment | Author version / HAL 29.01.2025, частичное чтение | S045: abstract, intro, related work, Appendix B | Только вопрос и контекст исследования; proofs/experiments не проверены |

## 3.6 MCC, ограничения и случаи

| claim_id | module_ids / kind / status | Утверждение | Scope и дата | Evidence / locator | Вывод и предел |
|---|---|---|---|---|---|
| P03-C065 | 3.6; legal; confirmed | Mastercard возлагает MCC assignment на acquirer | Rules 02.06.2026, §5.8.1 | S002: §5.8.1, с.116 | Анкета мерчанта дает сведения; окончательное решение не следует из выбранного поля |
| P03-C066 | 3.6; definition; confirmed | MCC 5815–5818 различают виды digital goods; 5818 охватывает минимум две из категорий 5815/5816/5817, без порога размера merchant | MC QRG 02.06.2026 | S006: с.162–164 | Цифровая форма не устраняет различий товара и финансового актива |
| P03-C067 | 3.6; legal; confirmed | SPME включает определенные adult/gambling/games/crypto виды в specialty registration | Категории §9.1, edition 04.08.2026 | S005: §9.1, с.111 | Это не запрет всех игр или признание законности adult в любой стране |
| P03-C068 | 3.6; legal; confirmed | MC crypto §9.4.9 предусматривает регистрацию до processing | Acquirer / sponsored merchant в определенном crypto scope | S005: §9.4.9, с.126–127 | Registration не устраняет local licensing и partner approval |
| P03-C069 | 3.6; legal; confirmed | MC crypto-маркировка в §9.4.9 использует MCC6051/TCC U и TTI P70/P76 по виду | P76 для полностью fiat-backed stablecoin/CBDC; edition 04.08.2026 | S005: §9.4.9, с.126–127 | Включение CBDC в reporting не означает определение всех CBDC как crypto |
| P03-C070 | 3.6; legal; confirmed | Visa Table7-9 различает crypto/NFT операции по природе/use case | Visa §7.4.14.1, edition 18.04.2026 | S001: Table7-9, с.563–565 | Нельзя копировать MC-кодировку в Visa; NFT-as-ticket требует квалификации конкретного случая |
| P03-C071 | 3.6; legal; open | Полный текущий Visa High-Integrity Risk список подтвержден этой главой | Отдельный VIRP guide недоступен | S001: §10.4.5, с.635–636 context | Полнота не установлена; закрытый список не выдуман |
| P03-C072 | 3.6; hypothesis; working_hypothesis | Прямая продажа stablecoin и оплата товара через отдельного off-ramp могут иметь разные договорные роли | Синтетические модели; конкретного provider approval нет | S001/S005 context; редакторский вывод | Различие требует исследования; готовый законный маршрут не заявлен |
| P03-C073 | 3.2,3.3; experience; confirmed | u/gbcox опубликовал рассказ о нежелательном DCC в Бразилии | Исходный Reddit post; дата unknown, label «2y ago» | S047: initial post | Подтвержден факт рассказа; 12%, обстоятельства и outcome независимо не проверены |
| P03-C074 | 3.2,3.3; experience; open | DCC в описанном ресторане юридически признано мошенничеством | Результат банковской жалобы не установлен | S047: initial post, не доказательство исхода | Нужны первичный чек, записи и решение; оценка автора не принята |
| P03-C075 | 3.3; legal; confirmed | Mastercard DCC guide требует выбора без навязывания DCC по умолчанию | Merchant Version2025, experience guidance | S046: с.31–32 | Не устанавливает нарушение из Reddit; региональные thresholds не использованы |

## Авторские расчеты и логические выводы

Входы этих примеров заданы в главе. Проверка состоит в сохранении денег и смысле состояния, а не в поиске рыночной статистики.

| Пример / module_ids | Проверка | Предел |
|---|---|---|
| Visa payout, 3.2 | 102 USD funding = 100 USD payout + 2 USD fee | Не подтверждает допустимость funding или eligibility получателя |
| Fee layers, 3.2 | 100−1.50−0.20−0.40=97.90; reserve 1 → 96.90 сегодня | Reserve отделен от расхода; освобождение определяется договором |
| Реальная Visa-строка на учебных 100 USD, 3.2 | 100×1.65%+0.15=1.80; 100×0.05%+0.21=0.26 (+0.01) | Только выбранные US qualified categories |
| VAMP, 3.2 | 1600/100000×10000=160 bps | Для статуса нужны counts, exclusions, portfolio и geography |
| Duplicate single-message, 3.3 | 12+12=24 USD требований | Условная модель сбоя, не обещание одинакового поведения каждого API |
| MC payout, 3.3 | 80+0.50=80.50 USD outflow | Обязательство 80 закрывается при подтвержденной доставке |
| FX refund, 3.3 | 100 EUR×1.10=110 USD; ×1.08=108 USD; разница 2 USD | Компенсация определяется issuer terms и применимым правилом |
| Canada Core table, 3.3 | 100 CAD×(1.96%−1.67%)=0.29 CAD | Иллюстрация прочитанной edition, не универсальный тариф |
| ECP, 3.3 | 100/10000×10000=100 bps | Знаменатель текущего месяца 5000 дал бы 200 bps другой метрики |
| Co-badging, 3.4 | (0.22−0.08)×10000=1400 EUR | Арифметика не создает routing rights или token eligibility |
| Subscription, 3.5 | 3×20=60 EUR; отмена перед третьим месяцем → 40 EUR | Договорные предпосылки заданы явно |
| Задача2 | 2.90+0.40+0.30=3.60; 200−3.60−4=192.40; сумма=200 | Все ставки синтетические |
| Задача4 | 150×1.08×1.015=164.43; 168−164.43=3.57 USD | Реальный будущий курс и fees не предсказаны |
| Задача5 | 160/20000×10000=80 bps; 160/25000×10000=64 bps | ECM status из одной дроби не следует |

## Конфликты и редакторские решения

1. **GMAP:** старые и вторичные описания запуска против SPME04.08.2026 §8.2. Решение: утверждать suspension в прочитанной edition; дата возобновления open. Количество перепечаток не меняет доказательство.
2. **Recurring receipt:** широко повторяемая безусловная обязанность против измененного FAQ2022. Решение: обозначить best practice и исключение для определенной группы; FAQ не объявлять полным текущим mandate.
3. **RTS metadata:** BOE Analysis entry 14/11/2018 против публикации 13/03/2018 и operative article38 next day. Решение: использовать 14.03.2018 для вступления в силу, 14.09.2019 для общего применения; ошибку метаданных показать явно.
4. **EMV latest:** новое metadata TF2.4 не делает старый guide актуальной полной specification. Решение: объяснять роли по прочитанному v2.2.1, новые технические требования оставить open.
5. **Социальный кейс:** утверждение DCC=scam против официальных условий добровольной DCC. Решение: сохранить рассказ со слов автора; универсальное обвинение и исход без доказательств не устанавливать.
6. **Разные бренды:** отсутствие полных API/operating guides не превращено в отсутствие функций. Пробел обозначен как «не проверено»; текущие географические доли не выдуманы.
