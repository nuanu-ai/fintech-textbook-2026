---
title: "Chapter 9 — research log and boundaries"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Payment project workshop](README.md) · [Contents](../README.md) · [All sources and fact-checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Chapter 9 — research log and boundaries

**2026-09-17 · private · v0.1 · draft_for_review.** Author: `part_09_research`. These are the author's notes and the results of a technical check, **not an independent review**. `REVIEW.md` was not created by the author.

## Work done

- Read: RESEARCH_BRIEF, the README of the teaching knowledge base, SOURCE_DATASET_SCHEMA, MODULE_TEMPLATE, RESEARCH_RUN and the full Chapter 9 section of v02; the adjacent Chapter 8 section was read in full to align terms, the role of the subledger and unknown/recovery.
An internal organizational reference from the historical author's note has been removed from the public edition; the research methodology and external sources are preserved.
- All modules 9.1–9.5 were written, along with four detailed synthetic scenarios, a public timeline and eight exercises with explanations.
- The chapter's own catalog contains 19 external sources and 2 internal inputs; 26 claim cards, including 3 working hypotheses and one explicitly open question about dating the dynamic docs. Sources from other chapters were not substituted for independent reading.

## Cutoff date and precision

The task date is the 2026-09-15 cutoff; the actual session took place on 2026-09-17. The clock was checked: 05:18:19 UTC / 13:18:19 Asia/Makassar. That is why all new snapshots carry the suffix `20260917`, not a fictitious `20260915`.

For dynamic pages, the text is confirmed as of the reading date. **There are no saved archived versions of the Stripe docs/FAQ and the x402 README as of 15 September.** Their product/API observations are explicitly limited to 17 September, and the original teaching constructs are not presented as historical attestation. Dated acts and publications from 2013–2026 before the cutoff are used with their own dates. Recent related posts and search labels do not replace the date of the main document.

Important observations for the editor of the 8–9 pair:

1. When read on 17 September, Stripe Stablecoin payments says `local currency` settlement, while keeping separate country/private-preview restrictions next to it. Support pages/older documents may say USD. The chapter does not resolve this by extending product availability; the EUR case is fully synthetic. Do not silently carry today's wording over into earlier snapshots.
2. The general and US URLs of the Stripe stablecoin terms redirect to the AU locale, but the text includes regional terms. The catalog records the actual URL; neither availability in Australia nor the contract applicable to a specific merchant is inferred from the redirect.
3. The Coinbase x402 README points to the x402 Foundation; both were reviewed, and the evidence catalog uses the Foundation. The exact SHA is not pinned. The names of new schemes from the current README are not used as facts for the historical cutoff.
4. In the Circle announcement, the body is dated 2023-03-12 and the page 13 March; the operational update has an as-of date of 15 March and a publication date of 16 March. Both pairs of dates are preserved.

## Unavailable, limited and unused candidates

| Candidate | What happened | How the conclusion is limited |
|---|---|---|
| [FCA Consider if you provide payment services](https://www.fca.org.uk/firms/consider-if-you-provide-payment-services) | The first response showed metadata; later reads returned timeout/internal error | Not used as a legal basis that was read; the narrow technical exclusion was read directly in the PSD2 consolidation |
| [AP2 topics/mandates](https://ap2-protocol.org/topics/mandates/) | Internal error | Not presented as a specification that was read; the available dated Google announcement was used, with an announcement-only limitation |
| [Circle March 11 update](https://www.circle.com/blog/an-update-on-usdc-and-silicon-valley-bank) | The historical link from the press release redirected to the general blog | The original text was not reconstructed; the timeline is built on the Fed statement and the two available Circle originals |
| [AP2 GitHub](https://github.com/google-agentic-commerce/AP2) | The README is available but did not provide the required exact immutable version of mandates | Not used as evidence of current protocol conformance; runtime/samples were not run |
| [Stripe support — stablecoin onboarding](https://support.stripe.com/questions/get-started-with-stablecoin-payments) | A search result about USD settlement was found; the full original was not read in this chapter | The snippet is not treated as evidence; the discrepancy is noted as a reason to check the version history |
| Reddit megathread | The original post was read; the UI relative date `4y ago` does not give a reliable absolute day | The content is attributed; the price and statements about causes are not used as facts |

Reddit was chosen deliberately as a trace of public discussion of a historical incident. The X links from this post were not opened separately and are not counted as primary posts that were read. No quota for social media publications was introduced. New AP2/security preprints and the ASP paper found by search were not studied in full text, are not included in the evidence and are not used to draw conclusions about vulnerability/readiness. The chapter's scientific and methodological basis is the Sandve et al. article that was read; it is not an empirical payment study.

## Author's technical check

On 2026-09-17, a local verification calculation was run using exact decimal arithmetic. For each ledger, debits/credits and account balances were summed, and then independent formulas and answers were reconciled. The verification code ran in memory; no separate program or fictitious bank file was created.

| Case | Merchant's final cash | Payment costs | Refunds | Total of final debit = credit balances | Open accounts |
|---|---:|---:|---:|---:|---|
| A | 1,071.50 EUR | 3.50 EUR | 25.00 EUR | 1,100.00 EUR | PSP, reserve, in-transit, delivery, refund debt = 0 |
| B | 3,186,300 IDR | 13,700 IDR | 400,000 IDR | 3,600,000 IDR | PJP, in-transit, delivery, refund debt = 0 |
| C | 1,072.50 EUR | 2.50 EUR | 25.00 EUR | 1,100.00 EUR | Partner, in-transit, delivery, refund debt = 0 |
| D | 47.80 USDC | 0.20 USDC | 12.00 USDC | 60.00 USDC | Delivery, refund debt = 0 |

Also checked: buyer balances A 425 EUR, B 1,800,000 IDR, C 418 USDC; conservation of 120 USDC in D; rounding up to 28.571429 USDC; 434 transactions for the synthetic break-even; exercise C 34.50 USDC refund / 1,067.40 EUR bank / 67.40 EUR result. These tests confirm the arithmetic of the conditions, not real money or legal permissibility.

Headings are strictly 9.1–9.5; source IDs P09-S001–S021; claim IDs P09-C001–C026. Links to local files and the existence of cards for referenced IDs were checked. All evidentiary external URLs were actually opened, except for the explicitly listed unused candidates; the final link check is not an independent review of the substance.

## What remains open

- Archival evidence that the dynamic documents were unchanged as of 2026-09-15, and immutable protocol commits.
- The exact eligibility of real merchant/provider accounts, contracts, licenses/registrations, national transitions and geography. The brands named do not make up a recommended shortlist.
- Applicability of PBI 10/2025/PADG/technical instructions to a particular connector; the official summary is not enough for this.
- A full MiCA/PSD2 analysis of a specific stablecoin/EMT service and all participants, as well as the AML/sanctions/consumer/tax specifics of a real route.
- The legal and operational finality criterion for a specific QRIS/A2A/refund rail; the teaching wire-refunds and fees are not guaranteed properties of the QRIS API.
- The specific mechanisms of current AP2/x402 implementations, security audit, production resilience and product quality. Example D is not presented as an implementation/conformance test.
- An independent review of the 8–9 pair and corrections based on its results. No PDF was created; there are no published materials and no changes to the canon.

## Handoff to the independent reviewer

Check the four ledgers starting from the opening balances; the quality of the distinctions between authorization/settlement/payout/fulfillment; the soundness of closed/unknown recovery; the amount of reserve liquidity; the currency of the obligation under FX; whether the wording about laws and current docs is acceptable; the weight of the operator self-report in the historical incident. The author does not give themselves an independent verdict.

An internal organizational reference from the historical author's note has been removed from the public edition; the research methodology and external sources are preserved.
