---
title: "Chapter 7 — research log"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← AI agent payments](README.md) · [Contents](../README.md) · [All sources and fact-checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Chapter 7 — research log

2026-09-15 · private · author `part_07_research` · work under `RESEARCH_BRIEF.md`.

An internal organizational link from the author's historical note has been removed from the public edition; the research methodology and external sources are preserved.

## Versions checked through the public GitHub API

| Project | Object checked | SHA | Commit/release date |
|---|---|---|---|
| x402 | current `x402-foundation/x402` HEAD | `6b9302737f16eea7de90b3bf617c045cef23e032` | 2026-09-15, 14:04:22 UTC |
| x402, old entry point | `coinbase/x402` HEAD | `dd927a26cfefc98c24b3ec38b3a8f204dad0c60d` | 2026-04-21; not taken as the current foundation HEAD |
| MPP | `tempoxyz/mpp-specs` HEAD | `a938bfdd443a9683aa0fcbeae487ed4ffadfe4be` | 2026-09-09 |
| UCP | `v2026-08-25` tag | `cd78fb38e819de77d9b527d110476eccb876f1bd` | release published 2026-08-25, 13:53:03 UTC |
| UCP | main for comparison | `8e600b0588c72d3bf23498bd403ef915cb6b1559` | 2026-09-10; the release tag is cited |
| ACP | HEAD; the released specification 2026-04-17 inside it | `7fdd78df677a94dce04c770644b0fbbb1401272b` | 2026-07-18 |
| AP2 | HEAD; CHANGELOG v0.2.0 of 2026-04-28 | `e1ea56db72a6385bce3e5c1112b3a56ce60acb43` | 2026-04-29 |

Raw files were read at these SHAs. A SHA pins the repository, not a deployment and not a certification. Temporary permitted copies were used only for reading in the researcher's temporary folder; they are not a promised archive of the knowledge base. Links in the final catalog point to specific blobs. For MPP, the published spec artifacts and preview PRs mean something different from an adopted RFC. The IETF core `draft-httpauth-payment-01` was published on 2026-09-09 and remains an Internet-Draft.

## Social sources

On 2026-09-15 the chapter author independently opened and read through the Chrome UI:

- Solana `https://x.com/solana/status/2036507994381492326`: the main post and two visible continuations by the same author. The UI showed 2026-03-25, 02:18 AM; the display timezone is unknown. Confirms the announcement of MPP support, not an SDK test.
- deX402 `https://x.com/deX402_official/status/2043175089198293291`: the main post. The UI showed 2026-04-12, 11:51 AM; the display timezone is unknown. The statement that there are no payment processors is treated as a marketing claim, not a property of all implementations.

The editor had also read these posts earlier; the editor's note helped locate the originals, but the final cards record the chapter author's own independent reading. There were no account actions, messages or likes, and the full UI/reader profile was not saved. Images and full discussions were not examined.

Reddit `r/fintech`, IndianDownUnder, `1vtl49r`: the main post was read via web extraction. The date in the extracted UI is relative, `2d ago`, while search indexing reports something different; the exact day was not established. Included only as the author's test-mode experience and as a reason to check the wire state. The code mentioned by the author was not run; the payments were not repeated. We do not accept the claimed SPT availability for AU as current eligibility: the official page we read lists US, CA and selected European countries.

## Limitations and unavailable sources

- EUR-Lex ELI 2023/1113 returned a browser-check page; the text of this regulation was not read through that URL and is not used for any legal conclusion in Chapter 7. The legal analysis remains in Chapter 1.
- `specs/x402-specification.md` returned 404; the actual name is `specs/x402-specification-v2.md`, and that file was read.
- In the UCP release, the path `docs/specification/overview.md` does not exist; `overview/index.md` is used.
- The SPT page requires a variant query; the official Markdown variants for sellers and agents were read directly over HTTPS. A private-preview search snippet was not used in place of the live text.
- Research results were read from the main HTML text, including methods, models, results and limitations; no replication of Tamarin, the scanner or the attacks was performed. There is no basis for declaring that all reported flaws exist in the newer versions pinned here.
- Not checked: closed scheme contracts, certification, production eligibility of specific accounts, a full agentic liability rulebook or real customer outcomes. Vendor statements about guaranteed settlement have not been turned into a universal unconditional guarantee.

## Author's check before handover

Status on 2026-09-15: `draft_for_review`; CHAPTER.md, SOURCES.md and CLAIMS.md completed. About 6,200 words of main text, all modules 7.1–7.6 with their original titles, two original teaching Mermaid diagrams, seven exercises with answers. 42 unique source IDs with 42 resolved reference links; 51 unique claim IDs. Checked: absence of unknown source references, local links and the arithmetic of the money examples. The link to Chapter 9, which does not exist yet, points to the existing structure of the knowledge base rather than to a nonexistent file.

The named fields x402 paymentFlow/settlement_pending and ACP Allowance were re-checked against the pinned raw spec; the attribution of the Solana charge authors was corrected. UCP governance was additionally read in full in the separate repo `.github` at SHA `ced53b98c2064d472b41a5aff1c20b8261e6dd91`, commit 2026-09-15 07:55:35 UTC; card P07-S042. MAINTAINERS.md was read as context. Governance scope is not a substitute for bank approval or independent certification.

Separately checked: the separation of quote/consent/rail authorization/settlement/fulfillment/refund; released/draft versions and product availability; uncertain settlement with safe reconciliation; the principle agent identity ≠ principal authority; customer controls and the prompt-injection boundary. The money figures are synthetic; no real wallet/customer data was used. Closed liability rules, onboarding of a specific account, production and security PoCs were not checked. Only the FATF 2021 publication page was read, and this is stated explicitly; current legal obligations were not established.

An internal organizational link from the author's historical note has been removed from the public edition; the research methodology and external sources are preserved.
