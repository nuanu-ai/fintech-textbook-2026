---
title: "Реестр существенных утверждений — часть 4"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Публичная редакция от 18.09.2026. Даты проверки и ограничения источников сохранены. Хеши в исторических аудитах относятся к исходной рукописи; публичные изменения и текущие хеши — в [паспорте издания](../../edition.md).

# Реестр существенных утверждений — часть 4

**Версия:** v0.1 · **Срез и last_checked_at:** 15.09.2026 · **Статус рукописи:** `independently_reviewed_draft` · **Автор:** `part_04_research` · private.

Фактчек исходной редакции завершен17.09.2026. Связь исходной версии с публичной копией, область адаптации и текущая навигация описаны в паспорте издания.

`confirmed` ниже означает подтверждение в точно указанной области источника, не независимую приёмку всей главы. Для всех строк `reviewer=see_REVIEW.md`, `review_status=see_REVIEW.md`; независимую проверку автор себе не присваивает. Полные карточки и права — [SOURCES.md](sources.md). `snapshot_id` в каждой ссылке имеет суффикс `-20260915`; это дата чтения, не хеш сохранённой копии. Сокращённая ссылка вида P04-S019 разрешается в P04-S019-20260915 и соответствующую карточку SOURCES; это правило действует также для context references.

Общие поля: `as_of=2026-09-15`; `last_checked_at=2026-09-15 Asia/Makassar`; `review_trigger=изменение документа, продукта, деятельности, географии или договора`. Для guide/product `effective_from/to=not_applicable`; для нормативного/договорного содержания действуют точные оговорки соответствующей карточки, неизвестное не заменено датой чтения. Ключи `module_id`, `kind`, `scope`, `status`, `evidence+locator`, `limitations/conflicts` указаны в каждой строке. `relation=supports`, если явно не указано иное. Синтетические суммы не являются эмпирическими claims: их арифметика проверена отдельно в конце.

## 4.1 Классификация

| Claim ID | Kind / статус / scope | Утверждение | Evidence: snapshot + locator | Ограничения и reasoning |
|---|---|---|---|---|
| P04-C001 | kind=definition; status=rejected; module_id=4.1; commercial role versus regulated activity | «PSP, PayFac и MoR — взаимозаменяемые юридические лицензии» | [P04-S001-20260915](https://www.fca.org.uk/firms/consider-if-you-provide-payment-services), receipt of money; [P04-S002-20260915](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-rules.pdf), §7.6.5; [P04-S004-20260915](https://www.paddle.com/legal/terms), §2; relation=contradicts | Источники описывают разные типы отношений: payment activity, scheme role, resale contract. Это не глобальный исчерпывающий правовой словарь. |
| P04-C002 | kind=mechanism; status=confirmed; module_id=4.1; Mastercard base rules, 2Jun2026 | Эквайер сохраняет ответственность за PayFac/sponsored merchants и может делегировать перечисленные функции | [P04-S002-20260915](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-rules.pdf), §§7.6.5–7.6.5.1, pp.172–173 | EU/US modifications просмотрены; частные thresholds/territorial exceptions не универсализируются; effective dates provision-specific. |
| P04-C003 | kind=legal; status=confirmed; module_id=4.1; UK marketplace perimeter guidance | Получение buyer money платформой до перечисления продавцу может входить в payment services | [P04-S001-20260915](https://www.fca.org.uk/firms/consider-if-you-provide-payment-services), “If your business receives customer money…” | FCA guidance updated22Mar2023; конкретное исключение требует фактов и law review. “May” не превращается в безусловный вывод. |
| P04-C004 | kind=product; status=confirmed; module_id=4.1; Stripe Connect charge configurations | Direct charge, indirect с on_behalf_of и indirect без него имеют указанную в Stripe схему определения MoR | [P04-S003-20260915](https://docs.stripe.com/connect/merchant-of-record), “Define the merchant of record” | Не заменяет реальный sales contract; Accounts v2 и merchant configuration — отдельные условия. |
| P04-C005 | kind=product; status=confirmed; module_id=4.1; Stripe indirect charges with on_behalf_of | MoR connected account не исключает конечное покрытие platform negative-balance losses | [P04-S003-20260915](https://docs.stripe.com/connect/merchant-of-record), indirect charge bullet | Утверждение в конкретной Stripe модели; нельзя переносить на все PSP. |
| P04-C006 | kind=product; status=confirmed; module_id=4.1; Paddle MSA8Oct2025 | Paddle выступает reseller, supplier сохраняет обязанности; refunds/CB могут предъявляться supplier | [P04-S004-20260915](https://www.paddle.com/legal/terms), §§2, 9.4, 10.1–10.4 | Вступление редакции различается для new/existing suppliers; нет individual order form и правового вывода о каждом покупателе. |
| P04-C007 | kind=product; status=confirmed; module_id=4.1; Spreedly Optimize/Composer | Документация описывает static, split-volume и conditional gateway routing | [P04-S005-20260915](https://developer.spreedly.com/docs/routing-rules-1), “Types of Routing” | Нет независимого доказательства uplift/optimality. Договорный допуск downstream не возникает от программного rule. |

## 4.2 Underwriting

| Claim ID | Kind / статус / scope | Утверждение | Evidence: snapshot + locator | Ограничения и reasoning |
|---|---|---|---|---|
| P04-C008 | kind=product; status=confirmed; module_id=4.2; Stripe Connect | Verification requirements зависят от страны, capabilities, бизнеса, договора и risk | [P04-S006-20260915](https://docs.stripe.com/connect/identity-verification), “Verification requirements” | Не полный KYC/KYB law checklist; actual account не исследован. |
| P04-C009 | kind=product; status=confirmed; module_id=4.2; Stripe Connect | После initial verification могут возникнуть новые требования и pause charges/payouts | [P04-S006-20260915](https://docs.stripe.com/connect/identity-verification), thresholds paragraph and “Onboarding flows” | Конкретный deadline/threshold берётся из аккаунта, не выдумывается. |
| P04-C010 | kind=product; status=confirmed; module_id=4.2; independent platform duties | Stripe verification не заменяет самостоятельные legal verification duties платформы | [P04-S006-20260915](https://docs.stripe.com/connect/identity-verification), introductory warning before Verification requirements | Какие именно обязанности существуют, определяется применимым законом. |
| P04-C011 | kind=mechanism; status=confirmed; module_id=4.2; Mastercard2Jun2026 sponsored merchant reporting | Требуется корректная идентификация merchant/URL/MCC/объёма и disputes в указанном отчётном/transaction model | [P04-S002-20260915](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-rules.pdf), §7.6.5.1(5), §7.6.6 | В (5) есть исключение при передаче PF/SM identifiers; глава не обещает одинаковый quarterly report для всех. |
| P04-C012 | kind=product; status=confirmed; module_id=4.2; Square US reserve policy | Rolling reserve откладывает долю платежей и освобождает её по времени; рисковые факторы включают предоплату и характер обработки | [P04-S007-20260915](https://squareup.com/help/us/en/article/6832-reserves-faq), About reserves; Before you begin | Процент/срок из индивидуального уведомления. Учебные10%/90days не приписаны Square. |
| P04-C013 | kind=mechanism; status=confirmed; condition=within synthetic accounting; module_id=4.2 | Само удержание возвратного reserve не является комиссией; стоимость финансирования и actual loss считаются отдельно | [P04-S007-20260915](https://squareup.com/help/us/en/article/6832-reserves-faq), ownership/release paragraph; author accounting example | Авторский вывод для заданного refundable reserve; не универсальная классификация restricted cash по IFRS/GAAP. |

## 4.3 Settlement и payouts

| Claim ID | Kind / статус / scope | Утверждение | Evidence: snapshot + locator | Ограничения и reasoning |
|---|---|---|---|---|
| P04-C014 | kind=product; status=confirmed; module_id=4.3; Stripe merchant payouts | Payout schedule не сокращает pending-to-available settlement timing | [P04-S008-20260915](https://docs.stripe.com/payouts), How payout timing works; Settlement timing | T и тип дней зависят от провайдера/страны; пример Friday T+2 синтетический. |
| P04-C015 | kind=product; status=confirmed; module_id=4.3; Adyen report | Settlement details report различает transaction/fee/reserve/invoice/payout entries и references | [P04-S009-20260915](https://docs.adyen.com/reporting/settlement-reconciliation/transaction-level/settlement-details-report/), Entries; Merchant payout | Specification, не фактическая выписка или proof of bank arrival. |
| P04-C016 | kind=mechanism; status=confirmed; module_id=4.3,4.4; Adyen report IC++ | Commission и его Markup/Scheme/Interchange breakdown представлены альтернативно в описанных колонках | [P04-S009-20260915](https://docs.adyen.com/reporting/settlement-reconciliation/transaction-level/settlement-details-report/), Standard columns11–14 | Запрет double counting — арифметическое следствие; читать optional fields/external settlement caveats. |
| P04-C017 | kind=product; status=confirmed; module_id=4.3; Stripe separate charges and transfers | Charge и transfers раздельны; platform balance дебетуется за fees/refunds/chargebacks | [P04-S024-20260915](https://docs.stripe.com/connect/separate-charges-and-transfers.md?platform=web&integration=checkout&ui=stripe-hosted), opening bullets | Hosted Checkout/web variant прочитан напрямую, а не один index. |
| P04-C018 | kind=product; status=confirmed; module_id=4.3; same Stripe flow | Refund charge не отменяет связанные transfers; требуется отдельное восстановление/reversal | [P04-S024-20260915](https://docs.stripe.com/connect/separate-charges-and-transfers.md?platform=web&integration=checkout&ui=stripe-hosted), Issue refunds; Reverse transfers | Reversal ограничен balance/capabilities; не доказательство взыскания с insolvent party. |
| P04-C019 | kind=product; status=confirmed; module_id=4.3; Stripe payout state | Payout может перейти из paid в failed при банковском возврате | [P04-S008-20260915](https://docs.stripe.com/payouts), Payout failures | Документ говорит о задержке банковского ответа до5businessdays; SLA конкретного банка не установлен. |

## 4.4 Экономика

| Claim ID | Kind / статус / scope | Утверждение | Evidence: snapshot + locator | Ограничения и reasoning |
|---|---|---|---|---|
| P04-C020 | kind=product; status=confirmed; module_id=4.4; Adyen processing invoice | Издержки могут возникать на non-settled/отклонённых событиях; settlement report недостаточен для полного invoice reconciliation | [P04-S010-20260915](https://help.adyen.com/knowledge/finance/invoices/how-do-i-reconcile-my-invoice), Which report to use; Processing Fees; Authorisation Scheme Fees | Не все attempts любого PSP одинаково тарифицируются; нужен договор и событие-база. |
| P04-C021 | kind=mechanism; status=confirmed; module_id=4.4; standard four-party card economic model | Interchange перераспределяет доход acquiring→issuing и влияет на стимулы обеих сторон | [P04-S016-20260915](https://www.federalreserve.gov/pubs/feds/2009/200923/), §§II–III | Исторический обзор2009: rates, timings и legal rules не экспортированы в2026. |
| P04-C022 | kind=mechanism; status=confirmed; condition=within assumptions; module_id=4.4; Rochet–Tirole2002 model | Объём и прибыль платформы зависят от цен обеим сторонам; распределение цены имеет значение | [P04-S017-20260915](https://tse-fr.eu/sites/default/files/medias/doc/wp/2002/platform.pdf), §2.1 pp.8–10 | Теория, не empirical estimate; цитируется author draft13Dec2002, не непрочитанная JEEA edition. |
| P04-C023 | kind=mechanism; status=confirmed; condition=within model; module_id=4.4; synthetic P&L | Break-even требует положительной contribution после всех непересекающихся variable costs | Author derivation, equations and numerical table in CHAPTER4.4; P04-S016/S017=context only | Это математическая модель, не тарифное/бухгалтерское утверждение. Constant ticket/mix/scaling записаны явно. |
| P04-C024 | kind=mechanism; status=confirmed; condition=within loss definitions; module_id=4.4 | Fraud cause и chargeback mechanism могут описывать один principal loss; его повторный вычет завышает убыток | Author disjoint-loss construction; P04-S004§10=context for refund/chargeback recovery | Не объявляется универсальная метрика PSP; в таблице прямо заданы непересекающиеся множества. |
| P04-C025 | kind=product; status=confirmed; module_id=4.4; Stripe Connect US price page15Sep2026 | You handle pricing включает2USD/active account и0.25%+0.25USD/payout, processing отдельно | [P04-S011-20260915](https://stripe.com/connect/pricing), You handle pricing; footer US English | Public price, не индивидуальная offer; other products/regions may differ. |
| P04-C026 | kind=mechanism; status=confirmed; condition=within synthetic comparison; module_id=4.4 | QR-интерфейс, ведущий на карточный платёж, сохраняет underlying card costs; low fee не гарантирует лучший contribution | Author same-rail table and checkout calculation; P04-S005=context routing | Учебный пример. Не заявляется тариф или causal conversion estimate QR/A2A на рынке. |

## 4.5 Crypto acceptance

| Claim ID | Kind / статус / scope | Утверждение | Evidence: snapshot + locator | Ограничения и reasoning |
|---|---|---|---|---|
| P04-C027 | kind=product; status=confirmed; module_id=4.5; Stripe stablecoin doc as read | Accepted tokens: USDC и указанные US-only USDP/USDG; USDT в прочитанном перечне отсутствует | [P04-S012-20260915](https://docs.stripe.com/payments/stablecoin-payments), Payment method properties | Отсутствие в списке не доказывает отсутствие отдельного непубличного продукта; сети/регионы не обобщаются. |
| P04-C028 | kind=product; status=confirmed; module_id=4.5; same page | Документ различает global customer locations с ограничениями и business locations: US, отдельно private previews | [P04-S012-20260915](https://docs.stripe.com/payments/stablecoin-payments), Business locations | US explicit; EU/HK/MX/CH labelled private preview; не заявляется GA для остальных. |
| P04-C029 | kind=product; status=open; module_id=4.5; Stripe country-code list | Точная доступность во всех перечисленных кодах стран не установлена | [P04-S012-20260915](https://docs.stripe.com/payments/stablecoin-payments), Business locations text versus code list; relation=conflicting documentation | Список шире фразы о preview. Не разрешается по количеству стран в массиве; требует provider clarification/eligibility evidence. |
| P04-C030 | kind=product; status=confirmed; module_id=4.5; Stripe stablecoin product | Settlement идёт в Stripe balance local currency, refund — stablecoin в исходный wallet | [P04-S012-20260915](https://docs.stripe.com/payments/stablecoin-payments), Limitations; Refunds | Balance credit не bank payout; allocation of fees конкретного refund не проверена. |
| P04-C031 | kind=product; status=open; module_id=4.5; delegated agent spending | Stablecoin acceptance page не устанавливает полномочие автономного агента расходовать кошелёк клиента | [P04-S012-20260915](https://docs.stripe.com/payments/stablecoin-payments), Payment flow/customer-authenticated | Это граница доказательства, не отрицание всех agentic products Stripe. |
| P04-C032 | kind=product; status=confirmed; module_id=4.5; Triple-A service FAQ | Triple-A описывает crypto/invoice payments с fiat или crypto receipt по модели продукта | [P04-S014-20260915](https://support.triple-a.io/knowledge/what-services-does-triple-a-provide), service bullets | Token matrix, geography и licensing не доказаны этим FAQ. |
| P04-C033 | kind=product; status=confirmed; condition=in FAQ only; module_id=4.5; Triple-A local currency withdrawal | FAQ указывает порог3000USD equivalent для automatic withdrawal | [P04-S015-20260915](https://support.triple-a.io/knowledge/i-didnt-receive-my-payment-what-can-i-do), threshold paragraph | Нет даты обновления/индивидуального договора; не выдаётся за универсальный SLA. |
| P04-C034 | kind=product; status=confirmed; module_id=4.5; Stripe restricted use | Crypto exchanges/wallets и перечисленные financial services требуют отдельного eligibility/due diligence | [P04-S013-20260915](https://stripe.com/legal/restricted-businesses), Restricted Businesses; Cryptocurrency; Financial products and services | Updated13May2026; service-specific approval, en-de response locale; не все crypto-sales автоматически запрещены. |
| P04-C035 | kind=hypothesis; status=working_hypothesis; module_id=4.5; generic crypto-in/fiat-out connector | Connector + supported crypto provider + merchant fiat settlement может исследоваться при договорной/правовой поддержке | P04-S012/S014=context; CHAPTER4.5 role decision tree is author synthesis | Не доказана применимость к конкретному юридическому лицу; downstream ordinary PSP не используется для скрытия третьего лица/истинной деятельности. |

## 4.6 Sponsorship

| Claim ID | Kind / статус / scope | Утверждение | Evidence: snapshot + locator | Ограничения и reasoning |
|---|---|---|---|---|
| P04-C036 | kind=product; status=confirmed; module_id=4.6; VisaNet Connect–Issuing | Non-members требуют Visa-member sponsorship; issuing production отделён от sandbox и требует review | [P04-S020-20260915](https://developer.visa.com/capabilities/visanet-connect-issuing/docs-getting-started), Eligibility; Next Steps | Конкретный API, не все способы выдачи карт; region icons не прочитаны как geo matrix. |
| P04-C037 | kind=mechanism; status=confirmed; module_id=4.6; acquiring versus issuing | Issuer/BIN sponsorship и acquiring/PayFac sponsorship относятся к разным функциям и участникам | [P04-S020-20260915](https://developer.visa.com/capabilities/visanet-connect-issuing/docs-getting-started), issuer/cardholder duties; [P04-S002-20260915](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-rules.pdf), §7.6.5 | Авторское сопоставление двух первичных источников; слово BIN может встречаться и в acquiring; не утверждается исключительное issuing-значение. |
| P04-C038 | kind=legal; status=confirmed; module_id=4.6; US supervised banks | Third-party arrangement не снимает с банка ответственность; guidance охватывает полный relationship lifecycle | [P04-S019-20260915](https://www.federalreserve.gov/frrs/guidance/interagency-guidance-on-third-party-relationships.htm), A; C; footnote2 | Guidance6Jun2023, не новый закон/BaaS-license; отдельные statutory references не анализировались целиком. |
| P04-C039 | kind=mechanism; status=confirmed; condition=within assumptions; module_id=4.6; Aurazo model | Стимул эквайера назначать access price зависит от competition with incumbent versus niche entry | [P04-S018-20260915](https://www.bis.org/publications/working-paper-1163-interchange-fees-access-pricing-and-sub-acquirers-payment-markets.pdf), §3 pp.9–12; §6 pp.19–20 | Теория: no bypass, upstream market power, simplified network objective. Не статистика actual sponsor behaviour. |
| P04-C040 | kind=legal; status=confirmed; module_id=4.6; US bank third-party planning | В guidance рассматриваются due diligence, contract information/audit rights и orderly termination/transition | [P04-S019-20260915](https://www.federalreserve.gov/frrs/guidance/interagency-guidance-on-third-party-relationships.htm), C.2; C.3; C.5 | Chapter checklist — авторский прикладной синтез; не обязательная одинаковая формулировка каждого договора. |
| P04-C041 | kind=legal; status=confirmed; condition=within guidance; module_id=4.6; Irish PI/EMI passporting to EU | Passporting связан с authorisation и notification для определённых услуг и стран | [P04-S021-20260915](https://www.centralbank.ie/regulation/industry-market-sectors/electronic-money-institutions/passporting), intro/Cross Border; [P04-S022-20260915](https://www.centralbank.ie/regulation/industry-market-sectors/payment-institutions/passporting), Cross Border | Общий механизм по CBI; полный consolidated PSD2 из EUR-Lex blocked; exact deadlines/exceptions не заявлены. |
| P04-C042 | kind=legal; status=rejected; module_id=4.6; US/EU/scheme distinctions | «US sponsor contract автоматически даёт EU passport или мировой compliance umbrella» | P04-S019/P04-S021/P04-S022/P04-S002, locators above; relation=contradicts | Разные основания, органы и области допуска. Не является полным conclusion о конкретной группе компаний. |
| P04-C043 | kind=experience; status=confirmed; condition=as existence of discussion only; module_id=4.6; Reddit10kwnbp | OP уточняет acquiring после ответа, понимающего BIN sponsorship как issuing | [P04-S023-20260915](https://www.reddit.com/r/fintech/comments/10kwnbp/bin_sponsorship_vs_payment_facilitator/), OP and clarification “sorry for not being clear” | Relative date only; комментарии не служат нормой и не доказывают реальных договорных условий. |
| P04-C044 | kind=hypothesis; status=working_hypothesis; module_id=4.6; generic partner transition | При замене партнёра проверить re-underwriting, договоры, токены/данные, programme migration и старые obligations | P04-S019 C.2/C.3/C.5=context; P04-S020 production review=context; author checklist | Не обещает обязательный одинаковый migration procedure для любого банка; exact BIN portability/termination clauses open. |

## Проверка синтетической арифметики

15.09.2026 автор пересчитал примеры и ответы. Дополнительная редакторская сверка родительского агента не заменяет независимого reviewer.

- MoR example: 20 + 8 + 92 = 120 USD.
- Reserve: 1000 × 10% × 90 = 9000 USD; financing9000 × 12% =1080/year; available1000−30−100=870; after goods850:20.
- Net payout: 10000−400−100−300−500=8700; gross variant9000 less later300 gives same8700.
- Split: 60+8+2+10=80 USD.
- PSP variable costs: 21000+1600+1000+1000+500+300+200+300=25900; contribution32000−25900=6100; after F15000:−8900.
- Break-even: 15000/0.0061≈2459016.39; after +0.4pp losses:15000/0.0021≈7142857.14.
- All-in variable table: card0.69, A2A0.29, QR-card0.70, crypto-partner0.40 USD; F/N0.20 adds once to each alternative model.
- Low ticket: 2×0.029+0.30=0.358=17.9%; 20×0.029+0.30=0.88=4.4%.
- Connect example: 100×2+100000×0.0025+400×0.25=550; with100payouts=475.
- Checkout: 80×(8−0.69)=584.80; 70×(8−0.29)=539.70.
- Sponsor residual example: (100000−75000)×20%=5000; max(6000,5000)=6000.
- Sponsor concentration example:5000000×0.006−24000=6000; remaining1000000×0.006−24000=−18000.
- Exercises: reserve6000→steady12000 EUR; payout21180USD; break-even2000000USD; equal-cost ticket20USD; sponsor normal4000 versus shutdown−11000USD.

Числа не характеризуют Square, Stripe, Paddle, Adyen, банк или Lab, кроме явно приведённых публичных Stripe Connect tariffs с ограниченным US scope. Проверка вычислений не является правовым заключением, подтверждением production или коммерческим одобрением.
