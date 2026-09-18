---
title: "Часть 8 — реестр существенных утверждений"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Публичная редакция от 18.09.2026. Даты проверки и ограничения источников сохранены. Хеши в исторических аудитах относятся к исходной рукописи; публичные изменения и текущие хеши — в [паспорте издания](../../edition.md).

# Часть 8 — реестр существенных утверждений

**v0.1 · independently_reviewed_draft · private.** Автор: `part_08_research`; независимая проверка: см. REVIEW.md. Срез всех текущих технических тезисов: **2026-09-15**; `last_checked_at=2026-09-15, Asia/Makassar`, точность day. Ни один статус здесь не означает эксплуатационную приемку продукта.

Фактчек исходной редакции завершен17.09.2026. Связь исходной версии с публичной копией, область адаптации и текущая навигация описаны в паспорте издания.

## Как читать

`confirmed` означает соответствие прочитанному источнику **в указанной области**. Для vendor docs подтвержден описанный контракт, а не фактическая конфигурация клиента; для социального/операторского рассказа — содержание атрибутированного сообщения, не независимая истинность всех наблюдений. У каждого evidence ID указан snapshot по фактической дате; копия документа не сохранена. Общие метаданные и URL: [SOURCES.md](sources.md).

Для всех карточек: `as_of=2026-09-15`, кроме явно датированного исторического опыта; `reviewer=see_REVIEW.md`, `review_status=see_REVIEW.md`; `effective_from/effective_to=not_applicable` к техническим пояснениям, национальная применимость BCBS не установлена. `review_trigger`: новая версия API/документа, смена account/страны/модели, релиз конкретного plugin либо новое противоречащее evidence. Необнаруженный конфликт не означает доказательство отсутствия всех конфликтов.

Авторские схемы, внутренние названия состояний, pilot/kill criteria, правила очередей и числовые примеры — **предлагаемая учебная конструкция**, не документированный API конкретной компании. Арифметика проверена отдельно; для synthetic amounts не создается фиктивный внешний источник. Практическое применение финансовой классификации и моделей1–5 требует профильной проверки.

## P08-C001

- **module_ids:** 8.1; **claim_kind:** `mechanism`; **status:** `confirmed` в scope ниже.
- **Claim:** Store API обслуживает клиентский контекст и не дает административного доступа к чужим данным.
- **Evidence:** [P08-S001 / P08-S001-20260915](sources.md#p08-s001); **locator:** Introduction; Requirements and limitations; Store API Namespace; **relation:** supports.
- **Scope / conditions:** WooCommerce Store API v1.
- **Reasoning / limits:** Unauthenticated не означает отсутствие nonce/session constraints. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C002

- **module_ids:** 8.1; **claim_kind:** `product`; **status:** `confirmed` в scope ниже.
- **Claim:** Woo REST API использует API keys с правами; документация показывает административный маршрут wc/v3/orders.
- **Evidence:** [P08-S002 / P08-S002-20260915](sources.md#p08-s002); **locator:** Generate keys; Make a basic request; **relation:** supports.
- **Scope / conditions:** WooCommerce REST API, описанный пример.
- **Reasoning / limits:** Версия конкретного магазина и permissions не проверялись. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C003

- **module_ids:** 8.1; **claim_kind:** `mechanism`; **status:** `confirmed` в scope ниже.
- **Claim:** Gateway может вернуть success для обработки checkout при еще ожидаемой оплате; classic guide отдельно отсылает к Blocks.
- **Evidence:** [P08-S003 / P08-S003-20260915](sources.md#p08-s003); **locator:** Creating a basic payment gateway; process_payment example; **relation:** supports.
- **Scope / conditions:** Классический Woo checkout; cheque example.
- **Reasoning / limits:** Не распространять success возвращаемого массива на settlement. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C004

- **module_ids:** 8.1; **claim_kind:** `product`; **status:** `confirmed` в scope ниже.
- **Claim:** Checkout Blocks требует отдельной интеграции метода; серверное повторное использование gateway не доказывает всю совместимость.
- **Evidence:** [P08-S004 / P08-S004-20260915](sources.md#p08-s004); **locator:** Server Side Integration; Processing Payments (legacy support); Processing Payments via the Store API; **relation:** supports.
- **Scope / conditions:** WooCommerce Blocks.
- **Reasoning / limits:** Конкретное расширение требует проверки; claim не о всех plugins. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C005

- **module_ids:** 8.1; **claim_kind:** `product`; **status:** `confirmed` в scope ниже.
- **Claim:** Woo исходящие webhooks имеют описанное отключение после пяти неудачных retries по умолчанию.
- **Evidence:** [P08-S005 / P08-S005-20260915](sources.md#p08-s005); **locator:** Creating webhooks, paragraph after activation ping; **relation:** supports.
- **Scope / conditions:** WooCommerce outgoing notifications.
- **Reasoning / limits:** Настраиваемое поведение; не контракт входящего PSP callback. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C006

- **module_ids:** 8.1,8.4; **claim_kind:** `product`; **status:** `confirmed` в scope ниже.
- **Claim:** Shopify Payments extensions требуют approved Partner; custom payment extensions имеют отдельную Plus eligibility.
- **Evidence:** [P08-S006 / P08-S006-20260915](sources.md#p08-s006); **locator:** Introduction; How it works; Considerations; **relation:** supports.
- **Scope / conditions:** Shopify Payments Platform as read.
- **Reasoning / limits:** Не подтверждает approval конкретного приложения или merchant. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C007

- **module_ids:** 8.1; **claim_kind:** `product`; **status:** `confirmed` в scope ниже.
- **Claim:** Checkout UI extensions на information/shipping/payment шагах описаны как Plus-only.
- **Evidence:** [P08-S007 / P08-S007-20260915](sources.md#p08-s007); **locator:** Shopify Plus notice; selector 2026-07; **relation:** supports.
- **Scope / conditions:** Указанные checkout steps.
- **Reasoning / limits:** Не относится автоматически ко всем поверхностям Shopify; не платежное approval. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C008

- **module_ids:** 8.1; **claim_kind:** `mechanism`; **status:** `confirmed` в scope ниже.
- **Claim:** Adobe gateway выделяет платежные команды и слои request/client/validation/handling.
- **Evidence:** [P08-S010 / P08-S010-20260915](sources.md#p08-s010); **locator:** What is Adobe Commerce payment provider gateway; operations; chapter components; **relation:** supports.
- **Scope / conditions:** Adobe Commerce conceptual gateway.
- **Reasoning / limits:** Наличие абстракции не гарантирует каждый метод/операцию у конкретного PSP. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C009

- **module_ids:** 8.2,8.5; **claim_kind:** `product`; **status:** `confirmed` в scope ниже.
- **Claim:** Adyen Modification Reference может совпасть у capture и chargeback.
- **Evidence:** [P08-S017 / P08-S017-20260915](sources.md#p08-s017); **locator:** Columns, Modification Reference; **relation:** supports.
- **Scope / conditions:** Adyen Settlement details report.
- **Reasoning / limits:** Ключ строить с типом и account scope; не предполагать независимую уникальность поля. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C010

- **module_ids:** 8.2,8.6; **claim_kind:** `mechanism`; **status:** `confirmed` в scope ниже.
- **Claim:** Stripe idempotency сохраняет результат начавшего исполнение запроса, включая500; ключ может быть удален после возраста не менее24h.
- **Evidence:** [P08-S011 / P08-S011-20260915](sources.md#p08-s011); **locator:** Saved status/body; key removal; execution start; **relation:** supports.
- **Scope / conditions:** Stripe API v1 mutating request contract.
- **Reasoning / limits:** После очистки прежний key может породить новый запрос; validation/concurrency exceptions отдельно. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C011

- **module_ids:** 8.2; **claim_kind:** `mechanism`; **status:** `confirmed` в scope ниже.
- **Claim:** AWS рассматривает семантически эквивалентный ответ, поздние повторы и измененное намерение как части idempotency contract.
- **Evidence:** [P08-S014 / P08-S014-20260915](sources.md#p08-s014); **locator:** Retries and semantic equivalence; Late arriving requests; Same client request ID, different intent; **relation:** supports.
- **Scope / conditions:** AWS design explanation.
- **Reasoning / limits:** Это контекст проектирования, не контракт финансового провайдера. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C012

- **module_ids:** 8.2; **claim_kind:** `mechanism`; **status:** `confirmed` в scope ниже.
- **Claim:** RIFL связывает exactly-once RPC с durable completion record, атомарной записью эффектов и обнаружением результата после миграции.
- **Evidence:** [P08-S016 / P08-S016-20260915](sources.md#p08-s016); **locator:** §3 Architecture; §4.1 ResultTracker; PDF pp.3–5; **relation:** supports.
- **Scope / conditions:** RIFL distributed storage model.
- **Reasoning / limits:** Не exactly-once произвольной цепочки PSP/shop/bank; leases/client failures ограничивают модель. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C013

- **module_ids:** 8.2,8.6; **claim_kind:** `mechanism`; **status:** `confirmed` в scope ниже.
- **Claim:** Stripe500 может иметь пользовательские побочные эффекты; новый idempotency key не рекомендован для такого повтора.
- **Evidence:** [P08-S013 / P08-S013-20260915](sources.md#p08-s013); **locator:** Server errors, especially indeterminate result paragraphs; **relation:** supports.
- **Scope / conditions:** Stripe500 and unknown outcomes.
- **Reasoning / limits:** Query/reconcile схема главы — проектная адаптация; network retry same key допускается контрактом. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C014

- **module_ids:** 8.2,8.6; **claim_kind:** `mechanism`; **status:** `confirmed` в scope ниже.
- **Claim:** Transactional outbox связывает локальное изменение базы с записью исходящего события; потребителю нужна защита от дублей.
- **Evidence:** [P08-S015 / P08-S015-20260915](sources.md#p08-s015); **locator:** Intent; Issues and considerations; Implementation; **relation:** supports.
- **Scope / conditions:** Database and message publication boundary.
- **Reasoning / limits:** Не делает внешний PSP частью локальной атомарной транзакции. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C015

- **module_ids:** 8.3,8.5; **claim_kind:** `product`; **status:** `confirmed` в scope ниже.
- **Claim:** Adyen settlement report разделяет финансовые типы строк и дает payout reference/batch для банковского сопоставления.
- **Evidence:** [P08-S017 / P08-S017-20260915](sources.md#p08-s017); **locator:** Report structure; Merchant payout; **relation:** supports.
- **Scope / conditions:** Adyen merchant reporting.
- **Reasoning / limits:** Синтетическая выписка главы не копия фактического формата Adyen. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C016

- **module_ids:** 8.3; **claim_kind:** `product`; **status:** `confirmed` в scope ниже.
- **Claim:** Stripe Payout reconciliation ориентирован на automatic payouts; manual/instant имеют ограничения и отдельный путь сверки.
- **Evidence:** [P08-S018 / P08-S018-20260915](sources.md#p08-s018); **locator:** Overview paragraphs1–4; Report sections; **relation:** supports.
- **Scope / conditions:** Stripe reports; includes manual-platform/automatic-connected exception.
- **Reasoning / limits:** Применять точную eligibility отчета; ни один report не заменяет банк. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C017

- **module_ids:** 8.3,8.6; **claim_kind:** `mechanism`; **status:** `confirmed` в scope ниже.
- **Claim:** Stripe предупреждает против клиентского запуска fulfillment: покупатель может уйти после оплаты.
- **Evidence:** [P08-S023 / P08-S023-20260915](sources.md#p08-s023); **locator:** Monitor a PaymentIntent with webhooks; **relation:** supports.
- **Scope / conditions:** PaymentIntents integration.
- **Reasoning / limits:** Webhook-trigger не доказывает успешную выдачу товара. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C018

- **module_ids:** 8.4; **claim_kind:** `product`; **status:** `confirmed` в scope ниже.
- **Claim:** Поддержка payment method зависит от business location, customer country, currency и product/API scope; Connect eligibility может отличаться.
- **Evidence:** [P08-S022 / P08-S022-20260915](sources.md#p08-s022); **locator:** Country and currency support; Connected accounts notice; Product support; **relation:** supports.
- **Scope / conditions:** Stripe support matrix.
- **Reasoning / limits:** Список стран не означает доступность всех комбинаций; individual terms не исследованы целиком. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C019

- **module_ids:** 8.5; **claim_kind:** `definition`; **status:** `confirmed` в scope ниже.
- **Claim:** Равенство trial balance не исключает ошибочные двойные записи.
- **Evidence:** [P08-S021 / P08-S021-20260915](sources.md#p08-s021); **locator:** Example3, p.3, explanatory paragraphs; **relation:** supports.
- **Scope / conditions:** ACCA teaching: double-entry bookkeeping.
- **Reasoning / limits:** Не текущая учетная политика; денежный контрпример главы синтетический. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C020

- **module_ids:** 8.5; **claim_kind:** `product`; **status:** `confirmed` в scope ниже.
- **Claim:** Stripe Balance Transaction хранит gross/fee/net и время доступности в Stripe balance отдельно.
- **Evidence:** [P08-S019 / P08-S019-20260915](sources.md#p08-s019); **locator:** Attributes: amount, fee, net, available_on, status; **relation:** supports.
- **Scope / conditions:** Stripe balance transactions.
- **Reasoning / limits:** available_on не означает банковское поступление. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C021

- **module_ids:** 8.5; **claim_kind:** `product`; **status:** `confirmed` в scope ниже.
- **Claim:** Stripe amount encoding имеет специальные случаи;5ISK передаются как500 без возможности дробных ISK.
- **Evidence:** [P08-S020 / P08-S020-20260915](sources.md#p08-s020); **locator:** Specify amounts; Special cases, ISK; **relation:** supports.
- **Scope / conditions:** Stripe currency contract.
- **Reasoning / limits:** Не универсальное encoding всех API; FX числа главы синтетические. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C022

- **module_ids:** 8.6; **claim_kind:** `product`; **status:** `confirmed` в scope ниже.
- **Claim:** Stripe не гарантирует порядок webhook events; live retries описаны до трех дней.
- **Evidence:** [P08-S012 / P08-S012-20260915](sources.md#p08-s012); **locator:** Event delivery behaviors: Automatic retries; Event ordering; **relation:** supports.
- **Scope / conditions:** Stripe live webhook delivery.
- **Reasoning / limits:** Не гарантия попадания/обработки каждого события в приложении. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C023

- **module_ids:** 8.6; **claim_kind:** `product`; **status:** `confirmed` в scope ниже.
- **Claim:** Shopify Webhook-Id идентифицирует delivery; Event-Id объединяет доставки одного merchant action.
- **Evidence:** [P08-S008 / P08-S008-20260915](sources.md#p08-s008); **locator:** Headers; Example request headers; **relation:** supports.
- **Scope / conditions:** Shopify webhook reference selector2026-07.
- **Reasoning / limits:** Event-ID не заменяет consumer-specific и economic-operation deduplication. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C024

- **module_ids:** 8.6; **claim_kind:** `product`; **status:** `confirmed` в scope ниже.
- **Claim:** Shopify HTTPS receiving guide описывает persistent deduplication, быстрый ответ и reconciliation; timeout1s/5s.
- **Evidence:** [P08-S009 / P08-S009-20260915](sources.md#p08-s009); **locator:** Ignoring duplicates; HTTPS delivery considerations; **relation:** supports.
- **Scope / conditions:** Shopify HTTPS, прочитанныйguide.
- **Reasoning / limits:** Не переносить параметры на Woo/PSP; схема durable inbox является проектной конкретизацией. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C025

- **module_ids:** 8.6; **claim_kind:** `mechanism`; **status:** `confirmed` в scope ниже.
- **Claim:** Stripe signature verification требует исходное неизмененное тело запроса и правильный endpoint secret.
- **Evidence:** [P08-S028 / P08-S028-20260915](sources.md#p08-s028); **locator:** Intro; Check endpoint secret; Check request body; **relation:** supports.
- **Scope / conditions:** Stripe webhook verification.
- **Reasoning / limits:** Не разрешение исполнять произвольный текст payload; секреты не логируются в предложенной схеме. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C026

- **module_ids:** 8.6; **claim_kind:** `mechanism`; **status:** `confirmed` в scope ниже.
- **Claim:** Stripe подписывает timestamp доставки; при retry подписывает новое время, поэтому recency и новизна события различаются.
- **Evidence:** [P08-S012 / P08-S012-20260915](sources.md#p08-s012); **locator:** Preventing replay attacks; **relation:** supports.
- **Scope / conditions:** Stripe signature contract.
- **Reasoning / limits:** Свежесть не заменяет durable deduplication; конкретная replay policy другого PSP проверяется отдельно. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C027

- **module_ids:** 8.6; **claim_kind:** `mechanism`; **status:** `confirmed` в scope ниже.
- **Claim:** OWASP API6:2023 описывает злоупотребление чувствительными бизнес-потоками через автоматизацию.
- **Evidence:** [P08-S026 / P08-S026-20260915](sources.md#p08-s026); **locator:** Is the API Vulnerable?; Example Attack Scenarios; **relation:** supports.
- **Scope / conditions:** OWASP awareness guidance.
- **Reasoning / limits:** Лимиты резервов/сумм в главе — проектный вывод; реальная атака на продукт не заявляется. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C028

- **module_ids:** 8.6; **claim_kind:** `experience`; **status:** `confirmed` в scope ниже.
- **Claim:** Инженеры Monzo сообщили о примерно часовом outage августа2024 и работе Stand-in; описали перенос эффектов и correlation IDs.
- **Evidence:** [P08-S024 / P08-S024-20260915](sources.md#p08-s024); **locator:** Syncing state; Correlating data; You might have seen Monzo Stand-in; **relation:** supports.
- **Scope / conditions:** Monzo operator account published2025-02-13.
- **Reasoning / limits:** Подтверждено содержание публикации; независимое SLO и точная причина не установлены. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C029

- **module_ids:** 8.6; **claim_kind:** `mechanism`; **status:** `confirmed` в scope ниже.
- **Claim:** BCBS Principles3–6 включают continuity testing, mapping, third-party dependencies и incident recovery.
- **Evidence:** [P08-S025 / P08-S025-20260915](sources.md#p08-s025); **locator:** Principles3–6, printed pp.5–7; **relation:** supports.
- **Scope / conditions:** Банки; международные надзорные принципы2021.
- **Reasoning / limits:** Национальная юридическая обязательность для конкретного субъекта не исследована; не правило для любого магазина. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

## P08-C030

- **module_ids:** 8.6; **claim_kind:** `experience`; **status:** `confirmed` в scope ниже.
- **Claim:** IndicationOne9495 публично описывает трудности inline webhook processing и задает вопрос об очередях.
- **Evidence:** [P08-S027 / P08-S027-20260915](sources.md#p08-s027); **locator:** Original post body; **relation:** supports.
- **Scope / conditions:** Reddit public question; absolute date unknown.
- **Reasoning / limits:** Подтвержден текст/автор в отображении, не частота/причина проблем и не benchmark. Тезис ограничен прочитанным locator, без экстраполяции на весь рынок.
- **Conflicts / resolution:** существенное противоречие прочитанному locator не выявлено; спорная универсализация исключена указанными условиями.

