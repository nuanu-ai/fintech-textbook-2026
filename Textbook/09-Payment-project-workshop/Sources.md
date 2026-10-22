---
title: "Chapter 9 — source catalog"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Payment project workshop](README.md) · [Contents](../README.md) · [All sources and fact-checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Chapter 9 — source catalog

**v0.1 · independently_reviewed_draft · private.** Author: `part_09_research`. Knowledge cutoff: **2026-09-15**. Actual reading of all listed originals: **2026-09-17, Asia/Makassar (UTC+08)**; `accessed_at=2026-09-17`, `date_precision=day`. Session clock check: 2026-09-17 05:18:19 UTC. Independent reviewer: see REVIEW.md (historical or internal material; kept by the owner, outside this copy).

Fact-checking of the original edition was completed on 2026-09-17. The relationship between the original version and the public copy, the scope of adaptation and the current navigation are described in the edition record.

## Common fields and limitations

For each card below, unless stated otherwise: `supersedes=none`; `origin_source_id=self`; `updated_at=unknown`; `language=en`; `locale=publisher original`; `access_status=partial_text`; `access_method=direct_page`; `reviewer=see_REVIEW.md`; `reviewed_at=see_REVIEW.md`; `review_status=see_REVIEW.md`. `Effective_from/effective_to=not_applicable` for explanations, documentation and historical announcements; the application dates of legal acts are given separately. The portion read is limited to `reviewed_scope`, not the whole site.

`Snapshot ID` identifies the **act of reading**, not a saved copy. For external sources `local_path=not_saved`, `sha256=not_computed`. Immutable snapshots of dynamic docs and exact repository commits were not obtained. A source without an update date confirms the observation of 17 September; its exact state on 15 September remains unknown. Later news was not used as facts as of the cutoff.

`Rights`: the publisher's copyright; permissions for full reprinting/figures/distribution are unknown unless explicitly stated. `rights_basis_url` matches the URL of the original and the notices on it. Links, short attributions and our own synthesis are used, without copying other people's illustrations. For vendor groups `interests=the vendor describes its own product`; this is not independent evidence of its effectiveness. Pages from one company share one `independence_group`.

## P09-S001

- **Title / author / publisher:** Directive (EU) 2015/2366 — PSD2; European Parliament and Council; EUR-Lex.
- **Snapshot:** `P09-S001-20260917`; **class / kind:** `law` / consolidated directive; **independence_group:** EU-legislation.
- **URL / canonical:** [consolidated 2025-01-17](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02015L2366-20250117); [original OJ](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32015L2366).
- **Dates / version:** adopted 2015-11-25; OJ publication 2015-12-23; consolidated version 2025-01-17. EUR-Lex shows this current consolidation. National application dates were not determined in this chapter; `effective_to=unknown`.
- **Reviewed scope / locator:** version metadata; Article 3(j); original recital 10 for the context of technical services.
- **Scope:** EU, exclusion of certain technical services; not a conclusion about any specific connector.
- **Limitations:** a consolidation is a documentation tool; a legal conclusion requires national application and the actual activity. Not holding funds does not exclude all regulated functions.

## P09-S002

- **Title / publisher:** Does PCI DSS apply to merchants who outsource all payment processing operations and never store, process or transmit cardholder data? PCI SSC, FAQ 1092.
- **Snapshot:** `P09-S002-20260917`; **class / kind:** `standard` / issuer FAQ; **independence_group:** PCI-SSC.
- **URL:** [FAQ original](https://www.pcisecuritystandards.org/faqs/does-pci-dss-apply-to-merchants-who-outsource-all-payment-processing-operations-and-never-store-process-or-transmit-cardholder-data/).
- **Publication / version:** unknown; dynamic FAQ, references to Requirements 12.8.2/12.8.4; not a standalone version of PCI DSS.
- **Access / reviewed scope:** `full_text` for the answer itself; the merchant responsibilities and validation paragraphs.
- **Scope:** merchants with outsourced processing; **limits:** does not determine specific SAQ eligibility and does not replace the standard or the acquirer's program. `Interests`: the standard's developer explains its own scope.

## P09-S003

- **Title / publisher:** Quick Response Code Indonesian Standard (QRIS); Bank Indonesia.
- **Snapshot:** `P09-S003-20260917`; **class / kind:** `regulator` / explanatory service page and FAQ; **independence_group:** Bank-Indonesia.
- **URL:** [BI QRIS](https://www.bi.go.id/en/fungsi-utama/sistem-pembayaran/ritel/kanal-layanan/QRIS/default.aspx).
- **Publication / version:** unknown; dynamic page. The historical launch on 2019-08-17 is described in the FAQ, but the chapter does not derive current authorizations from it.
- **Reviewed scope / locator:** Parties in QRIS Transaction Processing; Sources of Funds for QRIS Transactions; Types of QRIS Payments; FAQ What are the QRIS standards?; Pricing Schema reviewed for context, the exercise's fee is synthetic.
- **Scope:** Indonesia QRIS, sources of funds and presentment models.
- **Limitations:** the explanation is not a merchant agreement, a refund API specification or proof of specific bank finality. The partial cross-border overview is not used for geographic promises.

## P09-S004

- **Title / publisher:** Peraturan Bank Indonesia Nomor 10 Tahun 2025 tentang Pengaturan Industri Sistem Pembayaran; Bank Indonesia, Departemen Komunikasi.
- **Snapshot:** `P09-S004-20260917`; **class / kind:** `regulator` / official regulatory summary; **independence_group:** Bank-Indonesia; **language:** id.
- **URL:** [PBI 10/2025 — official summary](https://www.bi.go.id/id/publikasi/peraturan/Pages/PBI_102025.aspx).
- **Dates / version:** publication 2025-12-24; page updated 2026-04-21; `effective_from=2026-03-31`; `effective_to=unknown`. The act's version is PBI 10/2025; the HTML summary was read, not the full PDF of the act.
- **Reviewed scope:** Materi Pengaturan 1–4; TIKMI; Transisi; Penutup.
- **Scope:** Indonesia payment-system participants, transition; **limits:** no conclusion is drawn about the authorizations of a specific PJP/connector, the details of PADG 32/2025 or the technical instructions. The regulator is the primary source of the summary, but the summary is not treated as equivalent to reading the whole rule.

## P09-S005

- **Title / publisher:** The Payment Intents API; Stripe.
- **Snapshot:** `P09-S005-20260917`; **class / kind:** `vendor` / API guide; **independence_group:** Stripe.
- **URL:** [Payment Intents](https://docs.stripe.com/payments/payment-intents).
- **Publication / version:** unknown; dynamic guide, immutable API/doc version unknown.
- **Reviewed scope:** A complete set of APIs; Best practices; After the payment; Storing information in metadata.
- **Scope:** Stripe PaymentIntent object and application correlation; **limits:** the guide does not prove that every effect between the store and the PSP happens only once, nor settlement or the outcome for the goods. Support for a specific account was not checked.

## P09-S006

- **Title / publisher:** Refund and cancel payments; Stripe.
- **Snapshot:** `P09-S006-20260917`; **class / kind:** `vendor` / payment operations guide; **independence_group:** Stripe.
- **URL:** [Refunds](https://docs.stripe.com/refunds).
- **Publication / version:** unknown; dynamic docs.
- **Reviewed scope:** opening available balance paragraphs; Issue refunds; Refund destinations; Handle failed refunds; Refunds that require action.
- **Scope:** the conditions of the described Stripe methods; the text singles out card refunds.
- **Limitations:** does not promise uniform timelines for all banks and methods; instructions for a request do not prove crediting. The fees in case A are fictional and not derived from this document.

## P09-S007

- **Title / publisher:** Advanced error handling; Stripe.
- **Snapshot:** `P09-S007-20260917`; **class / kind:** `vendor` / technical guide; **independence_group:** Stripe.
- **URL:** [Advanced error handling](https://docs.stripe.com/error-low-level).
- **Publication / version:** unknown; dynamic docs.
- **Reviewed scope:** Errors in HTTP; Network errors; Server errors; Idempotency.
- **Scope:** the indeterminate outcome of Stripe API mutations; **limits:** not universal semantics for every HTTP 500 and every PSP. A request with a new key may repeat the economic effect; the state is investigated through the original operation.

## P09-S008

- **Title / publisher:** Idempotent requests; Stripe.
- **Snapshot:** `P09-S008-20260917`; **class / kind:** `vendor` / API reference; **independence_group:** Stripe.
- **URL:** [Idempotent requests](https://docs.stripe.com/api/idempotent_requests).
- **Publication / version:** unknown; dynamic API reference, exact API version not pinned.
- **Access / reviewed scope:** `full_text` for the explanation; the paragraphs on saving the result, pruning after an age of at least 24 h, parameter comparison, and the start of endpoint execution.
- **Scope:** Stripe documented idempotency contract; **limits:** the minimum age before a key can be deleted is not the same as a universal retention window; no specific key was checked.

## P09-S009

- **Title / publisher:** Payouts; Stripe.
- **Snapshot:** `P09-S009-20260917`; **class / kind:** `vendor` / operational documentation; **independence_group:** Stripe.
- **URL:** [Payouts](https://docs.stripe.com/payouts).
- **Publication / version:** unknown; dynamic docs.
- **Reviewed scope / locator:** only Payout failures: the paragraphs on returns by the bank, the paid→failed transition and bank details.
- **Scope:** Stripe bank payouts; **limits:** the rest of the long page was not read in full; its country tables are not used. Scenario C has its own synthetic conditions for a repeat payout.

## P09-S010

- **Title / publisher:** Stablecoin payments; Stripe.
- **Snapshot:** `P09-S010-20260917`; **class / kind:** `vendor` / payment-method documentation; **independence_group:** Stripe.
- **URL:** [Stablecoin payments](https://docs.stripe.com/payments/stablecoin-payments).
- **Publication / version:** unknown; dynamic docs; page observed 17 September, not immutable 15 September snapshot.
- **Reviewed scope:** Payment method properties; Business locations; Payment flow; Limitations; Refunds; Connect support.
- **Scope:** the described Stripe product; **limits:** the observed page says local currency settlement and, separately, private preview for some business locations. This does not confirm universal EUR availability. The chapter uses a narrow statement about the documented refund to the original wallet; specific eligibility was not checked.

## P09-S011

- **Title / publisher:** Stablecoin Payments; Stripe, payment method terms.
- **Snapshot:** `P09-S011-20260917`; **class / kind:** `vendor` / contractual terms; **independence_group:** Stripe.
- **URL / canonical observed:** [terms, AU locale](https://stripe.com/au/legal/stablecoin-payments). Requests to the general and `/us/` URLs were redirected to the AU locale; the text contains separate Regional Terms.
- **Publication / update / version:** displayed Last updated **2026-04-16**; a separate effective date is unknown, and applicability to a specific account was not established.
- **Reviewed scope:** §§1–8 and Appendix A, especially §§2, 7 and the mapping of regions.
- **Scope:** the architecture of separate settlement-provider agreements and Stripe entities.
- **Limitations:** the selected locale does not prove that the product is available to an Australian merchant; a contract page does not replace onboarding, partner terms and license checks. The chapter does not propose a real shortlist and draws no conclusion about the liability of a specific account.

## P09-S012

- **Title / author / publisher:** Regulation (EU) 2023/1114 — MiCA; European Parliament and Council; EUR-Lex.
- **Snapshot:** `P09-S012-20260917`; **class / kind:** `law` / regulation and consolidated text; **independence_group:** EU-legislation.
- **URL:** [consolidated 2024-01-09](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02023R1114-20240109); [original OJ](https://eur-lex.europa.eu/eli/reg/2023/1114/oj/eng).
- **Dates:** adopted 2023-05-31; OJ 2023-06-09; entry 2023-06-29; general application 2024-12-30; Titles III/IV 2024-06-30; Article 143(3) maximum transition 2026-07-01, subject to shorter national regimes. `effective_to=unknown`.
- **Reviewed scope:** original Articles 3(1)(16), 59–60, 143(3), 149; consolidated Article 59 and 143(3), version metadata.
- **Scope:** EU CASP services; **limits:** not a full legal opinion on the EMT/PSD2 overlap, exemptions, national implementation or any specific registration. A consolidation does not replace the authentic acts.

## P09-S013

- **Title:** Powering AI commerce with the new Agent Payments Protocol (AP2).
- **Authors / publisher:** Stavan Parikh; Rao Surapaneni; Google Cloud Blog.
- **Snapshot:** `P09-S013-20260917`; **class / kind:** `vendor` / dated announcement; **independence_group:** Google.
- **URL:** [AP2 announcement](https://cloud.google.com/blog/products/ai-machine-learning/announcing-agents-to-payments-ap2-protocol).
- **Published:** 2025-09-16, day precision; update unknown; version = announcement, protocol commit unknown.
- **Reviewed scope:** Why is a protocol needed?; How it works: Establishing trust via mandates and verifiable credentials; the human present/not present examples.
- **Scope / limitations:** the stated design of Intent/Cart mandates. Not a specification of the current implementation, not an independent security audit and not a universal legal allocation of liability. The publisher's words about non-repudiability are not carried over as a proven guarantee.

## P09-S014

- **Title / publisher:** x402 README; x402 Foundation GitHub repository.
- **Snapshot:** `P09-S014-20260917`; **class / kind:** `standard` / project README, protocol overview; **independence_group:** x402-project.
- **URL:** [x402 Foundation README](https://github.com/x402-foundation/x402).
- **Dates / version:** publication/update unknown; branch `main`, exact SHA unknown, mutable overview. `Maturity`: a published open-source protocol overview; production conformance of any individual implementation was not checked.
- **Reviewed scope:** Terms; Typical x402 flow, steps 1–12; Schemes vs Networks. The Coinbase fork was also reviewed to follow the move to the foundation source, but it is not counted as independent confirmation.
- **Scope:** the distinction between request/challenge, verify, settle and response; **limits:** the README is not a formal specification of all schemes. It does not confirm escrow, automatic refunds, product quality or the current readiness of Lab.
- **Rights:** the repository states Apache-2.0; no code or images were copied. Exact license coverage was not audited; there is no local copy/hash.

## P09-S015

- **Title:** Ten Simple Rules for Reproducible Computational Research.
- **Authors / publisher:** Geir Kjetil Sandve, Anton Nekrutenko, James Taylor, Eivind Hovig; PLOS Computational Biology.
- **Snapshot:** `P09-S015-20260917`; **class / kind:** `research` / methodological editorial, not an empirical payment study; **independence_group:** Sandve-et-al.
- **URL / DOI:** [article](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1003285), DOI `10.1371/journal.pcbi.1003285`.
- **Published:** 2013-10-24; version = journal article, update unknown.
- **Reviewed scope:** introduction; Rules 1–5, 7–10; Rule 6 reviewed as context on randomness. Rules 1, 3–5, 9 are used.
- **Scope:** reproducibility of computational research; `jurisdiction=not_applicable`.
- **Interests / limitations:** authors declare no competing interests; grants are described in the article; not evidence of the textbook's effectiveness and not permission to disclose private data.
- **Rights:** the article explicitly states Creative Commons Attribution; attribution is preserved, no illustrations or copies are used.

## P09-S016

- **Title / authors / publisher:** Joint Statement by Treasury, Federal Reserve, and FDIC; Janet L. Yellen, Jerome H. Powell, Martin J. Gruenberg; Federal Reserve Board.
- **Snapshot:** `P09-S016-20260917`; **class / kind:** `regulator` / joint press release; **independence_group:** US-bank-resolution.
- **URL:** [joint statement](https://www.federalreserve.gov/newsevents/pressreleases/monetary20230312b.htm).
- **Published / updated:** 2023-03-12, release 18:15 EDT; access `full_text` for press release.
- **Reviewed scope:** all main paragraphs, especially SVB depositors' access from Monday 13 March and the distinction between depositors and shareholders.
- **Scope:** US, specific SVB/Signature resolution actions; **limits:** gives no general guarantee for future bank failures and does not confirm any specific USDC payout. The regulators describe their own decision.

## P09-S017

- **Title / publisher:** $3.3 Billion of USDC Reserve Risk Removed, Dollar De-peg Closes; Circle.
- **Snapshot:** `P09-S017-20260917`; **class / kind:** `vendor` / company press release; **independence_group:** Circle.
- **URL:** [Circle release](https://www.circle.com/pressroom/3-3-billion-of-usdc-reserve-risk-removed-dollar-de-peg-closes).
- **Dates:** page publication 2023-03-13; body dateline Boston — 2023-03-12. Both dates are kept; update unknown.
- **Reviewed scope:** the whole short main text, the first paragraphs on the 3.3 billion USD reserve deposit and the expected reopening of banks.
- **Scope:** a historical statement by the USDC issuer, US banking dependencies; **limits:** issuer-interest; not an independent reserve audit. The headline about the depeg closing is not used as a verified market price.

## P09-S018

- **Title / author / publisher:** March 15, 2023 | Update on USDC operations; Team Circle; Circle.
- **Snapshot:** `P09-S018-20260917`; **class / kind:** `vendor` / operational update; **independence_group:** Circle.
- **URL:** [operational update](https://www.circle.com/blog/march-15-update-on-usdc-operations).
- **Dates:** body as of close of US banking operations 2023-03-15; page publication 2023-03-16; update unknown.
- **Reviewed scope:** the whole main text, the paragraphs on the backlog, 3.8 billion redeemed / 0.8 billion minted, and new banking connections.
- **Scope / limits:** an operator's account of its own operations. Substantially all does not mean every request; receipt by the end customer is not shown. Later related posts were not analyzed.

## P09-S019

- **Title / author / publisher:** USDC Depeg / Circle Megathread; `MediumAdhesiveness5`; Reddit, r/CryptoCurrency.
- **Snapshot:** `P09-S019-20260917`; **class / kind:** `social` / public discussion post; **independence_group:** reddit-MediumAdhesiveness5.
- **URL / permalink:** [original post](https://www.reddit.com/r/CryptoCurrency/comments/11odsvf/usdc_depeg_circle_megathread/).
- **Dates:** exact published_at unknown; viewed relative label `4y ago`, search/related metadata link the discussion to March 2023. We do not convert the inconsistent relative date into an exact day.
- **Reviewed scope:** original post, Updates, links to Circle and FDIC announcements; some top comments were viewed but are not used as facts.
- **Scope / limits:** `confirmed` only as to the content of the discussion. The market rate, causes and user outcomes were not checked; self-selection, possible later edits. The source is not an independent financial investigation. The public text was read without logging in to an account.

## P09-S020

- **Title / publisher:** FinTech 2026 — карта знаний и платежная специализация · v02 [FinTech 2026 — knowledge map and payments specialization · v02]; editorial structure of the Nuanu AI Lab textbook, individual author unknown.
- **Snapshot:** `P09-S020-20260917`; **class / kind:** `internal` / working curriculum; **independence_group:** Lab-editorial.
- **Path:** [STRUCTURE_v02_2026-09-15.md](../../Methodology/Original-plan.md); **language:** ru; **publication/version:** 2026-09-15 / v02; status working editorial structure.
- **Access:** local_file; the full Chapter 9 section and the adjacent Chapter 8 section were read. `local_path` = the original workspace file, not a newly created copy; `sha256=not_computed`.
- **Reviewed scope:** 9.1–9.5, 8.1–8.6 and the depth criteria.
- **Scope / limits:** a source of editorial requirements, not of external financial facts and not of launch decisions.
- **Public edition:** the editorial structure was included in this public textbook on 2026-09-18; its content is not external financial evidence.

## P09-S021

- **Publication status:** withheld_from_public_edition.
- **Scope:** a former internal organizational source is not included in the public edition. Its text, title, details and links are not distributed.
- **Use in public claims:** not used as evidence. P09-C008 and P09-C009 are stated as editorial positions with the audit verdict non_factual.
- **ID retention:** the identifier is kept for matching versions; this is an exclusion record, not an available primary-source card.

