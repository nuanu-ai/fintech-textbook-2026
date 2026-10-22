---
title: "Chapter 6 — log of access and research limits"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Crypto and stablecoins](README.md) · [Contents](../README.md) · [All sources and fact-checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Review dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Chapter 6 — log of access and research limits

**Status:** `draft_for_review` · v0.1 · knowledge cutoff 2026-09-15 · actual reading 2026-09-15 UTC · private.

An internal organizational link from a historical author's note has been removed from the public edition; the research methodology and the external sources are preserved.

## What counts as evidence

The full text is in CHAPTER.md; the passages actually read are in the 34 cards of SOURCES.md, and the material conclusions are in the 43 cards of CLAIMS.md. The author does not create REVIEW.md and does not assign independent approval. Old agent notes were used as navigation leads, not as evidence. Adjacent chapters were used to align terms and boundaries; the external claims of Chapter 6 were checked separately.

The suffix `20260915` is the access date in UTC. The clock tool was checked during reading; local time in Asia/Makassar may already fall on the next day during later editing. Publications after 2026-09-15 are not included. PDFs were read in memory; the original copies and hashes were not saved. The text reports are not accompanied by third-party illustrations.

## Access gaps and permitted alternatives

| Candidate / topic | Actual result | How the conclusion is limited |
|---|---|---|
| EUR-Lex, Regulation 2023/1114 EN HTML/PDF | Several original URLs returned a JS challenge; BOE republication timeout, EBA page 403 | The official ESMA Interactive Single Rulebook was opened; Articles 3, 48, 49, 59 and 149 were actually read. This is a sufficient source for the stated rules, but not a full expert review of the whole of MiCA. Exact consolidation ID unknown. |
| [Garuda English PoC report](https://www.bi.go.id/en/rupiah/digital-rupiah/Documents/Laporan_POC_Proyek_Garuda_EN.pdf) and Indonesian PDF | Web timeout; direct request connection reset | The fully read BI release of 2024-12-13 (S028) was used; the quality of the tests and the full technical results are not declared verified. |
| MAS speech 2025-11-13 | The initial web extract returned an error | The official BIS republication was successfully retrieved with HTTP 200 and read directly, including the wholesale trial paragraphs. S029 has method=official mirror and one origin group; do not count BIS as a second confirmation. |
| [CBUAE Annual Report 2025](https://centralbank.ae/media/4qbn11cl/annual-report-2025-en.pdf) | Web access error | The chapter uses the primer and the Ministry of Finance event; a broad retail rollout as of the cutoff is not claimed. |
| Circle reserve report July 2026 | All 5 PDF pages are accessible; the name of the independent accountant is illegible in the extracted text layer | The scope of the opinion was read; the name was not guessed. Visually check the signature if the editor wants to name the firm. |
| Tether current legal page / RID | Selected terms were read; the purchase fee statements in the RID look inconsistent | The chapter uses only the consistent direct redemption fee. Do not carry over old delay/in-kind wording from third-party quotes as current. Do not claim that the company has no other audits. |
| Stripe stablecoin docs | The full short text was read | The country list is broader than the described geographic availability; the private preview status is kept. An odd sentence about bank authentication was not used as evidence of fraud protection. |
| Dynamic Base/Ethereum/CCTP/API docs | The sections read are accessible; there is no exact commit | No immutable snapshot, production verification or check of a specific network configuration. |

For long BIS PDFs where web extraction produced errors, ordinary HTTPS requests and pypdf were used in memory. This is reading of permitted, openly available primary sources, not bypassing a login or copying an archive.

## Reddit/X: we looked for cases, not a quota

The search looked for situations involving a wrong-network payment, an unsupported token, a refund after conversion and a stuck credit. It found useful questions, but access to the full threads was not obtained. The entries below are **candidates, not evidence**; authors and exact dates that could not be established from the accessible text remain unknown.

- [Reddit USDC, 194quq9](https://www.reddit.com/r/USDC/comments/194quq9/): direct open error; the content was not reconstructed from memory.
- [Reddit Coinbase, rrte6i](https://www.reddit.com/r/CoinBase/comments/rrte6i/): wrong-network invoice lead; direct open error, outcome unknown.
- [Reddit Bitget, 1arscyw](https://www.reddit.com/r/bitget/comments/1arscyw): in the index, a user describes a recovery after choosing a different network; direct open error, no full context and no confirmation of the outcome.
- [Reddit USDC, 1bc9nme](https://www.reddit.com/r/USDC/comments/1bc9nme/sent_usdc_to_pyusd/): search_index only; mixing up USDC/PYUSD is a topic to check, not an established incident.
- X: the query `site.x.com USDC wrong network payment refund` did not return a verifiable, relevant original post. Irrelevant results and promotional guides are not included in the chapter's sources.

Neither accusations nor promotional promises of recovery from these fragments are repeated as facts. The practical failures in the chapter are explicitly synthetic scenarios, supported by protocol mechanisms and vendor docs.

## Limits that matter to the reviewer

- USDC non-EEA and EEA have different contractual access to redemption; the exact URL of the EEA policy was passed to the Chapter 5 researcher for their own check.
- Reserve examination, all-company audit, liquidity and insolvency priority are different questions. The legal recovery waterfalls of specific issuers were not fully researched.
- Fiat payout timing is set by the specific rail/cutoff/support. The text accepts neither "all fiat only on weekdays" nor "all stablecoin settlement is instant".
- The CBDC table reports the latest evidence read, with its date; it does not promise an exhaustive live registry for 2026. The Garuda PoC, the SG trial and the UAE pilot are not called a public retail launch. Digital euro 2029 is conditional.
- BIS 1164: the model, selected empirical identification pages and the results were actually read; not all mathematical appendices. BIS 159: a 2024 survey, not a current map. A large onchain volume does not measure retail adoption.
- The treasury case is an operational subledger of a single principal P with an assumed USD functional currency. Client safeguarding and a mandatory IFRS journal entry are not derived from it; revaluation of the other balances at a stress exchange rate would be calculated separately.

## Author's check before handover

The check covers all eight exact v02 headings, the links between files, the match between claim IDs and source IDs, and the arithmetic of the base/stress examples and the exercises. The result of such a check is the quality of the author's draft; independent review remains a separate stage.

Result of the author's check on 2026-09-15 UTC: all 8 headings matched v02; 34 source IDs and 43 claim IDs are consistent; local links exist; base balances, fees, rounding, the intraday gap and three stress results were recalculated with Decimal. There are no template TODO/TBD markers. CHAPTER contains about 7,100 words (counted by whitespace separators); only four permitted MD files.
