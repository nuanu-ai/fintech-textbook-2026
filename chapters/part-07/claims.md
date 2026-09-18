---
title: "Утверждения части 7"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Публичная редакция от 18.09.2026. Даты проверки и ограничения источников сохранены. Хеши в исторических аудитах относятся к исходной рукописи; публичные изменения и текущие хеши — в [паспорте издания](../../edition.md).

# Утверждения части 7

**v0.1 · 15.09.2026 · private · independently_reviewed_draft · independent_review=see_REVIEW.md.**

Фактчек исходной редакции завершен17.09.2026. Связь исходной версии с публичной копией, область адаптации и текущая навигация описаны в паспорте издания.

Общие поля: `as_of=2026-09-15`; `last_checked_at=2026-09-15, Asia/Makassar (UTC+08:00)`; `reviewer=part_07_research`; `review_status=author_checked; independent_scope=see_REVIEW.md`; `effective_from/effective_to=not_applicable` для технических и учебных выводов. Для правовых вопросов здесь не устанавливается вступление конкретной обязанности в силу. `confirmed` означает соответствие прочитанному источнику в указанном scope, а не независимую проверку реализации или юридическое одобрение. Все источники раскрыты в [SOURCES.md](sources.md), где указаны версии, фактический объем чтения и ограничения.

`review_trigger`: новая спецификация/release, изменение product documentation/availability, новое соглашение провайдера, изменение применимого права либо обнаруженное несоответствие первичке. Для учебных controls — изменение исходных предпосылок. В отсутствие отдельного конфликта `conflicts=none_identified_within_reviewed_scope`; это не обещание отсутствия всех внешних противоречий.

## P07-C001

- **module_ids:** 7.1, 7.3; **claim_kind:** definition; **status:** confirmed.
- **claim:** HTTP 402 в RFC 9110 зарезервирован; сам код не задает законченный платежный протокол.
- **jurisdiction / conditions:** HTTP semantics, RFC 9110.
- **evidence / locator / relation / reasoning:**
  - [P07-S001](sources.md#p07-s001) / `P07-S001-20260915`; §15.5.3; `supports`: Нормативное значение кода ограничено reserved for future use.
- **confidence_basis / limitations / resolution:** Параметры конкретной реализации следуют из отдельной спецификации; код не доказывает перевод денег.

## P07-C002

- **module_ids:** 7.1; **claim_kind:** hypothesis; **status:** working_hypothesis.
- **claim:** Quote, согласие principal, rail authorization, settlement и fulfillment следует учитывать отдельными состояниями.
- **jurisdiction / conditions:** Учебная архитектура commerce/payment; последовательность зависит от метода.
- **evidence / locator / relation / reasoning:**
  - [P07-S002](sources.md#p07-s002) / `P07-S002-20260915`; §§6–7 flows; `context`: Различные последовательности обработки x402.
  - [P07-S014](sources.md#p07-s014) / `P07-S014-20260915`; Status Lifecycle Values; `context`: Checkout status отражает собственный lifecycle.
  - [P07-S040](sources.md#p07-s040) / `P07-S040-20260915`; status; `context`: PaymentIntent имеет отдельные платежные состояния.
- **confidence_basis / limitations / resolution:** Это синтез автора, не универсальный нормативный state machine.

## P07-C003

- **module_ids:** 7.2; **claim_kind:** product; **status:** confirmed.
- **claim:** Visa Intelligent Commerce описывает agentic card infrastructure, но открытая overview не устанавливает универсальную production-доступность.
- **jurisdiction / conditions:** Публичная Visa developer overview на дату чтения.
- **evidence / locator / relation / reasoning:**
  - [P07-S026](sources.md#p07-s026) / `P07-S026-20260915`; Disclaimer; How does it work?; Controls; `supports`: Есть оговорка о разработке и изменении доступности.
- **confidence_basis / limitations / resolution:** Нужны eligibility, onboarding и договорные условия конкретной программы; карточная инфраструктура сохраняется.

## P07-C004

- **module_ids:** 7.2, 7.6; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** Visa Trusted Agent Protocol описывает распознавание подписанных agent requests на merchant boundary.
- **jurisdiction / conditions:** Открытая merchant specification Visa TAP; номер версии не установлен.
- **evidence / locator / relation / reasoning:**
  - [P07-S027](sources.md#p07-s027) / `P07-S027-20260915`; Introduction; Participants; Trust Model; Agent Recognition; `supports`: Роли и проверка trusted agent описаны самим владельцем протокола.
- **confidence_basis / limitations / resolution:** Это не самостоятельное доказательство полномочий на любую покупку и не исследование production security.

## P07-C005

- **module_ids:** 7.2; **claim_kind:** product; **status:** confirmed.
- **claim:** Visa ICC объявлялся 9 апреля 2026 как работа с select partners и pilot, что само по себе не доказывает общую доступность в сентябре.
- **jurisdiction / conditions:** Историческое заявление Visa от 2026-04-09.
- **evidence / locator / relation / reasoning:**
  - [P07-S028](sources.md#p07-s028) / `P07-S028-20260915`; Main announcement; pilot description; `supports`: Пилотный scope сохранен в формулировке.
- **confidence_basis / limitations / resolution:** Последующая GA в настоящем исследовании не установлена.

## P07-C006

- **module_ids:** 7.2; **claim_kind:** product; **status:** confirmed.
- **claim:** Mastercard в открытых материалах описывает agent registration, tokenization и передачу контекста агентской покупки.
- **jurisdiction / conditions:** Mastercard 2025 framework article; не полный scheme rulebook.
- **evidence / locator / relation / reasoning:**
  - [P07-S029](sources.md#p07-s029) / `P07-S029-20260915`; Framework; agent registration; tokenization; contextual data; `supports`: Публично описанный подход компании.
- **confidence_basis / limitations / resolution:** Не выводятся region-wide liability shift, обязательность или production eligibility.

## P07-C007

- **module_ids:** 7.2; **claim_kind:** product; **status:** confirmed.
- **claim:** Mastercard объявила Agent Pay for Machines 10 июня 2026; публикация не подтверждает подключение любого разработчика.
- **jurisdiction / conditions:** Пресс-релиз Mastercard 2026-06-10.
- **evidence / locator / relation / reasoning:**
  - [P07-S030](sources.md#p07-s030) / `P07-S030-20260915`; Headline; How it works; Partnering; `supports`: Подтверждает анонс и описанную цепочку партнеров.
- **confidence_basis / limitations / resolution:** Договоры, endpoint access и конкретная реализация не проверены.

## P07-C008

- **module_ids:** 7.2; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** Stripe SPT использует ограничения amount/expiry/seller context; token не является сам по себе фактом capture.
- **jurisdiction / conditions:** Shared payment tokens, seller documentation.
- **evidence / locator / relation / reasoning:**
  - [P07-S022](sources.md#p07-s022) / `P07-S022-20260915`; Sellers: How it works; restrictions; using a token; `supports`: SPT передает ограниченную платежную возможность.
  - [P07-S040](sources.md#p07-s040) / `P07-S040-20260915`; status; `context`: PaymentIntent отражает дальнейший результат.
- **confidence_basis / limitations / resolution:** Ограничения конкретного token и версия API должны проверяться перед выполнением.

## P07-C009

- **module_ids:** 7.2; **claim_kind:** product; **status:** confirmed.
- **claim:** Private preview на Stripe agentic-commerce overview относится к разделу Agents, а не автоматически ко всей странице возможностей.
- **jurisdiction / conditions:** Stripe overview на 2026-09-15.
- **evidence / locator / relation / reasoning:**
  - [P07-S024](sources.md#p07-s024) / `P07-S024-20260915`; Agents — Private preview; `supports`: Статус прочитан вместе с заголовком соответствующего раздела.
- **confidence_basis / limitations / resolution:** Availability может меняться; не подменяет документацию конкретной функции.

## P07-C010

- **module_ids:** 7.2, 7.3; **claim_kind:** product; **status:** confirmed.
- **claim:** ACP описан владельцами как beta; для главы выбрана released спецификация 2026-04-17, а не unreleased.
- **jurisdiction / conditions:** ACP repo pin 7fdd78d, released path spec/2026-04-17.
- **evidence / locator / relation / reasoning:**
  - [P07-S010](sources.md#p07-s010) / `P07-S010-20260915`; README status/versioning; CHANGELOG; `supports`: Репозиторий различает опубликованную версию и текущую работу.
- **confidence_basis / limitations / resolution:** Pin репозитория не равен версии deployed API.

## P07-C011

- **module_ids:** 7.2; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** ACP checkout представляет торговую сессию; delegate payment — отдельный контракт выдачи ограниченного payment token.
- **jurisdiction / conditions:** ACP release 2026-04-17.
- **evidence / locator / relation / reasoning:**
  - [P07-S011](sources.md#p07-s011) / `P07-S011-20260915`; checkout session operations and schema; `supports`: Операции управляют checkout.
  - [P07-S012](sources.md#p07-s012) / `P07-S012-20260915`; POST /agentic_commerce/delegate_payment; Allowance; `supports`: Описан отдельный allowance/token flow.
- **confidence_basis / limitations / resolution:** Не предполагается, что все sellers реализуют оба интерфейса.

## P07-C012

- **module_ids:** 7.2; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** ACP Delegate Payment задает поля max_amount, currency, merchant_id, expires_at и Idempotency-Key для соответствующего запроса.
- **jurisdiction / conditions:** Released delegate_payment OpenAPI 2026-04-17.
- **evidence / locator / relation / reasoning:**
  - [P07-S012](sources.md#p07-s012) / `P07-S012-20260915`; Allowance, lines 520–559; IdempotencyKeyHeader, lines 251–255; `supports`: Поля и header прочитаны в схеме.
- **confidence_basis / limitations / resolution:** Одинаковый смысл бизнес-заказа не выводится из наличия поля: реализация должна хранить связь.

## P07-C013

- **module_ids:** 7.2; **claim_kind:** product; **status:** confirmed.
- **claim:** Поддержка открытого checkout контракта не гарантирует прием product feed и distribution в ChatGPT.
- **jurisdiction / conditions:** OpenAI Get Started, публичное onboarding описание.
- **evidence / locator / relation / reasoning:**
  - [P07-S025](sources.md#p07-s025) / `P07-S025-20260915`; Approved partners; product feeds; onboarding; `supports`: Документация описывает отбор и отдельный onboarding.
- **confidence_basis / limitations / resolution:** Текущий статус конкретного merchant account не проверялся.

## P07-C014

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** x402 v2 HTTP transport использует PAYMENT-REQUIRED, PAYMENT-SIGNATURE и PAYMENT-RESPONSE.
- **jurisdiction / conditions:** Pinned x402 v2 HTTP transport.
- **evidence / locator / relation / reasoning:**
  - [P07-S003](sources.md#p07-s003) / `P07-S003-20260915`; Payment Required; Payment Payload; Payment Response; `supports`: Форматы заголовков определены в transport.
- **confidence_basis / limitations / resolution:** Другие transports или v1 нельзя считать тем же wire contract.

## P07-C015

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** В x402 проверка платежного payload через verify не тождественна выполненному settlement.
- **jurisdiction / conditions:** x402 v2 core and exact EVM.
- **evidence / locator / relation / reasoning:**
  - [P07-S002](sources.md#p07-s002) / `P07-S002-20260915`; Facilitator API /verify and /settle; `supports`: Контракт содержит разные операции.
  - [P07-S004](sources.md#p07-s004) / `P07-S004-20260915`; EIP-3009 phases 2 and 3; `supports`: Проверка и отправка разделены.
- **confidence_basis / limitations / resolution:** Внешний facilitator не становится автоматически гарантом исполнения товара.

## P07-C016

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** Текущий x402 v2 допускает разные порядки resource execution и settlement в зависимости от схемы/assetTransferMethod.
- **jurisdiction / conditions:** Pinned core v2; selected flows.
- **evidence / locator / relation / reasoning:**
  - [P07-S002](sources.md#p07-s002) / `P07-S002-20260915`; Authorization/Upfront/Escrow execution flow; `supports`: В документе представлены разные последовательности.
- **confidence_basis / limitations / resolution:** Нельзя переносить один tutorial flow на все схемы.

## P07-C017

- **module_ids:** 7.3, 7.5; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** EIP-3009 exact payment связывает transfer authorization с параметрами перевода и nonce, но не автоматически со всем бизнес-заказом.
- **jurisdiction / conditions:** x402 exact EVM, EIP-3009 branch.
- **evidence / locator / relation / reasoning:**
  - [P07-S004](sources.md#p07-s004) / `P07-S004-20260915`; PaymentPayload; authorization fields; verify/settle phases; `supports`: Подписываемые transfer поля ограничены данным контрактом.
  - [P07-S005](sources.md#p07-s005) / `P07-S005-20260915`; Purpose; Specification; `context`: Отдельная extension вводит application payment identifier.
- **confidence_basis / limitations / resolution:** Смысл SKU, fulfillment и application retry требует отдельной корреляции.

## P07-C018

- **module_ids:** 7.3, 7.5; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** x402 payment-identifier extension предназначена для корреляции и идемпотентной обработки повторных платежных запросов.
- **jurisdiction / conditions:** Pinned payment_identifier.md.
- **evidence / locator / relation / reasoning:**
  - [P07-S005](sources.md#p07-s005) / `P07-S005-20260915`; Purpose; Requirements; Example flow; `supports`: Extension описывает сохранение/повторное предъявление ID.
- **confidence_basis / limitations / resolution:** Extension нужно согласовать и реализовать; наличие nonce ее не заменяет.

## P07-C019

- **module_ids:** 7.3; **claim_kind:** definition; **status:** confirmed.
- **claim:** MPP core draft-httpauth-payment-01 — Internet-Draft, опубликованный 9 сентября 2026, не принятый RFC.
- **jurisdiction / conditions:** IETF draft metadata/status, expiry 2027-03-13.
- **evidence / locator / relation / reasoning:**
  - [P07-S006](sources.md#p07-s006) / `P07-S006-20260915`; Document metadata; Status of This Memo; `supports`: Статус и сроки доступны в опубликованном draft.
- **confidence_basis / limitations / resolution:** Intended Standards Track не означает завершенный стандарт.

## P07-C020

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** MPP Payment challenge отдельно указывает payment method и intent; ответ передает credential по согласованному authentication header.
- **jurisdiction / conditions:** MPP core draft01.
- **evidence / locator / relation / reasoning:**
  - [P07-S006](sources.md#p07-s006) / `P07-S006-20260915`; Payment Challenges; Payment Credentials; header selection; `supports`: Протокол разделяет действие и метод его исполнения.
- **confidence_basis / limitations / resolution:** Нельзя считать одним методом все settlement guarantees и refund capabilities.

## P07-C021

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** MPP Stripe charge использует SPT и Stripe PaymentIntent, следовательно машинный HTTP интерфейс не устраняет процессор.
- **jurisdiction / conditions:** Pinned draft-stripe-charge-00.
- **evidence / locator / relation / reasoning:**
  - [P07-S007](sources.md#p07-s007) / `P07-S007-20260915`; Overview; Flow; Payment Processing; `supports`: В описании явно участвуют Stripe token и серверная обработка платежа.
- **confidence_basis / limitations / resolution:** Это конкретный payment method, не весь MPP.

## P07-C022

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** MPP Solana charge описывает pull с подписанной транзакцией и push с transaction signature; consumed signatures должны учитываться атомарно.
- **jurisdiction / conditions:** Pinned draft-solana-charge-00.
- **evidence / locator / relation / reasoning:**
  - [P07-S009](sources.md#p07-s009) / `P07-S009-20260915`; Abstract; Replay Protection; Pull Mode Settlement; `supports`: Прямо прочитаны обе формы credential и требования replay protection.
- **confidence_basis / limitations / resolution:** Finality/Token2022/confidential profiles полностью не проверялись; SDK не запускался.

## P07-C023

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** MPP Tempo session использует депозит/канал и накопительные vouchers для учета последовательного потребления.
- **jurisdiction / conditions:** Pinned draft-tempo-session-00, введение и session flow.
- **evidence / locator / relation / reasoning:**
  - [P07-S008](sources.md#p07-s008) / `P07-S008-20260915`; Overview; Session flow; cumulative voucher model; `supports`: Модель разделяет пополнение и накопленный объем требований.
- **confidence_basis / limitations / resolution:** Числа главы синтетические; closing/challenge timing не аудированы.

## P07-C024

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** UCP release v2026-08-25 описывает commerce capabilities и payment handlers как разные элементы.
- **jurisdiction / conditions:** UCP tag cd78fb3.
- **evidence / locator / relation / reasoning:**
  - [P07-S013](sources.md#p07-s013) / `P07-S013-20260915`; Overview; Discovery; Capability/Extension Model; `supports`: Описана композиция торговых возможностей.
  - [P07-S015](sources.md#p07-s015) / `P07-S015-20260915`; Purpose; Participants; Processing; `supports`: Payment handler отвечает за выбранный платежный способ.
- **confidence_basis / limitations / resolution:** Не доказана совместимость любых двух реализаций или обязательность конкретного rail.

## P07-C025

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** В UCP complete_in_progress не является completed и не должно содержать order; completed означает placed order, а не доставленный товар.
- **jurisdiction / conditions:** UCP Checkout Capability release v2026-08-25.
- **evidence / locator / relation / reasoning:**
  - [P07-S014](sources.md#p07-s014) / `P07-S014-20260915`; Status Lifecycle Values; Complete checkout; `supports`: Статусы и наличие order различены в контракте.
- **confidence_basis / limitations / resolution:** Финальный fulfillment отслеживается отдельно от checkout.

## P07-C026

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** UCP допускает продолжение через continue_url, включая требуемое действие человека.
- **jurisdiction / conditions:** UCP checkout and payment authentication extension.
- **evidence / locator / relation / reasoning:**
  - [P07-S014](sources.md#p07-s014) / `P07-S014-20260915`; Continue URL; requires_escalation; `supports`: Контракт содержит переход к human action.
  - [P07-S016](sources.md#p07-s016) / `P07-S016-20260915`; Runtime flow and example; `context`: Платежная аутентификация согласуется отдельно.
- **confidence_basis / limitations / resolution:** Browser-assisted flow не гарантирует право bypass challenge или arbitrary merchant coverage.

## P07-C027

- **module_ids:** 7.4; **claim_kind:** product; **status:** confirmed.
- **claim:** Stripe Machine payments описывает crypto agent pay с fiat proceeds в Stripe balance и ограниченной географической доступностью.
- **jurisdiction / conditions:** Stripe Machine payments documentation on 2026-09-15.
- **evidence / locator / relation / reasoning:**
  - [P07-S023](sources.md#p07-s023) / `P07-S023-20260915`; Availability; settlement; supported methods; `supports`: Прочитана полная краткая страница, включая US except NY и запрос других регионов.
- **confidence_basis / limitations / resolution:** Не подтверждены eligibility конкретного аккаунта, банковский payout или безусловный SLA.

## P07-C028

- **module_ids:** 7.4; **claim_kind:** hypothesis; **status:** working_hypothesis.
- **claim:** Конверсия stablecoin→fiat и получение fiat продавцом — дополнительные денежные операции, которые HTTP payment challenge сам не выполняет.
- **jurisdiction / conditions:** Учебная модель crypto→fiat; зависит от provider agreement.
- **evidence / locator / relation / reasoning:**
  - [P07-S023](sources.md#p07-s023) / `P07-S023-20260915`; Settlement to Stripe balance; `context`: Пример провайдера с отдельным балансом.
  - [P07-S002](sources.md#p07-s002) / `P07-S002-20260915`; Core scope and participant model; `context`: HTTP/core протокол не устанавливает весь банковский payout.
- **confidence_basis / limitations / resolution:** Схемы и денежные числа главы — синтез автора, не реальная тарифная сетка.

## P07-C029

- **module_ids:** 7.4, 7.5; **claim_kind:** experience; **status:** confirmed.
- **claim:** Автор deX402 заявил в X об отсутствии payment processors; это не универсальное свойство x402/MPP и не проверенный результат продукта.
- **jurisdiction / conditions:** Точный публичный пост deX402 от 12 апреля 2026.
- **evidence / locator / relation / reasoning:**
  - [P07-S037](sources.md#p07-s037) / `P07-S037-20260915`; Main post; `supports`: Подтверждается факт собственного заявления.
  - [P07-S007](sources.md#p07-s007) / `P07-S007-20260915`; Stripe charge flow; `contradicts`: Универсальная трактовка несовместима с processor-backed method.
  - [P07-S023](sources.md#p07-s023) / `P07-S023-20260915`; Machine payments processing; `context`: Пример финансового посредника в реальном product description.
- **confidence_basis / limitations / resolution:** Пост рекламный; реальные операции автора не наблюдались.

## P07-C030

- **module_ids:** 7.3; **claim_kind:** experience; **status:** confirmed.
- **claim:** Solana публично объявила поддержку MPP; самостоятельный тест заявленных SDK в главе не проведен.
- **jurisdiction / conditions:** X @solana, 25 марта 2026, main plus two author continuations.
- **evidence / locator / relation / reasoning:**
  - [P07-S036](sources.md#p07-s036) / `P07-S036-20260915`; Main post and visible continuations; `supports`: Автор главы самостоятельно прочитал оригинал через Chrome UI.
  - [P07-S009](sources.md#p07-s009) / `P07-S009-20260915`; Pinned method specification; `context`: Техническая форма метода подтверждается отдельно.
- **confidence_basis / limitations / resolution:** Анонс не доказывает доступность всех SDK, вариантов token и merchants.

## P07-C031

- **module_ids:** 7.2, 7.5; **claim_kind:** experience; **status:** confirmed.
- **claim:** Reddit автор описал проблемы test-mode SPT integration; это полезный reproduction lead, а не измеренная частота отказов.
- **jurisdiction / conditions:** r/fintech post 1vtl49r; точная дата unknown.
- **evidence / locator / relation / reasoning:**
  - [P07-S038](sources.md#p07-s038) / `P07-S038-20260915`; Main post, test-mode points 1–4; `supports`: Самоотчет прочитан, код не запускался.
- **confidence_basis / limitations / resolution:** Статистика и production behavior не установлены; заявленная AU availability не принята вместо official eligibility.

## P07-C032

- **module_ids:** 7.5; **claim_kind:** empirical; **status:** confirmed.
- **claim:** AgentDojo исследует prompt injection в динамических tool-use задачах; benchmark не измеряет потери платежных систем.
- **jurisdiction / conditions:** NeurIPS 2024 benchmark, arXiv:2406.13352v3 от 24.11.2024, повторно проверена 17.09.2026.
- **evidence / locator / relation / reasoning:**
  - [P07-S033](sources.md#p07-s033) / `P07-S033-20260917`; §§3.4, 4.1–4.3; task/attack construction; `supports`: Прочитаны методы и ограничения оценки, не только abstract.
- **confidence_basis / limitations / resolution:** 97 tasks и 629 security cases описывают тестовую среду; перенос на новые модели и платежи требует проверки. Исходное чтение 15.09 не имеет сохраненного снимка; подтверждение выше относится к явно закрепленной v3.

## P07-C033

- **module_ids:** 7.5; **claim_kind:** empirical; **status:** confirmed.
- **claim:** Formal Analysis of Agent Payment Protocols применяет Tamarin и явно разделяет символические модели, traces и implementation evidence.
- **jurisdiction / conditions:** arXiv 2609.00060v1, submitted 2026-08-30, preprint.
- **evidence / locator / relation / reasoning:**
  - [P07-S034](sources.md#p07-s034) / `P07-S034-20260915`; §§III–VII; threat model; evaluation; limitations; `supports`: Прочитаны модель, evidence levels и ограничения.
- **confidence_basis / limitations / resolution:** Не выполнялась репликация и не доказаны production exploits на pinned версиях главы.

## P07-C034

- **module_ids:** 7.5; **claim_kind:** empirical; **status:** confirmed.
- **claim:** Beyond the Mandate исследует AP2 в собственном testbed/scanner setting; вывод о каждом актуальном deployment из этого не следует.
- **jurisdiction / conditions:** arXiv 2608.23858v1, submitted 2026-08-24, preprint.
- **evidence / locator / relation / reasoning:**
  - [P07-S035](sources.md#p07-s035) / `P07-S035-20260915`; §§3–9, especially threat model, demos, CDSE, ablations, limitations; `supports`: Изучены экспериментальные условия и границы, не только abstract.
- **confidence_basis / limitations / resolution:** Системы авторов и выбранные реализации не равны всему рынку; независимой репликации нет.

## P07-C035

- **module_ids:** 7.5; **claim_kind:** hypothesis; **status:** working_hypothesis.
- **claim:** Неопределенный settlement после broadcast должен сверяться по исходному rail/provider ID до решения о новом платеже.
- **jurisdiction / conditions:** Предлагаемый operational control для money-moving requests.
- **evidence / locator / relation / reasoning:**
  - [P07-S004](sources.md#p07-s004) / `P07-S004-20260915`; settlement_pending; transaction and network fields; `context`: Протокол дает устойчивые идентификаторы неопределенного исхода.
  - [P07-S005](sources.md#p07-s005) / `P07-S005-20260915`; Idempotency requirements; `context`: Повтор должен сохранять связь с прежней операцией.
- **confidence_basis / limitations / resolution:** Это safe recovery design; конкретный срок/operator procedure задается провайдером и договором.

## P07-C036

- **module_ids:** 7.5; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** x402 v2 допускает non-terminal settlement_pending с transaction hash и network при неопределенном подтверждении.
- **jurisdiction / conditions:** Pinned x402 exact EVM and core v2.
- **evidence / locator / relation / reasoning:**
  - [P07-S004](sources.md#p07-s004) / `P07-S004-20260915`; Settlement response; settlement_pending; `supports`: Исход обозначен не как финальный fail.
  - [P07-S002](sources.md#p07-s002) / `P07-S002-20260915`; SettleResponse handling; `context`: Core различает результат settlement.
- **confidence_basis / limitations / resolution:** Hash не доказывает finality: требуется сверка соответствующей сети.

## P07-C037

- **module_ids:** 7.5; **claim_kind:** hypothesis; **status:** working_hypothesis.
- **claim:** Два параллельных агента могут совместно превысить бюджет, если каждый проверяет один прежний остаток без атомарного резерва.
- **jurisdiction / conditions:** Синтетический пример общий budget=10, reservations 6+6.
- **evidence / locator / relation / reasoning:**
  - [P07-S020](sources.md#p07-s020) / `P07-S020-20260915`; Budget/recurrence constraints; `context`: Ограничения требуют учета предыдущих предъявлений.
  - [P07-S021](sources.md#p07-s021) / `P07-S021-20260915`; Server-side validation and replay considerations; `context`: Проверки должны исполняться на доверенной стороне.
- **confidence_basis / limitations / resolution:** Вывод из арифметики и конкурентного исполнения, не статистика инцидентов.

## P07-C038

- **module_ids:** 7.6; **claim_kind:** definition; **status:** confirmed.
- **claim:** RFC 8693 различает delegation и impersonation; actor identity сама по себе не определяет полный trust model финансовой операции.
- **jurisdiction / conditions:** RFC 8693 §§1, 1.1, 4.1.
- **evidence / locator / relation / reasoning:**
  - [P07-S031](sources.md#p07-s031) / `P07-S031-20260915`; Scope; Delegation vs. Impersonation; act; `supports`: Trust model и конкретные token security semantics ограничены scope RFC.
- **confidence_basis / limitations / resolution:** Для платежа нужны отдельные consent/authority и enforcement.

## P07-C039

- **module_ids:** 7.6; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** DPoP proof не является самостоятельным механизмом authentication/access control и не доказывает consent на товар.
- **jurisdiction / conditions:** RFC 9449 §§4,4.1,7.1.
- **evidence / locator / relation / reasoning:**
  - [P07-S032](sources.md#p07-s032) / `P07-S032-20260915`; DPoP Proof JWTs; checking proofs; binding access tokens; `supports`: Proof применяется вместе с token и проверками resource server.
- **confidence_basis / limitations / resolution:** Отсутствие права на recurring purchase не исправляется корректной подписью.

## P07-C040

- **module_ids:** 7.6; **claim_kind:** definition; **status:** confirmed.
- **claim:** RATS разделяет attester, verifier и relying party; attestation evidence не заменяет платежное поручение.
- **jurisdiction / conditions:** RFC 9334 Informational architecture.
- **evidence / locator / relation / reasoning:**
  - [P07-S041](sources.md#p07-s041) / `P07-S041-20260915`; §4.1; §5.2; §7; §8.5; `supports`: Доверяющая сторона применяет политику к результату оценки среды.
- **confidence_basis / limitations / resolution:** Последняя граница платежного согласия — авторский вывод из различия scopes.

## P07-C041

- **module_ids:** 7.6; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** AP2 v0.2 использует Checkout и Payment mandates, допускающие open/closed формы; старую терминологию нельзя смешивать без версии.
- **jurisdiction / conditions:** AP2 repo v0.2.0 changelog, pinned e1ea56d.
- **evidence / locator / relation / reasoning:**
  - [P07-S017](sources.md#p07-s017) / `P07-S017-20260915`; Mandates; Human-present and autonomous flows; CHANGELOG 0.2.0; `supports`: Термины и flows соответствуют указанной версии.
- **confidence_basis / limitations / resolution:** Не является утверждением совместимости со всеми earlier SDK.

## P07-C042

- **module_ids:** 7.6; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** AP2 agent authorization описывает User Credential и Trusted Agent Provider модели подтверждения согласия.
- **jurisdiction / conditions:** AP2 current agent_authorization.md.
- **evidence / locator / relation / reasoning:**
  - [P07-S018](sources.md#p07-s018) / `P07-S018-20260915`; Introduction; User Credential; Trusted Agent Provider; `supports`: Разные trust arrangements описаны в первичке.
- **confidence_basis / limitations / resolution:** Ни одна модель не объявлена универсальной юридической идентификацией клиента.

## P07-C043

- **module_ids:** 7.6; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** Checkout mandate в AP2 связывается с merchant-signed checkout посредством checkout_hash.
- **jurisdiction / conditions:** AP2 Checkout Mandate v0.2.
- **evidence / locator / relation / reasoning:**
  - [P07-S019](sources.md#p07-s019) / `P07-S019-20260915`; Usage; Type; Checkout Hash; `supports`: Связь с конкретным checkout задана структурой.
  - [P07-S017](sources.md#p07-s017) / `P07-S017-20260915`; Autonomous flow; `context`: Closed mandates проверяются относительно согласованных open mandates.
- **confidence_basis / limitations / resolution:** Подпись продавца не доказывает качество товара.

## P07-C044

- **module_ids:** 7.6; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** AP2 Payment Mandate задает ограничения payee/instrument/amount/date и optional recurrence/budget; повторные предъявления требуют учета.
- **jurisdiction / conditions:** AP2 Payment Mandate v0.2.
- **evidence / locator / relation / reasoning:**
  - [P07-S020](sources.md#p07-s020) / `P07-S020-20260915`; Constraints; Budget; Recurrence; Allowed Payees/Instruments; `supports`: Прочитан перечень ограничений и условия их проверки.
- **confidence_basis / limitations / resolution:** Динамические ограничения нельзя проверить только синтаксисом одной подписи.

## P07-C045

- **module_ids:** 7.6; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** Проверка line-items AP2 Checkout Mandate в прочитанном контракте не поддерживает разбиение одного open mandate на несколько checkouts.
- **jurisdiction / conditions:** AP2 checkout_mandate.md v0.2.
- **evidence / locator / relation / reasoning:**
  - [P07-S019](sources.md#p07-s019) / `P07-S019-20260915`; Line Items constraint; `supports`: Ограничение указано явно.
- **confidence_basis / limitations / resolution:** Не утверждается принципиальная невозможность будущего расширения; agent-to-agent delegation также вне рассмотренного core.

## P07-C046

- **module_ids:** 7.5, 7.6; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** AP2 security guidance выносит проверку consent/mandates за пределы недоверенных указаний модели и описывает trusted surface.
- **jurisdiction / conditions:** AP2 Security and Privacy Considerations v0.2.
- **evidence / locator / relation / reasoning:**
  - [P07-S021](sources.md#p07-s021) / `P07-S021-20260915`; Consent; deterministic verification; Trusted Surface; privacy; `supports`: Полностью прочитанный файл задает границы проверок.
- **confidence_basis / limitations / resolution:** Рекомендация спецификации не доказывает правильность конкретного runtime.

## P07-C047

- **module_ids:** 7.6; **claim_kind:** legal; **status:** confirmed.
- **claim:** FATF guidance 2021 служит контекстом функций VASP и Travel Rule; сама publication page предупреждает о последующих изменениях стандартов.
- **jurisdiction / conditions:** Только scope publication page FATF; не legal opinion.
- **evidence / locator / relation / reasoning:**
  - [P07-S039](sources.md#p07-s039) / `P07-S039-20260915`; Publication overview and update warning; `supports`: Полный PDF не прочитан; действующие обязанности по странам не выводятся.
- **confidence_basis / limitations / resolution:** Требуется актуальная норма и квалификация роли в выбранной юрисдикции; effective dates этой конкретной правовой обязанности unknown.

## P07-C048

- **module_ids:** 7.5, 7.6; **claim_kind:** legal; **status:** open.
- **claim:** Полное распределение agentic liability между principal, vendor, merchant и financial provider в выбранной стране здесь не установлено.
- **jurisdiction / conditions:** Реальное применение требует договоров и применимого права.
- **evidence / locator / relation / reasoning:**
  - [P07-S026](sources.md#p07-s026) / `P07-S026-20260915`; Public scope/disclaimer; `context`: Overview не заменяет договоры.
  - [P07-S029](sources.md#p07-s029) / `P07-S029-20260915`; Framework public description; `context`: Не полный rulebook.
  - [P07-S017](sources.md#p07-s017) / `P07-S017-20260915`; Dispute-resolution scope; `context`: Evidence и dispute mechanism имеют разные scopes.
- **confidence_basis / limitations / resolution:** RACI главы — проектная модель ownership, не юридическое заключение.

## P07-C049

- **module_ids:** 7.3, 7.5; **claim_kind:** mechanism; **status:** rejected.
- **claim:** Утверждение «любой x402 payload означает состоявшуюся продажу» отвергается.
- **jurisdiction / conditions:** Универсальное утверждение.
- **evidence / locator / relation / reasoning:**
  - [P07-S002](sources.md#p07-s002) / `P07-S002-20260915`; Verify/settle and response model; `contradicts`: Authorization и settlement разнесены.
  - [P07-S014](sources.md#p07-s014) / `P07-S014-20260915`; Checkout lifecycle; `context`: Order и fulfillment также раздельны.
- **confidence_basis / limitations / resolution:** Для продажи нужны соответствующие денежные и товарные evidence в конкретной модели.

## P07-C050

- **module_ids:** 7.6; **claim_kind:** mechanism; **status:** rejected.
- **claim:** Утверждение «известный agent identity автоматически дает право расходовать средства principal» отвергается.
- **jurisdiction / conditions:** Универсальное утверждение.
- **evidence / locator / relation / reasoning:**
  - [P07-S018](sources.md#p07-s018) / `P07-S018-20260915`; Agent Authorization; `contradicts`: Требуется отдельная модель согласия.
  - [P07-S031](sources.md#p07-s031) / `P07-S031-20260915`; Trust-model scope; delegation semantics; `contradicts`: Структура actor/subject не задает все права.
  - [P07-S032](sources.md#p07-s032) / `P07-S032-20260915`; Proof is not authentication/access control; `context`: Key proof сам по себе недостаточен.
- **confidence_basis / limitations / resolution:** Полномочия должны быть связаны с покупкой, лимитами и сроком.

## P07-C051

- **module_ids:** 7.2; **claim_kind:** definition; **status:** confirmed.
- **claim:** UCP governance назначает Governing Council владельцем UCP assets, Google хранителем домена, Google и Shopify founding organizations с постоянными местами.
- **jurisdiction / conditions:** governance policy Universal-Commerce-Protocol, отдельный repo pin ced53b98c2064d472b41a5aff1c20b8261e6dd91 от 15.09.2026.
- **evidence / locator / relation / reasoning:** [P07-S042](sources.md#p07-s042) / `P07-S042-20260915`; Governing Council; `supports`: распределение ролей дано явно в политике проекта.
- **confidence_basis / limitations / resolution:** Это описание собственных органов проекта; принятие закона, независимая сертификация и отсутствие vendor influence из него не выводятся.
