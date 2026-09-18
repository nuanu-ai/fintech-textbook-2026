---
title: "Claim audit — Part 00"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Публичная редакция от 18.09.2026. Даты проверки и ограничения источников сохранены. Хеши в исторических аудитах относятся к исходной рукописи; публичные изменения и текущие хеши — в [паспорте издания](../../edition.md).

# Claim audit — Part 00

Independent auditor:deep_audit_00_01_05. Checked17September2026,Asia/Makassar; knowledge cutoff15September2026. 48 claims assessed individually. Vendor assertions establish documented behaviour,not tested execution. Partial/unverifiable means evidence limitation,not automatically false. Contradicted rows here assess the explicitly rejected myth literally; they do not criticise its rejection. New post-baseline IDs included where present.

| claim_id | verdict | Independently read evidence:URL + locator | Checked scope/date | Finding / limits |
|---|---|---|---|---|
| P00-C001 | verified_as_reported |  [P00-S001](https://docs.stripe.com/payments/paymentintents/lifecycle):Lifecycle/succeeded | Stripe current docs | Completion is scoped to payment flow; no bank receipt established. |
| P00-C002 | verified_as_reported |  [P00-S002](https://docs.stripe.com/payments/balances):Balance states | Stripe current docs | Pending/available distinction supported; specific settlement timing varies. |
| P00-C003 | verified |  [P00-S001](https://docs.stripe.com/payments/paymentintents/lifecycle):succeeded; [P00-S002](https://docs.stripe.com/payments/balances):Available balances/payouts | Stripe product vocabulary | Combined documents separate account funds from bank payout. |
| P00-C004 | verified |  [P00-S003](https://www.bis.org/committees/cpmi/pfmi/overview):Principle8,key considerations1–3 | PFMI2012 financial infrastructures | Final settlement/revocation cutoff within system rules. |
| P00-C005 | verified |  [P00-S003](https://www.bis.org/committees/cpmi/pfmi/overview):Principle9,key considerations1–5 | PFMI2012 | Central-bank money preference includes practicable/available condition. |
| P00-C006 | verified_as_reported |  [P00-S004](https://docs.moderntreasury.com/platform/reference/ledger-balances-object):Balance table and balance formulas | Modern Treasury current page | Pending includes posted+pending;available includes pending debits;not generic ledger law. |
| P00-C007 | verified |  [P00-S005](https://files.consumerfinance.gov/f/documents/cfpb_bnpl-market-report_2025-12.pdf):Methodology printedpp6–7 | CFPB2025 report,six lenders2019–23 | Aggregate firm data,not account-level cross-provider deduplication. |
| P00-C008 | verified |  [P00-S005](https://files.consumerfinance.gov/f/documents/cfpb_bnpl-market-report_2025-12.pdf):Introduction and methodology | CFPB2023 sample statistic | 53.6m combined users cannot establish unique nationwide persons. |
| P00-C009 | verified |  [P00-S006](https://openstax.org/books/principles-finance/pages/4-2-economic-basis-for-accrual-accounting):Equation4.3 | Accounting identity,educational scope | Assets=liabilities+equity independently checked. |
| P00-C010 | verified |  [P00-S006](https://openstax.org/books/principles-finance/pages/4-2-economic-basis-for-accrual-accounting):Double-entry bookkeeping paragraphs | OpenStax§4.2 | At least two affected accounts and equal aggregate debits/credits. |
| P00-C011 | verified |  [P00-S006](https://openstax.org/books/principles-finance/pages/4-2-economic-basis-for-accrual-accounting):Debit/credit normal directions | Accounting example scope | Account type determines direction;not every debit a loss. |
| P00-C012 | verified |  [P00-S006](https://openstax.org/books/principles-finance/pages/4-2-economic-basis-for-accrual-accounting):Prose before Equation4.3 and equation | Current retrieved edition | Reversed subtraction in prose is real;equation and chapter are correct. |
| P00-C013 | verified_as_reported |  [P00-S007](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/chargebacks-made-simple-guide.pdf):§2.2,printedp5 | Mastercard July2025 educational guide | Dual-message auth/clearing distinguished from single-message;not whole rulebook. |
| P00-C014 | verified_as_reported |  [P00-S008](https://ethereum.org/developers/docs/transactions/):Transaction lifecycle bullets | Ethereum docs updated25Jul2026 | Broadcast,pool,inclusion,finality distinct;no particular transaction verified. |
| P00-C015 | verified_as_reported |  [P00-S009](https://www.mastercard.com/gb/en/business/support/payment-facilitators.html):Payment facilitator definition | Mastercard programme description | Registered by acquirer and submerchant services;individual admission not checked. |
| P00-C016 | verified_as_reported |  [P00-S010](https://docs.stripe.com/connect/merchant-of-record):MoR responsibilities | Stripe product documentation | Sale/refund responsibility within described model,not worldwide legal definition. |
| P00-C017 | verified |  [P00-S011](https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/mica/article-3-definitions):Article3(1)(7) | EU MiCA EMT definition | Single official currency reference preserved. |
| P00-C018 | partial |  [P00-S012](https://www.eba.europa.eu/single-rule-book-qa/qna/view/publicId/2022_6336):Final answer,EMD2 Article2(2),official index | EU Q&A17Jan2025 | Definition reproduced in indexed primary Q&A;full original statutory text not obtained. |
| P00-C019 | partial |  [P00-S012](https://www.eba.europa.eu/single-rule-book-qa/qna/view/publicId/2022_6336):Final answer,C-661/22§§47–49,official index | Commission interpretation17Jan2025 | Separate asset/contractual acceptance supported by index;not complete CJEU verification. |
| P00-C020 | verified |  [P00-S013](https://www.bankofengland.co.uk/-/media/boe/files/quarterly-bulletin/2014/money-creation-in-the-modern-economy.pdf):Money creation,printedpp16–17 | BoE2014 explanatory paper | Lending creates matching deposit;not unconstrained unlimited lending. |
| P00-C021 | verified |  [P00-S013](https://www.bankofengland.co.uk/-/media/boe/files/quarterly-bulletin/2014/money-creation-in-the-modern-economy.pdf):Loan repayment paragraph,printedp17 | BoE2014 | Repayment destroys deposit money in model. |
| P00-C022 | verified |  [P00-S014](https://www.bis.org/publications/aer-2023/blueprint-future-monetary-system-improving-old-enabling-new):John-Paul interbank payment example | BIS2023 model | Reserve settlement and new receiving-bank claim separated. |
| P00-C023 | verified |  [P00-S014](https://www.bis.org/publications/aer-2023/blueprint-future-monetary-system-improving-old-enabling-new):Singleness discussion | BIS2023 conceptual analysis | Par convertibility supports singleness;not every token guarantees par. |
| P00-C024 | partial |  [P00-S014](https://www.bis.org/publications/aer-2023/blueprint-future-monetary-system-improving-old-enabling-new):Central-bank money/tokenisation discussion | BIS2023 | Liability concept supported;full retail-vs-wholesale access passage not independently re-read. |
| P00-C025 | verified_as_reported |  [P00-S015](https://www.emvco.com/emv-technologies/qr-codes/):QR specifications scope and subsequent messaging | EMVCo current overview | Standard format does not standardise all provider messages. |
| P00-C026 | verified |  [FATF2021 PDF](https://www.fatf-gafi.org/content/dam/fatf/documents/recommendations/Updated-Guidance-VA-VASP.pdf):§73 | Global FATF guidance | Joint/multisig control can count;national factual classification remains separate. |
| P00-C027 | verified |  [P00-S016](https://www.fatf-gafi.org/en/publications/Fatfrecommendations/Guidance-rba-virtual-assets-2021.html):Publisher caveat on later standards | Landing read17Sep2026 | 2021 guidance explicitly omits later amendments including2025R1. |
| P00-C028 | verified_as_reported |  [P00-S017](https://docs.moderntreasury.com/ledgers/docs/transaction-status-and-balances):Posted/archived states and updating entries | Modern Treasury current docs | Status/entry immutability has metadata exception and reversal path. |
| P00-C029 | unverifiable |  [P00-S018](https://www.fdic.gov/consumer-resource-center/2024-06/banking-third-party-apps):Original URL attempt failed | US FDIC | Fresh original content not obtained;not evidence claim false,chapter already bounds source. |
| P00-C030 | verified |  [P00-S005](https://files.consumerfinance.gov/f/documents/cfpb_bnpl-market-report_2025-12.pdf):Introduction pay-in-four product definition | US CFPB report2025 | Credit product taxonomy;not every instalment contract globally. |
| P00-C031 | partial |  [P00-S019](https://www.investor.gov/introduction-investing/investing-basics/how-stock-markets-work/market-participants):Market Participants,clearing paragraphs | SEC investor guidance | Role distinctions visible;full set of intermediary paragraphs not exhaustively re-read. |
| P00-C032 | partial |  [P00-S020](https://content.naic.org/insurance-topics/auto-insurance):Background/coverage/underwriting/rating,official index | NAIC indexed update26Sep2025 | Definitions supported only by indexed body;direct page missing article. |
| P00-C033 | partial |  [P00-S021](https://www.bis.org/fsi/publ/insights19_summary.pdf):Executive summary,official indexed PDF | FSI Insights19,2019 | Authors broaden suptech definition;direct report failed,not full original reading. |
| P00-C034 | partial |  [P00-S021](https://www.bis.org/fsi/publ/insights19_summary.pdf):Executive summary and indexed research discussion | 39authorities2019,survey+supplements | Method/limitations not causal effectiveness;direct full paper unavailable. |
| P00-C035 | verified |  [P00-S022](https://www.bis.org/publications/fsi-summary-key-considerations-open-finance-executive-summary):Definition and potential benefits paragraphs | BIS26Jun2025 | Open finance extends beyond payment-account data;potential not measured causal effect. |
| P00-C036 | verified |  [P00-S023](https://thedocs.worldbank.org/en/doc/be6615202d1f08a25855c8ac2d615122-0050012025/related/Survey-methodology.pdf):Survey methodology,printed267 | Findex2025;observations2024 | 141economies,15+ target population;report year not survey year. |
| P00-C037 | partial |  [P00-S024](https://occ.treas.gov/publications-and-resources/publications/comptrollers-handbook/files/merchant-processing/pub-ch-merchant-processing.pdf):Merchant-processing roles,printedpp2–4 | OCC handbook retrieved17Sep2026 | Acquirer/agent/third party supported;exact ISO subsection not fully reread. |
| P00-C038 | non_factual | [CHAPTER](../../chapters/part-00/chapter.md):§0.4 two-bank tables | Synthetic,A/B/reserves/deposits | Recalculated:reserves350;deposits1440→1540;receiving B700=640+60. |
| P00-C039 | non_factual | [CHAPTER](../../chapters/part-00/chapter.md):§0.4 impairment example | Synthetic | 120loss produces equity−20;liquidity borrowing50 does not restore equity. |
| P00-C040 | non_factual | [CHAPTER](../../chapters/part-00/chapter.md):§0.5 eight journal entries | Synthetic | Debit/credit totals422;assets128=liabilities105+equity23;cash attribution correct. |
| P00-C041 | non_factual | [CHAPTER](../../chapters/part-00/chapter.md):§0.5 refund example | Synthetic20refund | Cash115,merchant liability15,assets138;not provider data. |
| P00-C042 | non_factual | [CHAPTER](../../chapters/part-00/chapter.md):§0.3 price/rate examples | Synthetic | 25bps×20000=50;1000×12%×30/365≈9.863;FX sides consistent. |
| P00-C043 | non_factual | [CHAPTER](../../chapters/part-00/chapter.md):§0.6 BNPL example | Synthetic | Payout114−collection90=loss24;merchant price120 not lender profit. |
| P00-C044 | non_factual | [CHAPTER](../../chapters/part-00/chapter.md):§0.6 insurance pool | Synthetic | 100000−60000−25000=15000;120000claims gives−45000. |
| P00-C045 | contradicted |  [P00-S001](https://docs.stripe.com/payments/paymentintents/lifecycle):succeeded; [P00-S002](https://docs.stripe.com/payments/balances):Available balance/payout distinction | Explicit rejected myth | Local success is insufficient evidence of end-beneficiary receipt;rejection is correct. |
| P00-C046 | contradicted | [P05-S033](https://www.circle.com/legal/mica-redemption-policy):§§1.4,2.1–2.3,3 | Explicit rejected universal redemption myth | Circle's scoped/conditional access is a counterexample;not a new universal restriction. |
| P00-C047 | non_factual | [CHAPTER](../../chapters/part-00/chapter.md):Rejected inference boundary | Research/product inference | Report/API existence does not establish own product effectiveness;logical warning,not empirical finding. |
| P00-C048 | non_factual | [CHAPTER](../../chapters/part-00/chapter.md):Research coverage limitation | Scope of this chapter | Full current MiCA/EMD review is expressly not claimed;cannot certify broader law. |

For recovered alternative URLs and access failures see [SOURCE_AUDIT](source-audit.md). No verdict is inherited from a previous review.

