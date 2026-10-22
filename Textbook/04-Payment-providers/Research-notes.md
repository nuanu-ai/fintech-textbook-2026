---
title: "Research notes — Chapter 4"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Payment providers](README.md) · [Contents](../README.md) · [All sources and fact-checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Verification dates and source limitations are preserved. Hashes in historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Research notes — Chapter 4

2026-09-15 · private · author: part_04_research · status: draft_for_review.

## Checked input and boundaries

An internal organizational link from the author's historical note has been removed from the public edition; the research methodology and the external sources are preserved.

## Versions found and important limitations

- Mastercard Rules: the new official path `/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-rules.pdf`, cover dated 2 June 2026, 503 pages. Via web, the text and individual pages are available; direct download returns 403. The old mastercard.us URL was not used as evidence. For this chapter, §§7.6.5–7.6.6 and the regional modifications were read, not the whole rulebook.
- Stripe stablecoin-payments: a dynamic original as of the date of reading. The US is listed explicitly; EU/HK/MX/CH are named as private preview. The list of country codes is broader than this sentence, so it does not prove general availability. The wording about authentication with bank in the Disputes section is inconsistent with the described wallet flow; the causal thesis about low fraud is not adopted. The page has no version/commit.
- Stripe separate-charges-and-transfers: the main URL returns an index of variants; web did not retrieve some of the variant URLs. A permitted direct GET of the public official Markdown of the web/Checkout/stripe-hosted variant succeeded. Lifecycle, transfers, async, refunds/reversals were read. The source is P04-S024, not just the index.
- EUR-Lex PSD2 original/consolidated HTML and PDF return a JS anti-bot challenge; EBA Q&A 2021_5726 returns 403. No circumvention was attempted. For the general explanation of passporting, the accessible pages of the Central Bank of Ireland are used. This is a regulator's guidance, not an independent check against the full consolidated law as of 2026.
- Reddit: the payout thread 1orjx8y was not retrieved (timeout). The substantive thread `10kwnbp` by songtu-staygold, about the confusion between acquiring and issuing sponsorship, is available. The UI shows the relative date `4y ago`; the exact day was not extracted from the page. The comments are not a rule and include commercial messages.
- BIS WP1163: the actual PDF was obtained via the PDF link on the original page; January 2024. The model description, the assumptions, sub-acquirer entry and the niche-market result were read. This is a theoretical model, not an empirical estimate of bank tariffs.
- Rochet–Tirole: the PDF from TSE is dated 13 December 2002; the catalogue marks it as IDEI Working Paper 152 (2003), replaced by JEEA 2003. What is cited is specifically the author version that was read; the journal text is not declared as read.

## Rights and provenance

The chapters are an original synthesis with synthetic examples. Third-party illustrations and full source PDFs are not included in the knowledge base. Working PDFs from BIS/TSE were temporarily extracted to /tmp for reading; the register does not promise archival preservation or a SHA. Public access is not the same as an open license. Search results do not become evidence in place of the original.

## Final author check

2026-09-15, Asia/Makassar: the six headings 4.1–4.6 exactly match the structure; the 24 source IDs and 44 claim IDs are sequential; all references to sources resolve to cards with the reading date 20260915. 26 numerical equalities were checked with decimal arithmetic. During this check, the sum of the crypto column was corrected: the components 0.12 + 0.06 + 0.08 + 0.04 + 0.05 + 0.02 + 0.03 give 0.40 USD / 2.00%, and with the allocated fixed cost of 0.20 they give 0.60. The table, the text that follows it and CLAIMS are consistent; the other exercises do not require this correction. The early editorial sample did not include the sum of these components.

CHAPTER contains 6,076 words, counted by splitting on whitespace. The local links within the chapter exist. The previously known neighboring targets part-06, part-08 and part-09 do not exist yet: other researchers are creating them, and this is a dependency of the overall build. There are no template placeholders; REVIEW.md was not created by the author. The status remains draft_for_review; an independent verdict is pending.
