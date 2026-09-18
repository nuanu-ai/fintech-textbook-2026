---
title: "FinTech 2026 — карта знаний и платежная специализация · v02"
date: "2026-09-15"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Публичная редакция от 18.09.2026. Даты проверки и ограничения источников сохранены. Хеши в исторических аудитах относятся к исходной рукописи; публичные изменения и текущие хеши — в [паспорте издания](edition.md).

> Историческое оглавление от15.09.2026. Упоминания ненаписанных глав описывают состояние на ту дату; текущие10частей и итоговый аудит доступны из оглавления базы.

# FinTech 2026 — карта знаний и платежная специализация · v02

**Дата:** 15.09.2026. **Видимость:** private. **Статус:** рабочая редакционная структура; наполнение глав еще не выполнено.

**Назначение:** база для самостоятельного обучения людей и агентов: объяснения, проверяемые источники, примеры, задачи и отдельные PDF-главы. Общий обзор финтеха + глубокий блок платежей, счетов, stablecoins и agentic commerce — рекомендуемый охват; это не утверждение нового продуктового направления Lab.

**Основа:** v01.1 (10 частей, 58 модулей), сохранена без изменений. Проведены три независимых review: предметное покрытие, обучение и источники. Итог и основания правок — STRUCTURE_REVIEW (исторический или служебный материал; сохранен у владельца, вне этой копии).

**Что изменилось:** добавлены основы денег/учета, обзор остальных областей финтеха, issuing, подробный ledger и надежность; раскрыты bank rails/open banking, сквозные кейсы и схема источников. Номера существующих модулей сохранены. Порядок глав для чтения выделен отдельно от тематических ID.

**Рабочая граница:** карта позволяет начать сбор источников; не означает, что все 2026-правила и продукты уже проверены. Это исторический план от 15.09.2026; состояние публичного издания описано в паспорте.

---

## Как читать эту структуру

| Слой | Что это |
|---|---|
| **Часть** | Большой блок картины мира (0–9) |
| **Модуль** | Учебный вопрос со своими prerequisites и результатом; несколько модулей могут образовать одну PDF-главу |
| **Подтема** | Атом: один вопрос / один механизм / один риск |
| **Глубина** | Критерий «достаточно глубоко» для модуля |
| **→ датасет** | Типы артефактов в корпус источников (не URL-dump) |

**Статусы наполнения:** `outline_only` · `sources_in_progress` · `sources_ready` · `draft` · `reviewed` · `pdf_verified`. Статус относится к конкретному модулю/версии; готовность учебной главы не меняет канон решений Lab.

**Правило учебной базы:** сначала объясняем механизм и его границы, затем применяем к задаче. Lab-кейсы вынесены в прикладной слой; общая теория не должна доказывать заранее выбранный продукт. Географии и бренды — датированные примеры. Один механизм имеет основной модуль; остальные главы ссылаются на него.

---

## Часть 0. Карта курса и метод

### 0.1 Как работать с этим учебником
- Картина мира vs портфель продуктов (обязательное vs опциональное)
- Граница: теория / working_hypothesis / тикет исполнения
- Стыковка с другими исследованиями через источники; внутреннее решение компании и норма права — разные виды документов. Внутреннее одобрение не превращает исследование в закон.

### 0.2 Метод «учебник из ресёрча»
- Первичка vs вторичка vs маркетинг вендора
- Claim → evidence → confidence; запрет citation theater
- Для платежных механизмов — схемы денег и ответственности; для методологии и сравнений — подходящая таблица, схема понятий или разбор источника
- «Достаточно глубоко» = роль + деньги + риск + регуляторный рычаг без слайда вендора

**Глубина:** отличить утверждение продукта от нормы права и от рыночной практики.  
**→ датасет:** чеклист источников; шаблон evidence row.

### 0.3 Словарь и единицы
- Money movement vs payment instruction vs settlement vs clearing
- MoR / PayFac / PSP / acquirer / issuer / scheme / processor / gateway / ISO
- Fiat rail / crypto rail / stablecoin / EMT / e-money / CBDC
- Custody / control of funds / AML trigger points
- Dual-message vs single-message; APM; QR как способ предъявления платежных данных, underlying scheme/rail — отдельный вопрос

**Глубина:** термин = определение + «чем не является» + пример card + пример crypto.  
**→ датасет:** glossary seed; запрещённые синонимы-ловушки.

---

### 0.4 Основы денег, банков и финансового риска
- Наличные, резервы центрального банка, банковские депозиты, e-money и stablecoins: чье обязательство получает владелец.
- Активы, обязательства и капитал; баланс банка и баланс клиента на простом примере.
- Кредит, создание депозитов, ликвидность и платежеспособность — учебный минимум.
- Проценты, basis points, FX quote, spread, время и стоимость денег; единицы и округление.
- Кредитный, ликвидностный, рыночный, операционный и правовой риск: где возникают в одном платеже.

**Глубина:** объяснить перевод между двумя банками на балансах; показать, почему остаток клиента и расчетный актив банков — разные записи.  
**→ датасет:** материалы центральных банков о деньгах, BIS/CPMI, открытый вводный курс по финансам.

### 0.5 Учет денег: первый ledger
- Двойная запись, журнал операций и счета; debit/credit зависят от типа счета.
- Учетный остаток, доступный остаток, hold/pending; деньги клиента и доход платформы.
- Покупка, комиссия, payout и refund на синтетических числах; валюты считаются отдельно.
- Внутренний учет, банковская выписка и данные провайдера: сверка, а не выбор удобной версии.

**Глубина:** собрать небольшой журнал и найти несовпадение без потери денег; сложный многовалютный случай — 8.5.  
**→ датасет:** открытые курсы учета, первичные документы ledger/reconciliation-систем с указанием их модели.

### 0.6 Карта финтеха за пределами платежей
- Digital banking / neobanks / BaaS: интерфейс, баланс и regulated principal.
- Lending / BNPL / credit scoring: выдача, обслуживание, просрочка, взыскание; funding и кредитный риск.
- Investing / wealthtech / capital markets: брокер, биржа, custody, clearing; платеж и покупка актива.
- Insurtech: страховой риск, underwriting, дистрибуция, премия и страховая выплата.
- RegTech / SupTech / open finance / финансовые данные: данные, согласие, модели и oversight.
- Финансовая доступность, конкуренция, безопасность и защита клиента как критерии полезности финтеха.

**Глубина:** для каждой области назвать задачу клиента, бизнес-модель, держателя риска и связь с платежами. Это обзорная карта; углубленные тома этих направлений пока не входят в платежную специализацию.  
**→ датасет:** IMF/World Bank/BIS, профильные регуляторы и университетские курсы; эмпирические исследования с методологией.

---

## Часть 1. Legal / регуляторика / лицензии / географии

### 1.1 Логика регулятора (не список аббревиатур)
- Что защищает: клиентские деньги, AML/CFT, потребитель, рынок платежей, стабильность
- Activity-based vs entity-based
- Когда «софт» становится платёжной услугой
- Экстерриториальность и «где происходит услуга»
- B2C vs B2B: где consumer law включается

**Глубина:** для любой схемы — 2–3 регуляторных вопроса (кто хранит деньги / кто клиент / какая гео).  
**→ датасет:** statutes / guidance; матрица activity→лицензия.

### 1.2 Типы лицензий и ролей (карта разрешений)
- Различать лицензию, регистрацию, вид деятельности и коммерческое название: банк / EMI / PI / MSB / VASP / CASP / актуальные категории BI и локальные аналоги. SSP — обозначение бизнес-роли, не универсальная лицензия.
- Действия: accept / hold / transfer / convert / payout / issue
- Аутсорсинг vs агент vs white-label
- Когда партнёр «закрывает» лицензию, а когда ты в периметре

**Глубина:** таблица «действие × лицензия × чей баланс × кто отвечает перед клиентом».  
**→ датасет:** license taxonomy; официальные глоссарии.

### 1.3 Пять учебных моделей организации приема платежей
1. Software connector (не трогаешь деньги)
2. Direct merchant–PSP
3. Platform / PayFac
4. Merchant of Record / reseller
5. Own payment stack / custody

Это рабочая типология, а не исчерпывающая классификация закона: platform не всегда PayFac, MoR не всегда простой reseller, собственная технология не всегда custody. Отдельно проверять продавца, regulated principal, контроль средств и роль в card scheme.

Для каждой: стороны договора, поток денег, поток претензий (refund/chargeback/consumer redress), AML ownership, что нельзя обещать в оффере.

**Глубина:** две диаграммы на модель (contracts + money) + запреты питча.  
**→ датасет:** публичные ToS/Connect/PayFac disclosures как эталоны чтения.

### 1.4 Географии — скрининг (обязательный минимум)
Одинаковый шаблон на каждую гео:
(1) регулятор(ы) (2) activity→permission (3) crypto/stablecoin/CBDC статус (4) card acquiring (5) local fiat payout / APM/QR (6) допустимые партнерские модели и их границы (7) open questions counsel

#### 1.4.1 США
- FinCEN MSB registration; state money transmitter licensing; bank partnership; актуальный federal stablecoin framework — проверка официальных актов и дат, без вывода из названия регистрации
- Карты vs stablecoin vs crypto broker
- Interstate; custodial wallet; consumer protection hooks (federal/state)

#### 1.4.2 EU / EEA
- Payment services framework: различать действующие нормы и реформы PSD3/PSR; фиксировать принятие, вступление в силу, переходные периоды; EMI/PI и SCA
- MiCA: EMT, ART, CASP × платёжное право
- Passporting / host; consumer / distance selling overlays

#### 1.4.3 UK
- PSRs, EMI, FCA perimeter; post-Brexit отличия

#### 1.4.4 Singapore
- MAS PS Act (majors/standards); DPT / stablecoin; hub/OpCo паттерн

#### 1.4.5 Indonesia
- Актуальная классификация и разрешения BI, граница BI/OJK для активов и услуг; QRIS и локальные APM; foreign PSP constraints; local payout. Исторические сокращения не выдавать за текущую таксономию без проверки.

#### 1.4.6 UAE
- Mainland vs DIFC/ADGM; раздельные области CBUAE / DFSA / FSRA / VARA и исключения; вид деятельности, местонахождение и crypto perimeter проверять по первичным правилам

#### 1.4.7 Расширение (короткие карточки)
- HK, JP, KR, AU, BR, TR, CIS-adjacent — только флаги риска + тип лицензии, без ложной полноты

**→ датасет:** primary acts + FAQ + registers; geo matrix CSV.

### 1.5 AML / KYC / sanctions / travel rule
- CDD / EDD; UBO
- Travel Rule (VASP) × bank rails
- Sanctions на on/off-ramp и address screening limits
- Who screens whom в моделях 1–5
- Monitoring после onboarding: alerts, case management, SAR/STR, recordkeeping, escalation и качество данных; конкретные требования — по юрисдикции

**Глубина:** на crypto→fiat цепочке — точки screening + кто несёт false-negative.  
**→ датасет:** FATF; локальные AML rules выбранных гео.

### 1.6 Данные, PCI, operational resilience
- PCI DSS scope при token / SPT / vault
- GDPR / PDPA и платёжные логи
- Incident / operational resilience (DORA-уровень как ориентир EU)

**Глубина:** показать, как интеграция меняет PCI scope, применимые проверки и оставшиеся обязанности мерчанта; outsourcing не равен исчезновению ответственности.  
**→ датасет:** PCI SSC; privacy guidance for payments.

### 1.7 Связка с учебным проектом: «нет своей лицензии»
- Партнёрский контур vs own stack
- Due diligence партнёра: permissions, geo, assets, dispute ownership
- Миф «лицензия = продукт»; правда: activity + geo + asset + client type

**Глубина:** DD-чеклист партнёра на 1 страницу.  
**→ датасет:** публичные license disclosures; вопросы counsel (не ответы).

### 1.8 Анатомия договоров (MSA / acquiring / processing / sponsorship)
- Стороны и иерархия: scheme membership ↔ sponsor bank ↔ acquirer/PSP ↔ sub-merchant ↔ buyer
- Типовые пакеты: MSA, acquiring agreement, payment processing terms, BIN sponsorship, ISA/ISO, marketplace addendum, MoR supply terms
- Ключевые клаузы: settlement timing, reserve, chargeback liability, termination for risk, data use, audit, indemnity, flow-down of scheme rules
- «Кто подписывает что» в моделях 1–5
- Что читают инженеры vs что читает counsel (и где команда ошибается)

**Глубина:** для модели PayFac и MoR нарисовать договорное дерево + 5 клаузул, без которых пилот нельзя обещать.  
**→ датасет:** публичные шаблоны/ToS крупных PSP (как учебный разбор); redacted clause maps.

### 1.9 Consumer redress / distance selling / digital goods
- Chargeback (scheme) ≠ statutory withdrawal / refund right (law)
- EU consumer / distance / digital content overlays (ориентир; не EU-only мышление)
- Digital goods: delivery proof, access revocation, partial performance
- Crypto/stablecoin checkout: где consumer law «не клеится» к finality
- Complaint handling / ADR как ops, не как PR

**Глубина:** таблица «тип претензии → основание (scheme/law/policy) → кто платит → срок».  
**→ датасет:** consumer regs выбранных гео; scheme vs statute comparison notes.

---

## Часть 2. Как устроены транзакции сегодня (fiat / card / bank / APM)

### 2.1 Участники и роли
- Issuer, acquirer, merchant, cardholder, scheme, processor, gateway, ISO
- Sponsor bank / BIN sponsor
- Clearing vs settlement vs funding

**Глубина:** E2E покупка — кто на hop видит деньги / данные / риск.

### 2.2 Authorization → clearing → settlement
- Auth request/response; soft vs hard decline
- Capture / void / partial capture / incremental auth
- Batch clearing; net settlement; cut-off; float; FX на settlement
- Prefund vs postfund (где встречается)

**Глубина:** таймлайн одной tx с T+ и кто кому должен.

### 2.3 Банковские платежи, instant payments и open banking
#### 2.3.1 Базовая механика
- Credit transfer vs direct debit: кто инициирует, mandate/consent, returns и recalls.
- RTGS vs deferred net settlement; расчетный актив, доступ участников, cut-off и ликвидность.
- ACH, SEPA, Faster Payments и локальные instant systems: классы сравнения с региональными исключениями.

#### 2.3.2 Cross-border и сообщения
- Корреспондентские банки, nostro/vostro; цепочка комиссий и FX, pre-funding, доступность коридора.
- SWIFT как сообщения; движение/окончательность денег проверяются отдельно.
- ISO 20022: business message, идентификаторы, remittance information, статус и сопоставление выписки.
- DvP/PvP как способы связать два исполнения; учебный смысл settlement risk.

#### 2.3.3 Open banking / open finance
- Доступ к данным vs initiation платежа; роли account provider, data recipient и initiator.
- Согласие, authentication, authorization, срок и отзыв доступа; API profile и security profile.
- Pay-by-bank UX: redirect, callbacks, pending, возвраты; перевод может существовать и без open banking API.

#### 2.3.4 Instant payments и выбор способа оплаты
- Доступность, скорость, liquidity, confirmation of payee, ошибочный перевод и authorized push payment scams.
- Авторизованный клиентом перевод под влиянием обмана и неавторизованный платеж: разные сценарии; средства защиты зависят от системы.
- Rail selection: полный cost, скорость, риск, ограничения доступа, опыт клиента.

**Глубина:** проследить credit transfer и direct debit, сравнить instant payment с card transaction, объяснить отдельные роли API/сообщения/расчета.  
**→ датасет:** CPMI/PFMI, официальные rulebooks выбранных систем, ISO 20022, Open Banking standards и security profiles.

### 2.4 Эквайринг и ценообразование
- MDR, interchange, scheme fees, acquirer markup
- IC++ vs blended; non-qualified; cross-border; FX markup
- Chargeback fees / fines как P&L

**Глубина:** разобрать «2.9% + $0.30» на составляющие без маркетинга.

### 2.5 Fraud, 3DS, risk engines
- Liability shift; 3DS2; SCA exemptions
- Velocity, device fingerprint, network tokens
- False positive economics; account takeover, scam/APP fraud, mule accounts и merchant fraud — сравнение контроля с 2.3.4
- ML/rules: labels, precision/recall, drift, объяснимость и человеческий разбор; заявления об эффективности проверять по данным

**Глубина:** кто несёт fraud loss до/после 3DS в типовых сценариях.

### 2.6 Refunds, disputes, chargebacks
- Reason codes; representment; arbitration; friendly fraud
- Refund (policy) vs chargeback (scheme) vs statutory redress (1.9)

**Глубина:** state machine спора + кто платит на шаге.

### 2.7 Message-level card tech (как реально «ходит» auth)
#### 2.7.1 Dual-message vs single-message
- Где какой режим; последствия для capture/refund
- Regional / product exceptions (без ложной глобальной симметрии)

#### 2.7.2 ISO 8583 как язык (учебный минимум)
- MTI; bitmap; ключевые поля (PAN/token, amount, MCC, STAN, RRN, auth code)
- DE55 / EMV data where relevant
- Что gateway прячет, а что важно для support/recon

#### 2.7.3 AVS, CVV/CVC, 3DS payload в auth
- Что проверяется на issuer; как влияет на liability
- Network token cryptogram vs PAN+CVV

#### 2.7.4 Response codes и диагностика отказов
- Issuer vs switch vs acquirer decline
- Soft decline → retry / SCA step-up
- Как читать отказ без «банк просто не любит»

#### 2.7.5 Clearing presentment / presentment files (обзор)
- Что уходит в clearing после capture
- Partial / multiple presentment pitfalls

**Глубина:** по одному живому decline и одному capture команда объясняет поля/роли без вендорского дашборда.  
**→ датасет:** ISO 8583 primers; scheme tech overviews (public); acquirer response-code guides.

### 2.8 APM, device wallets, QR, BNPL
#### 2.8.1 Device wallets
- Apple Pay / Google Pay: конкретный режим и источник credentials; network/device token, PAN и cryptogram не считать одинаковыми во всех интеграциях; merchant decryption vs host
- Как это меняет PCI и 3DS

#### 2.8.2 Account / bank APM
- iDEAL-like, Sofort-like, pay-by-bank — классы, не каталог брендов
- Redirect vs embedded; return URL hell; reconciliation

#### 2.8.3 QR и локальные rails (особенно SEA)
- Consumer-presented vs merchant-presented QR
- QRIS-класс (ID) и аналоги: кто оператор, кто acquirer, settlement в local fiat
- Почему foreign PSP часто упирается в локального партнёра

#### 2.8.4 BNPL как кредитный продукт в checkout
- Кто кредитует; кто MoR; chargeback/refund oddities
- Funding, underwriting, repayment, просрочка и защита заемщика; delayed capture карты не является кредитной моделью BNPL
- Доступность комбинации BNPL/crypto-in проверять у конкретного провайдера

#### 2.8.5 Карта выбора rail для мерчанта
- Ticket size, geo, dispute need, agent-compatibility, cost

**Глубина:** для ID/SEA и EU уметь выбрать rail и назвать dispute gap vs cards.  
**→ датасет:** national QR scheme docs; APM provider primary docs (marketing_risk tag); device wallet merchant guides.

**→ датасет частей 2.1–2.6:** scheme regs excerpts; NPSO docs; interchange tables; EMVCo 3DS; chargeback guides.

---

## Часть 3. Visa, Mastercard и нюансы схем

### 3.1 Scheme как институт
- Rules vs local law
- Membership: issue / acquire rights
- Brand vs network vs processor
- Почему «подключиться к Visa» ≠ «стать Visa»

**→ датасет:** membership overviews.

### 3.2 Visa — развёртка
#### 3.2.1 Продуктовая карта
- Consumer debit/credit/prepaid; commercial / fleet / virtual
- Product ID / interchange qualification basics

#### 3.2.2 Сеть и сообщения
- VisaNet обзор; dual-message доминирование и исключения
- Auth → clearing → settlement timing (учебный)

#### 3.2.3 Tokenization
- VTS; PAR; cryptogram; device vs merchant COF tokens
- Guest checkout vs COF

#### 3.2.4 Push / original credit / payout-adjacent
- Visa Direct / OCT-класс: use cases, risk, compliance overlays
- Отличие от ordinary purchase auth

#### 3.2.5 Cross-border, DCC, multicurrency
- Who sets FX; merchant vs cardholder DCC conflict
- Cross-border interchange / scheme fee hooks

#### 3.2.6 Fees и economics (схема)
- Interchange categories (high-level map, не зазубривание всей таблицы)
- Scheme fees / assessments; acquirer pass-through

#### 3.2.7 Disputes flavor (Visa)
- Reason code families; timeframes; compelling evidence patterns
- Collaboration / pre-dispute tools; Verifi / Order Insight как конкретный пример экосистемы Visa, с отдельной проверкой supported schemes и условий

#### 3.2.8 Compliance / MCC / programs
- MCC risk; registration programs; brand protection

**Глубина 3.2:** команда отличает purchase vs OCT, token vs PAN, и называет 3 рычага стоимости/риска Visa-specific.

### 3.3 Mastercard — развёртка (без ложной симметрии)
#### 3.3.1 Продуктовая карта
- Debit/credit/prepaid/commercial; региональные бренды где важно

#### 3.3.2 Сообщения и settlement
- Dual vs single-message reality; что меняется для capture/refund
- Clearing/settlement отличия, о которых спотыкаются интеграции

#### 3.3.3 Tokenization
- MDES; отличия от VTS на уровне merchant integration

#### 3.3.4 Push / Mastercard Send / payout-adjacent
- Use cases; compliance; когда это не «просто refund»

#### 3.3.5 Cross-border / FX
- Параллели и отличия от Visa (явно списком, не «аналогично»)

#### 3.3.6 Fees / interchange map (high-level)
- Где qualification ломается; digital goods pitfalls

#### 3.3.7 Disputes flavor (Mastercard)
- Reason families; arbitration path differences worth knowing
- Ethoca / Consumer Clarity-класса tools: владелец, поддерживаемые schemes, интеграция и текущая доступность проверяются отдельно

#### 3.3.8 Compliance / MCC / programs
- High-risk registration; brand rules impacting crypto-adjacent

**Глубина 3.3:** сравнить Visa/MC по одинаковым осям; фиксировать подтвержденные различия и сходства с продуктовым следствием. Квоты на число различий нет; отсутствие публичной спецификации — пробел, не повод придумать отличие.

### 3.4 Смежные схемы
- Amex / Discover / UnionPay / JCB
- Local debit schemes; когда local scheme обязателен
- Co-badging

**Глубина 3.2–3.4:** таблица auth model / token / push / dispute / geo strength.

### 3.5 Network tokens, COF, subscriptions
- COF / MIT / CIT; stored credential framework
- Account updater
- Agentic / delegated auth preview → ч.7
- Recurring + SCA exemptions (где применимо)

### 3.6 MCC, prohibited, high-risk
- Кто назначает MCC; mismatch risk
- Crypto, adult, gaming, digital goods
- Scheme vs acquirer vs sponsor policy blocks
- Registration programs

**Глубина:** digital goods + crypto-adjacent — где именно стоп.  
**→ датасет ч.3:** operating regs public excerpts; product rules; token docs; MCC/prohibited lists; chargeback guides.

---

## Часть 4. PSP, платформы, PayFac, MoR

### 4.1 Классификация провайдеров
- Gateway-only vs full-stack PSP
- PayFac; marketplace/platform; MoR/SoR
- Orchestration / smart routing layers

**Глубина:** кто MoR для scheme и кто для покупателя.

### 4.2 Underwriting и onboarding
- KYB / UBO; rolling reserve; delayed payout
- Matching MCC / URL / product / geo

### 4.3 Settlement к мерчанту
- Gross vs net; schedules; split; failed payout / return

### 4.4 Экономика PSP
- Take rate stack; IC++ pass-through
- Loss rates (fraud + CB + credit)
- Low-ticket digital traps; APM mix effects

**Глубина:** all-in cost card / A2A / QR / crypto-ramp на одном чеке.

### 4.5 Связка с учебным проектом: ordinary PSP + crypto acceptance
- Матрица проверенных возможностей конкретного PSP: fiat, crypto-in, delegation, settlement, eligibility и географии
- Connector vs SSP/VASP-партнёр vs MoR
- Оффер: «принимаем USDT» ≠ «мы VASP везде»
- Decision tree crypto-in/fiat-out → модели 1–5

### 4.6 Sponsorship и bank partnership economics
- Issuing BIN sponsorship, acquiring/PayFac sponsorship и BaaS bank partnership: отдельные роли и договоры; общий термин sponsor не делает их взаимозаменяемыми
- Scheme access и settlement bank; распределение контроля, а не универсальный «compliance umbrella»
- Кто underwrites sub-merchants в acquiring; кто отвечает за cardholders/program в issuing (см. 5.5)
- Economics: sponsor fee, residuals, reserve, termination risk
- Концентрация риска: один sponsor выключил — умер объём
- Отличие bank partnership (US-паттерн) от EU EMI/PI passporting
- Due diligence: audit rights, flow-down, notification of scheme programs

**Глубина:** объяснить P&L и kill-switch зависимость от sponsor на пальцах.  
**→ датасет:** публичные sponsor/PayFac disclosures; partnership program overviews.

---

## Часть 5. Wallets, accounts, money storage

### 5.1 Типы кошельков и счетов
- Bank / e-money / payment account
- Custodial crypto / non-custodial / smart account
- Closed-loop vs open-loop; stored value / gift / payroll

### 5.2 Контроль ключей и остатка
- Custody spectrum; MPC / MPC-aaS
- «Not your keys» vs regulator view
- Safeguarding / bankruptcy remoteness (EMI)

### 5.3 On-ramp / off-ramp
- Card→crypto; bank→crypto; crypto→bank/fiat
- Liquidity, spread, Travel Rule на ramp
- Stablecoin как unit vs speculative asset

### 5.4 Refunds и reversibility
- Финальность расчета; card refund/chargeback и bank recall как разные процессы. Требование возврата не означает отмену финальности исходного расчета
- UX-ложь «как карта» на irreversible rail

**Глубина:** wallet-модель → safeguarding / AML / consumer redress. Deposit insurance, safeguarding и insolvency treatment разобрать отдельно; механизм и ограничения — по конкретной юрисдикции.  
**→ датасет:** wallet disclosures; e-money safeguarding rules.

---

### 5.5 Issuing и жизненный цикл карточного продукта
- Issuer, program manager, processor, BIN sponsor и cardholder: роль и ответственность.
- Debit / prepaid / credit, funding source, виртуальная/физическая карта, provisioning и lifecycle credentials.
- Баланс/hold, authorization controls, card freeze, replacement, disputes и закрытие программы.
- Экономика issuing: interchange revenue, processor/sponsor fees, fraud, service cost; связь с acquiring — 2.4.

**Глубина:** нарисовать карточную программу со стороны держателя и эмитента, не подменяя ее схемой приема платежей мерчантом.  
**→ датасет:** scheme issuing docs и публичные cardholder/program agreements.

---

## Часть 6. Crypto rails, stablecoins, CBDC (платёжный угол)

### 6.1 Активы для payments
- Разделить сеть, расчетный актив и единицу учета: Bitcoin/Ethereum — примеры сетей, BTC/ETH/USDT/USDC — примеры активов; актуальные эмитенты/сети проверяются по источнику
- EMT / regulated stablecoin vs unregulated
- Bridged vs native stablecoin risk
- Depeg, freeze, blacklist — ops risk
- Issuer vs distributor vs merchant acceptor roles

### 6.2 On-chain payment mechanics
- Address / memo / invoice; confirmation depth
- Gas, batching, L2; watchers; recon; double-pay
- Reorgs, bridge/sequencer/RPC dependencies; observed/confirmed/finalized и конкретные параметры сети; recovery при неопределенном результате
- Invoice protocols vs «просто адрес»

### 6.3 Stablecoin settlement services
- SSP / treasury partners
- Mint/redeem vs secondary liquidity
- Резерв, право требования и погашения, доступ к redemption, эмитент и custodians; attestation vs audit, disclosure scope и insolvency risk
- Corporate treasury vs consumer checkout

### 6.4 Crypto→fiat для мерчанта (платежный проект)
- Accept → convert → settle fiat
- Клиент: agent / end-user / merchant
- Rate lock timing; spread; refunds after conversion
- Accounting/tax flags (map вопросов, не advice)
- Dispute gaps vs card world

**Глубина:** полная цепочка роли/балансы/AML/refund gap.

### 6.5 Compliance на crypto rails
- VASP/CASP triggers; Travel Rule patterns
- Address sanctions; chain analytics limits

### 6.6 Myths to kill
- «Stablecoin = e-money везде»
- «On-chain receipt = chargeback»
- «Одна лицензия = мир»
- «CBDC = USDT от государства» (см. 6.8)

### 6.7 Treasury / FX / nostro на crypto→fiat ops
- Где сидит liquidity: crypto inventory vs fiat float
- Rate sources; slippage; weekend/gap risk
- Nostro/vostro и settlement banks в off-ramp
- Pre-funding партнёра vs just-in-time convert
- Hedging (только map идей; не trading desk учебник)
- Ops controls: exposure limits, break-glass halt, recon of gas+FX+fee
- P&L stack: network fee + convert spread + payout fee + failure cost

**Глубина:** нарисовать дневной цикл treasury для мерчантского settle без «магии курса».  
**→ датасет:** SSP/treasury partner docs; bank payout SLAs; internal pilot assumptions as secondary.

### 6.8 CBDC — карточка 2026
- Что обещают CBDC (retail vs wholesale)
- Чем CBDC не является: не stablecoin рынка, не «крипта свободна», не универсальный API
- Статус: пилоты / live / none — по гео из 1.4 (без фейковой глобальной карты)
- Платежный угол: merchant acceptance, offline, privacy, intermediary role
- Влияние на PSP/agentic: пока гипотезы, не продукт-roadmap Lab

**Глубина:** объяснить отличия CBDC / EMT / bank deposit / cash на одной схеме.  
**→ датасет:** central bank papers выбранных гео; BIS overviews; tag `status=pilot|live|research`.

**→ датасет 6.1–6.6:** MiCA EMT; MAS stablecoin; vendor settlement docs; публичные первоисточники и авторские учебные примеры.

---

## Часть 7. Agentic / machine payments и протоколы

### 7.1 Почему агенты ломают checkout
- API-only, browser-driven и human-assisted агенты: разные возможности; нельзя считать отсутствие браузера свойством всех агентов
- Делегированное намерение, authentication/3DS, подтверждение человека и недоступный challenge — отдельные вопросы
- Credentials delegation; spend limits
- Principal vs agent confusion (деталь в 7.6)

### 7.2 Карточные ответы рынка
- Shared Payment Tokens / network tokens for agents
- Agentic commerce продукты: announcement / private preview / public preview / GA — дата, гео и eligibility каждого; зрелость продукта и статус стандарта — разные оси
- UCP / ACP и соседи: уровень задачи, publisher/governance, версия, implementation и статус спецификации проверяются по оригиналу

### 7.3 Machine-native protocols
- HTTP 402 / x402: идея, flow, что standardized
- MPP и другие именованные протоколы: расшифровка, издатель, версия и действующий primary URL обязательны; неизвестный статус помечать open
- Agent accounts, micropayments, prepaid credits

**Глубина:** протокол ≠ PSP-продукт ≠ лицензия.

### 7.4 Crypto-native agent pay → merchant fiat
- Stablecoin in → convert → fiat out
- MoR vs direct merchant vs PSP connector
- Catalog/order API ≠ payment rail

### 7.5 Risk & liability
- Unauthorized agent spend; replay; prompt injection → payment instruction
- Who is MoR when agent buys
- Threat model → mapping на модели 1.3

### 7.6 Identity агента vs principal
- Кто subject KYC/KYB: пользователь, агент-оператор, платформа, кошелёк
- Аутентификация агента: keys, attested runtime, OAuth-like delegation — классы механизмов
- Authorization: spend policy, merchant allowlist, velocity, geo, asset allowlist
- Audit trail: кто поручил платёж (human intent evidence)
- Liability allocation: principal / agent vendor / PSP / merchant
- Когда агент = «новый канал fraud», а не «новый UX»
- Связка с Travel Rule / sanctions: whose wallet?

**Глубина:** одна страница RACI на KYC + spend control + dispute для agentic crypto→fiat.  
**→ датасет:** security/delegation notes; scheme agentic pilots; авторские учебные заметки как вторичный материал.

---

## Часть 8. Интеграции, продукт и операционка

### 8.1 Commerce platforms
- WooCommerce REST / Store API: catalog, order, webhooks
- Shopify / custom headless
- Что платформа даёт / не даёт в payments

### 8.2 Connector design
- Idempotency; webhooks; reconciliation keys
- Internal ledger vs PSP statements; базовая модель 0.5, подробный учет 8.5
- Partial failures (paid on-chain, order not created)

### 8.3 Reporting, reconciliation, ops
- Daily settlement files; exception queues
- Support: «деньги ушли, товар не отдали»
- Treasury break-glass (связка 6.7)

### 8.4 Go-to-market claims hygiene
- Claims по моделям 1–5; geo без «worldwide»
- Preview ≠ GA; APM list hygiene

**Глубина:** пилотный чеклист = legal model + rail + geo + claims + kill criteria.

---

### 8.5 Ledger, сверка и финансовые инварианты
- Journal/subledger/general ledger; журнал событий и бухгалтерская запись — разные объекты.
- Pending/posted/available, fees, reserve, refund, chargeback и negative balance; исправление обратной записью.
- Идентификаторы заказа, попытки платежа, settlement и payout; идемпотентность и граница дубликата.
- Трехсторонняя сверка: внутренний ledger, PSP/network, bank/on-chain; несоответствия, aging и close.
- Мультивалютность: amount/currency, decimal precision, FX и отдельный учет комиссии/конверсии.
- Неизвестный результат: query/reconcile, затем решение; не создавать вторую оплату слепым retry.

**Глубина:** пройти один цикл sale → fee → payout → partial refund, затем найти missing/duplicate event. Итоги сходятся с внешним источником; балансировка ledger сама по себе не доказывает деньги в банке.  
**→ датасет:** первичные accounting/reconciliation docs, учебные синтетические выписки и журнал.

### 8.6 Надежность, безопасность и восстановление
- Duplicate/out-of-order webhooks, timeout после отправки, retries, idempotency window, подтверждение результата.
- Authentication вебхука, replay protection, права, секреты и контроль изменений реквизитов.
- Доступность vs сохранность денег; monitoring и алерты на потерю/дублирование исполнения.
- Incident response, recovery, backup/restore, exit plan при потере провайдера; пользовательская поддержка.
- Переход от объявленного успеха к доказательству: ledger + внешний расчет + исполнение заказа.

**Глубина:** разобрать сбой провайдера в середине оплаты с известным и неизвестным результатом; показать безопасное восстановление и связь с 1.6.  
**→ датасет:** API/security specifications, публичные postmortems, regulator resilience guidance.

---

## Часть 9. Сквозная практика и применение к платежному проекту

### 9.1 Сквозная карта «деньги × договор × данные × лицензия»
- Матрица на типовые платежные сценарии (вкл. QR/APM и agentic)

### 9.2 Working hypotheses (не канон)
- Crypto-in / fiat-out слой для ordinary PSP
- Партнёрский rail (классы: Bridge-like SSP, Triple-A-like, Coinbase Business-like, CoinGate-like) — не shortlist без evidence refresh
- Agentic storefront — отдельно от settle-stake

### 9.3 Что НЕ входит в учебник v1
- Trading / DeFi yield / token design
- Полный tax treatise; углубленные lending / capital markets / insurance — пока только обзор 0.6
- POS card-present как ядро курса
- Внутренний HR и бюджетирование организаций; сторонние среды без разрешения владельца

### 9.4 Путь структура → датасет → уроки
1. Source registry + claim/evidence links по схеме источников.
2. Три эталонных модуля: **0.5** (учет), **2.2** (жизненный цикл), **1.3** (модели и ответственность); проверить метод на связанных темах.
3. Следующий сквозной модуль — **6.4**, опирается на кошельки, AML, учет и settlement.
4. Независимое review смысла, источников и учебных задач; затем PDF и визуальная проверка.
5. Расширение по пакетам ниже. Учебный статус reviewed не означает разрешения на реальные операции.

---

### 9.5 Сквозные кейсы и итоговая проверка
- Один заказ в разных механизмах: карта / bank transfer / QR / stablecoin; одинаковые вопросы к деньгам, ответственности и результату.
- Частичный refund после FX, failed payout, duplicate webhook и provider shutdown.
- Agent покупает digital goods: intent → delegation → order → payment → reconciliation → fulfillment; спорный/неизвестный исход.
- Публичный инцидент: хронология, доступные документы, утверждения участников, неизвестные детали; не выводить вину по Reddit/X.
- Применение к учебному проекту — отдельный учебный разбор с working_hypothesis, без переноса на текущий статус проектов.

**Глубина:** решить новый кейс, показать доказательства и назвать вопросы, на которые данных недостаточно.  
**→ датасет:** публичные postmortems/решения/документы и явно синтетические задачи; никаких production credentials или платежей для обучения.

---

## Критерии «достаточно глубоко» (сводка)

| Часть | Достаточно глубоко, если команда умеет… |
|---|---|
| 0 | Объяснить виды денег, простые балансы и двойную запись; ориентироваться в финтехе; проверять источник |
| 1 | Выбрать модель 1–5 + geo flags; назвать ключевые клаузулы и consumer vs scheme redress |
| 2 | Разложить auth–clear–settle; прочитать простой decline на уровне полей; выбрать APM/QR vs card |
| 3 | Объяснить scheme как институт; сравнить подтвержденные сходства/различия Visa/MC; token/push/MCC risk |
| 4 | Собрать all-in cost; сказать кто MoR; объяснить зависимость от BIN sponsor |
| 5 | Классифицировать wallet и защиту средств; объяснить роли и lifecycle issuing |
| 6 | Провести crypto→fiat с AML/refund/treasury; отличить CBDC/EMT/deposit |
| 7 | Отделить протокол/продукт/лицензию; RACI identity агента |
| 8 | Проследить деньги в ledger, сверить внешние данные и восстановить исполнение после сбоя |
| 9 | Решить новый сквозной кейс и отделить подтверждение от неизвестности и гипотез |

**Качество:** определение → механизм → пример → ограничения → проверка понимания. Формулы с единицами и смыслом; название компании с конкретной ролью; спорное утверждение с границами знания. Схема выбирается по задаче, объем и число ссылок сами по себе не критерии глубины.

---

## Датасет и формат базы

Полная схема — [SOURCE_DATASET_SCHEMA.md](source-dataset-schema.md); формат главы — [MODULE_TEMPLATE.md](module-template.md).

- Отдельно: law/regulator, scheme, standard, vendor, research, course, analysis, social (Reddit/X), internal.
- Source ID описывает конкретный источник и версию; Claim ID — проверяемое утверждение со ссылками на точные места.
- Полный текст, abstract, сниппет и заблокированная страница имеют разные access/review status.
- Даты публикации, действия нормы, версии и фактического чтения не заменяют друг друга.
- Reddit/X дают практические кейсы и вопросы; официальные объявления в соцсетях — свидетельство объявления, не независимое доказательство результата.
- PDF — читаемое издание главы; Markdown и реестры сохраняют редактируемость и происхождение материала. Чужие PDF остаются источниками, а не автоматически главами нашей книги.

## Порядок обучения и будущие PDF-пакеты

Номера частей — постоянные тематические адреса. Порядок чтения начинается с денег и механизмов, затем переходит к ролям/праву и специализациям. Ни один PDF пока не создан; названия ниже — план упаковки, объем определяется связностью материала.

| Пакет | Глава | Модули | До чтения |
|---|---|---|---|
| CH-00 | Карта финтеха и работа с источниками | 0.1, 0.2, 0.3, 0.6 | — |
| CH-01 | Деньги, балансы и первый ledger | 0.4, 0.5 | CH-00 |
| CH-02 | Одна покупка от запроса до расчета и возврата | 2.1, 2.2, 2.6 | CH-01 |
| CH-03 | Банковские переводы и open banking | 2.3 | CH-01, CH-02 |
| CH-04 | Wallet checkout, QR и BNPL | 2.8 | CH-02, CH-03 |
| CH-05 | Роли, модели бизнеса, договоры и sponsorship | 1.1, 1.2, 1.3, 1.7, 1.8, 4.1, 4.6 | CH-02, CH-03 |
| CH-06 | Шесть географий: как читать правила | 1.4 | CH-05 |
| CH-07 | AML, данные, безопасность и права клиента | 1.5, 1.6, 1.9 | CH-05, выбранная карточка CH-06 |
| CH-08 | Карточная транзакция: цена, риск, сообщения и токены | 2.4, 2.5, 2.7, 3.1, 3.5 | CH-02, CH-05, CH-07 |
| CH-09 | Visa | 3.2 | CH-08 |
| CH-10 | Mastercard | 3.3 | CH-08 |
| CH-11 | Другие схемы и MCC | 3.4, 3.6 | CH-08; CH-09/10 для сравнений |
| CH-12 | PSP: onboarding, выплаты и экономика | 4.2, 4.3, 4.4, 4.5 | CH-05, CH-07, CH-08; 4.5 повторно после CH-15 |
| CH-13 | Счета, custody, ramps и issuing | 5.1, 5.2, 5.3, 5.5 | CH-01, CH-05, CH-07, CH-08 |
| CH-14 | Crypto rails, stablecoins и возвраты | 5.4, 6.1, 6.2, 6.3, 6.5, 6.6 | CH-03, CH-07, CH-13 |
| CH-15 | Crypto→fiat, treasury и FX | 6.4, 6.7 | CH-12, CH-14 |
| CH-16 | CBDC в сравнении с депозитами и stablecoins | 6.8; сравнительные ссылки на 0.4, 6.1 | CH-01, CH-14 |
| CH-17 | Agentic и machine payments | 7.1–7.6 | CH-05, CH-07, CH-11, CH-15 |
| CH-18 | Интеграция, учет, сверка и восстановление | 8.1–8.6 | CH-01, CH-02, CH-05, CH-07, CH-12; crypto-примеры после CH-14/15 |
| CH-19 | Сквозные кейсы и применение к платежному проекту | 9.1–9.5 | выбранные рельсы + CH-18; agent-кейс после CH-17 |

Маршрут знакомства: CH-00 → CH-01 → CH-02 → CH-03 → CH-05 → одна карточка CH-06 → CH-07. Затем специализации по интересу. Географии — отдельные сравнительные карточки внутри CH-06; первые шесть сохраняются, дополнительные не назначаются автоматически.

Вводные определения SCA/3DS в ранних главах даются на месте; глубокая техника — CH-08. Ранний 4.5 — только карта ролей, детальный разбор crypto→fiat идет после CH-15.

## Порядок наполнения агентами

1. **Ограниченная партия источников:** для 0.4/0.5, 2.2 и 1.3; source registry и список нерешенных вопросов.
2. **Три образца модулей:** 0.5, 2.2, 1.3 по единому шаблону. Для каждого — исследователь/автор и другой агент-рецензент; ведущий редактор согласует термины между модулями.
3. **Проверка обучения и PDF:** новая задача с ответом, проверяемые ссылки и просмотр отрендеренных страниц. После этого 6.4 как тест сквозной связности.
4. **Наполнение пакетами:** основы; rails/cards; модели/географии/compliance; accounts/crypto/treasury; agentic; ops/cases. Обнаруженные prerequisites закрываются раньше зависимого текста.
5. **Индекс версий:** у каждого пакета дата, статус, ссылка на PDF/исходник, пробелы и причины следующего обновления. Не смешивать sources_ready и готовую главу.

Количество страниц и ссылок не назначаем до трех образцов. Структура описывает содержание; результат текущего этапа — review и подготовленный каркас, а не законченный учебник.

## Рабочие допущения

- Рекомендуемый охват: обзор всего финтеха и глубокая платежная специализация. Полные тома lending/investing/insurance потребуют отдельного расширения оглавления.
- Географии: сохранить US/EU/UK/SG/ID/UAE; для первой практической главы выбирать одну конкретную географию и activity, не писать универсальный юридический вывод.
- CBDC остается коротким сравнительным модулем; ISO 8583 — углубленная ветка после lifecycle, не вход в курс.
- Предыдущие внутренние исследования использовать через evidence rows и внешнюю первичку, не импортировать непроверенный текст целиком.

## Материалы review

- Итоговый разбор (исторический или служебный материал; сохранен у владельца, вне этой копии).
- Предметная проверка (исторический или служебный материал; сохранен у владельца, вне этой копии).
- Проверка обучения (исторический или служебный материал; сохранен у владельца, вне этой копии).
- Источники и проверенные входы (исторический или служебный материал; сохранен у владельца, вне этой копии).
- v01.1 (исторический или служебный материал; сохранен у владельца, вне этой копии) и v01 (исторический или служебный материал; сохранен у владельца, вне этой копии) — сохраненные версии.
