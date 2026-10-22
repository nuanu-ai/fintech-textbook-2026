---
title: "Sources for Chapter 0"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Money and fintech basics](README.md) · [Contents](../README.md) · [All sources and fact-checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Sources for Chapter 0

**Status:** `independently_reviewed_draft` · v0.1 · author `part_00_research` · 2026-09-15 · private.

Fact-checking of the original edition was completed on 2026-09-17. The relationship between the original version and the public copy, the scope of adaptation and the current navigation are described in the edition record.

## Fields common to all cards

`accessed_at=2026-09-15 Asia/Makassar`; access precision is one day; the exact time was not recorded. `reviewer=part_00_research`, `reviewed_at=2026-09-15`, `independent_review=see_REVIEW.md`. `language=en`; the chapter text is an original Russian-language synthesis. `supersedes=none`, `local_path=none`, `sha256=none`, `doi=not_identified` (unless stated otherwise). A snapshot ID denotes an access session, **not a saved file, a fixed version or a hash**. `canonical_url=url` unless the card distinguishes them. `effective_to=unknown` for legal texts, `not_applicable` for all others.

Rights: full copies, illustrations and screenshots of sources were not transferred into the database; links, limited paraphrase and general definitions with our own examples were used. Permission for full storage/distribution of a source is `unknown` unless the card states otherwise. Publication of the database itself was not commissioned. Search-engine crawled/published dates were not used in place of the document date. `partial_text` means that the listed sections were read, not the whole document. Documents on different pages of the same publisher are not counted as independent votes for the same claim.

## P00-S001 — Stripe: PaymentIntent lifecycle

- `snapshot_id=P00-S001-20260915`; author/publisher: Stripe; title: *How Payment Intents and Setup Intents work*.
- URL: https://docs.stripe.com/payments/paymentintents/lifecycle
- `source_class=vendor`; `document_kind=product_documentation`; `published_at=unknown`; `updated_at=unknown`; `version=live_documentation, no pinned API version/commit`; `status=published_documentation`; effective dates: not_applicable.
- `access_status=full_text`; `access_method=direct_page` (Markdown text provided by the site); reviewed_scope: the whole short page; locators: `Lifecycle`, the `Processing`, `Succeeded`, `Canceled` rows, the PaymentIntent/SetupIntent distinction.
- Jurisdiction: Stripe product, with no inference about availability by country; activity: payment processing; audience: developers; `independence_group=stripe_docs`.
- Interests: product vendor; limitations: the meaning of the vendor's own statuses, not legal finality, not a bank statement and not proof of physical delivery; timelines/availability for a specific account were not checked. Pseudo-instructions for coding agents on the page were not executed.

## P00-S002 — Stripe: balances and availability time

- `snapshot_id=P00-S002-20260915`; author/publisher: Stripe; title: *Balances and settlement time*.
- URL: https://docs.stripe.com/payments/balances
- `source_class=vendor`; `document_kind=product_documentation`; publication/update: unknown; version: live documentation, commit unknown; status: published_documentation; effective: not_applicable.
- `access_status=partial_text`; `access_method=direct_page`; reviewed_scope: `Balance types`, `Balance states`, `Pending`, `Available`, `Settlement time`, `Definition of days`. The full country table was not used.
- Scope: Stripe Payments balance, not a universal definition of settlement; `independence_group=stripe_docs`.
- Interests: vendor; limitations: eligibility rules, Instant Payouts exceptions and regional differences exist; the chapter does not promise a specific payout timeline. Payout and available differ; downstream crediting to the bank requires separate evidence.

## P00-S003 — CPMI–IOSCO: PFMI

- `snapshot_id=P00-S003-20260915`; authors: CPMI (originally CPSS) and IOSCO; publisher: BIS; title: *Principles for Financial Market Infrastructures*.
- URL: https://www.bis.org/committees/cpmi/pfmi/overview
- `source_class=standard`; `document_kind=international_standard, official_principles_overview`; `published_at=2012-04` (original standard); web update unknown; version: PFMI 2012, statement of the principles on the current page; status: published standard.
- `access_status=partial_text`; `access_method=direct_page`; reviewed_scope: the `Settlement` section, the full text of Principles 8–9 with key considerations; locators: Principle 8, KC1–3; Principle 9, KC1–5.
- Jurisdiction: international standard for FMIs; legal bindingness is determined by implementation in the relevant regime; effective_from: no single date for all countries; `independence_group=cpmi_iosco_pfmi`.
- Limitations: not a rule for every retail API and not proof of execution of a specific payment; subsequent guidance was not examined in full. The standard risk and finality mechanism is presented, without passing off a summary as the full 188-page report.

## P00-S004 — Modern Treasury: balance formulas

- `snapshot_id=P00-S004-20260915`; author/publisher: Modern Treasury; title: *Ledger Balances*.
- URL: https://docs.moderntreasury.com/platform/reference/ledger-balances-object
- `source_class=vendor`; kind: API documentation; publication/update/version: unknown; status: published documentation; effective: not_applicable.
- `access_status=partial_text`; `access_method=search_index` for the table actually used for content. A direct open initially returned metadata for 148 lines, and a subsequent read timed out; the Markdown version was not read.
- Reviewed_scope/locator: the `Types of Balances` table, the `Pending`, `Posted`, `Available` rows; the warning `Pending balances include both posted and pending amounts`.
- Scope: specifically the Modern Treasury balance object, debit/credit normality; `independence_group=modern_treasury_docs`.
- Interests: ledger vendor; limitations: the meaning of `pending_balance` must not be carried over to Stripe pending; the specific API version and the full schema were not recorded. A direct reading of the full document is not claimed.

## P00-S005 — CFPB: BNPL research

- `snapshot_id=P00-S005-20260915`; authors: Nicolas Salem, Laura Udis, CFPB Office of Markets; publisher: Consumer Financial Protection Bureau; title: *The Buy Now, Pay Later Market — Data Spotlight*.
- URL: https://files.consumerfinance.gov/f/documents/cfpb_bnpl-market-report_2025-12.pdf
- `source_class=research`; kind: regulator empirical report; `published_at=2025-12`, date_precision month; update unknown; version: December 2025; status: published, peer review status not identified; effective not_applicable.
- `access_status=partial_text`; `access_method=official_pdf`; reviewed_scope: Introduction pp.3–4; Key Findings p.5; Data Collection Methodology pp.6–7; Results §§4.1–4.2, pp.8–10; the remaining sections are not used for conclusions.
- Method: aggregated data from six large lenders for 2019–2023, pay-in-four or four or fewer payments; no loan/account-level matching across lenders; representativeness of the whole BNPL industry is not claimed; dollar values are adjusted to 2024 prices.
- Jurisdiction: US; audience: market/researchers/policy; `independence_group=cfpb_bnpl_2025`.
- Limitations: an observational study, not a causal effect of BNPL; 53.6 million summed users in 2023 do not guarantee as many unique people. The data are not a live 2026 snapshot; no conclusions about the current consumer-law regime are drawn from the report.

## P00-S006 — OpenStax: the accounting equation and double-entry bookkeeping

- `snapshot_id=P00-S006-20260915`; authors: Julie Dahlquist, Rainford Knight; publisher: OpenStax, Rice University; title: *Principles of Finance*, §4.2 *Economic Basis for Accrual Accounting*.
- URL: https://openstax.org/books/principles-finance/pages/4-2-economic-basis-for-accrual-accounting
- `source_class=course`; kind: open university textbook; `published_at=2022-03-24`; visible copyright date 2026-04-23 is not treated as the editorial date of the section; version: live HTML without immutable edition hash; effective not_applicable.
- `access_status=full_text`; `access_method=direct_page`; reviewed_scope: the full §4.2; locators: `The Accounting Equation`, equations 4.2–4.3; `Double-Entry Accounting`; `Debits and Credits`.
- Jurisdiction: general introductory accounting, US-oriented education; `independence_group=openstax_finance`; interests: educational publisher.
- Important discrepancy: under `Think It Through / The Accounting Equation`, a sentence suggests subtracting assets from liabilities; equation 4.3 and the worked result on the same page correctly give assets minus liabilities. The chapter uses the correct equation and its own arithmetic check; the erroneous phrase is not carried over.
- Rights visible: CC BY-NC-SA, the publisher's own restrictions on LLM use; full texts/illustrations were not stored or redistributed. The card does not claim that the license permits any further use. Basic definitions are briefly paraphrased; the numerical examples are original.

## P00-S007 — Mastercard: messages and transaction stages

- `snapshot_id=P00-S007-20260915`; author/publisher: Mastercard; title: *Chargebacks Made Simple Guide*.
- URL: https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/chargebacks-made-simple-guide.pdf
- `source_class=scheme`; kind: educational guide; `published_at=2025-07`; date_precision month (cover p.1: JULY2025); visible copyright `2025`; version identifier unknown; status: published guide, explicitly not rulebook replacement; effective_from unknown/not used.
- `access_status=partial_text`; `access_method=official_pdf`; reviewed_scope: disclaimer and §§1.1–1.2 pp.2–3; §2.1 `Transaction Flow` p.4; §2.2 `Transaction Message Types` p.5. Chargeback categories/deadlines were not used.
- Scope: Mastercard card message terminology; `independence_group=mastercard_guides`.
- Interests: scheme operator; limitations: guide states actual rules prevail; non-public technical manuals were not read; not a source for current dispute deadlines/limits. Rights: the publicly available PDF is marked `Proprietary and Confidential`; the file was not copied or distributed; limited definitions are used with a link.

## P00-S008 — Ethereum: transaction lifecycle

- `snapshot_id=P00-S008-20260915`; author/publisher: ethereum.org contributors; title: *Transactions*.
- URL: https://ethereum.org/developers/docs/transactions/ ; the original URL `/en/developers/docs/transactions/` redirects here.
- `source_class=standard`; kind: protocol educational documentation, not consensus specification; publication/update/commit unknown; status: published explanatory documentation; effective not_applicable.
- `access_status=partial_text`; `access_method=direct_page`; reviewed_scope: `Transaction lifecycle`, the introductory explanation of transactions; locator: the sequence broadcast → pool → inclusion → justified/finalized.
- Scope: Ethereum, not carried over to L2s/other networks; `independence_group=ethereum_org`.
- Limitations: client source code, network parameters and commit were not checked; the documentation gives a simplified description, and a hash by itself does not establish success, token amount, chain or performance of a commercial contract.

## P00-S009 — Mastercard: Payment Facilitator

- `snapshot_id=P00-S009-20260915`; author/publisher: Mastercard; title: *Find a payment facilitator*.
- URL: https://www.mastercard.com/gb/en/business/support/payment-facilitators.html
- `source_class=scheme`; kind: scheme role explanation and directory; publication/update/version unknown; status: public page; effective not_applicable for glossary use.
- `access_status=partial_text`; `access_method=direct_page`; reviewed_scope: `About payment facilitators`, the definition and disclaimer; the actual list of companies was not checked.
- Scope: Mastercard definition; the UK landing page does not limit the international definition to the UK only; `independence_group=mastercard_guides`.
- Limitations: the mention of Rule 7.8 is kept as the publisher's reference; the current full version of the rules was not confirmed; the directory disclaimer does not allow reliance on the completeness/quality of the companies. The chapter does not confirm the registration of any specific PayFac.

## P00-S010 — Stripe: MoR in Connect

- `snapshot_id=P00-S010-20260915`; author/publisher: Stripe; title: *Understand the merchant of record in a Connect integration*.
- URL: https://docs.stripe.com/connect/merchant-of-record
- `source_class=vendor`; kind: product documentation; publication/update/version unknown; status: published documentation; effective not_applicable.
- `access_status=full_text`; `access_method=direct_page`; reviewed_scope: the whole short page; used: introduction, `Clear identification of the merchant of record`, `Customer service responsibility`. The charge types table was read but not turned into integration instructions.
- Scope: Stripe Connect; `independence_group=stripe_docs`; interests: vendor.
- Limitations: a description of MoR responsibility within the product, not a universal legal opinion on reseller/agency/tax; the parties' specific contracts and scheme rules were not examined in Chapter 0.

## P00-S011 — ESMA: definition of EMT

- `snapshot_id=P00-S011-20260915`; author: EU legislature, excerpt published by ESMA; publisher: European Securities and Markets Authority; title: *MiCA — Article 3 Definitions*.
- URL: https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/mica/article-3-definitions
- `source_class=law`; kind: official regulator reproduction of statutory definitions; legal instrument: Regulation (EU) 2023/1114; publication/update/consolidation stamp of web page unknown; status: official interactive rulebook excerpt, no full-current-law verification.
- `access_status=partial_text`; `access_method=direct_page`; reviewed_scope: Article 3(1), points (1)–(10), especially (6) ART, (7) EMT, (8) official currency; the other definitions are available, but not all of them were analyzed.
- Jurisdiction: EU, MiCA definitions; audience: market participants/regulators; `independence_group=eu_mica`.
- `effective_from=not_reverified_in_this_part`; original publication/entry/application/transition chronology belongs to Chapter 1; the definition is used with a check date of 2026-09-15. Limitations: EUR-Lex original blocked; no conclusion is drawn about licensing, exemptions, a specific token or the full regime of the current version.

## P00-S012 — EBA: electronic money and acceptance by third parties

- `snapshot_id=P00-S012-20260915`; publisher: European Banking Authority; author of submitted scenario: credit institution (not named); institution authoring final answer not independently identified; title: *2022_6336 Definition of electronic money*.
- URL: https://www.eba.europa.eu/single-rule-book-qa/qna/view/publicId/2022_6336
- `source_class=regulator`; kind: Single Rulebook Q&A, not statute; submission `2022-01-12`; final publishing `2025-01-17`; page update unknown; status: final published Q&A.
- `access_status=partial_text`; `access_method=search_index`: the long question text, the background and the full final answer were read; direct open failed. Locator: `Final answer`, Article 2(2) EMD2 definition and references to CJEU C-661/22 §§47–49.
- Jurisdiction: EU, electronic-money definition; `independence_group=eu_emd_qa`; effective dates: no independent legal commencement for Q&A.
- Limitations: the submitter's account is not treated as an EBA conclusion; the court judgment was not read separately in full. The final answer distinguishes a separate monetary asset that is voluntarily accepted from the receipt of ordinary funds after redemption of e-money. The chapter uses the definition and the caution about classification; it does not decide the legal status of any specific card program.

## P00-S013 — Bank of England: money creation

- `snapshot_id=P00-S013-20260915`; authors: Michael McLeay, Amar Radia, Ryland Thomas; publisher: Bank of England; title: *Money creation in the modern economy*, Quarterly Bulletin 2014 Q1.
- URL: https://www.bankofengland.co.uk/-/media/boe/files/quarterly-bulletin/2014/money-creation-in-the-modern-economy.pdf
- `source_class=regulator`; kind: central-bank educational research article; `published_at=2014-03-14` (publication landing page); version: QB 2014 Q1; status: published historical article; effective not_applicable.
- `access_status=partial_text`; `access_method=official_pdf`; reviewed_scope: printed pp.14–18, PDF pp.1–5; `Money creation in reality`, `Other ways of creating and destroying deposits`, `Limits to broad money creation`, `Market forces facing individual banks`, Figures 1–2 context. The QE section was not studied in full and was not used.
- Jurisdiction: UK institutional setting and general bank-balance mechanism; `independence_group=boe_money_education`.
- Limitations: the 97%/2013 shares and the historical regime of reserves and monetary policy are not presented as current. The chapter's example is original and stylized: no correspondents, netting, interest/FX or credit impairment, except in the explicit stress scenario.

## P00-S014 — BIS: singleness of money and forms of claims

- `snapshot_id=P00-S014-20260915`; author/publisher: BIS; title: *Annual Economic Report 2023, Chapter III: Blueprint for the future monetary system: improving the old, enabling the new*.
- URL: https://www.bis.org/publications/aer-2023/blueprint-future-monetary-system-improving-old-enabling-new
- `source_class=analysis`; kind: official policy analysis; `published_at=2023-06` (chapter report year/month); exact day not reverified; update unknown; version: AER2023 ChIII; effective not_applicable.
- `access_status=partial_text`; `access_method=direct_page`; reviewed_scope: introduction, `Tokenisation and the monetary system`, explanatory comparison of deposits and stablecoins, Graph 3 surrounding prose; not all chapters/footnotes of the report were read.
- Locators: paragraph beginning `Supported by regulation and supervision...`; `When John makes a payment of GBP 100...`; `Enhanced digital representations of central bank money...`.
- Scope: an analytical model of the two-tier monetary system, not a description of every token; `independence_group=bis_aer2023`; interests: central bank policy and infrastructure.
- Limitations: unified ledger proposals are not presented as production; broad 2023 statements about the absence of stablecoin regulation are not carried over to 2026; the claim/redemption of a specific issuer requires the issuer's documents and the law.

## P00-S015 — EMVCo: QR codes

- `snapshot_id=P00-S015-20260915`; author/publisher: EMVCo; title: *EMV QR Codes*.
- URL: https://www.emvco.com/emv-technologies/qr-codes/
- `source_class=standard`; kind: official technical primer; publication/update unknown; specification catalogue lists QRCPS MPM/CPM v1.1 dated 2020-11-27, but the specifications themselves were not studied here; status: public explainer; effective not_applicable.
- `access_status=partial_text`; `access_method=search_index`; reviewed_scope: `What is EMV QR Code?`, `What are the EMV QR Code Specifications?`, the description of the format and the boundary of messaging; direct page failed/timeout.
- Scope: EMV QR data formats; `independence_group=emvco_qr`; interests: payment industry standard.
- Limitations: no conclusion about support for QRIS/Pix/any other local scheme, not proof of conformance of a specific payload. Being able to scan a QR code with a camera does not mean being able to pay with any app.

## P00-S016 — FATF: VA/VASP, custody and control

- `snapshot_id=P00-S016-20260915`; author/publisher: FATF/OECD; title: *Updated Guidance for a Risk-Based Approach to Virtual Assets and Virtual Asset Service Providers*.
- Landing URL: https://www.fatf-gafi.org/en/publications/Fatfrecommendations/Guidance-rba-virtual-assets-2021.html
- PDF URL: https://www.fatf-gafi.org/content/dam/fatf-gafi/guidance/Updated-Guidance-VA-VASP.pdf.coredownload.inline.pdf
- `source_class=standard`; kind: international guidance; `published_at=2021-10-28`; version: October 2021 guidance; status: historical guidance accompanied by current publisher warning; effective_from: national implementation varies.
- `access_status=partial_text`; `access_method=direct_page + official_pdf`; reviewed_scope: landing-page warning; PDF §§55–62, §§72–76, especially §73 multisignature and §76 ancillary infrastructure. PDF p.31 / printed p.29 contains §§72–76.
- Jurisdiction: international VA/VASP AML framework, local enactment required; `independence_group=fatf_va2021`.
- Limitations: publisher says guidance does not incorporate later standards changes, including Recommendation 1 revisions in 2025; no current Travel Rule threshold/deadline asserted. The terms custody/control are used within their own VA/VASP domain, not mechanically for all banking/brokerage services.

## P00-S017 — Modern Treasury: states of journal entries

- `snapshot_id=P00-S017-20260915`; author/publisher: Modern Treasury; title: *Transaction Status and Balances*.
- URL: https://docs.moderntreasury.com/ledgers/docs/transaction-status-and-balances
- `source_class=vendor`; kind: ledger documentation; publication unknown; updated visible `about 1 year ago` (exact date unknown); version/commit unknown; status: published documentation; effective not_applicable.
- `access_status=full_text`; `access_method=direct_page`; reviewed_scope: the whole short text, especially `Ledger Transaction Statuses` and `Account Balances`.
- Scope: Modern Treasury ledger; `independence_group=modern_treasury_docs`; interests: product supplier.
- Limitations: immutable applies to status/entries after posted/archived; metadata can change. `Posted` is set through the integration process and is not an independent bank statement. The chapter does not claim that its synthetic hold model matches the provider's internal model.

## P00-S018 — FDIC: fintech intermediaries and deposit insurance

- `snapshot_id=P00-S018-20260915`; author/publisher: FDIC; title: *Banking With Third-Party Apps*.
- URL: https://www.fdic.gov/consumer-resource-center/2024-06/banking-third-party-apps
- `source_class=regulator`; kind: consumer explainer; published_at unknown (the URL contains 2024-06, which is not accepted as a confirmed publication date); update unknown; status: public guidance; effective dates: no standalone effect.
- `access_status=partial_text`; `access_method=search_index`; reviewed_scope: the full substantive text of `What to know about fintech...`, `FDIC deposit insurance coverage`, `Nonbank companies` was available; direct open returned 403.
- Jurisdiction: US, FDIC-insured deposits and nonbank intermediaries; `independence_group=fdic_consumer`.
- Limitations: the chapter does not confirm coverage for any specific account/person and does not calculate limits; pass-through and ownership conditions require checking. A nonbank's bankruptcy is not described as covered by the bank's insurance.

## P00-S019 — SEC/Investor.gov: securities market participants

- `snapshot_id=P00-S019-20260915`; author/publisher: SEC Office of Investor Education and Assistance / Investor.gov; title: *Market Participants*.
- URL: https://www.investor.gov/introduction-investing/investing-basics/how-stock-markets-work/market-participants
- `source_class=regulator`; kind: investor education; publication/update/version unknown; status: public education; effective not_applicable.
- `access_status=partial_text`; `access_method=direct_page`; reviewed_scope: the description of brokers/clearing agencies, clearing corporations, depositories, investment advisers, securities exchanges, transfer agents.
- Jurisdiction: US securities markets; `independence_group=sec_investor`; interests: investor protection.
- Limitations: not a worldwide list of licenses and not confirmation of a broker's registration. T+1/T+2 timelines and SIPC protection are not used in the chapter; the user's purchase of a security is a synthetic example, not a recommendation.

## P00-S020 — NAIC: insurance risk, rates and coverage

- `snapshot_id=P00-S020-20260915`; author/publisher: National Association of Insurance Commissioners; title: *Auto Insurance*.
- URL: https://content.naic.org/insurance-topics/auto-insurance
- `source_class=regulator`; kind: insurance-supervisor association educational topic page, not binding law; published unknown; `updated_at=2025-09-26` visible; version: live page; status: public education; effective not_applicable.
- `access_status=partial_text`; `access_method=direct_page`; reviewed_scope: `Background`, `Pricing`, `Coverages`, overview of UBI/telematics.
- Jurisdiction: US auto insurance; `independence_group=naic_education`.
- Limitations: licensing/rating factor legality depends on the state; the list of factors is not carried over as permission for any product. The synthetic insurance pool is an original illustration of risk, not a calculation of regulatory capital, IFRS17 or a specific insurer's premium.

## P00-S021 — FSI: SupTech and the role of supervisory expertise

- `snapshot_id=P00-S021-20260915`; authors: Simone di Castri, Stefan Hohl, Arend Kulenkampff, Jermy Prenio; publisher: BIS Financial Stability Institute; title: *The suptech generations*, FSI Insights No19.
- PDF URL: https://www.bis.org/publications/fsi-insight-19-suptech-generations.pdf
- Landing: https://www.bis.org/publications/fsi-insight-19-suptech-generations
- `source_class=research`; kind: policy research paper; `published_at=2019-10-17` (landing), PDF October 2019; status: published FSI Insights, peer-reviewed status not identified; effective not_applicable.
- `access_status=partial_text`; `access_method=official_pdf`; reviewed_scope: Executive summary printed pp.1–2; §§1–3 printed pp.3–6. Method: initiatives in 39 authorities, 31 jurisdictions; survey Q2 2019 supplemented by earlier studies/tracker.
- Locators: Executive summary, paragraphs about transparency and expertise; §2 `Suptech redefined`, paras6–9; §3 technology generations.
- `independence_group=fsi_r2a_2019`; interests: BIS/FSI and donor-funded RegTech for Regulators Accelerator; authors expressly do not speak for BIS/committees.
- Limitations: not a representative assessment of the whole market and not the level of adoption in 2026; the definition of innovative technologies is the authors' own. Rights: PDF permits brief attributed excerpts/translations; no full copy is stored in the database.

## P00-S022 — FSI: Open Finance

- `snapshot_id=P00-S022-20260915`; publisher: BIS Financial Stability Institute; title: *Key Considerations for Open Finance — Executive Summary*; personal author unknown.
- URL: https://www.bis.org/publications/fsi-summary-key-considerations-open-finance-executive-summary
- `source_class=analysis`; kind: official executive summary of joint high-level considerations; `published_at=2025-06-26`; update unknown; status: published summary; effective not_applicable.
- `access_status=full_text` of short HTML summary; `access_method=direct_page`; reviewed_scope: all summary prose; locator: opening paragraphs on permissioned sharing and broader products; discussion of risks and inclusion. Full joint report/FSI Connect tutorials not read.
- Scope: international design considerations for financial authorities; `independence_group=joint_openfinance_2025`; participating institutions described as BIS/CGAP/IMF/UNSGSA/World Bank.
- Limitations: potential benefits are not measured causal effects; no legal authority to access an individual's data created by this document. Permissioned reading is distinguished from payment initiation by the chapter's synthetic example.

## P00-S023 — World Bank/Gallup: Global Findex methodology

- `snapshot_id=P00-S023-20260915`; institutional authors/publishers: World Bank (book), Gallup Inc. (survey fieldwork); title: *The Global Findex Database 2025: Connectivity and Financial Inclusion in the Digital Economy*, Appendix A, *Survey methodology*.
- URL: https://thedocs.worldbank.org/en/doc/be6615202d1f08a25855c8ac2d615122-0050012025/related/Survey-methodology.pdf
- `source_class=research`; kind: empirical survey methodology appendix; published_at 2025, date_precision year; data collection 2024; version Global Findex2025; status: published research; effective not_applicable.
- `access_status=partial_text`; `access_method=official_pdf`; reviewed_scope: printed pp.267–269: target population, sampling, interview modes, mode changes; country table not fully analysed. Key locator: Appendix A p.267, first paragraphs and `Interview procedure`.
- Method: nationally representative samples across 141 economies, noninstitutionalized civilian population aged15+; survey mode varies. Appendix wording `more than 140,000`; report landing says about148,000; the chapter avoids a disputed pseudo-precise total.
- `independence_group=global_findex_2025`; interests: development/financial inclusion research; limitations: self-report survey, not transaction census or causal experiment; 2025 report measures 2024, not live2026. No chart/dataset copied.

## P00-S024 — OCC: the acquirer and intermediaries

- `snapshot_id=P00-S024-20260915`; author/publisher: Office of the Comptroller of the Currency; title: *Comptroller's Handbook — Merchant Processing*.
- URL: https://occ.treas.gov/publications-and-resources/publications/comptrollers-handbook/files/merchant-processing/pub-ch-merchant-processing.pdf
- `source_class=regulator`; kind: examiner handbook; version1.0 August2014; visible update note2025-03-20 removes reputation-risk references; status: published handbook at canonical download URL. Effective dates: supervisory guidance, no general permission conferred.
- `access_status=partial_text`; `access_method=official_pdf`; reviewed_scope: cover/version/update note, Introduction and `Types of Merchant Processors and Other Participants`, printed pp.1–4, especially `Acquiring Banks`, `Agent Banks`, `Third-Party Organizations`.
- Jurisdiction: US national banks/federal savings associations in OCC scope; `independence_group=occ_merchant_handbook`.
- Limitations: used to explain roles, not current scheme rules, registration requirements or global licensing. The earlier PDF with the suffix previous is not used; the document read carries an explicit 2025 change note. Old market shares and brand descriptions are not carried over into the chapter.

## Additional explainer read, not a separate basis for claims

Bank of England, *How is money created?*, https://www.bankofengland.co.uk/explainers/how-is-money-created — the full short explainer was read on 2026-09-15, updated 2019-10-01. It repeats the main mechanism of P00-S013 and is not counted as separate independent confirmation. Old shares of cash/reserves/deposits are not used. The remaining unavailable and rejected candidates are in [RESEARCH_NOTES.md](Research-notes.md).

### Clarification of 2026-09-17

P00-S007: the editor and the reviewer reopened the official PDF; the cover on p.1 states July2025. Additional access P00-S007-20260917; no saved copy. P00-S012: direct access during review remains unavailable; the attribution of the final answer and the scope of the index reading are limited by this access.
