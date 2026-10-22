---
title: "Chapter 3 — sources register"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Cards: Visa and Mastercard](README.md) · [Contents](../README.md) · [All sources and fact-checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Check dates and source limitations have been preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Chapter 3 — sources register

**v0.1 · 2026-09-15 · private · independently_reviewed_draft · author: part_03_research · independent review: see REVIEW.md.**

Fact-checking of the original edition was completed on 2026-09-17. The relationship between the original version and the public copy, the scope of adaptation and the current navigation are described in the edition record.

## How to read the cards

The register follows SOURCE_DATASET_SCHEMA.md. The common fields below are inherited by **every** card unless it overrides them:

- `snapshot_id = <source_id>@2026-09-15`; this is an identifier of the reading of a specific version, **not an archived copy**. `supersedes = none`; `accessed_at = 2026-09-15, Asia/Makassar (UTC+08), date_precision of access = day`.
- `url = canonical_url = the card's link`, unless a redirect is indicated separately. `doi = unknown`; `updated_at = unknown`; `effective_to = unknown`; for a non-normative page `effective_from/to = not_applicable`. `origin_source_id = self`.
- `local_path = none`, `sha256 = not_applicable`: publishers' PDFs, images and full texts are not stored in the database. Some PDFs were read by extracting text from the official URL in memory; this is a reading of the original, not of an author's mirror.
- `rights`: storage/distribution of a full copy — `unknown, not exercised`; illustrations — `unknown, not used`; paraphrase in our own words with attribution, without long quotations. Public availability is not treated as a license. `rights_basis_url = card URL / document copyright notice`; explicit specifics are indicated below.
- `reviewer = see_REVIEW.md`, `reviewed_at = see_REVIEW.md`: the author checked the reading and traceability; the coverage, date and verdict of the independent agent are in REVIEW.md.
- `access_status = partial_text` for large documents means that the listed sections were read, not the whole document. `full_text` for a short page means that the main text was read; menus, other pages and related specifications are not automatically in scope.
- Edition/publication dates and effective dates differ. For a rulebook without a single confirmed effective date, the value is `effective_from = provision_specific`; the exact date of the provision used is given in CLAIMS. The cover date is not turned into the start date of every provision.
- `independence_group` by publisher: Visa/Verifi = `visa`; Mastercard/Ethoca = `mastercard`; independence of pages within one group is not asserted. Commercial interest: promotion of the publisher's own network and services; claimed marketing uplift/coverage metrics are not used as an independent assessment of results.

## Visa / Mastercard rules and infrastructure

### P03-S001 — Visa Core Rules and Visa Product and Service Rules

- Author/publisher: Visa; `class=scheme`, `kind=public rulebook`, `language=en`, `locale=global`; [official PDF](https://usa.visa.com/content/dam/VCOM/download/about-visa/visa-rules-public.pdf).
- `published_at/version=2026-04-18` (edition date), `date_precision=day`, `status=public edition available`, `effective_from=provision_specific`.
- `jurisdiction=global with named regional rules`; `activity=issuing/acquiring/processing/disputes`; `product=Visa`; `audience=members/acquirers/issuers`.
- `access_status=partial_text`, `access_method=official_pdf`; `reviewed_scope`: structure and introductory limitations; §4.1.7 virtual; §1.7 authorization/clearing/settlement; §7.4.14.1 Table 7-9, pp. 563–565; §10.4.5, pp. 635–636; §11.2–11.3, pp. 669–673. 923 PDF pages; the locator "p." is the document's printed page numbering, where given.
- `independence_group=visa`; limitations: public omissions of proprietary/security information, regional exceptions; the full VTS/VIRP guide was not obtained in this reading. The public PDF does not replace a participant's official contractual set.

### P03-S002 — Mastercard Rules

- Author/publisher: Mastercard; `class=scheme`, `kind=rulebook`, `language=en`, `locale=global`; [official PDF](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-rules.pdf).
- `published_at/version=2026-06-02`, `date_precision=day`, `status=public edition available`, `effective_from=provision_specific`.
- `jurisdiction=global with regional chapters`; `activity=membership/issuing/acquiring`; `product=Mastercard/Maestro as defined`; `audience=scheme customers`.
- `access_status=partial_text`, `access_method=official_pdf`; `reviewed_scope`: Applicability pp. 29–31; §§1.1–1.1.6 pp. 34–36; §§1.6–1.7.1 pp. 42–43; §5.8.1 p. 116. 503 PDF pages. Substantive paragraphs were read, not only the table of contents.
- `independence_group=mastercard`; limitations: regional/digital activity exceptions are separate; the public copy may be subordinate to the official Standards. This is not a permission for any particular startup.

### P03-S003 — Mastercard Transaction Processing Rules

- Author/publisher: Mastercard; `class=scheme`, `kind=rulebook`, `language=en`, `locale=global`; [official PDF](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/transaction-processing-rules.pdf).
- `published_at/version=2026-06-09`, `date_precision=day`, `status=public edition available`, `effective_from=provision_specific`.
- `jurisdiction=global/regional variations`; `activity=processing`; `product=Mastercard/Maestro`; `audience=issuers/acquirers/processors`.
- `access_status=partial_text`, `access_method=official_pdf`; `reviewed_scope`: §1.2 p. 29 account ranges; §2.2.1 p. 46 refund processing; Transaction Identification Requirements pp. 330–333, DE48 subelement 22 subfield 5 C/M and MIT types. 436 PDF pages.
- `independence_group=mastercard`; limitations: reading the message requirements does not give access to the full Customer Interface Specification; indicators and regional exceptions are checked against the specific integration.

### P03-S004 — Mastercard Switch Rules

- Author/publisher: Mastercard; `class=scheme`, `kind=rulebook`, `language=en`, `locale=global`; [official PDF](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-switch-rules-manual.pdf).
- `published_at/version=2025-12-16`, `date_precision=day`, `status=public edition available`, `effective_from=provision_specific`.
- `jurisdiction=system participation with local law`; `activity=clearing/settlement`; `product=Mastercard switching`; `audience=participants`.
- `access_status=partial_text`, `access_method=official_pdf`; `reviewed_scope`: §§3.1–3.1.2 p. 40, settlement methods, currencies, financial message cutoff, offset messages and funds-transfer law. 114 PDF pages.
- `independence_group=mastercard`; limitations: not the actual settlement calendar of a specific customer, not universal legal finality of all underlying rails.

### P03-S005 — Security Rules and Procedures — Merchant Edition

- Author/publisher: Mastercard; `class=scheme`, `kind=rulebook`, `language=en`, `locale=global`; [SPME PDF](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/SPME-Manual.pdf).
- `published_at/version=2026-08-04`, `date_precision=day`, `status=public edition available`, `effective_from=provision_specific`.
- `jurisdiction=global with listed exceptions`; `activity=merchant monitoring/specialty registration`; `product=Mastercard`; `audience=acquirers/merchants`.
- `access_status=partial_text`, `access_method=official_pdf`; `reviewed_scope`: §§8.2–8.3 pp. 87–88; §9.1 p. 111; §9.4.9 pp. 126–127. 236 PDF pages.
- `independence_group=mastercard`; limitations: the GMAP suspension has no resumption date in the provision that was read; ECM/HECM thresholds are referred to the Data Integrity Monitoring Program, which was not read. The crypto list is not carried over to Visa. No legal analysis of licenses was performed.

### P03-S006 — Quick Reference Booklet — Merchant Edition

- Author/publisher: Mastercard; `class=scheme`, `kind=MCC reference`, `language=en`, `locale=global`; [official PDF](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-quick-reference-booklet-merchant.pdf).
- `published_at/version=2026-06-02`, `date_precision=day`, `status=public edition available`, `effective_from=provision_specific`.
- `jurisdiction=Mastercard applicability`; `activity=MCC/TCC classification`; `product=digital goods`; `audience=acquirers/processors`.
- `access_status=partial_text`, `access_method=official_pdf`; `reviewed_scope`: MCC 5815–5818, pp. 162–164, including MCC/TCC pair requirements. 359 PDF pages.
- `independence_group=mastercard`; limitations: not all MCCs and exceptions; the selected codes are not a permission for any particular merchant.

### P03-S007 — Visa Direct for Card: Getting Started

- Author/publisher: Visa Developer; `class=scheme`, `kind=developer documentation`, `language=en`, `locale=global`; [page](https://developer.visa.com/capabilities/visa_direct/docs-getting-started).
- `published_at=unknown`, `version=undated page read 2026-09-15`, `date_precision=unknown`, `status=public product documentation`.
- `jurisdiction=market/product dependent`; `activity=funding/push transfers`; `product=Visa Direct for Card`; `audience=originators/developers`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: Getting Started, AFT/OCT, originator participation, end-to-end lifecycle, funds availability limitations.
- `independence_group=visa`; limitations: not the Visa Direct Service Guide, not a confirmation of card eligibility, route, timing or production approval.

### P03-S008 — Visa Token Service

- Author/publisher: Visa; `class=scheme`, `kind=product overview`, `language=en`, `locale=US/global product`; [page](https://usa.visa.com/products/visa-token-service.html).
- `published_at=unknown`, `version=undated`, `date_precision=unknown`, `status=public product page`.
- `jurisdiction=participating markets`; `activity=tokenization`; `product=VTS/PAR Inquiry/Cloud Token Framework/Click to Pay`; `audience=business partners`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: main text, the listed services; marketing uplift is not used.
- `independence_group=visa`; limitations: no production API, full scope or methodology for the claimed improvements.

### P03-S009 — Visa Token Service Fact Sheet

- Author/publisher: Visa; `class=scheme`, `kind=fact sheet`, `language=en`, `locale=global`; [official PDF](https://usa.visa.com/dam/VCOM/global/products/documents/visa-token-service-fact-sheet.pdf).
- `published_at=unknown`, `version=copyright 2022`, `date_precision=year_only_copyright_not_publication`, `status=historical product explanation`.
- `jurisdiction=illustrative global service`; `activity=token authorization flow`; `product=VTS`; `audience=business readers`.
- `access_status=full_text`, `access_method=official_pdf`; `reviewed_scope`: both pages, especially How it works, p. 2. The illustration was not copied.
- `independence_group=visa`; limitations: the diagram explains roles, not current fields/the full protocol.

### P03-S010 — EMV Payment Tokenisation: A Guide to Use Cases v2.2.1

- Author/publisher: EMVCo; `class=standard`, `kind=illustrative use-case guide`, `language=en`, `locale=global`; [official PDF](https://www.emvco.com/wp-content/uploads/2023/03/EMVCo-Payment-Tokenisation-A-Guide-To-Use-Cases-v2.2.1.pdf).
- `published_at/version=2023-01/v2.2.1`, `date_precision=month`, `status=historical edition; newer metadata in S011`.
- `jurisdiction=technical framework, not law`; `activity=tokenization`; `product=EMV payment tokens`; `audience=implementers`.
- `access_status=partial_text`, `access_method=official_pdf`; `reviewed_scope`: cover/imprint/contents, Introduction pp. 2–4; §§3–7 selectively pp. 15–16, 19–20, 24, 27–28, 30; §11.3 guest checkout pp. 150–155 and 157; §11.4 introductory paragraph p. 157. In the PDF, pages are offset by 13 relative to the main printed numbering; 187 PDF pages in total.
- `independence_group=emvco`; interests: standard-setting consortium; limitations: illustrative/non-exhaustive, does not replace the Technical Framework or a token program. Technical details outside the reviewed scope are not claimed as read. `rights`: reproduction/distribution governed by applicable EMVCo agreement per the imprint; the copy and figures are not distributed.

### P03-S011 — EMVCo current Payment Tokenisation / specifications index

- Author/publisher: EMVCo; `class=standard`, `kind=version index`, `language=en`, `locale=global`; [Payment Tokenisation](https://www.emvco.com/emv-technologies/payment-tokenisation/), additional [specifications index](https://www.emvco.com/specifications/page/2/).
- `published_at=unknown`; `version=metadata lists Technical Framework v2.4 2026-07-09 and A Guide to Use Cases v2.3_DRAFT, 2026-04-02 (comment period ended2026-05-01)`; `date_precision=day for TF metadata`, `status=metadata only; TF2.4 final, Use Cases2.3 draft; independently rechecked2026-09-17`.
- `jurisdiction=technical/global`; `activity=version tracking`; `product=EMV tokenization`; `audience=implementers`.
- `access_status=metadata_only`, `access_method=search_index` for the current versions; `reviewed_scope`: index information; the initial landing page opened, later readings were unstable; the full TF 2.4 was not read.
- `independence_group=emvco`; limitations: an input for further research, not a confirmation of the content of the new specs.

### P03-S012 — What is tokenization? A primer on card tokenization

- Author/publisher: Mastercard; `class=scheme`, `kind=product explainer`, `language=en`, `locale=global`; [page](https://newsroom.mastercard.com/news/perspectives/2024/what-is-tokenization/).
- `published_at=2024 (URL year; exact day unknown)`, `version=page read 2026-09-15`, `date_precision=year`, `status=public explainer`.
- `jurisdiction=participating markets`; `activity=tokenization`; `product=Mastercard tokens/MDES context`; `audience=general/business`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: main text, token request approval, stored token and cryptogram; effectiveness claims are not used.
- `independence_group=mastercard`; limitations: the primer is not a merchant MDES API spec.

### P03-S013 — Visa Acquirer Monitoring Program Fact Sheet

- Author/publisher: Visa; `class=scheme`, `kind=program fact sheet`, `language=en`, `locale=global regional table`; [official PDF](https://corporate.visa.com/content/dam/VCOM/corporate/visa-perspectives/security-and-trust/documents/visa-acquirer-monitoring-program-fact-sheet-2025.pdf).
- `published_at=2025 filename, exact day unknown`, `version=2025 sheet with 2026 threshold`, `date_precision=year/explicit effective day`, `status=public program summary`; `effective_from=2025-06-01 thresholds, 2025-10-01 enforcement after advisory, selected change 2026-04-01`.
- `jurisdiction=AP/Canada/EU/US and separately LAC/CEMEA, country footnotes`; `activity=monitoring CNP`; `product=VisaNet VAMP`; `audience=acquirers`.
- `access_status=full_text`, `access_method=official_pdf`; `reviewed_scope`: the entire 1 page, numerator/denominator, tiers, counts, portfolio conditions, exclusions, enforcement/country footnotes.
- `independence_group=visa`; limitations: 150 bps is not a global universal trigger; data extract and pre-dispute/CE timing affect the calculation. The full program guide was not read.

### P03-S014 — Dynamic Currency Conversion

- Author/publisher: Visa; `class=scheme`, `kind=consumer guidance`, `language=en`, `locale=en-US`; [page](https://www.visa.com/en-us/personal/travel/dynamic-currency-conversion).
- `published_at=unknown`, `version=undated`, `date_precision=unknown`, `status=public guidance`.
- `jurisdiction=consumer travel guidance`; `activity=DCC`; `product=Visa`; `audience=cardholders`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: the entire short page — disclosure, exchange rate/markup, choice/no pressure.
- `independence_group=visa`; limitations: not a full merchant rulebook and not an assessment of whether any particular rate is favorable.

### P03-S015 — Mastercard Currency Converter Calculator

- Author/publisher: Mastercard; `class=scheme`, `kind=calculator disclaimer`, `language=en`, `locale=en-US`; [page](https://www.mastercard.com/us/en/personal/get-support/currency-exchange-rate-converter.html).
- `published_at=unknown`, `version=undated`, `date_precision=unknown`, `status=public guidance`.
- `jurisdiction=issuer/card dependent`; `activity=FX`; `product=Mastercard`; `audience=cardholders`.
- `access_status=partial_text`, `access_method=direct_page`; `reviewed_scope`: disclaimer main text around conversion timing, bank fees and merchant/ATM conversion. An actual calculator quote was not obtained.
- `independence_group=mastercard`; limitations: issuer may not use Mastercard rate; auth-time default/processing-time fallback; not the rate of any particular bank.

### P03-S016 — Visa USA Interchange Reimbursement Fees

- Author/publisher: Visa; `class=scheme`, `kind=rate schedule`, `language=en`, `locale=en-US`; [official PDF](https://usa.visa.com/content/dam/VCOM/download/merchants/visa-usa-interchange-reimbursement-fees.pdf).
- `published_at/version=2026-04-18`, `effective_from=2026-04-18 as table states`, `date_precision=day`, `status=published rates`.
- `jurisdiction=US 50 states/DC as defined`; `activity=domestic interchange`; `product=debit/prepaid/credit/commercial tables`; `audience=merchants/acquirers`.
- `access_status=partial_text`, `access_method=official_pdf`; `reviewed_scope`: cover/scope, selected printed pp. 3–4 (PDF 5–6), CNP exempt debit 1.65%+0.15 and regulated debit 0.05%+0.21 with eligible 0.01 adjustment; Network 002 note. 28 PDF pages.
- `independence_group=visa`; limitations: only the selected rows and assumptions; not MDR, not a global rate, not a calculation of an actual merchant invoice.

### P03-S017 — Mastercard merchant interchange rates

- Author/publisher: Mastercard; `class=scheme`, `kind=pricing explainer`, `language=en`, `locale=en-US`; [page](https://www.mastercard.com/us/en/business/support/merchant-interchange-rates.html).
- `published_at=unknown`, `version=undated`, `date_precision=unknown`, `status=public pricing explanation`.
- `jurisdiction=US page`; `activity=interchange qualification`; `product=Mastercard`; `audience=merchants`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: main text What is interchange/MDR, qualification and official-rules precedence. The linked complete US rate PDF was not read.
- `independence_group=mastercard`; limitations: does not support numerical US MC rates; commercial interest.

### P03-S018 — Mastercard Canada Interchange Rates, May 2026

- Author/publisher: Mastercard Canada; `class=scheme`, `kind=rate schedule`, `language=en`, `locale=en-CA`; [official PDF](https://www.mastercard.com/content/dam/mccom/ca/en/business/support/documents/interchange-rates-en-may-2026.pdf).
- `published_at/version=2026-05 by filename`, `date_precision=month`, `status=public rate table`, `effective_from=unknown (not equated to filename)`.
- `jurisdiction=Canada domestic consumer credit selected table`; `activity=interchange`; `product=Core/World/World Elite/World Legend`; `audience=merchants/acquirers`.
- `access_status=partial_text`, `access_method=official_pdf`; `reviewed_scope`: p. 2 consumer credit rates, Digital Commerce and Standard rows, sale/refund distinction. 14 PDF pages; a later attempt to reopen it timed out; the initial text was read.
- `independence_group=mastercard`; limitations: the May edition date is not a proven single effective date; qualification details and current specific merchant applicability not fully verified. Used only as labeled table illustration.

### P03-S019 — Evolution of Compelling Evidence – Client FAQs

- Author/publisher: Visa; `class=scheme`, `kind=FAQ`, `language=en`, `locale=external/global with scope`; [PDF](https://usa.visa.com/content/dam/VCOM/regional/na/us/support-legal/documents/evolution-of-compelling-evidence-external-faqs.pdf).
- `published_at/version=2022-10`, `date_precision=month`, `status=historical FAQ; cover title Client FAQs rechecked2026-09-17, filename external-faqs is not title`, `effective_from=2023-04 as initiative described, not current full rule`.
- `jurisdiction=specified Visa dispute context`; `activity=compelling evidence`; `product=Visa CE3.0`; `audience=issuers/acquirers/merchants`.
- `access_status=partial_text`, `access_method=official_pdf`; `reviewed_scope`: issuer questions1–7, merchant FAQ, 4pages.
- `independence_group=visa`; limitations: a historical explanation of two prior undisputed transactions and match fields, not the full qualification for 2026.

### P03-S020 — Order Insight improved placement in Visa issuer dispute platform

- Author/publisher: Verifi (Visa group); `class=vendor`, `kind=product announcement`, `language=en`, `locale=global product`; [page](https://www.verifi.com/order-insight-improved-placement-in-visa-issuer-dispute-platform.html).
- `published_at=unknown`, `version=undated`, `date_precision=unknown`, `status=public product announcement`.
- `jurisdiction=participating issuers/merchants`; `activity=pre-dispute data sharing`; `product=Order Insight/VROL`; `audience=issuers/merchants`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: main text, the concluding paragraphs on Visa integration and non-Visa direct integration.
- `independence_group=visa`; limitations: mention July BER without a reliable year is not used as a current mandatory date; supported scheme ≠ every issuer connected.

### P03-S021 — Chargebacks Made Simple

- Author/publisher: Mastercard; `class=scheme`, `kind=introductory guide`, `language=en`, `locale=global`; [official PDF](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/chargebacks-made-simple-guide.pdf).
- `published_at=unknown`, `version=copyright2025`, `date_precision=year_only_copyright`, `status=public educational guide`.
- `jurisdiction=Mastercard overview`; `activity=disputes`; `product=Mastercom/chargeback systems`; `audience=business readers`.
- `access_status=partial_text`, `access_method=official_pdf`; `reviewed_scope`: pp. 2–5 dual/single, p. 7 families, pp. 8–10 second presentment/pre-arbitration/arbitration. 16 pages.
- `independence_group=mastercard`; limitations: the full current Chargeback Guide was not opened; there are no exact current global deadlines or an exhaustive digital-goods exception.

### P03-S022 — Ethoca Consumer Clarity

- Author/publisher: Mastercard/Ethoca; `class=vendor`, `kind=product page`, `language=en`, `locale=global`; [page](https://www.mastercard.com/global/en/business/cybersecurity-fraud-prevention/dispute-management/ethoca-consumer-clarity.html).
- `published_at=unknown`, `version=undated`, `date_precision=unknown`, `status=public product offer`.
- `jurisdiction=participating markets`; `activity=transaction recognition`; `product=Consumer Clarity`; `audience=issuers/merchants`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: main text, What makes us different/API integration. Marketing metrics were not carried over.
- `independence_group=mastercard`; limitations: the technical specification, a register of issuer coverage and commercial terms were not obtained.

### P03-S023 — Ethoca Smart Subscriptions

- Author/publisher: Mastercard/Ethoca; `class=vendor`, `kind=product page`, `language=en`, `locale=global`; [page](https://www.mastercard.com/global/en/business/cybersecurity-fraud-prevention/dispute-management/smart-subscriptions.html).
- `published_at=unknown`, `version=undated`, `date_precision=unknown`, `status=public product offer`.
- `jurisdiction=participating markets`; `activity=subscription management`; `product=Smart Subscriptions`; `audience=banks`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: main text, Powering the global subscription economy, explicit brand-agnostic wording.
- `independence_group=mastercard`; limitations: brand independence is the service's positioning; not proof of specific live issuer/merchant coverage.

### P03-S024 — Improving Authorization Management for Transactions with Stored Credentials

- Author/publisher: Visa; `class=scheme`, `kind=framework guide`, `language=en`, `locale=global`; [official PDF](https://usa.visa.com/content/dam/VCOM/global/support-legal/documents/stored-credential-transaction-framework-vbs-10-may-17.pdf).
- `published_at/version=2017-05 (filename10May17)`, `date_precision=month`, `status=historical framework; exact cover title independently checked 2026-09-17`, `effective_from=not used as current mandate`.
- `jurisdiction=Visa framework`; `activity=stored credential/CIT/MIT`; `product=COF`; `audience=merchants/acquirers`.
- `access_status=partial_text`, `access_method=official_pdf`; `reviewed_scope`: pp. 3–6 definitions, single-purchase storage distinction, CIT active interaction and MIT agreement basis. 15 pages.
- `independence_group=visa`; limitations: not current complete field implementation; historical dates do not establish 2026 full requirements.

### P03-S025 — Subscription / Recurring Payments and Negative Option Billing Merchants FAQ

- Author/publisher: Mastercard; `class=scheme`, `kind=FAQ`, `language=en`, `locale=global with named exceptions`; [official PDF](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/subscription_recurring-payments-and-negative-option-billing-merchants.pdf).
- `published_at=unknown`, `updated_at/version=2022-11`, `date_precision=month`, `status=historical FAQ`, `effective_from=initial2022-09-22 with modification2022-10-11 as described`.
- `jurisdiction=specified subscription merchants`; `activity=recurring billing/trials/notifications`; `product=Mastercard`; `audience=merchants/acquirers`.
- `access_status=partial_text`, `access_method=official_pdf`; `reviewed_scope`: questions1–9,18–23, first4pages of6; scope exclusions and receipt modification. Later full questions not used.
- `independence_group=mastercard`; limitations: cannot infer every monthly receipt mandatory today; merchant cohort and ACMP exception matter; current partner implementation not checked.

### P03-S026 — Visa Account Updater documentation

- Author/publisher: Visa Developer; `class=scheme`, `kind=developer overview`, `language=en`, `locale=global`; [page](https://developer.visa.com/capabilities/vau/docs).
- `published_at=unknown`, `version=undated current public page`, `date_precision=unknown`, `status=public service documentation`.
- `jurisdiction=participating issuers/acquirers`; `activity=account credential updates`; `product=VAU`; `audience=developers`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: overview and transaction information update types, including PAN/expiry/closed-account advices.
- `independence_group=visa`; limitations: not consent management and not a guarantee that every card is updated; old community messages about a sunset were not accepted as the current status.

### P03-S027 — Mastercard Automatic Billing Updater Privacy Notice

- Author/publisher: Mastercard; `class=scheme`, `kind=privacy notice`, `language=en`, `locale=Canada-hosted global notice`; [page](https://www.mastercard.com/ca/en/abu-privacy.html).
- `published_at=unknown`, `version/effective_from=2025-10-01`, `date_precision=day`, `status=effective date stated`.
- `jurisdiction=notice global scope including separate EEA/UK/Swiss controller`; `activity=ABU data processing`; `product=ABU`; `audience=cardholders/participants`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: main notice, data types, purposes/participants, effective date.
- `independence_group=mastercard`; limitations: the privacy notice confirms the data/model, not a recurring mandate and not a full integration specification.

## Independent education, adjacent schemes and law

### P03-S028 — The Payment System: Payments, Securities and Derivatives, and the Role of the Eurosystem

- Author: Tom Kokkola (editor), publisher ECB; `class=course`, `kind=educational textbook`, `language=en`, `locale=EU`; [official PDF](https://www.ecb.europa.eu/pub/pdf/other/paymentsystem201009en.pdf).
- `published_at/version=2010-09`, `date_precision=month`, `status=published textbook`.
- `jurisdiction=EU educational context`; `activity=payment systems/card models`; `product=general`; `audience=students/practitioners`.
- `access_status=partial_text`, `access_method=official_pdf`; `reviewed_scope`: imprint, pp. 55–57 and 139–140, three/four-party models and processing. 371 PDF pages.
- `independence_group=ecb`; interests: central-bank educational perspective; limitations: established models, not current rules/market share in 2026. `rights`: imprint permits educational/noncommercial reproduction with source acknowledgment; diagrams not copied; no full copy redistributed.

### P03-S029 — Report on card schemes and processors

- Author/publisher: ECB; `class=regulator`, `kind=market report`, `language=en`, `locale=EU`; [official PDF](https://www.ecb.europa.eu/pub/pdf/other/ecb.reportcardschemes202502~1614226b0a.en.pdf).
- `published_at=2025-02-28`, `version=February2025`, `date_precision=day (publication announcement)`, `status=published report`.
- `jurisdiction=EU/euro area`; `activity=card scheme/processing market`; `product=national/international schemes`; `audience=policymakers/market participants`.
- `access_status=partial_text`, `access_method=official_pdf`; `reviewed_scope`: Introduction and §§1–3, primary main text throughPDFp7 of9; survey basis and geography.
- `independence_group=ecb`; limitations: best-effort surveyFebruary2024 and historical2022/23 statistics, not current2026 live coverage. Scheme vs processor distinction used; no forecast adopted.

### P03-S030 — American Express OptBlue

- Author/publisher: American Express; `class=scheme`, `kind=merchant product/FAQ`, `language=en`, `locale=en-US`; [page](https://www.americanexpress.com/us/merchant/optblue.html).
- `published_at=unknown`, `version=undated`, `date_precision=unknown`, `status=public offer`.
- `jurisdiction=US eligible merchants`; `activity=acquiring channel`; `product=OptBlue`; `audience=merchants`.
- `access_status=partial_text`, `access_method=direct_page`; `reviewed_scope`: intro and FAQ on third-party provider setting rate and managing merchant relationship.
- `independence_group=amex`; interests: product marketing; limitations: eligibility, actual contract and all country models not examined; not proof every Amex transaction is direct closed-loop.

### P03-S031 — American Express Tokenization Services

- Author/publisher: American Express Global Network; `class=scheme`, `kind=product documentation overview`, `language=en`, `locale=global`; [page](https://network.americanexpress.com/globalnetwork/v4/products/card-on-file-tokenization/tokenization-services.html).
- `published_at=unknown`, `version=undated`, `date_precision=unknown`, `status=public overview`.
- `jurisdiction=country-dependent availability`; `activity=tokenization`; `product=COF/digital wallet/SRC/QR`; `audience=partners/aggregators`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: main product overview and registration path to implementation guide.
- `independence_group=amex`; interests: product offer; limitations: full implementation guide requires Amex Enabled registration, not read. Do not infer all-country launch or open API rights.

### P03-S032 — Discover Global Network Stored Token Services

- Author/publisher: Discover Global Network; `class=scheme`, `kind=product page`, `language=en`, `locale=global`; [page](https://www.discoverglobalnetwork.com/solutions/fraud-security/stored-token-services/).
- `published_at=unknown`, `version=undated`, `date_precision=unknown`, `status=public product offer`.
- `jurisdiction=participating markets`; `activity=tokenization`; `product=Stored Token Services/DDX`; `audience=partners`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: main description, domain restriction, cryptogram validation before detokenization, cloud/in-store DDX.
- `independence_group=discover`; interests: vendor/scheme marketing; limitations: no full operating/message/dispute guide or measured acceptance map.

### P03-S033 — JCB and Adyen launch card-on-file tokenization

- Author/publisher: JCB, announcement with Adyen; `class=scheme`, `kind=press release`, `language=en`, `locale=global`; [page](https://www.global.jcb/en/press/2025/202505131100_products.html).
- `published_at/version=2025-05-13`, `date_precision=day`, `status=announced rollout`.
- `jurisdiction=domestic/global merchants described`; `activity=COF tokenization`; `product=JCB/Adyen`; `audience=merchants/press`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: announcement, described rollout and parties.
- `independence_group=jcb-adyen`; interests: joint launch promotion; limitations: announcement not deployment outcome, not issuer coverage or independent performance study.

### P03-S034 — J/Secure™ FAQ for Merchants

- Author/publisher: JCB; `class=scheme`, `kind=FAQ`, `language=en`, `locale=global`; [page](https://www.global.jcb/en/products/security/jsecure/faq/).
- `published_at=unknown`, `version=undated`, `date_precision=unknown`, `status=public FAQ`.
- `jurisdiction=participating JCB issuers`; `activity=e-commerce authentication`; `product=J/Secure`; `audience=merchants/partners`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: main FAQ, 3DS-based authentication. Independent reread 2026-09-17: Q1/Q4 establish J/Secure / EMV3-D Secure without an exact2.0 release; the earlier version attribution was unsupported and removed.
- `independence_group=jcb`; limitations: not transaction authorization/settlement API; issuer participation and full liability rules not read.

### P03-S035 — UnionPay MoneyExpress

- Author/publisher: UnionPay International; `class=scheme`, `kind=product overview`, `language=en`, `locale=global English`; [page](https://www.unionpayintl.com/en/servicesProducts/servicesBenefits/crossBorderRemittance/index.shtml).
- `published_at=unknown`, `version=undated`, `date_precision=unknown`, `status=public product page`.
- `jurisdiction=remittance destination China`; `activity=cross-border remittance`; `product=MoneyExpress to UnionPay debit`; `audience=consumers/partners`.
- `access_status=partial_text`, `access_method=direct_page`; `reviewed_scope`: main product paragraphs: RMB credit after conversion and eligible card account.
- `independence_group=unionpay`; interests: marketing; limitations: speed/coverage claims not guaranteed or adopted, no complete eligibility/operating rules and no verified COF specs.

### P03-S036 — Instrumen Sistem Pembayaran Ritel

- Author/publisher: Bank Indonesia; `class=regulator`, `kind=instrument overview`, `language=id`, `locale=id-ID`; [page](https://www.bi.go.id/id/fungsi-utama/sistem-pembayaran/ritel/instrumen/default.aspx).
- `published_at=unknown`, `version=undated`, `date_precision=unknown`, `status=public regulator overview`.
- `jurisdiction=Indonesia`; `activity=retail payment instruments/GPN`; `product=ATM/debit cards`; `audience=public/industry`.
- `access_status=partial_text`, `access_method=direct_page`; `reviewed_scope`: ATM/debit and GPN logo paragraphs referring to PBI19/8/PBI/2017; KKI context.
- `independence_group=bi`; interests: regulator policy explanation; limitations: underlying complete current GPN legislation not examined, no universal mandate asserted for every card/transaction.

### P03-S037 — Commission Delegated Regulation (EU) 2018/389

- Author: European Commission, publisher DOUE via BOE; `class=law`, `kind=RTS original legal text`, `language=es`, `locale=EU`; [official BOE text](https://www.boe.es/buscar/doc.php?id=DOUE-L-2018-80459). Cross-check: [official English adopted article14 XML](https://www.legislation.gov.uk/eur/2018/389/article/14/adopted/data.xml).
- `published_at=2018-03-13`, `version=adopted2017-11-27 original`, `effective_from=2018-03-14 by article38; application2019-09-14 with article38 exceptions`, `date_precision=day`, `status=original adopted act, not complete current consolidation`.
- `jurisdiction=EU/EEA applicability must be checked`; `activity=SCA/secure communication`; `product=payment services`; `audience=PSPs/regulators`.
- `access_status=partial_text`, `access_method=direct_page (official publisher)/mirror for English adopted reproduction`; `reviewed_scope`: articles14,38 and BOE Analysis amendments list; Englisharticle14 full, not UK-current-law inference.
- `independence_group=eu-rts2018389`; limitations/conflict: BOE Analysis metadata says entrada14/11/2018, but article38 unequivocally next day after publication; operative provision governs. BOE lists2022/2360 changes to10/30; whole consolidation not read. Spanisharticle14corrigendum inS044. Not evidence for complete MIT scope exemptions.

### P03-S038 — Regulation (EU) 2015/751 on interchange fees for card-based payment transactions

- Author: European Parliament/Council, publisher DOUE via BOE; `class=law`, `kind=regulation original text`, `language=es`, `locale=EU`; [official BOE text](https://www.boe.es/buscar/doc.php?id=DOUE-L-2015-80958). Cross-check [official English adopted article8 XML](https://www.legislation.gov.uk/eur/2015/751/article/8/adopted/data.xml).
- `published_at=2015-05-19`, `version=adopted2015-04-29 original`, `effective_from=2015-06-08 overall; article8 applies2016-06-09 per article18`, `date_precision=day`, `status=original adopted act`.
- `jurisdiction=EU within article1 scope`; `activity=co-badging/choice`; `product=card-based payments`; `audience=schemes/PSPs/merchants`.
- `access_status=partial_text`, `access_method=direct_page`; `reviewed_scope`: articles8 and18, relevant recitals; Englisharticle8 full including6. Not all current national implementation/litigation checked.
- `independence_group=eu-ifr2015751`; limitations: not global routing right, no unlimited right to route token across domains; no full modern legal opinion.

### P03-S039 — Interchange fees, access pricing and sub-acquirers in payment markets

- Author: José Aurazo — the only author listed in the Authors block on the official BIS page (rechecked 2026-09-17; P03-S039-20260917); publisher BIS; `class=research`, `kind=working paper summary`, `language=en`, `locale=research/global model`; [official summary](https://www.bis.org/publications/working-paper-1163-interchange-fees-access-pricing-and-sub-acquirers-payment-markets).
- `published_at=2024-01-25`, `version=BIS Working Papers1163`, `date_precision=day`, `status=working paper, full paper not read`.
- `jurisdiction=theoretical payment market`; `activity=interchange/access pricing`; `product=acquiring/sub-acquiring`; `audience=researchers/policy`.
- `access_status=abstract_only`, `access_method=direct_page`; `reviewed_scope`: Focus/Contribution/Findings/Abstract on official page; requested work1163.pdf redirected to landing.
- `independence_group=bis-wp1163`; interests: research/policy, author views not automatically BIS policy; limitations: no proof, calibration, data or full method verified; only conceptual context, no empirical claim.

### P03-S040 — Mastercard Move: Payments to businesses

- Author/publisher: Mastercard; `class=scheme`, `kind=product page`, `language=en`, `locale=Europe English`; [Europe page that was read](https://www.mastercard.com/europe/en/business/payments/mastercard-move/payments-to-businesses.html). Original global path repeatedly timed out; same regional product page independently opened.
- `published_at=unknown`, `version=undated with October2025 metrics footnote`, `date_precision=unknown`, `status=public offer`.
- `jurisdiction=market-dependent`; `activity=business disbursements`; `product=Move portfolio`; `audience=banks/nonbank financial institutions/payment providers`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: Use Cases, FAQ, footnotes limiting endpoints/features/jurisdictions. Portfolio totals not adopted as current delivery guarantee.
- `independence_group=mastercard`; limitations: portfolio is broader than one card rail/Send API, exact product and market availability required.

### P03-S041 — Mastercard rules and compliance index

- Author/publisher: Mastercard; `class=scheme`, `kind=official rulebook index`, `language=en`, `locale=en-US`; [page](https://www.mastercard.com/us/en/business/support/rules.html).
- `published_at=unknown`, `version=undated`, `date_precision=unknown`, `status=current public index`.
- `jurisdiction=public global rules listing`; `activity=rule access`; `product=Mastercard`; `audience=participants/merchants`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: Rules impacting processors and merchants; precedence caveat and linked documents.
- `independence_group=mastercard`; limitations: index not full source, dates verified in individual PDF; public updates may lag official rules.

### P03-S042 — Visa Rules and Policy

- Author/publisher: Visa; `class=scheme`, `kind=public rulebook index`, `language=en`, `locale=en-US`; [page](https://www.visa.com/en-us/support/visa-rules).
- `published_at=unknown`, `version=undated`, `date_precision=unknown`, `status=public rules entry`.
- `jurisdiction=regional rule caveats`; `activity=rule access`; `product=Visa`; `audience=public/merchants`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: main intro on local applicability, withheld proprietary/security material and merchant agreements.
- `independence_group=visa`; limitations: dated sanctions examples on page not used as current sanctions law; PDF provision controls substantive claims.

### P03-S043 — Visa: Credit Card Processing Fees & Interchange Rates

- Author/publisher: Visa; `class=scheme`, `kind=pricing explainer`, `language=en`, `locale=en-US`; [page](https://usa.visa.com/support/small-business/regulations-fees.html).
- `published_at=unknown`, `version=undated`, `date_precision=unknown`, `status=public explanation`.
- `jurisdiction=US merchant guidance`; `activity=interchange/MDR`; `product=Visa`; `audience=small businesses`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: The Visa System: Rates, Fees and Rules; Interchange reimbursement fees paragraphs. Surcharging and debit-choice lines not applied globally.
- `independence_group=visa`; limitations: transfer-fee vs merchant-discount distinction; not every invoice charge or global fee schedule.

### P03-S044 — Corrigendum to Delegated Regulation (EU) 2018/389

- Author: EU publisher, publisher DOUE via BOE; `class=law`, `kind=corrigendum`, `language=es`, `locale=EU`; [official text](https://www.boe.es/buscar/doc.php?id=DOUE-L-2020-80441).
- `published_at=2020-03-24`, `version=Spanish corrigendum`, `date_precision=day`, `status=published correction`, `effective_from=correction to original provision`.
- `jurisdiction=Spanish language of EU RTS`; `activity=SCA recurring wording`; `product=article14`; `audience=legal readers`.
- `access_status=full_text`, `access_method=direct_page`; `reviewed_scope`: short complete correction replacing inicie with cree (creation) inarticle14.
- `origin_source_id=P03-S037`, `independence_group=eu-rts2018389`; limitations: correction not new independent policy source or all-language amendment.

### P03-S045 — Who Pays Whom? Anonymous EMV-Compliant Contactless Payments

- Authors: Charles Olivier-Anclin, Ioana Boureanu, Liqun Chen, Christopher Newton, Tom Chothia, Anna Clee, Andreas Kokkinis, Pascal Lafourcade; publisher/host: author institutional LIMOS page with HAL cover; `class=research`, `kind=author manuscript`, `language=en`, `locale=international`; [author's PDF](https://perso.limos.fr/~palafour/PAPERS/PDF/USENIX2025-Pay.pdf); canonical record shown on cover: [HAL04917364v1](https://hal.science/hal-04917364v1).
- `published_at=2025-01-29 HAL submission`, `version=HAL04917364v1; cover cites34th USENIX Security Symposium August2025`, `date_precision=day/month`, `status=author manuscript; conference attribution from cover, final proceedings not independently checked`, `doi=unknown`.
- `jurisdiction=technical EMV/privacy model, legal claims author-specific`; `activity=privacy protocol design`; `product=PrivBank/PrivProxy`; `audience=researchers`.
- `access_status=partial_text`, `access_method=direct_page author_pdf`; `reviewed_scope`: cover, abstract, Introduction, Research Questions, Related Work and AppendixB (PDFpages1–3,19); 31PDF-pages. Proofs, experiments and remaining threat-model details not fully read.
- `independence_group=who-pays-whom-authors`; interests: academic proposal, author affiliations include be ys Pay; limitations: paper proposes privacy engineering, not evidence deployed in Visa/MC; no marketshare/statistics claims adopted. No universal legal compliance conclusion independently endorsed. `rights=unknown for redistribution; no copy/figures stored`.

### P03-S046 — Dynamic Currency Conversion Performance Guide, Merchant Version

- Author/publisher: Mastercard; `class=scheme`, `kind=merchant guidance`, `language=en`, `locale=global with regional program sections`; [official PDF](https://www.mastercard.com/content/dam/public/mastercardcom/na/global-site/documents/DCC-Guide-2025-Merchant-Version.pdf).
- `published_at=unknown`, `version=2025 filename/copyright`, `date_precision=year_only`, `status=publicly hosted proprietary guide`, `effective_from=provision_specific; not inferred from copyright`.
- `jurisdiction=general DCC experience guidance used, no regional thresholds adopted`; `activity=DCC`; `product=Mastercard`; `audience=acquirers/merchants`.
- `access_status=partial_text`, `access_method=official_pdf`; `reviewed_scope`: Cardholder Experience Guidance pp. 31–32, training/cardholder choice/default selection. 42PDF-pages.
- `independence_group=mastercard`; limitations: no complete current binding rule extraction; marked Proprietary and Confidential despite public URL. No PDF, screenshots or reproduced guide text distributed; short factual paraphrase only.

### P03-S047 — International Travelers, Beware Dynamic Currency Conversion (DCC)

- Author: public Reddit account u/gbcox; publisher/host: Reddit r/CreditCards; `class=social`, `kind=personal-experience post`, `language=en`, `locale=US cardholder/Brazil story`; [exact permalink](https://www.reddit.com/r/CreditCards/comments/1i851tq/international_travelers_beware_dynamic_currency/).
- `published_at=unknown, UI relative label "2y ago" retained`, `version=archived post as read2026-09-15`, `date_precision=relative`, `status=public archived post`.
- `jurisdiction=claimed Brazil restaurant/US-issued card`; `activity=DCC complaint`; `product=Bilt Mastercard/Wells Fargo/REDE as author's report`; `audience=Reddit users`.
- `access_status=partial_text`, `access_method=direct_page`; `reviewed_scope`: complete initial post, author and relative date; not all851lines/comments. Initial fetch failed; later direct read succeeded. No outcome of complaint established in reviewed scope.
- `independence_group=reddit-gbcox-1i851tq`; interests: complainant/self-selection; limitations: transaction/receipt not independently inspected, 12% and chosen currency self-reported. Author's global assertions (DCC=scam, brand exclusions) not adopted. `rights`: public text attribution, no screenshots or extended reproduction.

## Access gaps and candidates that are not evidence

- EBA Single Rulebook Q&A 2018_4031, 2018_4048, 2019_4794: direct fetch/403 errors; snippets were not used for a legal conclusion about MIT. The exact answers were not reconstructed.
- EUR-Lex ELI original/HTML for RTS/IFR: JS verification; the openly available official BOE original texts S037/S038 and the English adopted article cross-check were used, with consolidation limitations.
- The full current Mastercard Chargeback Guide was not opened via the public shared path; S021 is a different, introductory guide. The Data Integrity Monitoring Program and the Visa Integrity Risk Program Guide were not obtained.
- Public VTS/MDES landing pages/primers do not provide the full merchant wire contract. Restricted access was not circumvented.
- Current EMVCo TF 2.4/new Use Cases: only version metadata S011, not technical evidence. S010 is a deliberately dated old edition that was read.
- X: a suitable original post with verifiable full content was not obtained for the evidence set. No fictitious date/quote/result was added.
- A full university video course with a lesson/timecode that was actually read was not found in the checked set; S028 is a textbook, S045 is a partially read scholarly paper, S039 is the summary of a working paper. These are three different levels of reading.

### Additional editorial check 2026-09-17

P03-S006 was reopened directly on 2026-09-17 (access P03-S006-20260917): QRG 2026-06-02, printed p. 164, MCC 5818. The condition of at least two of the categories 5815/5816/5817 was checked; there is no merchant size threshold in the definition. A historical copy was not kept; the initial reading on 15 September and its scope remain separate.

### P03-S048 — PCI SSC FAQ1374: Is Payment Account Reference (PAR) as defined by EMVCo considered PCI Account Data?

- Author/publisher: PCI Security Standards Council; source_class=standard; document_kind=FAQ; language=EN; [original FAQ1374](https://www.pcisecuritystandards.org/faqs/1374/).
- Page date: January2016; exact day and later update date unknown. Refers to EMVCo Specification Bulletin167 and PAR properties; not a complete current PCI DSS scope assessment.
- snapshot_id=P03-S048-20260917-deep; accessed_at=2026-09-17 Asia/Makassar; access_status=full_text for answer; access_method=direct_page. Root read the complete answer: transaction linkage; no initiation using PAR alone; data classification and connected-system caveats. Site navigation and unrelated FAQs excluded.
- Locator: answer paragraphs1–5, especially paragraph3 on authorization/capture/clearing/settlement initiation. Supports C012 credential distinction. Does not prove merchant consent, deployment, anonymity, or automatic PCI exemption for a connected environment.
- local_path=not_saved; hash=not_recorded. Limited original synthesis; no extended reproduction. Independent recheck recorded separately in audit matrices. Added 2026-09-17 to complete the evidence, without expanding the chapter's technical claim.
