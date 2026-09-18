---
title: "Реестр утверждений части 2"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Публичная редакция от 18.09.2026. Даты проверки и ограничения источников сохранены. Хеши в исторических аудитах относятся к исходной рукописи; публичные изменения и текущие хеши — в [паспорте издания](../../edition.md).

# Реестр утверждений части 2

v0.1 · `independently_reviewed_draft` · private · 15.09.2026.

Фактчек исходной редакции завершен17.09.2026. Связь исходной версии с публичной копией, область адаптации и текущая навигация описаны в паспорте издания.

Общие поля: `as_of=2026-09-15`; `last_checked_at=2026-09-15`; `reviewer=part-02 researcher`; `review_status=see_REVIEW.md`. `confirmed` означает подтверждение в указанной области, не независимую приёмку всей главы. Каждая evidence-ссылка имеет snapshot `<source_id>-20260915`, relation `supports`, если строка не задаёт другое. Snapshot обозначает обращение, не неизменяемую копию. Даты/версии и rights/access ограничения раскрыты в [SOURCES.md](sources.md).

Для каждого claim `review_trigger`: изменение указанного документа/версии/договора, выпуск новой редакции главы или переход от учебного примера к реальному продукту. Для empirical claims дополнительно — новый отчёт или изменение методологии; для source-access gaps — получение читаемого первичного текста. Неизвестные значения не заменяются оценкой вероятности.

## Подтверждённые определения и механизмы

| claim_id | module_id; kind | Утверждение и scope | Evidence: source + snapshot + locator | Ограничение / основание вывода |
|---|---|---|---|---|
| P02-C001 | 2.1; mechanism | `confirmed`: функции продавца, эквайера и посредника могут принадлежать разным субъектам; в модели Visa эквайер сохраняет ответственность за действующих через него участников | P02-S034 / P02-S034-20260915, Backdrop p.2 | Публичный role overview 2024; детальные действующие правила и договор обязательны для конкретного запуска |
| P02-C002 | 2.1; definition | `confirmed`: ISO в продажах эквайринга означает Independent Sales Organization и не является ISO-стандартом сообщений | P02-S034 / P02-S034-20260915, Third Party Agents / ISO p.7 | Роль продаж/сопровождения не доказывает самостоятельное право держать settlement funds |
| P02-C003 | 2.1; mechanism | `confirmed`: PF в описанной Visa-модели может заключать договоры приёма и/или получать средства для sponsored merchants | P02-S034 / P02-S034-20260915, Payment Facilitator p.3 | Не универсальный закон обо всех PSP; количественные thresholds из старого overview не перенесены |
| P02-C004 | 2.1,2.2; definition | `confirmed`: authorization, clearing и settlement обозначают разные стадии карточного процесса | P02-S003 / P02-S003-20260915, §§2.1–2.2 pp.4–5; P02-S002 / P02-S002-20260915 §2.18.1 pp.68–69 | Merchant payout/fulfillment нельзя вывести из authorization response |
| P02-C005 | 2.2; product | `confirmed`: в Stripe конкретный capture_before и ограничения метода определяют окно manual capture; универсальных семи дней нет | P02-S004 / P02-S004-20260915, Authorization validity windows; Capture the funds | Только описанные Stripe routes; таблицы rolling, не immutable |
| P02-C006 | 2.2,2.7; product | `confirmed`: частичный capture обычно освобождает остаток в описанной Stripe-модели; multiple capture требует поддержки | P02-S004 / P02-S004-20260915, Capture the funds, multicapture paragraph | Не универсально для всех PSP и карточных продуктов |
| P02-C007 | 2.2; product | `confirmed`: ручной capture Adyen асинхронен; request receipt не равен окончательному финансовому успеху | P02-S005 / P02-S005-20260915, Manual capture; Failed capture | Проверить точный webhook и settlement record; CAPTURE_FAILED может уточнять прежний результат |
| P02-C008 | 2.2; mechanism | `confirmed`: изменение суммы authorization и продление её срока — различные операции; результат влияет на исходную операцию по правилам маршрута | P02-S040 / P02-S040-20260915, Adjust amount; Extend authorization | Нельзя обобщать, что после любой неудачной extension исходный hold обязательно остаётся |
| P02-C009 | 2.1,2.3; definition | `confirmed`: PFMI требует ясной точки окончательности расчёта | P02-S001 / P02-S001-20260915, Principle 8, key considerations 1–3 | Нормативный принцип FMI, а не заявление о фактической архитектуре каждой схемы |
| P02-C010 | 2.3; mechanism | `confirmed`: в direct debit получатель инициирует collection на основании предварительного mandate | P02-S010 / P02-S010-20260915, A different scheme; creditor-driven mandate | Описан SEPA; другой rail может иметь другую форму/хранителя authorization |
| P02-C011 | 2.3; mechanism | `confirmed`: SEPA SDD Core допускает no-questions refund восемь недель и запрос для unauthorized collection до 13 месяцев | P02-S010 / P02-S010-20260915, Main differences, refund bullets | Scope Core, отсчёт от debit; не переносить на A2A credit transfer или весь B2B |
| P02-C012 | 2.3; mechanism | `confirmed`: SDD B2B не даёт того же права refund по авторизованной операции; mandate проверяет payer PSP | P02-S010 / P02-S010-20260915, Main differences, B2B bullets | Не означает отсутствия всех returns/правовых средств защиты |
| P02-C013 | 2.3; mechanism | `confirmed`: ACH reversal в объяснении Nacha ограничен ошибками отправителя и пятибанковским сроком после settlement | P02-S008 / P02-S008-20260915, right time; timing; what reversals cannot be used for | US ACH; scam recovery не произвольная reversal; при отсутствии средств возврат может не исполниться |
| P02-C014 | 2.3; mechanism | `confirmed`: Faster Payments customer availability 24/7 и межбанковский net settlement по графику RTGS — разные события | P02-S006 / P02-S006-20260915, Faster Payments Service; How does net settlement work | На прочитанной странице три цикла в business day; расписание требует обновления перед выпуском |
| P02-C015 | 2.3; mechanism | `confirmed`: FPS prefunding ограничивает максимальное обязательство участника заранее внесёнными средствами | P02-S006 / P02-S006-20260915, Prefunded net settlement | Не приравнивать к merchant reserve или конкретному sponsor-program deposit |
| P02-C016 | 2.3; mechanism | `confirmed`: FedNow разделяет settlement, новый return transfer и nonvalue request | P02-S042 / P02-S042-20260917, §§2.39,7.1,9.1.16,9.6–9.8 | Effective01.04.2026; checked17.09.2026; исторический S007 не опора текущего статуса; доступ конечного клиента не доказан |
| P02-C017 | 2.3; mechanism | `confirmed`: SCT Inst landing page на дату чтения обозначает rulebook 2025 v1.1 текущим и описывает десятисекундный timeline | P02-S009 / P02-S009-20260915, Current rulebook; Regulatory changes | Полный rulebook не прочитан; точные recall deadlines не выводятся из summary |
| P02-C018 | 2.3; mechanism | `confirmed`: correspondent banking использует счета банков друг у друга; nostro/vostro — разные точки зрения на отношения счёта | P02-S035 / P02-S035-20260915, correspondent banking description; P02-S043 / P02-S043-20260917-deep, §7010.1 Vostro account, PDFp30 | Не доказательство маршрута конкретного перевода; chain fees/FX в главе синтетические |
| P02-C019 | 2.3; mechanism | `confirmed`: передача сообщения Swift и действия банка получателя по зачислению разделены | P02-S011 / P02-S011-20260915, How does Swift work | Доставленное сообщение не подтверждает beneficiary balance/fulfillment |
| P02-C020 | 2.3; definition | `confirmed`: ISO20022 catalogue содержит message definitions, MDR/MUG, schemas, иногда примеры | P02-S012 / P02-S012-20260915, Which documents can I download | Не равно доступу к банковскому счёту или сертификации XSD |
| P02-C021 | 2.3; definition | `confirmed`: pain.001 — CustomerCreditTransferInitiation; camt.053 — BankToCustomerStatement | P02-S039 / P02-S039-20260915, Payments Initiation; Bank-to-Customer Cash Management | Имена/семейства проверены, полные схемы не прочитаны; версии банка могут отличаться от последних в каталоге |
| P02-C022 | 2.3; mechanism | `confirmed`: в Fedwire pacs.002/PDNG промежуточен; следующий статус ACSC или RJCT завершает pending согласно FAQ | P02-S013 / P02-S013-20260915, FAQ PDNG | Scope Fedwire; ACSC не подтверждает исполнение коммерческого товара |
| P02-C023 | 2.3; mechanism | `confirmed`: camt.056 в Fedwire запрашивает return ранее settled value message | P02-S013 / P02-S013-20260915, FAQ return of funds | Запрос не гарантирует исполненный возврат |
| P02-C024 | 2.3; product | `confirmed`: в историческом UK OB domestic-payment-consent Consumed не отражает статус самого платежа | P02-S014 / P02-S014-20260915, State Model: Consumed | Исторический example v3.1.2/page-path3.1.3; не утверждается current mandatory profile |
| P02-C025 | 2.3; definition | `confirmed`: FAPI2 Security Profile регулирует защищённое получение/использование OAuth tokens, а не платёжный settlement | P02-S015 / P02-S015-20260915, §1 Scope; §5 | General-purpose final standard; adoption каждым банком не доказан |
| P02-C026 | 2.3,2.5; legal | `confirmed`: PSR guidance описывает локальный UK APP reimbursement с 07.10.2024 до GBP85000 для допустимых клиентов/переводов | P02-S016 / P02-S016-20260915, protections; eligibility; exclusions | Eligibility реального требования не установлена; civil dispute не автоматически scam; география не глобальна |
| P02-C027 | 2.4; definition | `confirmed`: Visa различает межбанковский interchange и merchant discount, согласованный продавцом с финансовым провайдером | P02-S017 / P02-S017-20260915, interchange/merchant discount explanation | US Visa context; синтетические тарифы главы не официальные schedule rates |
| P02-C028 | 2.4; product | `confirmed`: отчёты Adyen различают interchange, scheme fees и markup | P02-S018 / P02-S018-20260915, Payment method fees | Видимость расходов не гарантирует экономию; отсутствует независимая сравнительная оценка PSP |
| P02-C029 | 2.5; mechanism | `confirmed`: 3DS challenge требует дополнительного взаимодействия с ACS; frictionless может пройти без него | P02-S037 / P02-S037-20260915, Business Overview; P02-S041 / P02-S041-20260915, Business Overview | Аутентификация не тождественна approval/settlement; маркетинговые efficacy claims не заимствуются |
| P02-C030 | 2.5; product | `confirmed`: 3DS liability shift в описании Stripe относится к подходящим fraud-disputes и имеет исключения | P02-S020 / P02-S020-20260915, Disputes and liability shift | Нельзя распространять на недоставку; подтверждать конкретную операцию, данные и правила |
| P02-C031 | 2.5; mechanism | `confirmed`: временная проверка fraud ML должна учитывать задержку labels и drift | P02-S021 / P02-S021-20260915, Validation strategies introduction/hold-out | Методологический вывод академического handbook; модель на данных магазина не тестировалась |
| P02-C032 | 2.5; empirical | `confirmed`: EBA/ECB на данных EU/EEA 2022–2024 сообщает меньшие fraud rates для SCA-authenticated card payments в целом и отличающийся рисунок для credit transfers | P02-S022 / P02-S022-20260915, Executive Summary pp.6–7 | Наблюдательная связь, selection/transaction mix; не индивидуальный причинный эффект 3DS |
| P02-C033 | 2.5; empirical | `confirmed`: по тому же отчёту манипуляция плательщиком составляет более половины стоимости fraudulent credit transfers | P02-S022 / P02-S022-20260915, Executive Summary p.6 | Конкретные период/география/метрика value; не доля всех платежей и не мировая оценка |
| P02-C034 | 2.6; product | `confirmed`: refund может pending/failed и нуждается в отдельном tracing; cancellation до capture — другой процесс | P02-S033 / P02-S033-20260915, pending/failed refunds; cancel; tracing | Scope Stripe methods, без общего SLA и без утверждения реального зачисления |
| P02-C035 | 2.6; mechanism | `confirmed`: chargeback распределяет финансовую ответственность через reason-based workflow; second presentment, pre-arbitration и arbitration имеют условия | P02-S003 / P02-S003-20260915, §§3,5 pp.6–11 | Упрощённая учебная схема; не замена полного Chargeback Guide |
| P02-C036 | 2.6; product | `confirmed`: Stripe отдельно дебетует сумму спора и fee; обычный refund во время открытого dispute ограничен | P02-S036 / P02-S036-20260915, Receive a dispute; Dispute fees | Тариф/возвратность fees зависят от договора/страны; учебные USD15 не текущий тариф Stripe |
| P02-C037 | 2.7; mechanism | `confirmed`: dual-message разделяет authorization/clearing, single-message объединяет данные этих стадий в одном financial format | P02-S003 / P02-S003-20260915, §2.2 p.5 | Single-message не значит один сетевой пакет и не отменяет settlement; debit/credit не глобальное соответствие |
| P02-C038 | 2.7; mechanism | `confirmed`: MTI, bitmap и названные DE имеют описанные назначения в Worldpay V2.63 | P02-S024 / P02-S024-20260915, §1.2 p.6; Chapter5 pp.236,241,248,255,276–278,302,310 | Только опубликованный профиль; синтетический trace не wire-compatible fixture; ISO original не прочитан |
| P02-C039 | 2.7; product | `confirmed`: Adyen raw mapping различает 05 general refusal, 51 insufficient funds и Mastercard 65 authentication required | P02-S023 / P02-S023-20260915, Visa/Mastercard raw responses | Код 65 не универсален для всех сетей/профилей; нельзя придумывать issuer cause по 05 |
| P02-C040 | 2.7; mechanism | `confirmed`: Mastercard clearing requirements требуют acknowledgements, исправления rejects и сверки с net settlement advisement | P02-S002 / P02-S002-20260915, §2.18.1 pp.68–69 | Обязанности участника схемы, не гарантия, что конкретный PSP выполнил их |
| P02-C041 | 2.8; product | `confirmed`: Google Pay Web PAN_ONLY и CRYPTOGRAM_3DS связаны с разными источниками credentials | P02-S025 / P02-S025-20260915, CardParameters.allowedAuthMethods | Нельзя утверждать network/device token для каждого Google Pay-платежа |
| P02-C042 | 2.8; product | `confirmed`: Apple описывает DAN и уникальный security code для указанного карточного Apple Pay flow | P02-S026 / P02-S026-20260915, payment processing after authentication | Не обобщать на все wallet/все режимы доступа и liability |
| P02-C043 | 2.8; product | `confirmed`: Google PaymentMethodToken — подписанный/зашифрованный конверт, содержащий PAN либо device PAN с криптограммой | P02-S027 / P02-S027-20260915, overview ECv2 | API token envelope не обязательно EMV Payment Token; прямое decrypt меняет data/security scope |
| P02-C044 | 2.8; mechanism | `confirmed`: PCI scope исключение для корректного EMV Payment Token вне TSP environment не снимает scope PAN/connected systems | P02-S028 / P02-S028-20260915, Applicability of PCI DSS | Оценка среды конкретного продавца не проводилась |
| P02-C045 | 2.8; mechanism | `confirmed`: QRIS допускает MPM/CPM; PJP/switching processing требует предварительного разрешения BI | P02-S029 / P02-S029-20260915, Para Pihak; Karakteristik | QR интерфейс не самостоятельная лицензия и не доказательство доступа foreign PSP |
| P02-C046 | 2.8; product | `confirmed`: BI page показывает MDR0.7% для UKE/UME/UBE, с иными micro/special categories | P02-S029 / P02-S029-20260915, Skema Tarif QRIS | As-of15.09.2026; категория конкретного кафе не установлена, её принадлежность задана синтетически |
| P02-C047 | 2.8; definition | `confirmed`: CFPB2022 определяет исследуемый pay-in-four как кредит с четырьмя взносами, обычно 25% первым | P02-S030 / P02-S030-20260915, §2.1 p.6 | Исторический scope исследования; не вся мировая BNPL и не текущая legal classification |
| P02-C048 | 2.8; product | `confirmed`: Klarna имеет отдельную refund operation, успешный запрос возвращает refund_id | P02-S031 / P02-S031-20260915, full/partial refund; Success response | API receipt недостаточен для полного результата borrower/merchant settlement |

## Социальный кейс, открытые вопросы и отклонённые обобщения

| claim_id | module_id; kind/status | Тезис | Evidence / locator | Редакционное решение |
|---|---|---|---|---|
| P02-C049 | 2.3; experience, `confirmed` только как факт публикации | Consistent-Virus-959 описывает проблему XSD-valid pain.001, который не принимает отдельный банковский профиль | P02-S032 / P02-S032-20260915, main post intro/layered validation | Авторский опыт и конкретные банки не верифицированы; используется постановка вопроса, не статистика инцидентов. В конце поста автор продвигает свой validator/explainer (повторно прочитано17.09.2026, P02-S032-20260917) |
| P02-C050 | 2.5; legal, `open` | Точные действующие на15.09.2026 thresholds и cumulatives для SCA exemptions по консолидированному RTS | P02-S038 / P02-S038-20260915, metadata only, relation=context | Прямой текст не получен; главой не выдаётся юридическая таблица по snippets |
| P02-C051 | 2.8; product, `open` | Допустима конкретная комбинация BNPL и crypto-in у конкретного провайдера | Evidence absent; P02-S030/P02-S031 лишь context | Ни поддержка, ни разрешение, ни реальная оплата не заявляются |
| P02-C052 | 2.7; empirical, `open` | Синтетический decline/capture trace отражает реально произошедший live платёж | Evidence absent | Такой вывод прямо запрещён маркировкой примера; нужны разрешённые фактические логи для реального кейса |
| P02-C053 | 2.1–2.8; hypothesis, `rejected` | Успешная авторизация/callback доказывает merchant payout и исполнение заказа | P02-S003/P02-S005/P02-S007/P02-S013/P02-S014/P02-S036, relation=contradicts, locators выше | Разделены стадии и объекты; только соответствующее внешнее подтверждение отвечает на конкретный вопрос |
| P02-C054 | 2.3; hypothesis, `rejected` | Любой instant payment означает немедленный межбанковский gross settlement | P02-S006 / P02-S006-20260915, FPS/Net settlement, relation=contradicts | UK FPS — конкретный контрпример; не универсализировать его устройство обратно на FedNow |
| P02-C055 | 2.5; hypothesis, `rejected` | 3DS делает невозможными любые потери продавца по dispute | P02-S020 / P02-S020-20260915, liability shift exclusions, relation=contradicts | Fraud-liability coverage ограничена; доставка/возврат остаются самостоятельными обязательствами |
| P02-C056 | 2.8; hypothesis, `rejected` | Wallet token всегда означает network token и автоматически выводит всю среду из PCI | P02-S025/P02-S027/P02-S028, locators выше, relation=contradicts | Проверять credential mode, реальные данные и connected environment |
| P02-C057 | 2.8; hypothesis, `rejected` | BNPL — это только карточный delayed capture | P02-S030 / P02-S030-20260915 §2.1; P02-S004 / P02-S004-20260915 manual capture; relation=contradicts | Кредитор, funding, underwriting и график погашения отличают экономическую модель |

## Собственный синтез и арифметика

Синтетические числа не являются empirical claims. Проверены отдельно:

- 80 × 2.9% + 0.30 = 2.62 USD; 80 − 2.62 = 77.38.
- Трёхсторонний netting100/90/80 даёт позиции−20/+10/+10; сумма0.
- FX1000 EUR ×1.10 −10 −5 =1085 USD.
- Processing100 ×2.9% +0.30 =3.20; 1.70+0.25+1.25=3.20.
- Risk case: precision80/380=21.05%; recall80/100=80%; FPR300/9900=3.03%; 8000−7500=500 USD до дополнительных издержек.
- Dispute case: 96.80−100−15=−18.20; после возврата100 при невозвращаемой fee итог81.80.
- QRIS example:150000 ×0.7%=1050 IDR; net148950 IDR.
- BNPL example:200−10=190 merchant payout;190−50=140 initial funding gap; future principal receipts150.
- Упражнения: netting200/140/90 →−110/+60/+50; total costs320+75+50=445 USD;445/10000=4.45%; precision40/200=20%, recall40/50=80%.

Синтез о выборе rail и практические схемы расследования — учебные методы, выведенные из различий подтверждённых механизмов; они не являются юридическим advice, ценовым предложением или product-readiness verdict. Охват независимой проверки карточек и ограничения описаны в REVIEW.md (исторический или служебный материал; сохранен у владельца, вне этой копии).
