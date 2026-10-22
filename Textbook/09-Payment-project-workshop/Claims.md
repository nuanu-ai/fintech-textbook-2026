---
title: "Chapter 9 — register of material claims"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Payment project workshop](README.md) · [Contents](../README.md) · [All sources and fact-checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Chapter 9 — register of material claims

**v0.1 · independently_reviewed_draft · private.** Author: `part_09_research`. Knowledge cutoff 2026-09-15; actual check **2026-09-17, Asia/Makassar**. Independent review: see REVIEW.md (historical or internal material; kept by the owner, outside this copy).

Fact-checking of the original edition was completed on 2026-09-17. The relationship between the original version and the public copy, the scope of adaptation and the current navigation are described in the edition record.

## Reading rules

For all cards: `last_checked_at=2026-09-17`, `reviewer=see_REVIEW.md`, `review_status=see_REVIEW.md`. `Confirmed` applies only to the stated content/scope: vendor docs confirm the described product; a publication confirms the author's own statement. This is not operational acceptance and not a legal opinion.

For dated legal acts and historical materials, their own period applies. For dynamic pages `as_of_observation=2026-09-17`; the state on 15 September, without an archived snapshot, is **open**. Source IDs and snapshot IDs lead to [Sources](Sources.md), where the URLs, dates and scope of reading are kept. `Effective_from/effective_to=not_applicable` for methodological/technical statements; for legal acts, see the corresponding source card. Review trigger: a change in the document/version, country, contract, authorizations or operation parameters, or the appearance of contradicting data.

The author's cases, ledgers, limits, fees, state names and recovery procedures are synthetic teaching constructs. Their arithmetic is checked separately; there is no fictitious external evidence for the amount of 100 EUR. The scope does not extend to Lab's real products. `Relation=supports` unless stated otherwise.

## P09-C001

- **module_ids:** 9.1; **kind:** legal; **status:** confirmed.
- **Claim:** PSD2 Article 3(j) contains a conditional exclusion for technical services and separately carves PIS/AIS out of that exclusion.
- **Evidence:** [P09-S001 / P09-S001-20260917](Sources.md#p09-s001), Article 3(j), consolidation 2025-01-17.
- **Scope / limits:** EU, classification of services; the absence of custody is not in itself a universal ground for exclusion. National applicability to a specific operator is open; no significant textual contradiction was found.

## P09-C002

- **module_ids:** 9.1, 9.5; **kind:** mechanism; **status:** confirmed.
- **Claim:** QRIS allows different sources of funds; static and dynamic merchant-presented QR codes differ in whether they contain the amount.
- **Evidence:** [P09-S003 / P09-S003-20260917](Sources.md#p09-s003), Sources of Funds; FAQ What are the QRIS standards?
- **Scope / limits:** Indonesia, content of the BI page observed 2026-09-17; QRIS as a whole is not equated with A2A. The state of the page on 15 September was not recorded.

## P09-C003

- **module_ids:** 9.1; **kind:** mechanism; **status:** confirmed.
- **Claim:** Outsourcing processing does not relieve the merchant of all obligations to protect account data and to manage the provider.
- **Evidence:** [P09-S002 / P09-S002-20260917](Sources.md#p09-s002), answer / merchant responsibilities.
- **Scope / limits:** PCI SSC FAQ 1092; no specific SAQ or scope assessment was chosen. The FAQ does not replace the full standard.

## P09-C004

- **module_ids:** 9.2; **kind:** product / contractual; **status:** confirmed.
- **Claim:** The Stripe Stablecoin Payments terms that were read describe separate merchant–Settlement Services Provider agreements and the allocation of settlement functions.
- **Evidence:** [P09-S011 / P09-S011-20260917](Sources.md#p09-s011), §§1–2, 7–8; version displayed 2026-04-16.
- **Scope / limits:** the observed document, AU locale with Regional Terms. Does not confirm access for a specific merchant, legal suitability or any specific company's contract.

## P09-C005

- **module_ids:** 9.2; **kind:** hypothesis; **status:** working_hypothesis.
- **Claim:** Some ordinary merchants may need crypto-in / fiat-out while keeping their usual accounting.
- **Evidence:** the author's H1; [P09-S020 / P09-S020-20260917](Sources.md#p09-s020), 9.2, `relation=context`, not demand evidence.
- **Scope / limits:** there is no defined cohort, observed demand or confirmed economics. The test criteria are explained in the chapter; there are no results from a real experiment.

## P09-C006

- **module_ids:** 9.2; **kind:** hypothesis; **status:** working_hypothesis.
- **Claim:** A suitable partner can cover some of the model's regulated and settlement functions, reducing how much the company has to build itself.
- **Evidence:** H2; [P09-S020 / P09-S020-20260917](Sources.md#p09-s020), 9.2, context; S011 shows one contractual architecture and does not prove suitability for a specific company.
- **Scope / limits:** a specific country, entity, functions, contract, eligibility, economics and refund path are needed. Named classes are not a shortlist.

## P09-C007

- **module_ids:** 9.2; **kind:** hypothesis; **status:** working_hypothesis.
- **Claim:** The usefulness of an agentic storefront and the usefulness of a new settlement rail can be tested in separate experiments.
- **Evidence:** the author's H3; [P09-S020 / P09-S020-20260917](Sources.md#p09-s020), 9.2, context.
- **Scope / limits:** this is a proposed test design, not an empirical conclusion about conversion. It requires controlled conditions and sufficient data.

## P09-C008

- **module_ids:** 9.2, 9.4; **kind:** editorial_guidance; **status:** confirmed (only as a description of this version's editorial principle); **audit_verdict:** non_factual.
- **Claim:** In this textbook, research analysis, a product decision and authorization for real-world actions are treated separately.
- **Evidence:** the author's editorial principle for the public version of 2026-09-18; [edition record](../../Methodology/Edition-record.md#public-adaptations).
- **Scope / limits:** a methodological recommendation, not a verified external financial fact and not a description of any organization's internal rules. The former organizational wording and its source have been removed; the ID is kept for matching versions.

## P09-C009

- **module_ids:** 9.3; **kind:** editorial_scope; **status:** confirmed (only as a description of this version's editorial scope); **audit_verdict:** non_factual.
- **Claim:** The topics listed in section 9.3 are excluded from the core of this teaching edition.
- **Evidence:** the course's editorial boundary; [P09-S020](Sources.md#p09-s020), [outline, 9.3](../../Methodology/Original-plan.md).
- **Scope / limits:** this is a choice of the textbook's scope, not an external financial fact and not a statement that taxes, credit risk or POS requirements are unimportant. The internal organizational part of the former statement was removed during the public adaptation of 2026-09-18.

## P09-C010

- **module_ids:** 9.4; **kind:** product; **status:** confirmed.
- **Claim:** The Stripe stablecoin documentation that was read describes full/partial refunds and the return of stablecoins to the original wallet.
- **Evidence:** [P09-S010 / P09-S010-20260917](Sources.md#p09-s010), properties / Limitations / Refunds.
- **Scope / limits:** observation 2026-09-17; not a property of all tokens and not an unchanged snapshot as of 15 September. The country/account, liquidity and an executed refund were not checked.

## P09-C011

- **module_ids:** 9.4; **kind:** methodology; **status:** confirmed.
- **Claim:** Sandve et al. propose tracking how results are produced, their versions, and the link between textual conclusions and data.
- **Evidence:** [P09-S015 / P09-S015-20260917](Sources.md#p09-s015), Rules 1, 3–5, 9; published 2013-10-24.
- **Scope / limits:** methodological editorial; applying it to the textbook is the author's transfer of the method. No study of this chapter's learning effect was conducted.

## P09-C012

- **module_ids:** 9.5; **kind:** mechanism; **status:** confirmed.
- **Claim:** The Stripe guide recommends saving/reusing a PaymentIntent for a resumable purchase and linking the payment to the order.
- **Evidence:** [P09-S005 / P09-S005-20260917](Sources.md#p09-s005), Best practices; After the payment; metadata.
- **Scope / limits:** the observed API guide; this does not guarantee the absence of duplicate fulfillment and does not prove bank settlement.

## P09-C013

- **module_ids:** 9.5; **kind:** mechanism; **status:** confirmed.
- **Claim:** Stripe describes a `500` on a mutation as potentially indeterminate and warns against using a new idempotency key when the original request may have had an effect.
- **Evidence:** [P09-S007 / P09-S007-20260917](Sources.md#p09-s007), Server errors.
- **Scope / limits:** Stripe API; not every HTTP error has the same semantics. The teaching recovery procedure additionally checks the order and fulfillment.

## P09-C014

- **module_ids:** 9.5; **kind:** mechanism; **status:** confirmed.
- **Claim:** Documented pruning of Stripe keys is possible once they are at least 24 hours old; after deletion, reusing the key may create a new request.
- **Evidence:** [P09-S008 / P09-S008-20260917](Sources.md#p09-s008), pruning paragraph.
- **Scope / limits:** not a statement about the exact deletion time of each key. Internal storage of the operation identity has its own separate retention period.

## P09-C015

- **module_ids:** 9.5; **kind:** product; **status:** confirmed.
- **Claim:** A Stripe card refund may wait for a sufficient available balance; the request and the final crediting are different things.
- **Evidence:** [P09-S006 / P09-S006-20260917](Sources.md#p09-s006), opening; Refund destinations; Handle failed refunds.
- **Scope / limits:** a specific product and the card branch; the synthetic fees/reserve of case A are not attributed to Stripe.

## P09-C016

- **module_ids:** 9.5; **kind:** regulatory description; **status:** confirmed.
- **Claim:** The BI QRIS overview describes approved PSPs and switching institutions in QRIS processing.
- **Evidence:** [P09-S003 / P09-S003-20260917](Sources.md#p09-s003), Parties in QRIS Transaction Processing.
- **Scope / limits:** Indonesia, BI's primary explanation; specific entities, authorized functions and contracts were not checked.

## P09-C017

- **module_ids:** 9.5; **kind:** legal context; **status:** confirmed to the extent of the official summary.
- **Claim:** The BI summary of PBI 10/2025 states that it applies from 2026-03-31 and describes a transition to a new model for regulating participants.
- **Evidence:** [P09-S004 / P09-S004-20260917](Sources.md#p09-s004), Materi Pengaturan; Transisi; Penutup.
- **Scope / limits:** a summary, not a full reading of the act/PADG/technical instructions. A licensing conclusion for a specific connector remains open.

## P09-C018

- **module_ids:** 9.5; **kind:** legal; **status:** confirmed.
- **Claim:** MiCA sets out specific grounds for providing crypto-asset services; Article 143(3) allows no transition beyond the maximum deadline of 2026-07-01.
- **Evidence:** [P09-S012 / P09-S012-20260917](Sources.md#p09-s012), Articles 59–60, 143(3).
- **Scope / limits:** EU; not an authorization for any individual partner and not a full analysis of the interaction with payments law. Classifying the actual function requires a separate check.

## P09-C019

- **module_ids:** 9.5; **kind:** product; **status:** confirmed.
- **Claim:** Stripe payout documentation allows for a later status change from paid to failed after a bank return.
- **Evidence:** [P09-S009 / P09-S009-20260917](Sources.md#p09-s009), Payout failures.
- **Scope / limits:** vendor documentation observed 17 September; not a universal timing guarantee from banks and not a statement that this happened in a real Lab case.

## P09-C020

- **module_ids:** 9.5; **kind:** product announcement; **status:** confirmed as the content of the announcement.
- **Claim:** The Google AP2 announcement describes Intent/Cart mandates as evidence of the user's intent and of the purchase.
- **Evidence:** [P09-S013 / P09-S013-20260917](Sources.md#p09-s013), How it works; published 2025-09-16.
- **Scope / limits:** an announcement, not the current spec, certified conformance or a universal legal guarantee. Case D is our own teaching model.

## P09-C021

- **module_ids:** 9.5; **kind:** mechanism; **status:** confirmed in the overview that was read.
- **Claim:** The x402 overview separates the challenge, payload verification, settlement and return of the resource; verify is not the same as settlement.
- **Evidence:** [P09-S014 / P09-S014-20260917](Sources.md#p09-s014), Typical x402 flow, steps 1–12.
- **Scope / limits:** mutable README on main, commit unknown; the status of the exact text on 15 September is open. The order of final delivery in the case is a separate teaching rule.

## P09-C022

- **module_ids:** 9.5; **kind:** historical regulatory action; **status:** confirmed.
- **Claim:** The Treasury/Fed/FDIC statement of 2023-03-12 announced protection for SVB depositors and access to their funds from 13 March.
- **Evidence:** [P09-S016 / P09-S016-20260917](Sources.md#p09-s016), main paragraph on SVB resolution.
- **Scope / limits:** a specific action by US authorities; not a guarantee that any USDC operation will be executed or that a bank will be rescued in the future.

## P09-C023

- **module_ids:** 9.5; **kind:** historical company statement; **status:** confirmed as attribution.
- **Claim:** Circle reported a 3.3 billion USD reserve deposit at SVB and expected access to be restored after the authorities' announcement.
- **Evidence:** [P09-S017 / P09-S017-20260917](Sources.md#p09-s017), opening paragraphs; body 2023-03-12, page 2023-03-13.
- **Scope / limits:** the issuer's self-report; not an independent reserve audit, not a price-feed. The difference between the event and page dates is preserved.

## P09-C024

- **module_ids:** 9.5; **kind:** historical operational report; **status:** confirmed as attribution.
- **Claim:** Circle reported that the backlog had been practically cleared by the end of 2023-03-15, and reported redemption/minting volumes since Monday.
- **Evidence:** [P09-S018 / P09-S018-20260917](Sources.md#p09-s018), first three paragraphs; page published 2023-03-16.
- **Scope / limits:** an operator's report; not proof of every final payout. Substantially all is kept as a limitation and is not replaced with the word "all".

## P09-C025

- **module_ids:** 9.5; **kind:** social statement; **status:** confirmed only as to the content of the post.
- **Claim:** MediumAdhesiveness5 published a megathread discussing the depeg, with links to Circle/FDIC updates.
- **Evidence:** [P09-S019 / P09-S019-20260917](Sources.md#p09-s019), original post and Updates.
- **Scope / limits:** the absolute date was not established; the author's market and causal claims are not accepted as facts. The replies are not used to assign blame.

## P09-C026

- **module_ids:** 9.1, 9.4, 9.5; **kind:** evidence boundary; **status:** open.
- **Claim under evaluation:** "The dynamic Stripe docs and the x402 README looked exactly the same on 2026-09-15 as when they were read on 2026-09-17".
- **Evidence:** [S005–S010, S014](Sources.md), snapshots `20260917`, `relation=context`.
- **Reasoning / limits:** archived copies/commits as of the cutoff date were not obtained; there is no direct evidence that nothing changed. The text keeps the dates separate, and new product availability is not presented as historically confirmed.

## Numerical models

Cases A–D are not empirical claims. The initial conditions, journal totals, final positions and exercise answers were checked. An error in the terms of a real contract cannot be fixed by correct arithmetic: fees, reserve release, the refund destination, FX risk and the moment the buyer's debt is discharged must be established separately for a real route. The author's machine check is described in [RESEARCH_NOTES.md](Research-notes.md); an independent review of the substance has not yet been done.
