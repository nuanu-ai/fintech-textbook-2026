---
title: "Часть 5 — реестр существенных утверждений"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Публичная редакция от 18.09.2026. Даты проверки и ограничения источников сохранены. Хеши в исторических аудитах относятся к исходной рукописи; публичные изменения и текущие хеши — в [паспорте издания](../../edition.md).

# Часть 5 — реестр существенных утверждений

**Версия:** v0.1. **Статус:** independently_reviewed_draft. **Автор:** part_05_research. **Срез знаний:** 15.09.2026. Первая рецензия: см. REVIEW.md (исторический или служебный материал; сохранен у владельца, вне этой копии).

Фактчек исходной редакции завершен17.09.2026. Связь исходной версии с публичной копией, область адаптации и текущая навигация описаны в паспорте издания.

## Как читать реестр

Все строки наследуют `as_of=2026-09-15`, `last_checked_at=2026-09-15, Asia/Makassar (UTC+08:00)`, `reviewer=see_REVIEW.md`, `review_status=see_REVIEW.md`. `confirmed` означает подтверждение **в указанной области**, а не одобрение внедрения или универсальность вывода. Для ненормативных тезисов `effective_from/to=not_applicable`; неизвестная дата договора/правила обозначается `unknown`.

В evidence указан источник, snapshot и точный раздел; полные прямые URL, реальный объём чтения, метод доступа и права находятся в [SOURCES.md](sources.md). `supports` означает поддержку тезиса, `context` — основание для явно авторского вывода, `contradicts` — опровержение сформулированного мифа. Упрощённые расчёты главы — синтетические сценарии, а не эмпирические данные провайдеров.

**Общее основание уверенности:** прочитанный релевантный фрагмент первичного документа; для социальных свидетельств — только факт опубликованного высказывания, для академического кейса — результат авторов в исторической постановке. Продуктовые документы одной компании не являются независимыми подтверждениями качества её исполнения. Общий триггер повторной проверки: изменение нормы, документа, программы, API, юрисдикции или новая редакция главы. Особые триггеры указаны ниже.

## 5.1 Типы кошельков и счетов

| claim_id / module_ids | claim / kind / status | evidence + locator + relation | Scope, условия и ограничения |
|---|---|---|---|
| P05-C001 · 5.1 | EU e-money представляет требование к эмитенту и определяется совокупностью признаков выпуска и использования. `definition; confirmed` | P05-S001 · P05-S001-20260915 · Final answer, EMD2 Art. 2(2), C-661/22 §§47–48 · supports | EU; Q&A final 17.01.2025. Прочитан ответ через индекс; это разъяснение, не полный действующий национальный закон. Дата действия самой нормы отдельно не проверена. |
| P05-C002 · 5.1 | Классификация payment account зависит от платёжной функции; reference account сам по себе вопрос не решает. `definition; confirmed` | P05-S002 · P05-S002-20260915 · Final answer, PSD2 Art. 4(5),(12), C-191/17 · supports | EU; Q&A final 12.03.2021. Не определяет лицензию конкретного оператора. |
| P05-C003 · 5.1 | Gift card может быть open-loop; её защиты могут отличаться от обычного prepaid-продукта. `legal; confirmed` | P05-S003 · P05-S003-20260915 · Card types; open-loop/closed-loop; protections · supports | US consumer guidance. Не переносится на любую территорию и любой подарочный сертификат. |
| P05-C004 · 5.1 | ERC-4337 использует UserOperation, bundler и EntryPoint; правила проверки задаёт реализация аккаунта. `mechanism; confirmed` | P05-S009 · P05-S009-20260915 · Abstract; Motivation; Definitions; account context · supports | Спецификация с отображённым статусом Final. Дата Final и commit неизвестны; конкретный deployment не проверен. |
| P05-C005 · 5.1 | Для идентификации поддерживаемого токена нужны сеть и сетевой идентификатор, а не только название USDC. `mechanism; confirmed` | P05-S028 · P05-S028-20260915 · Introduction; Mainnet/Testnet contract tables · supports | Circle публикует разные идентификаторы. Это не доказательство поддержки конкретным ramp, redemption или резерва. |

## 5.2 Контроль ключей и остатка

| claim_id / module_ids | claim / kind / status | evidence + locator + relation | Scope, условия и ограничения |
|---|---|---|---|
| P05-C006 · 5.2 | Пороговая подпись может создаваться без восстановления полного ключа в одной точке. `mechanism; confirmed` | P05-S008 · P05-S008-20260915 · Executive Summary, PDF p.7; §1, PDF p.10 · supports | Модель threshold cryptography NISTIR 8214A, 2020. Не утверждение о любой реализации MPC. |
| P05-C007 · 5.2 | Криптографический порог сам по себе не определяет юридическое custody и независимость администраторов. `mechanism; confirmed` | P05-S008 · P05-S008-20260915 · §2.5 Auditability, printed p.10/PDF p.19 · context; P05-S012 · P05-S012-20260915 · §§72–75 · context | Авторский вывод из различия модели угроз и функционального правового подхода. Национальная квалификация требует собственного анализа. |
| P05-C008 · 5.2 | Privy custodial `owner` не получает права единолично транзакционировать без хранителя или экспортировать ключ. `product; confirmed` | P05-S010 · P05-S010-20260915 · Meaning of owner for custodial wallets · supports | Только описанный custodial-продукт Privy; другие wallet types не обобщаются. Дата/версия страницы unknown. |
| P05-C009 · 5.2 | Fireblocks описывает отдельные средства восстановления Vault, включая сценарий остановки поставщика. `product; confirmed` | P05-S011 · P05-S011-20260915 · Overview; Recovery Tools · supports | Публичное описание Direct Custody/Vault. Наличие и успешный тест recovery kit конкретного клиента не подтверждены. |
| P05-C010 · 5.2 | Возможность совместного контроля не исключает VASP-квалификации по руководству FATF. `legal; confirmed` | P05-S012 · P05-S012-20260915 · §§72–75, footnote 20, printed p.29/PDF pp.30–31 · supports | Международное руководство 2021, не национальный закон. Publisher предупреждает о последующих обновлениях стандартов; числовые пороги из него не переносятся. |
| P05-C011 · 5.2 | FDIC страхует соответствующий депозит при банкротстве банка, а не само банкротство небанковского приложения. `legal; confirmed` | P05-S004 · P05-S004-20260915 · fintech/nonbank insolvency and placement paragraphs · supports | US FDIC; условия фактического размещения и покрытия должны выполняться. Direct fetch 403, прочитано индексное представление. |
| P05-C012 · 5.2 | Pass-through требует фактического владения principal, отражённой агентской связи и надлежащего реестра владельцев/долей. `legal; confirmed` | P05-S005 · P05-S005-20260915 · §III Requirements for Pass-through Deposit Insurance Coverage · supports | US; источник ссылается на 12 CFR 330.5/330.7. Прочитан содержательный раздел через индекс; конкретная схема не проверена. |
| P05-C013 · 5.2 | Pass-through не создаёт отдельную категорию страхования: позиции одного владельца в одной категории и банке агрегируются. `legal; confirmed` | P05-S005 · P05-S005-20260915 · §V Aggregation of Deposits · supports | В примерах — single-account category и лимит 250 000 USD. Иные категории не моделируются. |
| P05-C014 · 5.2 | UK safeguarding у небанковских PSP отличается от непосредственного FSCS-покрытия при их несостоятельности. `legal; confirmed` | P05-S006 · P05-S006-20260915 · How you're protected; How safeguarding works; How to make a claim · supports | UK EMI/API и оговорки для SPI; возможны задержка и расходы процедуры. Не заключение о конкретном банкротстве. |
| P05-C015 · 5.2 | Supplementary safeguarding regime из FCA PS25/12 начал действовать 07.05.2026. `legal; confirmed` | P05-S007 · P05-S007-20260915 · Next steps; Who this applies to · supports | UK перечисленные категории; `effective_from=2026-05-07`, `effective_to=unknown`. Будущий Post-Repeal Regime не объявлен уже действующим. |
| P05-C016 · 5.2 | MiCA требует юридического и операционного обособления клиентских crypto-assets при custody в сфере статьи 75. `legal; confirmed` | P05-S013 · P05-S013-20260915 · Art. 75(7); Art. 149; Art. 143(3) · supports | EU MiCA CASPs. Общее применение 30.12.2024; национальный переход мог закончиться раньше общего предела 01.07.2026. Не доказательство исполнения отдельным CASP. |
| P05-C017 · 5.2 | Ответственность MiCA custody за утрату связана с относимым к CASP инцидентом и ограничена рыночной стоимостью в момент утраты. `legal; confirmed` | P05-S013 · P05-S013-20260915 · Art. 75(8) · supports | EU, конкретная статья. Не депозитная страховка и не защита от падения цены. Причинность конкретного инцидента не исследовалась. |
| P05-C018 · 5.2 | «MPC автоматически означает non-custodial и регулируемую защиту активов». `hypothesis; rejected` | P05-S008 · P05-S008-20260915 · §1, §2.5 · contradicts; P05-S010 · P05-S010-20260915 · Meaning of owner · contradicts; P05-S012 · P05-S012-20260915 · §§72–75 · contradicts | Миф смешивает механизм подписи, фактический контроль и правовой режим; единого следствия нет. |

## 5.3 On-ramp / off-ramp

| claim_id / module_ids | claim / kind / status | evidence + locator + relation | Scope, условия и ограничения |
|---|---|---|---|
| P05-C019 · 5.3 | Coinbase может разрешать торговлю на средства с hold, сохраняя ограничение внешней отправки/вывода. `product; confirmed` | P05-S014 · P05-S014-20260915 · Cash deposits on hold; Sends and withdrawals after a deposit hold clears · supports | Описанные Coinbase account flows. Срок конкретного пользователя не известен; не self-custody protocol. |
| P05-C020 · 5.3 | Coinbase Offramp Quote — оценка, которая не гарантирует фактическую цену исполнения. `product; confirmed` | P05-S015 · P05-S015-20260915 · Offramp Quote; Limitations · supports | Конкретный quote API; страна, asset/network и метод входят в условия. Не вывод о любом RFQ/rate-lock продукте. |
| P05-C021 · 5.3 | EBA Travel Rule guidance описывает сведения об отправителе/получателе и обработку отсутствующих данных. `legal; confirmed` | P05-S016 · P05-S016-20260915 · основной анонс; Background; Legal basis · supports | EU PSP/CASP в названной сфере; дата применения руководства 30.12.2024. Основной PDF не прочитан: пороги и подробные процедуры не заявлены. |
| P05-C022 · 5.3 | On/off-ramp требует раздельно учитывать funding, обмен, доступность вывода и конечное получение. `mechanism; confirmed` | P05-S014 · P05-S014-20260915 · Hold periods · context; P05-S015 · P05-S015-20260915 · Request/Response fields, Limitations · context | Авторская модель состояний; поставщик может объединять или предфинансировать этапы. Пример не является аудитом его реализации. |

## 5.4 Refunds и reversibility

| claim_id / module_ids | claim / kind / status | evidence + locator + relation | Scope, условия и ограничения |
|---|---|---|---|
| P05-C023 · 5.4 | Окончательность исходного расчёта сама по себе не прекращает отдельно возникшее возвратное обязательство. `mechanism; confirmed` | P05-S031 · P05-S031-20260915 · Right of withdrawal; Exceptions · context; P05-S017 · P05-S017-20260915 · Return options · context | Авторский синтез различия права требования и способа исполнения. Основание, валюта, сумма и допустимость возврата в токене определяются отдельно. |
| P05-C024 · 5.4 | Digital content не является универсальным исключением из EU права отказа: существенны условия согласия и исполнения. `legal; confirmed` | P05-S031 · P05-S031-20260915 · Exceptions, digital content / fully delivered services · supports | EU consumer guidance, last checked 28.04.2026; не полный текст директивы и не заключение по договору. |
| P05-C025 · 5.4 | SCT Request for Recall by the Originator не гарантирует возврат и зависит от согласия получателя. `legal; confirmed` | P05-S018 · P05-S018-20260915 · 2025 v1.1 §4.3.2.4, printed/PDF p.35 · supports | SEPA SCT EUR; `effective_from=2025-10-05`, `effective_to=unknown`. Не все разновидности Recall/return и не любые bank rails. |
| P05-C026 · 5.4 | Исходящий Coinbase sending address не обязательно принадлежит клиенту и не является безопасным автоматическим refund destination. `product; confirmed` | P05-S017 · P05-S017-20260915 · warning; Return options · supports | Переводы из Coinbase account по описанной модели; поддерживаемый новый адрес ещё требует проверки полномочия на возврат. |
| P05-C027 · 5.4 | McCorry et al. исследовали недостаточную аутентификацию возвратных реквизитов в историческом Bitcoin Payment Protocol. `empirical; confirmed` | P05-S026 · P05-S026-20260915 · §§2.2–3, §4 experiments, §§5–5.2, §6 · supports | Авторская версия 2016/024, BIP70/процессы периода исследования. Не оценка нынешней уязвимости, частоты потерь или всей отрасли. |
| P05-C028 · 5.4 | Доказательство контроля нового адреса само по себе не доказывает право на возврат по прежнему заказу. `mechanism; confirmed` | P05-S026 · P05-S026-20260915 · §§5–5.2, linkage/authentication discussion · context | Авторский defensive-вывод: нужна связь principal↔order↔instruction. Не предписание единственного технического способа идентификации. |
| P05-C029 · 5.4 | Автор Reddit сообщил о длительно pending Coinbase Card refunds; участники спорили о маршруте поддержки. `experience; confirmed` | P05-S027 · P05-S027-20260915 · original post u/RandyMachoManSavage; initial comments u/radman430, u/OhmazingJ · supports | Подтверждён опубликованный рассказ, не виновность/причина. День 16.07.2024 выведен из архивной навигации; комментарии только «2y ago». |
| P05-C030 · 5.4 | Stripe описывает возможность двойного зачисления при refund и параллельном dispute банковского debit-платежа. `product; confirmed` | P05-S030 · P05-S030-20260915 · Bank debit payment methods · supports | Конкретные Stripe rails. Синтетический пример 80+80 не статистика и не универсальный порядок списания дубля. |
| P05-C031 · 5.4 | Card refund у Stripe может ожидать достаточного available balance; reference нужен для поиска, но не заменяет сверку получателя. `product; confirmed` | P05-S030 · P05-S030-20260915 · Refund requests; Trace a refund · supports/context | Первая часть — описание продукта; требование сверки — авторский контроль результата. Universal refund SLA не установлен. |

## 5.5 Issuing и жизненный цикл карточного продукта

| claim_id / module_ids | claim / kind / status | evidence + locator + relation | Scope, условия и ограничения |
|---|---|---|---|
| P05-C032 · 5.5 | Stripe processor-only не использует центральный Issuing Balance; программа и sponsor организуют funding и расчётный счёт. `product; confirmed` | P05-S022 · P05-S022-20260915 · Overview; program/funding responsibilities; BIN sponsor settlement · supports | Только processor-only конфигурация. Не переносить модель на интегрированный Issuing. Доступность договора для нового клиента не проверена. |
| P05-C033 · 5.5 | VisaNet Connect Issuing описывает отдельные возможности для authorization, completion, return и provisioning. `product; confirmed` | P05-S025 · P05-S025-20260915 · How it Works; APIs Used · supports | Официальный overview, не полный Visa rulebook/доступ к закрытым спецификациям. Capability не означает одобрение программы. |
| P05-C034 · 5.5 | Доступное US Coinbase Card Agreement называет Pathward эмитентом, Marqeta program manager и продукт prepaid. `product; confirmed` | P05-S019 · P05-S019-20260915 · short form; definitions; §1, PDF pp.1–2 · supports | US personal/family/household программа. Дата, редакция и effective unknown; подписанный договор конкретного пользователя не проверен. |
| P05-C035 · 5.5 | Debit в Coinbase Help и prepaid в договоре описывают данный продукт с разных сторон. `definition; confirmed` | P05-S032 · P05-S032-20260915 · opening; issuer disclosure · context; P05-S019 · P05-S019-20260915 · §1 · context | Видимое расхождение терминов разрешено через конкретный договор, без вывода о депозитном счёте. Не Coinbase One credit и не мировая классификация. |
| P05-C036 · 5.5 | Stripe Issuing поддерживает hold и incremental/partial authorization; окончательная сумма может отличаться. `product; confirmed` | P05-S020 · P05-S020-20260915 · Authorization lifecycle; partial/incremental authorization; currency conversion · supports | API states table — 2025-03-31.basil и новее. Учебная проводка не тождественна API object или network settlement. |
| P05-C037 · 5.5 | Marqeta Gateway JIT даёт программе участие в финансировании операции; результат нужно сверять по уведомлениям. `product; confirmed` | P05-S023 · P05-S023-20260915 · Concepts/JIT Funding · supports; P05-S024 · P05-S024-20260915 · JIT Funding notifications · supports | Gateway JIT; локальный approve может не дойти до процессора. Не необеспеченная кредитная линия и не общая модель всех issuing. |
| P05-C038 · 5.5 | Card status и spending controls Stripe Issuing не применяются к последующему capture. `product; confirmed` | P05-S021 · P05-S021-20260915 · introduction, capture controls note · supports | Stripe Issuing; freeze не отменяет ранее возникшее денежное обязательство. Другие процессоры требуют проверки правил. |
| P05-C039 · 5.5 | Stripe Issuing может принимать refunds на inactive/canceled карты. `product; confirmed` | P05-S021 · P05-S021-20260915 · Handling other transactions: Refunds · supports | Описанная возможность не гарантирует корректный банковский/внутренний маршрут любого реального возврата. |
| P05-C040 · 5.5 | Stripe replacements по lost/stolen дают новые реквизиты; ранее открытые authorizations могут завершаться на исходной карте. `product; confirmed` | P05-S029 · P05-S029-20260915 · replacement scenarios; All replacements · supports | Только описанный продукт. Expired/damaged и card-on-file updates имеют другие условия; фактическая доставка не проверена. |
| P05-C041 · 5.5 | Закрытие Coinbase Card по прочитанному §10(b) сохраняет ранее возникшие права и обязательства. `legal; confirmed` | P05-S019 · P05-S019-20260915 · §10(b), PDF p.5 · supports | Тот же доступный US договор; effective unknown. Не доказательство версии, применявшейся к автору Reddit в 2024. |
| P05-C042 · 5.5 | Coinbase Wallet в этом договоре — определённый связанный счёт; слово не доказывает self-custody. `definition; confirmed` | P05-S019 · P05-S019-20260915 · definitions, PDF pp.1–2; §9(b), PDF p.5 · supports | В пределах US agreement. Туда передаётся полученный card refund; не любой Coinbase-аккаунт или одноимённое приложение. |

## Открытые границы и авторские модели

| claim_id / module_ids | claim / kind / status | evidence + locator + relation | Scope, условия и дальнейшая проверка |
|---|---|---|---|
| P05-C043 · 5.4 | Предложенная модель состояний refund помогает не закрывать долг до проверки исполнения. `hypothesis; working_hypothesis` | P05-S030 · P05-S030-20260915 · events; failed refunds; tracing · context; P05-S026 · P05-S026-20260915 · §§5–5.2 · context | Авторский учебный контроль; не доказанная универсальная эффективность. Проверяется на тестовых сценариях дубля, unknown и частичного возврата. |
| P05-C044 · 5.2, 5.5 | Доступность и успешное восстановление конкретного custody/issuing продукта для конкретного пользователя не установлены. `product; open` | P05-S011 · P05-S011-20260915 · Recovery Tools · context; P05-S022 · P05-S022-20260915 · setup/program responsibilities · context | Публичные документы не заменяют применимый договор, проверку eligibility и техническое испытание. Реальные операции в исследование не входили. |

## Дополнение к 5.3 после согласования частей

| claim_id / module_ids | claim / kind / status | evidence + locator + relation | Scope, условия и ограничения |
|---|---|---|---|
| P05-C045 · 5.3 | Circle France предусматривает отдельный путь redemption для EEA Retail Holders через форму и проверки. `product; confirmed` | P05-S033 · P05-S033-20260917 · §§1.4, 2.1–2.3, 3 · supports | При чтении17.09 policy помечена15.09.2026; ранее автор записал13.07, исторический snapshot отсутствует. EEA IBAN и eligibility существенны. Не worldwide institutional-only rule и не подтверждение исполнения конкретного запроса. |

## Авторская проверка перед передачей

Проверены соответствие module IDs, связность идентификаторов источников, прямые ссылки в главе и арифметика синтетических примеров. Свидетельства Reddit не используются для вывода о причине сбоя; историческая статья не объявляется современным vulnerability assessment. Неразрешённого противоречия, скрытого универсальным правовым выводом, не оставлено; названия debit/prepaid и ограничения доступа указаны явно. Независимый reviewer должен повторно оценить соответствие тезисов прочитанным местам и достаточность доступа; автор не ставит себе `checked`.
