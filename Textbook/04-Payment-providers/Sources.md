---
title: "Sources for Chapter 4"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Payment providers](README.md) · [Contents](../README.md) · [All sources and fact-checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Verification dates and source limitations are preserved. Hashes in historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Sources for Chapter 4

**Knowledge cutoff:** 2026-09-15 · **Version:** v0.1 · **Status:** `independently_reviewed_draft` · **Researcher:** `part_04_research` · private.

The fact-check of the original edition was completed on 2026-09-17. The link between the original version and the public copy, the scope of adaptation and the current navigation are described in the edition record.

## Common fields of the source cards

Below are the 24 sources that were actually read. Candidates that could not be obtained are moved to [RESEARCH_NOTES.md](Research-notes.md) and are not counted as evidence that was read. `source_id` is stable within this chapter; `snapshot_id = source_id-20260915` means the date of access, not an archived file.

For each card, unless overridden: `accessed_at=2026-09-15 Asia/Makassar`, `date_precision.accessed=day`; `language=en`; `supersedes=none`; `origin_source_id=self`; `canonical_url=url`; `doi=unknown`; `published_at=unknown`, `updated_at=unknown`, `version=unversioned live page`; `effective_from/effective_to=not_applicable` for help and reference pages, `unknown` for legally significant documents; `reviewer=see_REVIEW.md`, `reviewed_at=see_REVIEW.md`, `independent_review=see_REVIEW.md`. A search engine's `Last crawled` date was not used as the publication date.

**Rights:** open access allows reading via a public URL but does not prove an open license. `rights.storage=temporary research access only, no archival distribution granted`; `rights.quotation=brief attributed use, no long reproduction`; `rights.illustrations=not_reused`; `rights.redistribution=unknown/not_asserted`. The basis for public reading is the URL of each card; separate republication licenses have not been established. Third-party full texts and images are not included in the teaching knowledge base. `local_path=none in knowledge base`, `sha256=not_recorded`; temporary files in /tmp are not declared to be stable snapshots. The content of the sources is retold briefly and in our own words; most of the teaching material consists of the author's own connections and synthetic exercises.

`access_status=full_text` means the full body of the source was accessible; `reviewed_scope` separately states the sections that were actually read. For example, access to a 503-page rulebook does not mean that all of its pages were read.

## P04-S001 — FCA: perimeter for marketplaces

- `snapshot_id`: P04-S001-20260915.
- **Title/author/publisher:** Consider if you provide payment services; Financial Conduct Authority.
- **URL:** [original](https://www.fca.org.uk/firms/consider-if-you-provide-payment-services).
- `source_class=regulator`; `document_kind=perimeter guidance webpage`; `independence_group=FCA`.
- `published_at=2019-06-06`; `updated_at=2023-03-22`; both dates at day precision; version: these dates on the original. This is guidance on the PSRs/PSD2, not the text of the law. The date from which the rule applies was not established from this page.
- `jurisdiction=UK`; `activity=receiving customer money and onward payment`; `audience=marketplaces/booking services`.
- `access_status=full_text`; `access_method=direct_page`; `reviewed_scope=the entire substantive body of the short page`; locators: “If your business receives customer money before passing it on to a seller”; “You might be excluded from regulation if you”.
- **Limitations:** an individual exclusion and the applicable legal regime have not been determined; this requires analysis of the facts. Interest: a regulatory explanation, not a commercial sale.

## P04-S002 — Mastercard Rules, 2 June 2026

- `snapshot_id`: P04-S002-20260915.
- **Author/publisher:** Mastercard; **title:** Mastercard Rules.
- **URL:** [official PDF](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-rules.pdf).
- `source_class=scheme`; `document_kind=rulebook`; `independence_group=Mastercard`.
- `published_at/version=2026-06-02 / 2 June 2026`; date precision day; `status=public rulebook edition`. The cover gives the edition date, not a universal effective date for all provisions; `effective_from=provision-specific, no blanket date inferred`; non-public bulletins issued after this version were not checked.
- `jurisdiction=global base rules with Europe/US modifications`; `activity=acquiring PayFac and sponsored merchants`; audience: scheme customers/service providers.
- `access_status=full_text`; `access_method=official_pdf via web extraction`; **reviewed_scope:** cover; §§7.6.4–7.6.6, printed/PDF pp.172–174; Europe §7.6.5.1 p.321; US §7.6.5 p.367; US fee-disclosure text p.368. The rest of the 503 pages are not declared as read.
- **Locators:** §7.6.5 liability; §7.6.5.1(2) settlement proceeds; (3) delegation; (5) reporting; §7.6.6 identifiers. The Europe/US modifications were checked, but their specific conditions are not generalized.
- **Access limit:** the old mastercard.us URL and direct download returned 403; the new official URL was read via web, and no access restriction was circumvented.
- **Rights:** the PDF is marked Proprietary / All rights reserved; a brief synthesis is used, and illustrations are not copied. Interest: the network's own rules; this is not a government license.

## P04-S003 — Stripe Connect: merchant of record

- `snapshot_id`: P04-S003-20260915.
- **Author/publisher/title:** Stripe, Understand the merchant of record in a Connect integration.
- **URL:** [documentation](https://docs.stripe.com/connect/merchant-of-record).
- `source_class=vendor`; `document_kind=technical/product guidance`; `independence_group=Stripe`; `status=live documentation, maturity label not given`.
- `jurisdiction=Stripe Connect supported configurations, no worldwide legal conclusion`; `product=Connect`; audience: platforms.
- `access_status=full_text`; `access_method=direct_page returned text/markdown`; `reviewed_scope=entire 58-line body`.
- **Locators:** “Define the merchant of record” (direct, indirect + on_behalf_of, indirect without it); “Clear identification”; “Customer service responsibility”; “Merchant category”.
- **Limitations:** the API version is not pinned, and the Accounts v2 caveat is present; Stripe's description does not replace scheme rules and sales contracts. Platform loss liability and MoR are not treated as the same thing.

## P04-S004 — Paddle Master Services Agreement

- `snapshot_id`: P04-S004-20260915.
- **Author/publisher:** Paddle.com Market Ltd / Paddle Payments Ltd / Paddle.com Inc.; **title:** Paddle Master Services Agreement.
- **URL:** [agreement](https://www.paddle.com/legal/terms).
- `source_class=vendor`; `document_kind=contract`; `independence_group=Paddle`.
- `updated_at=2025-10-08`; version: Last updated 8 October 2025; date precision day. Effective rule in Acceptance of Terms: publication for new suppliers, 30 days after publication for existing suppliers; individual applicability not established.
- `jurisdiction=contracting entity depends on buyer/supplier location under §1`; `product=software/digital content resale via Paddle Checkout/Invoicing`.
- `access_status=full_text`; `access_method=direct_page`; `reviewed_scope=Acceptance; definitions; §§2–4; §9.4; §§10.1–10.4`; other provisions not asserted reviewed.
- **Locators:** §2 reseller and fulfilment; §§3–4 supplier amount/tax; §9.4 product information; §10 refunds/chargebacks and recovery from supplier.
- **Limitations:** a public contractual model, without an individual order form; MoR does not mean there is no regress to the supplier. The provider has a commercial interest; neither actual performance nor customer eligibility was checked.

## P04-S005 — Spreedly Transaction routing

- `snapshot_id`: P04-S005-20260915.
- **Author/publisher/title:** Spreedly; Transaction routing.
- **URL:** [documentation](https://developer.spreedly.com/docs/routing-rules-1).
- `source_class=vendor`; `document_kind=product documentation`; `independence_group=Spreedly`; `product=Optimize / Composer`.
- `updated_at=relative UI: Updated 12 months ago`; exact day unknown; no API version/commit. `jurisdiction=not specified; contractual gateway support still required`.
- `access_status=full_text`; `access_method=direct_page`; `reviewed_scope=entire substantive body`; locator: “Types of Routing” → Single/Static, Split Volume, Conditional Routing Rules.
- **Limitations:** statements about the optimal/most successful route are marketing; an independent uplift has not been established and is not carried over into the chapter. The section shows that routing can be configured, not that it is permitted to bypass a processor's decline.

## P04-S006 — Stripe identity verification

- `snapshot_id`: P04-S006-20260915.
- **Author/publisher/title:** Stripe; Identity verification for connected accounts.
- **URL:** [documentation](https://docs.stripe.com/connect/identity-verification).
- `source_class=vendor`; `document_kind=onboarding documentation`; `independence_group=Stripe`; `product=Connect`.
- `jurisdiction=country/account/capability dependent`; audience: platform responsible for relevant collection obligations.
- `access_status=full_text`; `access_method=direct_page/markdown`; **reviewed_scope:** introductory paragraphs, “Verification requirements”, “Onboarding flows”, “Collect additional public details”, “Business type”; the country legal-entity tables are not used for legal conclusions.
- **Locators:** country/capabilities/business structure/service agreement/risk factors; additional thresholds; currently_due/eventually_due; warning that verification does not satisfy independent platform legal duties.
- **Limitations:** the live guide does not fix every field of a specific account or a single UBO threshold for the whole world; no actual onboarding was carried out.

## P04-S007 — Square reserves (US)

- `snapshot_id`: P04-S007-20260915.
- **Author/publisher/title:** Square; Manage payment reserves with Square.
- **URL:** [US Support Center](https://squareup.com/help/us/en/article/6832-reserves-faq).
- `source_class=vendor`; `document_kind=support FAQ`; `independence_group=Square`; `jurisdiction=US`; `product=Square merchant card payment reserve`.
- `access_status=full_text`; `access_method=direct_page`; `reviewed_scope=About reserves; Before you begin`; rest of page not used.
- **Locators:** percentage set aside/released rolling; advance payments, industry disputes, sporadic activity, new seller history; individual Reserve Dashboard/email terms.
- **Limitations:** rates/durations are set individually; the figures 10%/90 days in the chapter are synthetic. The FAQ does not determine the accounting status in every jurisdiction. Interest: the provider explaining its risk policy.

## P04-S008 — Stripe payouts

- `snapshot_id`: P04-S008-20260915.
- **Author/publisher/title:** Stripe; Receive payouts.
- **URL:** [documentation](https://docs.stripe.com/payouts).
- `source_class=vendor`; `document_kind=product/operations documentation`; `independence_group=Stripe`; `product=merchant payouts`, not Global Payouts.
- `jurisdiction=country-specific supported payouts`; no universal T+X adopted.
- `access_status=full_text`; `access_method=direct_page/markdown`; **reviewed_scope:** “Payout schedule”; “How payout timing works”; “Settlement timing”; “Definition of days”; “Payout failures”. The full regional test tables were not examined.
- **Locators:** schedule does not change pending→available timing; definition of T; bank return and paid→failed up to five business days; incorrect-bank-information warning.
- **Limitations:** the provider's description and its status model; arrival at the bank was not checked on a real account. Dynamic documentation without an immutable version.

## P04-S009 — Adyen Settlement details report

- `snapshot_id`: P04-S009-20260915.
- **Author/publisher/title:** Adyen; Settlement details report.
- **URL:** [documentation](https://docs.adyen.com/reporting/settlement-reconciliation/transaction-level/settlement-details-report/).
- `source_class=vendor`; `document_kind=report specification`; `independence_group=Adyen`; `product=merchant Settlement details report`.
- `jurisdiction=Adyen merchant accounts; external/platform cases have caveats`.
- `access_status=full_text`; `access_method=direct_page`; **reviewed_scope:** introduction, “Entries”, “Merchant payout”, “Standard columns” through Batch Number; actual customer report not fetched.
- **Locators:** Refund/Chargeback rows; DepositCorrection/ReserveAdjustment/InvoiceDeduction; MerchantPayout bank reference; columns 9–14 Gross/Net/Commission/Markup/Scheme Fees/Interchange.
- **Limitations:** the spec allows optional columns, external settlement reference FX and different report scopes. It is not evidence of an actual movement of money at a bank.

## P04-S010 — Adyen invoice reconciliation

- `snapshot_id`: P04-S010-20260915.
- **Author/publisher/title:** Adyen; How do I reconcile my invoice?
- **URL:** [official Help](https://help.adyen.com/knowledge/finance/invoices/how-do-i-reconcile-my-invoice).
- `source_class=vendor`; `document_kind=operations guide`; `independence_group=Adyen`; `product=Payment Accounting Report / Payment processing invoice`.
- `access_status=full_text`; `access_method=direct_page`; **reviewed_scope:** “Which report to use”; “Essential ... Columns”; “Processing Fees”; “Payment Method Fees” → “Authorisation Scheme Fees”.
- **Locators:** processing on Received/SentForRefund; some Refused fees only at invoice generation; non-settled authorization fees; incomplete scope of settlement report for complete invoice reconciliation.
- **Limitations:** the specific rate depends on the contract; an empty field does not automatically mean a zero fee. Timezone details only provider-specific, not generalized.

## P04-S011 — Stripe Connect US pricing

- `snapshot_id`: P04-S011-20260915.
- **Author/publisher/title:** Stripe; Pricing information / Stripe Connect.
- **URL:** [public pricing](https://stripe.com/connect/pricing).
- `source_class=vendor`; `document_kind=price page`; `independence_group=Stripe`; `locale=United States (English)` — confirmed by the footer; `currency=USD`.
- `jurisdiction=US price page`; `product=Connect, You handle pricing for your users`; `published_at/updated_at=unknown`; quote not contract.
- `access_status=full_text`; `access_method=direct_page`; **reviewed_scope:** two pricing model sections; active account/payout figures; core payment price reference; page footer.
- **Locators:** “You handle pricing”: USD2 monthly active account; 0.25% + USD0.25 payout; platform responsibility for separate processing fees. “Stripe handles pricing” has different pricing allocation.
- **Limitations:** prices as of the viewing date; individual discounts, other fee items and geography were not established. The numerical example of 100 accounts and a 100000 payout is synthetic, not market data.

## P04-S012 — Stripe Stablecoin payments

- `snapshot_id`: P04-S012-20260915.
- **Author/publisher/title:** Stripe; Stablecoin payments.
- **URL:** [documentation](https://docs.stripe.com/payments/stablecoin-payments).
- `source_class=vendor`; `document_kind=payment method documentation`; `independence_group=Stripe`; `product=Stablecoin payments, Checkout/Elements/Billing/Connect`.
- `version=unversioned live markdown`; `status=US explicitly listed; EU/HK/MX/CH explicitly private preview`; no universal GA label inferred.
- `access_status=full_text`; `access_method=direct_page`; `reviewed_scope=entire 162-line body`; locators: “Payment method properties”, “Business locations”, “Payment flow”, “Limitations”, “Refunds”, “Connect support”.
- `jurisdiction=US and separately labelled private previews`; buyer-location statement has sanctions caveat.
- **Contradictions:** the list of country codes is broader than the sentence about the preview; the list is not treated as evidence of eligibility. Disputes section explains low fraud via bank authentication while flow describes wallet authentication; the causal low-fraud thesis is excluded.
- **Limitations:** individual activation was not checked; agent authority was not established; USDT does not appear in the accepted-token list that was read; this is not a full legal opinion on support for the asset.

## P04-S013 — Stripe restricted businesses

- `snapshot_id`: P04-S013-20260915.
- **Author/publisher/title:** Stripe; Prohibited and Restricted Businesses.
- **URL:** [original URL](https://stripe.com/legal/restricted-businesses); `canonical_url` returned: [en-de page](https://stripe.com/en-de/legal/restricted-businesses).
- `source_class=vendor`; `document_kind=contract-linked acceptance policy`; `independence_group=Stripe`.
- `updated_at=2026-05-13`, day precision; `effective_from=not independently established`; applies via relevant services agreement.
- `jurisdiction=general list plus explicit regional sections; en-de response locale`; `activity=merchant/financial/crypto eligibility`.
- `access_status=full_text`; `access_method=direct_page`; **reviewed_scope:** header, Why/How, Restricted Businesses introduction, Cryptocurrency, Financial products and services; no exhaustive sanctions opinion.
- **Locators:** additional due diligence; service-specific/revocable approval; limited cryptocurrency exchanges/wallets availability.
- **Limitations:** approval of ordinary merchant does not establish approval of separate financial use case. Commercial/compliance interest; the policy does not replace the law.

## P04-S014 — Triple-A service descriptions

- `snapshot_id`: P04-S014-20260915.
- **Author/publisher/title:** Triple-A Technologies Pte. Ltd.; What services does Triple-A provide?
- **URL:** [Help Center](https://support.triple-a.io/knowledge/what-services-does-triple-a-provide).
- `source_class=vendor`; `document_kind=support/product FAQ`; `independence_group=Triple-A`; `jurisdiction=not specified by this FAQ`; `product=crypto payments/invoice payments/crypto payouts/fiat payouts`.
- `access_status=full_text`; `access_method=direct_page`; `reviewed_scope=entire 15-line page`; locator: four service bullets; Invoice Payment settlement option.
- **Limitations:** it does not contain a token-network matrix, a list of merchant countries, licenses, a signed SLA or delegated-agent support; these capabilities are not claimed as confirmed. The date in the copyright notice is not treated as the update date.

## P04-S015 — Triple-A settlement threshold

- `snapshot_id`: P04-S015-20260915.
- **Author/publisher/title:** Triple-A Technologies Pte. Ltd.; I didn’t receive my settlement, what can I do?
- **URL:** [Help Center](https://support.triple-a.io/knowledge/i-didnt-receive-my-payment-what-can-i-do).
- `source_class=vendor`; `document_kind=support FAQ`; `independence_group=Triple-A`; `jurisdiction=unspecified`; `product=local-currency bank settlements`.
- `access_status=full_text`; `access_method=direct_page`; `reviewed_scope=entire 16-line page`; locator: heading and paragraphs on threshold USD3000 equivalent and at least one business day/bank holidays.
- **Limitations:** applicability to an individual contract, manual withdrawal and other products is unknown. This is a condition stated on the help page on the date of reading, not a guarantee of an actual payout. The figures in the teaching merchant flow are not taken from a real business.

## P04-S016 — Federal Reserve FEDS 2009/23

- `snapshot_id`: P04-S016-20260915.
- **Authors:** Robin A. Prager, Mark D. Manuszak, Elizabeth K. Kiser, Ron Borzekowski; **publisher:** Board of Governors of the Federal Reserve System.
- **Title:** Interchange Fees and Payment Card Networks: Economics, Industry Developments, and Policy Issues.
- **URL:** [official screen-reader full text](https://www.federalreserve.gov/pubs/feds/2009/200923/).
- `source_class=research`; `document_kind=FEDS discussion paper / economic survey`; `independence_group=FederalReserve-research`; `published_at=2009-05-13`; `version=2009-23`; day precision; `status=discussion paper, not current rulebook`.
- `jurisdiction=historical US industry and economic theory`; `access_status=full_text`; `access_method=direct_page`.
- **reviewed_scope:** title/authors/date; executive summary; §§II “Background…” and III economics through common-interchange discussion; not all later policy case law.
- **Method/locator:** analytical literature review, §III two-sided incentives/externalities. The chapter makes no current causal-effect claim of its own; old timing/rates/surcharge statements are not used as 2026 rules.
- **Limitations:** historical institutional data and theoretical assumptions; an authors' research paper is not a regulator's decision.

## P04-S017 — Rochet–Tirole, author working paper

- `snapshot_id`: P04-S017-20260915.
- **Authors:** Jean-Charles Rochet, Jean Tirole; **publisher/host:** IDEI/Toulouse School of Economics.
- **Title:** Platform Competition in Two-Sided Markets.
- **URL:** [author PDF](https://tse-fr.eu/sites/default/files/medias/doc/wp/2002/platform.pdf); [TSE catalogue](https://www.tse-fr.eu/publications/platform-competition-two-sided-markets?lang=en).
- `source_class=research`; `document_kind=author working paper`; `independence_group=RochetTirole`; `version/date=13 December 2002 on PDF title`; `published_at=2002-12-13 version date`; catalogue identifies IDEI WP152 (2003).
- **Status:** the catalogue says replaced by JEEA 2003 1(4), 990–1029; the journal version was not read and is not substituted with this copy. The DOI of the draft that was read has not been established.
- `access_status=full_text`; `access_method=official university PDF`; **reviewed_scope:** title/introduction; §2 pp.8–11; §4 pp.23–24; §6 pp.26–27; §7.1 context. The full proofs in the appendices were not checked.
- **Method:** a theoretical model of two-sided participation, quasi-demands, monopoly/competition; the teaching point is limited to the price-structure intuition and the form of the profit function in §2.1 p.9.
- **Limitations:** assumptions about matching/demand/price coherence; not an empirical forecast for 2026. `rights_basis_url=PDF and TSE catalogue`; open redistribution license unknown; figures were not used.

## P04-S018 — Aurazo, BIS Working Paper 1163

- `snapshot_id`: P04-S018-20260915.
- **Author:** Jose Aurazo; **publisher:** Bank for International Settlements, Monetary and Economic Department.
- **Title:** Interchange fees, access pricing and sub-acquirers in payment markets.
- **URL:** [PDF](https://www.bis.org/publications/working-paper-1163-interchange-fees-access-pricing-and-sub-acquirers-payment-markets.pdf); [catalogue](https://www.bis.org/publications/working-paper-1163-interchange-fees-access-pricing-and-sub-acquirers-payment-markets).
- `source_class=research`; `document_kind=working paper`; `independence_group=Aurazo`; `published_at=2024-01-25 catalogue`, day precision; `version=January 2024, WP1163`; `status=working paper`.
- `access_status=full_text`; `access_method=official_pdf`; **reviewed_scope:** PDF pp.1–5 (cover/abstract/introduction), pp.7–12 (§§2–3), pp.19–20 (§6 and the start of §7). The full algebra of §§4–5/appendix is not reproduced.
- **Method/locator:** theoretical six-agent model; upstream access fee vs downstream merchant competition; §3 assumptions pp.9–12; niche-market result §6 pp.19–20. No estimated current sponsor-price series.
- **Limitations/interests:** no-bypass and upstream market power, assumed efficiency advantages, no fixed entry cost in the baseline entry case; the model's card network objective is not a universal description of current listed corporations. Title notes FIT IN/TSE/Gates support; authors’ views, not BIS policy.
- **Rights:** PDF p.2 allows brief excerpts/translation with attribution; all rights reserved otherwise; diagrams/maps not reused.

## P04-S019 — US interagency third-party guidance

- `snapshot_id`: P04-S019-20260915.
- **Authors/publishers:** Federal Reserve, FDIC, OCC; **title:** Interagency Guidance on Third-Party Relationships: Risk Management.
- **URL:** [full official FRRS text](https://www.federalreserve.gov/frrs/guidance/interagency-guidance-on-third-party-relationships.htm); [dated announcement](https://www.federalreserve.gov/newsevents/pressreleases/bcreg20230606a.htm).
- `source_class=regulator`; `document_kind=supervisory guidance`; `independence_group=USBankRegulators`; `published_at=2023-06-06`; `version=SR-23-4`; date precision day.
- `status=final supervisory guidance`; footnote2 explicitly says no force/effect of law or new requirements; statutory duties it references are not newly enacted here. `effective_from=guidance issue date, not a new legal transition deadline`.
- `jurisdiction=US banking organisations supervised by agencies`; `activity=third-party risk incl merchant processing/fintech`; audience: banks.
- `access_status=full_text`; `access_method=direct_page`; **reviewed_scope:** A, B, C.1–C.3 substantive contract sections, C.4 monitoring, C.5 termination, footnotes1–2. Not every footnote-linked statute read.
- **Locators:** A responsibility retained; C.2 tailored due diligence; C.3 audit/information/default/termination; C.5 orderly transition.
- **Limitations:** principles vary with risk/complexity; this is not a promise that any clause can be imposed on a partner. It does not establish a separate BaaS license.

## P04-S020 — VisaNet Connect–Issuing

- `snapshot_id`: P04-S020-20260915.
- **Author/publisher/title:** Visa; Getting Started with VisaNet Connect - Issuing.
- **URL:** [Visa Developer](https://developer.visa.com/capabilities/visanet-connect-issuing/docs-getting-started).
- `source_class=scheme`; `document_kind=product onboarding documentation`; `independence_group=Visa`; `product=VisaNet Connect–Issuing APIs`.
- `jurisdiction=product eligibility; region-icon table not readable and not interpreted`; version/date unknown; `maturity=sandbox and production process distinguished, no release-date claim`.
- `access_status=full_text`; `access_method=direct_page`; `reviewed_scope=entire substantive body`; locators: “Eligibility”, “Next Steps”, “Best Practices and Tips”.
- **Limitations:** a specific issuing API, not all Mastercard/Visa sponsorship models. Sandbox connectivity is not production authorization; BIN sponsorship is not enough without reviews/security/program controls.

## P04-S021 — CBI EMI passporting

- `snapshot_id`: P04-S021-20260915.
- **Author/publisher/title:** Central Bank of Ireland; Passporting In/Out for Electronic Money Institutions.
- **URL:** [regulator](https://www.centralbank.ie/regulation/industry-market-sectors/electronic-money-institutions/passporting).
- `source_class=regulator`; `document_kind=operational regulatory guidance`; `independence_group=CBI`; `jurisdiction=Irish-authorised EMI and EU host states`; `activity=passporting`.
- `published_at/updated_at=unknown`; `version=live guidance`; `effective_from=not established from this page`.
- `access_status=full_text`; `access_method=direct_page`; `reviewed_scope=body from Passporting In/Out to Home/Host regulator roles`.
- **Locators:** introduction single authorisation; Branch/Agents/Distributors; Cross Border/Freedom of Services; Changes.
- **Limitations:** the page contains a sloppy string “2018 2011” in the name of the regulations; the name is not cited as a precise legal act. The full PSD2/national law via EUR-Lex was not accessible; detailed deadlines were not carried over into the chapter.

## P04-S022 — CBI PI passporting

- `snapshot_id`: P04-S022-20260915.
- **Author/publisher/title:** Central Bank of Ireland; Passporting for Payment Institutions.
- **URL:** [regulator](https://www.centralbank.ie/regulation/industry-market-sectors/payment-institutions/passporting).
- `source_class=regulator`; `document_kind=operational regulatory guidance`; `independence_group=CBI`; `jurisdiction=Irish-authorised PI and other EU Member States`.
- `published_at/updated_at=unknown`; `effective_from=not established`; `version=live guidance`.
- `access_status=full_text`; `access_method=direct_page`; `reviewed_scope=passporting body, especially Cross Border/Freedom of Services and Changes`.
- **Locators:** Cross Border/Freedom of Services requires communication of information; Changes notification. No individual passport/register checked.
- **Limitations:** supports the general mechanism; it does not replace a 2026 legal map and does not serve as evidence of worldwide authority or scheme membership.

## P04-S023 — Reddit: sponsorship ambiguity

- `snapshot_id`: P04-S023-20260915.
- **Author:** u/songtu-staygold; **publisher:** Reddit, r/fintech; **title:** BIN sponsorship vs Payment Facilitator.
- **URL:** [public thread](https://www.reddit.com/r/fintech/comments/10kwnbp/bin_sponsorship_vs_payment_facilitator/).
- `source_class=social`; `document_kind=question and comments`; `independence_group=reddit-10kwnbp`.
- `published_at=unknown exact day; visible UI relative date 4y ago`; `date_precision=relative`; the search engine's relative date and the UI differ, and no absolute date is invented. `updated_at=unknown`.
- `access_status=partial_text`; `access_method=direct_page`; `reviewed_scope=OP plus visible comment chain (PierreTanguy, OP acquiring clarification, Stonehill76, talltad); collapsed replies not read`.
- `jurisdiction=not fixed by OP`; `activity=question about acquiring BIN sponsorship/PayFac`; audience: forum users.
- **Locators:** OP; OP reply beginning “sorry for not being clear”; response discussing issuing vs later acquiring discussion.
- **Limitations:** self-selection, unverified expertise, later commercial replies; not statistics and not a source of law. Chapter cites question/ambiguity only, not correctness of comments. User identity not independently verified.

## P04-S024 — Stripe separate charges and transfers, specific variant

- `snapshot_id`: P04-S024-20260915.
- **Author/publisher/title:** Stripe; Create separate charges and transfers.
- **URL:** [main entry point](https://docs.stripe.com/connect/separate-charges-and-transfers); **read URL:** [official Markdown, Checkout stripe-hosted/web](https://docs.stripe.com/connect/separate-charges-and-transfers.md?platform=web&integration=checkout&ui=stripe-hosted).
- `source_class=vendor`; `document_kind=integration documentation`; `independence_group=Stripe`; `product=Connect separate charges and transfers + hosted Checkout`; API version/commit not provided.
- `jurisdiction=supported region list plus transfer restrictions; no universal cross-border claim in chapter`.
- `access_status=full_text`; `access_method=direct GET of official Markdown using urllib after web returned only variant index/error`.
- **reviewed_scope:** introduction; Cross-border transfers; post-payment events; Create a Transfer/availability; Asynchronous payment methods; Issue refunds; Reverse transfers. Language examples/test-card tables not treated as real transactions.
- **Locators:** opening bullets (platform balance bears fees/refunds/chargebacks); Issue refunds (refund leaves associated transfers unaffected); Reverse transfers (balance conditions); funds segregation explicitly private preview.
- **Limitations:** API success depends on capabilities, balances and region; it does not prove enforceable collection from an insolvent merchant. The temporary extracted text of the Stripe page is not an archived copy in the knowledge base.
