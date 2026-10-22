---
title: "Research notes for Chapter 0"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Money and fintech basics](README.md) · [Contents](../README.md) · [All sources and fact-checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Research notes for Chapter 0

2026-09-15 · `draft_for_review` · private · author `part_00_research`.

## What limited the reading

| Candidate | Actually obtained | Decision |
|---|---|---|
| EUR-Lex, Regulation 2023/1114, https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32023R1114 | A JavaScript/robot verification page; the text was not read | EMT is defined based on the official ESMA Article 3. The full current legal regime and application dates are not inferred |
| EUR-Lex, Directive 2009/110, https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32009L0110 | The same verification; the text was not read | The EBA 2022_6336 final answer was used, limited to the text of the definition and the topic of classification |
| CPMI current glossary, https://www.bis.org/committees/cpmi/glossary | Web extraction returned only the introductory page, without substantive entries | Not claimed as a glossary that was read. Finality/money settlement rely on PFMI 8–9, which were read |
| Old CPMI PDFs `glossary.pdf`, `glossary_030301.pdf`, `publ/d00.pdf` | 404, or a redirect to a page with no terms, or a tool fetch error | Not used as evidence for definitions |
| ECB glossary, https://www.ecb.europa.eu/services/glossary/html/act4p.en.html | An accessible shell without the needed substantive glossary | Not a basis for claims |
| IAIS, *FinTech Developments in the Insurance Industry*, 21 February 2017, https://www.iais.org/uploads/2022/01/Report_on_FinTech_Developments_in_the_Insurance_Industry.pdf ; alternative official URL https://www.iais.org/file/65625/report-on-fintech-developments-in-the-insurance-industry | The first open recognized a 46-page PDF, but substantive reading of specific passages consistently ended in an internal error; search showed individual paragraphs | Not included in SOURCES as a report that was read. The insurance basis is NAIC; the full IAIS value-chain research remains additional reading |
| Reddit r/stripe, *Webhook: How to detect invoice that are in payout?*, https://www.reddit.com/r/stripe/comments/laz3za/ | A search snippet about succeeded and balance availability; direct open error; publication date and username not confirmed | Only a candidate for a question; not cited as investigated experience or as evidence of a failure |
| Modern Treasury `ledger-balances-object.md` | The documented path to the Markdown did not open via the web tool | The main card S004 honestly states that the table was read from the index; S017 was read directly |

The Reddit/X search targeted a meaningful question about the difference between success, balance and payout. No complete, reliably read social media case was obtained. Posts are not invented to fill a quota; the absence of a case does not prevent a verifiable analysis of the documents.

## Editorial decisions

1. The method section is devoted to a concrete analysis of Stripe/PFMI/Modern Treasury, not to a repetition of the internal brief.
2. One original end-to-end ledger: top-up 200, purchase 100, fee 5, external expense 2, payout 60, refund 30; separate client/own bank positions. This is an educational operational subledger, not a universal statutory chart of accounts.
3. The following are not carried over to 2026: the historical BoE 2014 share of deposits, early BIS 2023 statements about the regulatory environment for stablecoins, SupTech adoption in 2019 or BNPL data for 2023.
4. The definition of e-money is not reduced to any prepaid card: the EBA 2022_6336 final answer shows why that is dangerous.
5. An internal contradiction was found in OpenStax between the subtraction text and the correct equation. The error is recorded explicitly; the chapter's numerical logic is checked independently.
6. Links to Chapters 1/2/5/6/8 point to paths planned in advance; the lead editor checks that their files exist after the parallel build.

## Author's self-check

Checked: module IDs 0.1–0.6 and the exact titles from v02; both bank tables, the journal, the final balances, FX/bps/interest and the answers to the exercises. For the ledger, the total is Dr=Cr 422USD; final client cash105=customer liabilities100+merchant liabilities5; total assets128=liabilities105+equity23. The files remain `draft_for_review`; the independent check is done by another agent.

An internal organizational link from the historical author's note has been removed from the public edition; the research methodology and external sources are preserved.

The author's final automated self-check: 6 modules, 24 source cards, 48 unique claim IDs, about 6,450 words in CHAPTER. All links to the project's own files and to the canon exist. At the time of the check, the neighboring `part-05`, `part-06`, `part-08` did not yet have a CHAPTER; these are known dependencies of the parallel build, not missing materials of Chapter 0. Checked: 7 rows of bank balances, all journal rows, the result ACT/365=9.86 and FX spread≈18.50bps. The self-check does not replace an independent review.
