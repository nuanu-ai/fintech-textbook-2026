---
title: "Editor's cross-chapter check"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../Methodology/Edition-record.md).

# Editor's cross-chapter check

2026-09-17 · private · completed_with_limitations. This is an additional check by root, not a replacement for the independent matrices.

| ID | Location and finding | Editor's change / independent check |
|---|---|---|
| ROOT-01 | Chapter 6 §6.1: the rounded 103.092784 was called the value before rounding | Now states 100/0.97 = 103.092783505…; rounding up to six decimal places is shown separately and explicitly. Re-checked by C; closed in the report. |
| ROOT-02 | Chapter 5 §5.3: redemption refers to 6.2 instead of 6.3 | Link corrected; re-checked by A; closed in the report. |
| ROOT-03 | P02-S026: the first GET of Apple en-ca returned 404 | This is access instability: B obtained the full text at the original URL; root also read Apple's canonical page. It is not classified as a false source or a broken link on the basis of one response. |
| ROOT-04 | P01-S029: an article by a BSA guest author was wrongly attributed to the regulator PDPC | Author, type, interest and access status corrected. The legal explanation in §1.6 was replaced with a narrow conclusion from the official guidance P01-S063; C052 added. Re-checked by A; closed in the report. |
| A-01 | P01-C021: FinCEN ruling S002 on processor/ISO does not support the statement about registration and licensing | Added FinCEN alert S064 with the exact fragment on p. 6; the chapter and the claim were corrected. S002 kept for its own question. Re-checked by A; closed in the report. |
| B-01 | P02-S015: inaccurate FAPI version date | The publication date 2025-02-22 is given; the approval date is shown separately. Re-checked by B; closed in the report. |
| B-02 | P02-S032 / C049: the Reddit author's interest was not stated | The promotion of the author's own validator/explainer was added to the card, the claim and the chapter. The experience is not presented as a confirmed incident. Re-checked by B; closed in the report. |
| B-03 | P03-S039: et al was wrongly added to José Aurazo | The sole author is given. Re-checked by B; closed in the report. |
| B-04 | P03-S011: Use Cases 2.3 without draft status | Technical Framework 2.4 final and Use Cases 2.3_DRAFT are separated, with dates. Re-checked by B; closed in the report. |
| B-05 | P03-S019: the title was derived from the file name | The title was replaced with Client FAQs, as on the cover; the filename External FAQs is kept in the URL. Re-checked by B; closed in the report. |
| B-06 | P03-S034 / C047: the JCB FAQ does not confirm the exact version 2.0 | Title/audience corrected; the version was removed from the source, the claim and the chapter. The EMV3DS authentication mechanism is confirmed. Re-checked by B; closed in the report. |
| C-01 | P06-S010: the PDF signatory and the meaning of the date were not established | After a visual reading, Deloitte & Touche LLP is given; 2026-08-27 is the signature date, not an established publication date. Re-checked by C; closed in the report. |
| C-02 | P06-S020: inaccurate page title | Now given as Processing windows & cutoff times; the date of the new reading is separated from the old observation. Re-checked by C; closed in the report. |
| C-03 | P06-C026 / S024: an unconfirmed conclusion about retail volume was attributed to BIS | The incorrect locator and the supporting attribution were removed. What remains is an explicitly synthetic counterexample, 300/100, without market statistics; verdict non_factual. A major error; re-checked by C; closed in the report. |
| C-04 | P07-S042: Apache-2.0 was attributed to the GOVERNANCE.md file without grounds | The unconfirmed license was removed; coverage unknown and a limited paraphrase in our own words. Re-checked by C; closed in the report. |
| A-02 | Chapter 1 §1.2: liability and control of outsourcing were jointly attributed to Art. 19 PSD2 | The exact Art. 19(6) for control and 20(2) for liability are given. Re-checked by A; closed in the report. |
| C-05 | P06-S021 / C023: too broad a locator for unhosted transfers | The exact FATF ¶203–204 and a working link to the official PDF were added; the difference between collection from the customer and transmission to a private individual is shown separately. Re-checked by C; closed in the report. |
| B-07 | P03-S024: the card title was derived from the file name | The exact title from the cover is given: Improving Authorization Management for Transactions with Stored Credentials. Re-checked by B; closed in the report. |
| B-08 | P02-C018: the original source does not confirm both parts of the nostro/vostro definition | Added P02-S043: Federal Reserve glossary, §7010.1, PDF p. 30; cited in the chapter and the claim. Read independently by B; the evidence is confirmed. |
| B-09 | P03-C012: the reference on PAR Inquiry does not fully confirm the difference from a credential | Added P03-S048: PCI SSC FAQ 1374, ¶3; payment initiation is separated from the teaching conclusion about consent. Read independently by B; the evidence is confirmed. |

The priorities and the final closure of the findings are recorded in the corresponding independent reports by chapter (historical or internal material; kept by the owner, outside this copy). This table links the findings to the changes made; a repeated record of a finding in an auditor's report is not another error.

## Cross-chapter mechanisms checked by root

- Stripe stablecoin acceptance in chapters 4/6/9: current business locations and preview are separated from customer geography; local-currency settlement does not promise EUR GA to a specific account. [Documentation](https://docs.stripe.com/payments/stablecoin-payments), Payment method properties / Business locations / Limitations, direct reading on 17 September.
- Stripe idempotency in chapters 8/9: the result is saved once execution has started, and the parameters must match; the retention period does not guarantee infinite deduplication. [Documentation](https://docs.stripe.com/api/idempotent_requests), main paragraphs, direct reading on 17 September. No confident contradiction between chapters was found.
- Modern Treasury pending includes posted, unlike Stripe's payment pending; Chapter 0 does not carry one definition over to the other. [Original](https://docs.moderntreasury.com/platform/reference/ledger-balances-object), Types of Balances / Available Balance, direct reading on 17 September; the historical index-only access remains a separate observation.
- Circle: EEA and retail/institutional routes in chapters 5/6 were compared with the [MiCA Redemption Policy](https://www.circle.com/legal/mica-redemption-policy), §§1–4. For non-EEA, the [USDC Terms](https://www.circle.com/legal/usdc-terms), §§1–2 (P06-S007/C003), were read separately: the geographic scope and the Circle Mint conditions for direct redemption. Both of the editor's accesses were on 17 September; complete legal regimes are not derived from a single document. Auditor C additionally read §8.4–8.5 on stress deferral; the existing text does not promise an unconditional execution time. A contractual possibility of redemption is not equated with a guarantee of instant payout.

The HTTP crawl in URL_CHECK.json is a check that a response was received, not evidence of content. An index, a guest article, a PDF, an official act and vendor docs are checked as different types of sources.

## Additional check of the summary

Auditor A separately compared this log with the chapters and reports: the 19 correction items and ROOT-03 are consistent. Following A's comment, the editor added a separate primary source, USDC Terms, to the non-EEA line and read §§1–2 independently. This is a refinement of the source in the summary, not a new change to the chapter or an additional finding on its content.
