---
title: "Реестр утверждений части 1"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Публичная редакция от 18.09.2026. Даты проверки и ограничения источников сохранены. Хеши в исторических аудитах относятся к исходной рукописи; публичные изменения и текущие хеши — в [паспорте издания](../../edition.md).

# Реестр утверждений части 1

15.09.2026 · private · `independently_reviewed_draft`.

Фактчек исходной редакции завершен17.09.2026. Связь исходной версии с публичной копией, область адаптации и текущая навигация описаны в паспорте издания.

Общие поля: `as_of=2026-09-15`; `last_checked_at=2026-09-15 Asia/Makassar`; все evidence относятся к `snapshot_id=<source_id>-20260915`; relation `supports`, если не отмечено иначе. `reviewer=see_REVIEW.md`, `review_status=see_REVIEW.md`; автор не присваивает себе независимое одобрение. `effective_to=unknown`; review trigger — новая редакция акта, договора, supervisory statement или новая фактическая модель. `confirmed` означает подтвержденный **ограниченный тезис**, а не одобрение деятельности и не полноту географии. Условия, правовая сила и неполный доступ отражены в каждой строке и [SOURCES](sources.md).

## Датированные findings для межглавной проверки

| claim_id / modules | Тезис | Kind / status | Условия и effective_from | Evidence + locator | Reasoning / confidence / conflicts |
|---|---|---|---|---|---|
| P01-C001 /1.4,1.6 | FCA Supplementary Safeguarding Regime применяется с 07.05.2026 | legal / confirmed | UK in-scope payment/e-money firms; исключения и SPI opt-in в S009 | P01-S009, heading Who this applies to / What we are changing / Next steps; P01-S056,CASS15.2.1R, context | Прочитан PS25/12; это действующий supplementary этап. Future end-state отдельно зависит от законодательства. Нельзя использовать прежний safeguarding FAQ как доказательство отсутствия новых правил |
| P01-C002 /1.4 | Максимальный MiCA CASP grandfathering в ЕС завершился 01.07.2026 | legal / confirmed | Законно работавшие до 30.12.2024 incumbents; в государствах могли быть более ранние сроки | P01-S006, PDFp1 first two paragraphs and bullets | ESMA прямо называет максимальную дату; на срез переход уже завершен. Не превращать это в утверждение, что каждая фирма получила разрешение |
| P01-C003 /1.2,1.4 | MiCA authorization принадлежит конкретному legal entity, а не всем компаниям группы | legal / confirmed | CASP authorization/notification scope | P01-S006, pp2–3 paragraph on group structures | Прочитано напрямую; foreign sister company не становится авторизованной через общий бренд |
| P01-C004 /1.4 | PBI10/2025 и PADG32/2025 вступили в силу 31.03.2026 | legal / confirmed | Indonesia payment-system industry | P01-S013 official Ringkasan, issue/effective fields; P01-S014 issue/effective fields | Подтверждено официальными BI страницами; прежняя классификация сама по себе недостаточна для текущей карты |
| P01-C005 /1.2,1.4 | Новая карта BI содержит PJP permission, PIP designation, activity bundles и PSP Utama по TIKMI | legal / confirmed within official summary | Indonesia;initial PSP/TIKMI classification ≤1 year after 31.03.2026 | P01-S013,Ringkasan2.7,2.10–2.12; status transition paragraphs | PJP/PIP термины не исчезли; изменена окружающая система. Нельзя объявить все фирмы окончательно переклассифицированными 15.09.2026. Точные pasal акта не проверены полностью |
| P01-C006 /1.4 | OJK описывает передачу надзора над crypto/digital financial assets 10.01.2025 и завершение переходного сотрудничества в январе 2026 как разные события | legal / confirmed as regulator-reported chronology | Indonesia assets vs money/FX derivatives | P01-S015, main transfer statement (partial index/context); P01-S058,SP13/GKPB/OJK/I/2026 main text (direct) | S058 прямой официальный follow-up; ending MoU 20.01.2026 не новый handover date. POJK27/2024 отдельно не прочитан полностью |
| P01-C007 /1.4 | GENIUS стал Public Law119-27 18.07.2025 | legal / confirmed | US payment stablecoin definition §2 | P01-S003, approval footer and §§1–2 | Прямой statutory text, не pending bill |
| P01-C008 /1.4 | Общий effective date GENIUS — раньше 18 месяцев после enactment или 120 дней после указанного final implementing regulation | legal / confirmed | §20; календарный outer date 18.01.2027 | P01-S003,§20 | Условие прочитано напрямую; фактическое срабатывание второго условия на срез не установлено. Нельзя писать «уже весь действует» или «точно только 2027» |
| P01-C009 /1.4 | Фактическая общая дата применения GENIUS к 15.09.2026 полностью сверена | legal / open | Требуется реестр final rules всех primary federal regulators | P01-S003,§20; P01-S004,context proposed 25.02.2026 | Найденный OCC NPRM не запускает final-rule trigger и не доказывает отсутствие других final rules |
| P01-C010 /1.4 | §3(b)(1) GENIUS имеет отдельный срок 3 года после enactment | legal / confirmed | Specified service-provider offering/sale restriction;18.07.2028 | P01-S003,§3(b)(1) | Не переносить общую дату§20 на каждый transitional provision |
| P01-C011 /1.4 | PSD3/PSR нельзя преподавать как применимые нормы только на основании political agreement | legal / confirmed | EU legislative process; дата применения реформы open | P01-S007,Next steps; P01-S057,rows 5–6 COREPER confirmation 22.04.2026 context | Есть progress 2026 после news 2025; OJ final act и application date этим не подтверждены. Глава не утверждает, что статус замер в 2025 |
| P01-C012 /1.4 | BoE/FCA joint paper 30.06.2026 — консультация, хотя ссылается на FCA PS26/10 | legal / confirmed | Systemic stablecoin issuers UK; consult to  30.09.2026 | P01-S010,intro/status and PS26/10 passage | Само упоминание другого final PS не финализирует BoE proposals. Содержание PS26/10 уточнено самостоятельным чтением S062 / C051 |
| P01-C013 /1.1,1.4 | MAS expansion охватывает названные DPT custody/facilitation и некоторые cross-border services без possession | legal / confirmed | SG specified services, from 04.04.2024 | P01-S011,p1 para2 | Прямая официальная 2-page release; отсутствие possession не универсальное исключение |
| P01-C014 /1.4 | Overseas-only DTSP regime применяется с 30.06.2025 к указанным лицам/услугам | legal / confirmed | SG covered DTSPs servicing only overseas DPT/capital-market-product token clients | P01-S012,p1–2 Scope of New Regulation | MAS generally will not issue such licences/high bar; не общий запрет всех software exporters |
| P01-C015 /1.4 | MAS stablecoin framework announcement 2023 доказывает operative law 2026 | legal / rejected | Legislative implementation matters | P01-S011/S012 context; недоступная MAS consultation 01.09.2026 в SOURCES gaps | Сам по себе framework announcement не enacted amendments; точный latest status оставлен open |
| P01-C016 /1.4 | DFSA updated Crypto Token framework effective 12.01.2026 | legal / confirmed as regulator statement | In/from DIFC financial services; suitable crypto excludes separate fiat-token treatment | P01-S019,Latest regulatory update and Suitable Crypto Tokens | Прямая страница регулятора; не UAE-wide permission и не подтверждение individual licence |
| P01-C017 /1.4 | FSRA FRT amendments effective 01.01.2026 | legal / confirmed as regulator statement | ADGM regulated activities/client FRTs | P01-S020,paragraphs 3–4; finalised 31.10.2025 | Финальный статус и дата прямо заявлены; детали каждой измененной rule не проверены |
| P01-C018 /1.5 | FATF current Recommendations version amended June 2026; standard требует местной имплементации | definition / confirmed | Global standards, local legal scope separate | P01-S021,landing Publication details and intro; PDF Recommendations10–11,20–21 | Не «единый мировой AML закон»; конкретные country thresholds не выводим автоматически |
| P01-C019 /1.5 | R16 guidance consultation 2026 не делает новый стандарт одинаково обязательным всем PSP уже 2026 | legal / confirmed | International implementation vs national rules | P01-S023,paragraphs on June 2025 revision and end 2030 implementation | Consultation/comments deadline 21.08.2026, не дата вступления national Travel Rule |

## Механизмы, договоры и redress

| claim_id / modules | Ограниченный тезис | Kind / status | Evidence + locator | Применимость и объяснение |
|---|---|---|---|---|
| P01-C020 /1.1–1.3 | Отсутствие custody само по себе не исключает регулируемую услугу | legal / confirmed in examples | P01-S001, art.3(j), annex I; P01-S011, p1 para2 | EU PIS/AIS и SG facilitation — примеры, не универсальная квалификация |
| P01-C021 /1.2 | Регистрация MSB в FinCEN не является лицензией на работу в США и не заменяет применимые разрешения штатов | definition / confirmed | P01-S064, p6, Guidance on Avoiding MSB Registration Scams | США; разъяснение18.12.2024. Это не проверка всех режимов штатов и исключений. Исправлено17.09.2026: S002 относится к классификации ISO/processor, а не к этому тезису |
| P01-C022 /1.3 | Пять учебных моделей могут сочетаться; own stack не всегда custody | mechanism / confirmed as taxonomy | P01-S001 и P01-S011 context; авторские схемы | Классификация автора, не официальный список лицензий |
| P01-C023 /1.3,1.8 | Stripe allocation зависит от account/charge/loss settings | product / confirmed | P01-S032, Marketplace liability / Negative balance responsibility; P01-S031, §§1,4–5 | Публичная модель не доказывает индивидуальные negotiated terms |
| P01-C024 /1.3,1.8 | Paddle MSA описывает reseller relationship и централизованные refunds | product / confirmed | P01-S033-20260917, §§2.2(ii),9,10.1–10.2; P01-S034, Relationship with Suppliers | Не освобождает supplier автоматически от поддержки, IP, indemnity |
| P01-C025 /1.3 | UK nonbank safeguarding отличается от прямой FSCS protection | legal / confirmed | P01-S055, Safeguarding / FSCS | В insolvency возможны задержки и затраты; банковский look-through отдельно не исследован |
| P01-C026 /1.5 | CDD включает identity, beneficial owner, purpose, ongoing scrutiny | definition / confirmed as standard | P01-S021, R10 pp14–15; INR10 pp66–67 | FATF стандарт реализуется местным правом; не только паспортный виджет |
| P01-C027 /1.5 | SAR/STR основан на подозрении, а не на доказанном преступлении | definition / confirmed as standard | P01-S021, R20–21 p19; INR20 p92 | Конкретная обязанность, FIU, сроки и конфиденциальность — местное право |
| P01-C028 /1.6 | SAQ A embedded-form eligibility сохраняет script-attack условие | definition / confirmed | P01-S026, FAQ1588 | PCI DSS4.0.1, SAQ A r1, February 2025; redirect и остальные критерии проверяются отдельно |
| P01-C029 /1.6 | GDPR требует основания для конкретной цели обработки | legal / confirmed within guidance | P01-S059, Possible legal bases; P01-S028 context | Не разрешает любые fraud/marketing uses; точный PSD2-consent анализ здесь не заявлен |
| P01-C030 /1.6 | DORA применяется с 17.01.2025 к in-scope financial entities и включает ICT register | legal / confirmed within explanation | P01-S030, main body | Статус vendor не определяет автоматически весь DORA scope |
| P01-C031 /1.7 | Аутсорсинг не устраняет ответственность банка; DD соразмерен риску | mechanism / confirmed as guidance | P01-S035, Overview и III.B Due diligence | US interagency guidance 06.06.2023; чеклист автора — учебная адаптация |
| P01-C032 /1.9 | Statutory remedy, card chargeback и voluntary refund имеют разные основания | mechanism / confirmed | P01-S061,(a)–(c); P01-S037,withdrawal; P01-S038,arts13–18 | Несколько оснований не означают двойное возмещение одного ущерба |
| P01-C033 /1.9 | Directive 2019/770 различает non-supply и non-conformity remedies | legal / confirmed | P01-S038,arts5–9,13–18,22,24 | EU covered B2C digital content/services; национальные меры с 01.01.2022; не автоматический refund при любом недовольстве |
| P01-C034 /1.9 | Sanadak current portal использует 15 calendar-day этап внутренней жалобы | legal / confirmed as portal instruction | P01-S042,complaint eligibility | UAE eligible LFI complaints; дата исторического изменения unknown |
| P01-C035 /1.3,1.9 | Onchain finality не доказывает поставку или прекращение договорного требования | mechanism / confirmed as synthesis | P01-S038,arts5,13–18 context; авторская модель | Техническая необратимость записи не исключает новый refund transfer; право зависит от scope |
| P01-C036 /1.5 | EU TFR 2023/1113 применяется с 30.12.2024 | legal / confirmed | P01-S025,BOE Analysis, art40 | Act entry 29.06.2023 и application различаются |
| P01-C037 /1.5 | TFR данные передаются безопасно до/вместе с переводом, необязательно onchain | legal / confirmed | P01-S025,art14(4) | Охватываемые crypto transfers; не лицензия раскрывать PII публично |
| P01-C038 /1.5 | Self-hosted threshold свыше 1000 EUR относится к дополнительной оценке контроля | legal / confirmed | P01-S025,arts14(5),16(2) | Не общее освобождение меньших переводов от информации/проверок |
| P01-C039 /1.6 | TFR ограничивает цели обработки и регулирует retention | legal / confirmed | P01-S025,arts25–26 | Запрет commercial processing на этом основании; сроки/национальное продление по условиям |
| P01-C040 /1.5 | BI PADG15/2025 действует с 30.06.2025 для описанного nonbank scope | legal / confirmed via summary | P01-S060,RingkasanII.1–5 | Written policies, risk, CDD, data/reporting; не автоматический перенос FATF thresholds |
| P01-C041 /1.9 | Reg E§1005.11 имеет 10-business-day базу и условные продления/исключения | legal / confirmed | P01-S061,(a),(b),(c)(1)–(3) | Covered error notice;20 businessdays/45/90days и provisional credit зависят от условий |
| P01-C042 /1.4 | QRIS cross-border — согласованная схема с participating PSP | mechanism / confirmed as BI explanation | P01-S016,QRIS Cross-Border, merchant reconfirmation | Индексированный substantive text; не подтверждение подключения конкретного merchant |
| P01-C043 /1.4.7 | HK issuer-regime commencement 01.08.2025 | legal / confirmed as announcement | P01-S043,whole short release | Ограниченный флаг, не весь SFC/PSP режим |
| P01-C044 /1.4.7 | Japan FSA intermediary regime начал действовать 01.06.2026 | legal / confirmed as guidance | P01-S044,introduction and two listed services | Listed brokerage only for principal по поручению; не custody permission |
| P01-C045 /1.4.7 | Korea User Protection Act применяется с 19.07.2024 отдельно от AML registration | legal / confirmed as announcement | P01-S045,Background/Key provisions | Полный актуальный корейский кодекс не проверен |
| P01-C046 /1.4.7 | AUSTRAC описывает conditional transition новых VASP services в 2026 | legal / confirmed as guidance | P01-S046,Newly regulated, updated 30.07.2026 | Для заявки до 29.07.2026; не общий бессрочный waiver |
| P01-C047 /1.4.7 | BCB520 содержит разные application dates | legal / working_hypothesis bounded | P01-S047,arts91–92 через search_index | Общая 02.02.2026 и отдельная 30.10.2026; direct text и amendments требуют проверки перед использованием |
| P01-C048 /1.4.7 | CMBIII-35/B.1 охватывает establishment/operation crypto providers | legal / working_hypothesis bounded | P01-S048,arts1–2 через search_index | Официальная English translation; operative Turkish text не прочитан полностью |
| P01-C049 /1.4.7 | AFSA DASP permission относится к определенным AIFC activities | definition / confirmed | P01-S049,definition/activities | Не эквивалент общенациональной/региональной лицензии |
| P01-C050 /1.9 | Reg E two-business-day loss/theft rule и 60-day statement rule не взаимозаменяемы | legal / confirmed | P01-S036, §1005.6(b)(1)–(3); P01-S061, §1005.11(b)–(c) context | Liability клиента отличается от сроков расследования; конкретная сумма зависит от условий, времени последующих EFT, extensions и более благоприятных правил |

## Границы выпуска

Независимому рецензенту: проверить C001–C017 в первую очередь, особенно actual GENIUS trigger, reform application, BI current taxonomy и границы UK stablecoin consultations. Главу можно проверять по модульным выводам; все обнаруженные gaps сохранены. Полнота российского/казахстанского/турецкого права, CBDC production rollout и contract terms конкретных партнеров не заявляется.

## Дополнение 17.09.2026

| claim_id / modules | Тезис | Kind / status | Scope / as_of | Evidence + locator | Ограничение |
|---|---|---|---|---|---|
| P01-C051 /1.4.3 | FCA PS26/10 содержит final issuance rules с commencement 25.10.2027 | legal / confirmed | Non-systemic UK-issued qualifying stablecoins; as_of2026-09-15; checked2026-09-17 | P01-S062-20260917: Summary, §1.2, Appendix1 Commencement(C), PDF pp.63,98 | Не действующий на срез режим и не завершение BoE systemic consultation; полный Handbook не проверен |
| P01-C052 /1.6 | PDPC выделяет обязанности data intermediary при обработке по письменному договору; передающая обработку организация сохраняет собственные обязанности | legal / confirmed в прочитанной области guidance | Singapore; revision29.04.2026, checked17.09.2026 | P01-S063-20260917-deep: printedpp24–25, Data intermediaries / Obligations / Considerations;§4(3) | Не вся PDPA и не договорная квалификация конкретного бизнеса; гостевая статья S029 больше не служит доказательством |
