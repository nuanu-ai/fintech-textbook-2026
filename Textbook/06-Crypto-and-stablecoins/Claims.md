---
title: "Chapter 6 — register of material claims"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Crypto and stablecoins](README.md) · [Contents](../README.md) · [All sources and fact-checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Review dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Chapter 6 — register of material claims

**Status:** `independently_reviewed_draft` · **Version:** v0.1 · **Knowledge cutoff:** 2026-09-15 · private.

Fact-checking of the original edition was completed on 2026-09-17. The link between the original version and the public copy, the scope of the adaptation and the current navigation are described in the edition record.

## Reading rules

`confirmed` means consistency with the source as read **within the stated scope**, not a successful transaction or an independent approval of the chapter. A dated announcement confirms the report of an event, not all later stages. `rejected` refers to a stated myth. Synthetic numbers and operational schemes are marked in the [chapter](README.md); their arithmetic was checked separately, and they are not market data.

Common fields of every card: `as_of=2026-09-15`; `last_checked_at=2026-09-15 UTC`; `reviewer=part_06_research (author)`; `review_status=see_REVIEW.md` for the independent review. `effective_to=unknown` for a legal rule/contract, `not_applicable` for the rest. By default `relation=supports`; for rejected claims, `contradicts` the false thesis; for hypothesis/open, `context`. `review_trigger`: an update of the source/law, a change of network/version/contract, a new CBDC decision or preparation for a real launch; before that launch, the dynamic conditions must be rechecked. `confidence_basis`: direct reading of the named scope, not the number of references; `conflicts/resolution` are reflected in the limitations and in the [log](Research-notes.md).

## P06-C001

- **module_ids:** 6.1, 6.6; **claim_kind:** `legal`; **status:** `confirmed`.
- **claim:** EMT is a MiCA category defined by reference to a single official currency.
- **jurisdiction / conditions:** EU; **as_of:** 2026-09-15; **effective_from:** TitleIV:2024-06-30.
- **evidence:**
  - [P06-S001](https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/mica/article-3-definitions) / `P06-S001-20260915` — Art.3(1)(7); relation=supports.
  - [P06-S002](https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/mica/article-48-requirements-offer-public-or) / `P06-S002-20260915` — Art.48(1–2); relation=supports.
- **reasoning / confidence / limits:** The definition is kept separate from the issuer's authorization and from global regimes.

## P06-C002

- **module_ids:** 6.1; **claim_kind:** `legal`; **status:** `confirmed`.
- **claim:** MAS announced a specific SCS framework in August 2023; this is not proof that any token is currently admitted.
- **jurisdiction / conditions:** Singapore; **as_of:** 2026-09-15; **effective_from:** unknown.
- **evidence:**
  - [P06-S006](https://www.sgpc.gov.sg/api/file/getfile/Media%20Release_MAS%20Finalises%20Stablecoin%20Regulatory%20Framework.pdf?path=/sgpcmedia/media_releases/mas/press_release/P-20230815-2/attachment/Media+Release_MAS+Finalises+Stablecoin+Regulatory+Framework.pdf) / `P06-S006-20260915` — PDFpp.1–2, scope/framework/label; relation=supports.
- **reasoning / confidence / limits:** An announcement; implementation and the issuer register were not checked.

## P06-C003

- **module_ids:** 6.1, 6.3; **claim_kind:** `legal`; **status:** `confirmed`.
- **claim:** Outside the EEA, direct redemption of USDC depends on the holder's access to Circle Mint.
- **jurisdiction / conditions:** non-EEA; **as_of:** 2026-09-15; **effective_from:** version of 2025-12-12.
- **evidence:**
  - [P06-S007](https://www.circle.com/legal/usdc-terms) / `P06-S007-20260915` — §§1–4, TypeA/TypeB, redemption eligibility; relation=supports.
- **reasoning / confidence / limits:** Holding the token does not prove an active account. Do not carry this over to the EEA.

## P06-C004

- **module_ids:** 6.1, 6.3; **claim_kind:** `legal`; **status:** `confirmed`.
- **claim:** The Circle France policy provides for separate retail and nonretail USDC redemption procedures.
- **jurisdiction / conditions:** EEA; **as_of:** 2026-09-15; **effective_from:** unknown; displayed revision 2026-09-15 on rereading on 2026-09-17; the author's earlier record of 2026-07-13 has no saved copy.
- **evidence:**
  - [P06-S008](https://www.circle.com/legal/mica-redemption-policy) / `P06-S008-20260917` — §§1.4,2.1–2.3,3; relation=supports.
- **reasoning / confidence / limits:** The procedure requires checks and bank details; no conclusion is drawn about any specific applicant.

## P06-C005

- **module_ids:** 6.1; **claim_kind:** `legal`; **status:** `confirmed`.
- **claim:** Restrictions and blocking can prevent the use of USDC even when the on-chain record exists.
- **jurisdiction / conditions:** USDC terms scope; **as_of:** 2026-09-15; **effective_from:** version of 2025-12-12.
- **evidence:**
  - [P06-S007](https://www.circle.com/legal/usdc-terms) / `P06-S007-20260915` — §§13–17, blocked addresses/risks; relation=supports.
- **reasoning / confidence / limits:** Distinguish availability and transferability from the market price and the state of the bank reserves.

## P06-C006

- **module_ids:** 6.1; **claim_kind:** `mechanism`; **status:** `confirmed`.
- **claim:** Third-party bridged USDC has an additional dependency on unbridging, unlike native USDC.
- **jurisdiction / conditions:** Circle third-party bridged terms; **as_of:** 2026-09-15; **effective_from:** version of 2025-12-12.
- **evidence:**
  - [P06-S009](https://www.circle.com/legal/bridged-usdc-terms) / `P06-S009-20260915` — §§1–2; relation=supports.
- **reasoning / confidence / limits:** The fact that a service may perform the unbridge does not turn the wrapper into an obligation of Circle.

## P06-C007

- **module_ids:** 6.2; **claim_kind:** `mechanism`; **status:** `confirmed`.
- **claim:** ERC-681 defines a payment request; its existence does not prove a payment or the merchant's authenticity.
- **jurisdiction / conditions:** ERC681 implementations; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S013](https://eips.ethereum.org/EIPS/eip-681) / `P06-S013-20260915` — Syntax, Semantics, Security Considerations; metadata Final; relation=supports.
- **reasoning / confidence / limits:** Final status does not confirm compatibility with every wallet.

## P06-C008

- **module_ids:** 6.2; **claim_kind:** `mechanism`; **status:** `confirmed`.
- **claim:** Bitcoin confirmation depth is a measure of risk, not a universal guarantee of timing.
- **jurisdiction / conditions:** Bitcoin; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S014](https://developer.bitcoin.org/devguide/payment_processing.html) / `P06-S014-20260915` — Verifying Payment / confirmations, Pricing Orders; relation=supports.
- **reasoning / confidence / limits:** Historical numerical probabilities from the guide are not used as current.

## P06-C009

- **module_ids:** 6.2; **claim_kind:** `mechanism`; **status:** `confirmed`.
- **claim:** Finality in Ethereum PoS is determined by voting/checkpoints and consensus assumptions.
- **jurisdiction / conditions:** Ethereum PoS; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S015](https://ethereum.org/developers/docs/consensus-mechanisms/pos/gasper/) / `P06-S015-20260915` — What is finality?, justification/finalization; relation=supports.
- **reasoning / confidence / limits:** It is not equated with any number of confirmations on another network; the exact consensus release was not recorded.

## P06-C010

- **module_ids:** 6.2; **claim_kind:** `product`; **status:** `confirmed`.
- **claim:** Base distinguishes stages of confirmation; the canonical L1 withdrawal has a separate time frame.
- **jurisdiction / conditions:** Base; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S016](https://docs.base.org/specifications/transactions/transaction-finality) / `P06-S016-20260915` — Stages of finality; withdrawals; relation=supports.
- **reasoning / confidence / limits:** The estimates 200ms/2s/2m/20m and 7 days are taken from live docs; they are not an SLA and not a promise for all bridges.

## P06-C011

- **module_ids:** 6.2; **claim_kind:** `mechanism`; **status:** `confirmed`.
- **claim:** The sender's address is not always suitable for a refund, especially when the payment was sent from a custodial service.
- **jurisdiction / conditions:** Bitcoin merchant processing; broader operational inference marked; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S014](https://developer.bitcoin.org/devguide/payment_processing.html) / `P06-S014-20260915` — Refunds; relation=supports.
- **reasoning / confidence / limits:** For other networks, what carries over is the principle of verifying the destination, not the specific Bitcoin flow.

## P06-C012

- **module_ids:** 6.3; **claim_kind:** `product`; **status:** `confirmed`.
- **claim:** In the Tether document, direct redemption has a minimum of 100,000 USD and fee=max(1000USD;0.1%).
- **jurisdiction / conditions:** Tether direct verified customers; **as_of:** 2026-09-15; **effective_from:** document2026-02-20.
- **evidence:**
  - [P06-S011](https://tether.to/public/Relevant_Information_Document_-_Tether_International,_S.A._de_C.V..pdf) / `P06-S011-20260915` — PDFpp.13–15, redemption/minimum/fees; relation=supports.
- **reasoning / confidence / limits:** Not a secondary exchange tariff. The synthetic arithmetic in the text is not a real quote.

## P06-C013

- **module_ids:** 6.3; **claim_kind:** `empirical`; **status:** `confirmed`.
- **claim:** The July examination relates to the reserve assertion as of the two stated dates.
- **jurisdiction / conditions:** USDC reserve report July2026; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S010](https://6778953.fs1.hubspotusercontent-na1.net/hubfs/6778953/USDCAttestationReports/2026/2026%20USDC_Examination%20Report%20July%2026%20(1).pdf) / `P06-S010-20260915` — PDFpp.1–5, opinion and management assertion; relation=supports.
- **reasoning / confidence / limits:** A dated subject of examination, not a guarantee of daily liquidity or of the whole business.

## P06-C014

- **module_ids:** 6.3; **claim_kind:** `empirical`; **status:** `confirmed`.
- **claim:** BDO provides assurance within the stated scope of financial figures, with explicit exclusions.
- **jurisdiction / conditions:** Tether Q2 report; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S012](https://assets.ctfassets.net/vyse88cgwfbl/2kYf7r64h3tzwiu6F0CbUB/2997abd2f11ecea74a21528048b50707/Opinion___Report_-_Tether_International_Financial_Figure_30-06-2026.pdf) / `P06-S012-20260915` — PDFpp.2–4 opinion/limitations;pp.6–9 reserves/notes; relation=supports.
- **reasoning / confidence / limits:** Full financial statements, notes and going concern cannot be silently included in the assurance. No claim is made that other audits do not exist.

## P06-C015

- **module_ids:** 6.3; **claim_kind:** `empirical`; **status:** `confirmed`.
- **claim:** In the studied model, the effect of disclosure on a stablecoin run depends on prior beliefs and the signal.
- **jurisdiction / conditions:** BIS WP1164 model and selected episodes; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S023](https://www.bis.org/publications/working-paper-1164-public-information-and-stablecoin-runs.pdf) / `P06-S023-20260915` — §§2–5; PDF29–31 identification; selected results; relation=supports.
- **reasoning / confidence / limits:** Global-games model + counterfactual regression; a limited set of episodes, assumptions and control validity. Not a universal causal law.

## P06-C016

- **module_ids:** 6.3; **claim_kind:** `mechanism`; **status:** `confirmed`.
- **claim:** CCTP uses burn, message attestation and mint instead of the usual lock-and-wrapper scheme.
- **jurisdiction / conditions:** CCTP V2 supported networks; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S017](https://developers.circle.com/cctp/references/technical-guide) / `P06-S017-20260915` — How CCTP works / message passing / receiveMessage; relation=supports.
- **reasoning / confidence / limits:** Circle/service/chain dependencies remain; a cryptographic attestation differs from a reserve attestation.

## P06-C017

- **module_ids:** 6.4; **claim_kind:** `product`; **status:** `confirmed`.
- **claim:** Stripe describes the local currency of the settlement balance, product limitations and uneven geographic availability.
- **jurisdiction / conditions:** eligible Stripe stablecoin accounts; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S018](https://docs.stripe.com/payments/stablecoin-payments) / `P06-S018-20260915` — overview, supported countries/currencies, limitations; relation=supports.
- **reasoning / confidence / limits:** Private preview is not GA; live docs do not confirm access for a specific company. Do not treat a capability as legal authorization.

## P06-C018

- **module_ids:** 6.4, 6.7; **claim_kind:** `product`; **status:** `confirmed`.
- **claim:** Bridge distinguishes receipt of funds, submission, processing and return states.
- **jurisdiction / conditions:** Bridge orchestration; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S019](https://apidocs.bridge.xyz/platform/orchestration/transfers/transfer-states) / `P06-S019-20260915` — complete transfer state table and hash note; relation=supports.
- **reasoning / confidence / limits:** The internal model must take into account provider semantics and evidence from the recipient.

## P06-C019

- **module_ids:** 6.4, 6.7; **claim_kind:** `product`; **status:** `confirmed`.
- **claim:** Bank payout timing depends on rail/cutoff/support; some of the described routes are 24/7.
- **jurisdiction / conditions:** Bridge listed rails; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S020](https://apidocs.bridge.xyz/platform/orchestration/more/cutoffs) / `P06-S020-20260915` — USD Wire/ACH/FedNow rows;SEPA Instant/SCT rows; relation=supports.
- **reasoning / confidence / limits:** The 16:45 ET wire cutoff, FedNow beta/invitation and the Instant→SCT fallback are conditional; not an SLA for all accounts.

## P06-C020

- **module_ids:** 6.4; **claim_kind:** `product`; **status:** `confirmed`.
- **claim:** Stripe describes a stablecoin refund to the original wallet and the absence of card chargebacks.
- **jurisdiction / conditions:** Stripe stablecoin refund flow; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S018](https://docs.stripe.com/payments/stablecoin-payments) / `P06-S018-20260915` — Refunds;Disputes;Payment method properties; relation=supports.
- **reasoning / confidence / limits:** A vendor flow is not a universal refund policy and does not cancel consumer-law requirements.

## P06-C021

- **module_ids:** 6.5; **claim_kind:** `legal`; **status:** `confirmed`.
- **claim:** FATF guidance is not a worldwide license or a substitute for national implementation.
- **jurisdiction / conditions:** FATF international guidance; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S021](https://www.fatf-gafi.org/content/dam/fatf-gafi/guidance/Updated-Guidance-VA-VASP.pdf.coredownload.inline.pdf) / `P06-S021-20260915` — ¶25–26 and29–34; relation=supports.
- **reasoning / confidence / limits:** A durable principle of scope; current obligations in any specific country are not determined here.

## P06-C022

- **module_ids:** 6.5; **claim_kind:** `legal`; **status:** `confirmed`.
- **claim:** MiCA defines a CASP through services to clients and provides for authorizations for specific services.
- **jurisdiction / conditions:** EU; **as_of:** 2026-09-15; **effective_from:** general application 2024-12-30; individual transitions unknown.
- **evidence:**
  - [P06-S001](https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/mica/article-3-definitions) / `P06-S001-20260915` — Art.3(1)(15–26); relation=supports.
  - [P06-S004](https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/mica/article-59-authorisation) / `P06-S004-20260915` — Art.59(1),(6–8); relation=supports.
- **reasoning / confidence / limits:** Adjacent exemptions/financial entities/transitions and the actual functions require case-by-case analysis.

## P06-C023

- **module_ids:** 6.5; **claim_kind:** `legal`; **status:** `confirmed`.
- **claim:** The Travel Rule involves information about the parties; the public network is not a mandatory channel for publishing it.
- **jurisdiction / conditions:** FATF guidance; national implementation varies; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S021](https://www.fatf-gafi.org/content/dam/fatf-gafi/guidance/Updated-Guidance-VA-VASP.pdf.coredownload.inline.pdf) / `P06-S021-20260915` — ¶177–193, especially communication/security; additionally [official PDF](https://www.fatf-gafi.org/content/dam/fatf-gafi/guidance/Updated-Guidance-VA-VASP.pdf), ¶203–204 (printedp65/PDFp66), collection from customer versus transmission to private individual. Independently reread 2026-09-17, `P06-S021-20260917-deep`; relation=supports.
- **reasoning / confidence / limits:** Collection of information by the servicing VASP and transmission between VASPs are different things; current national thresholds are not derived.

## P06-C024

- **module_ids:** 6.5; **claim_kind:** `legal`; **status:** `confirmed`.
- **claim:** OFAC treats addresses as part of identification; the published list does not exhaust related addresses.
- **jurisdiction / conditions:** US sanctions context; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S022](https://ofac.treasury.gov/media/913571/download?inline=) / `P06-S022-20260915` — printedpp.15–17;PDF18–20; relation=supports.
- **reasoning / confidence / limits:** An analytics flag does not establish guilt; historical country lists/retention rules are not used.

## P06-C025

- **module_ids:** 6.6; **claim_kind:** `legal`; **status:** `confirmed`.
- **claim:** MiCA Article 49 establishes the holder's claim against the issuer and redemption at par value.
- **jurisdiction / conditions:** EU EMT; **as_of:** 2026-09-15; **effective_from:** 2024-06-30.
- **evidence:**
  - [P06-S003](https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/mica/article-49-issuance-and-redeemability-e) / `P06-S003-20260915` — Art.49(2–6); relation=supports.
  - [P06-S005](https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/mica/article-149-entry-force-and-application) / `P06-S005-20260915` — Art.149(3); relation=supports.
- **reasoning / confidence / limits:** The redemption rule does not assert a fixed secondary price; proper execution of the procedure is a separate matter.

## P06-C026

- **module_ids:** 6.6; **claim_kind:** `mechanism`; **status:** `confirmed` only as a logical limit on inference.
- **claim:** Gross on-chain transfer volume does not by itself establish the volume of retail purchases.
- **jurisdiction / conditions:** the author's methodological inference, not empirical statistics; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence / reasoning:** an explicit synthetic counterexample in CHAPTER §6.6: a purchase of 100 and two subsequent movements of 100 each give a gross volume of 300 with a single purchase of 100. This shows that one aggregate is insufficient without classifying the purpose of the transfers. A possible coincidence of aggregates in a particular dataset is not ruled out.
- **source correction, 2026-09-17:** the original P06-S024 locator about own-account movements/arbitrage and retail measurement was not confirmed by rereading BIS. Relation=supports was removed; the article remains context in SOURCES, not evidence for this counterexample.
- **limits:** no claims are made about the shares of real transfers, market turnover or the results of an empirical study. The independent audit treats the entry as `non_factual` in the sense of an explicitly teaching construct.

## P06-C027

- **module_ids:** 6.8; **claim_kind:** `definition`; **status:** `confirmed`.
- **claim:** Retail and wholesale CBDC are distinguished by access/purpose and by the central bank's obligation.
- **jurisdiction / conditions:** BIS CBDC definitions; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S025](https://www.bis.org/publications/paper-159-advancing-tandem-results-2024-bis-survey-central-bank-digital-currencies-and-crypto.pdf) / `P06-S025-20260915` — definitions and AnnexA questionnaire; relation=supports.
- **reasoning / confidence / limits:** Not a universal technical architecture and not access for any wallet.

## P06-C028

- **module_ids:** 6.8; **claim_kind:** `empirical`; **status:** `confirmed`.
- **claim:** BIS 2024 survey: 85 of 93 responding central banks were exploring CBDC.
- **jurisdiction / conditions:** 93 central-bank respondents, observation2024; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S025](https://www.bis.org/publications/paper-159-advancing-tandem-results-2024-bis-survey-central-bank-digital-currencies-and-crypto.pdf) / `P06-S025-20260915` — Introduction;AnnexesA–B; relation=supports.
- **reasoning / confidence / limits:** Self-report/selection; the 2025 publication is not a 2026 status map, and exploration is not launch.

## P06-C029

- **module_ids:** 6.8; **claim_kind:** `product`; **status:** `confirmed`.
- **claim:** The ECB indicates a conditional horizon of possible issuance in 2029 and a separate decision after legislation.
- **jurisdiction / conditions:** EU digital euro project; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S026](https://www.ecb.europa.eu/euro/digital_euro/progress/html/index.en.html) / `P06-S026-20260915` — next phase / legislation2026 / issuance2029 conditions; relation=supports.
- **reasoning / confidence / limits:** The plan is conditional; the date of the dynamic page is unknown; there is no claim that an issuance decision has been made.

## P06-C030

- **module_ids:** 6.8; **claim_kind:** `product`; **status:** `confirmed`.
- **claim:** The BoE report that was read describes the design phase without a decision to introduce the digital pound.
- **jurisdiction / conditions:** UK; report2026-03-04 updated03-12; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S027](https://www.bankofengland.co.uk/the-digital-pound/progress-update-digital-pound-design-phase) / `P06-S027-20260915` — Introduction;What we will do next;Conclusion; relation=supports.
- **reasoning / confidence / limits:** The dated status of the document is confirmed. A later 2026 decision was not established, and it is not declared permanently absent.

## P06-C031

- **module_ids:** 6.8; **claim_kind:** `product`; **status:** `confirmed`.
- **claim:** BI reported the completion of the Garuda immediate-state wholesale cash ledger PoC.
- **jurisdiction / conditions:** Indonesia; announcement2024-12-13; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S028](https://www.bi.go.id/en/iru/highlight-news/Pages/Garuda-Project-Proof-of-Concept,-New-Chapter-of-Digital-Rupiah-Exploration.aspx) / `P06-S028-20260915` — release body, PoC scope/completion; relation=supports.
- **reasoning / confidence / limits:** The full technical report is unavailable; a later retail/live rollout and current commercial availability were not established.

## P06-C032

- **module_ids:** 6.8; **claim_kind:** `product`; **status:** `confirmed`.
- **claim:** MAS reported a live wholesale CBDC trial for overnight lending among three banks.
- **jurisdiction / conditions:** Singapore; speech2025-11-13; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S029](https://www.bis.org/speeches/20251120-creating-future-finance-journey-innovation-and-collaboration) / `P06-S029-20260915` — paragraph In the CBDC space; subsequent MAS Bills future sentence; relation=supports.
- **reasoning / confidence / limits:** An official speech; the republication is not an independent check; not a retail launch and not a completed test of the future Bills.

## P06-C033

- **module_ids:** 6.8; **claim_kind:** `product`; **status:** `confirmed`.
- **claim:** The announcement of the first government Digital Dirham transaction explicitly places it in the pilot phase.
- **jurisdiction / conditions:** UAE; government event2025-11-11; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S031](https://mof.gov.ae/en/news/ministry-of-finance-and-dubai-finance-conduct-first-government-transaction-using-digital-dirham/) / `P06-S031-20260915` — article body, pilot-phase sentence; relation=supports.
  - [P06-S030](https://centralbank.ae/media/lczb23l4/cbdc-short-report_july.pdf) / `P06-S030-20260915` — Executive Summary/progress context; relation=supports.
- **reasoning / confidence / limits:** Real value in a limited pilot; a broad retail rollout as of the cutoff is not proven by this event.

## P06-C034

- **module_ids:** 6.8; **claim_kind:** `legal`; **status:** `confirmed`.
- **claim:** EO14178 §5 prohibits agencies from CBDC creation/issuance/promotion, except as required by law.
- **jurisdiction / conditions:** US federal agencies, EO2025-01-23; **as_of:** 2026-09-15; **effective_from:** 2025-01-23 order; effective_to unknown.
- **evidence:**
  - [P06-S032](https://www.whitehouse.gov/presidential-actions/2025/01/strengthening-american-leadership-in-digital-financial-technology/) / `P06-S032-20260915` — §5(a–b), CBDC definition§2; relation=supports.
- **reasoning / confidence / limits:** Not all private digital payments; subsequent legislative/judicial changes were not fully researched.

## P06-C035

- **module_ids:** 6.8; **claim_kind:** `product`; **status:** `confirmed`.
- **claim:** The CBUAE primer discusses the intermediated architecture and offline capabilities of the Digital Dirham.
- **jurisdiction / conditions:** UAE design primerJuly2025; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S030](https://centralbank.ae/media/lczb23l4/cbdc-short-report_july.pdf) / `P06-S030-20260915` — design section, PDFpp.8–10; relation=supports.
- **reasoning / confidence / limits:** A design statement is not a security check and not universal offline availability. The general discussion of double-spend is the author's engineering interpretation.

## P06-C036

- **module_ids:** 6.8; **claim_kind:** `product`; **status:** `confirmed`.
- **claim:** The BoE distinguishes programmable payments from programmable money in its design commitments.
- **jurisdiction / conditions:** UK digital pound design; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S027](https://www.bankofengland.co.uk/the-digital-pound/progress-update-digital-pound-design-phase) / `P06-S027-20260915` — Annex: privacy/programmability commitments and definitions; relation=supports.
- **reasoning / confidence / limits:** This is the stated design/intentions for a future system, not an operating retail product.

## P06-C037

- **module_ids:** 6.8; **claim_kind:** `hypothesis`; **status:** `working_hypothesis`.
- **claim:** CBDC could give PSPs and agents new interface functions, provided they have access.
- **jurisdiction / conditions:** potential PSP/agent use; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S025](https://www.bis.org/publications/paper-159-advancing-tandem-results-2024-bis-survey-central-bank-digital-currencies-and-crypto.pdf) / `P06-S025-20260915` — definitions:context; relation=context.
  - [P06-S027](https://www.bankofengland.co.uk/the-digital-pound/progress-update-digital-pound-design-phase) / `P06-S027-20260915` — experiments/Lab and user-set conditional payments:context; relation=context.
- **reasoning / confidence / limits:** The author's hypothesis, not a confirmed API or Lab roadmap; published interfaces, authorization and operational evidence are needed.

## P06-C038

- **module_ids:** 6.7; **claim_kind:** `definition`; **status:** `confirmed`.
- **claim:** Correspondent settlement uses accounts that banks hold with each other and separate messages.
- **jurisdiction / conditions:** correspondent banking; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S033](https://www.bis.org/publications/correspondent-banking-final-report.pdf) / `P06-S033-20260915` — §2.1 printedpp.9–10;Annex2 printedp.43; relation=supports.
- **reasoning / confidence / limits:** Nostro/vostro are the sides of the relationship; an ordinary API balance of a non-bank is not automatically such an account. Current rails are not inferred from 2016.

## P06-C039

- **module_ids:** 6.6; **claim_kind:** `mechanism`; **status:** `rejected`.
- **claim:** An on-chain receipt is identical to a card chargeback.
- **jurisdiction / conditions:** claim as universal identity; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S018](https://docs.stripe.com/payments/stablecoin-payments) / `P06-S018-20260915` — Disputes/Refunds; relation=contradicts.
  - [P06-S014](https://developer.bitcoin.org/devguide/payment_processing.html) / `P06-S014-20260915` — Verifying Payment;Refunds; relation=contradicts.
- **reasoning / confidence / limits:** Refuted by the difference between a dispute procedure and an on-chain result; a refund is a separate operation.

## P06-C040

- **module_ids:** 6.6; **claim_kind:** `legal`; **status:** `rejected`.
- **claim:** A single license permits all services in all countries.
- **jurisdiction / conditions:** claim as global authorization; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S004](https://www.esma.europa.eu/publications-and-data/interactive-single-rulebook/mica/article-59-authorisation) / `P06-S004-20260915` — Art.59(6–8); relation=contradicts.
  - [P06-S021](https://www.fatf-gafi.org/content/dam/fatf-gafi/guidance/Updated-Guidance-VA-VASP.pdf.coredownload.inline.pdf) / `P06-S021-20260915` — ¶25–26; relation=contradicts.
- **reasoning / confidence / limits:** The list of services and the jurisdiction are limited; Union passporting is not worldwide authorization.

## P06-C041

- **module_ids:** 6.6, 6.8; **claim_kind:** `definition`; **status:** `rejected`.
- **claim:** CBDC is the same obligation as USDT, just with a state brand.
- **jurisdiction / conditions:** CBDC/private stablecoin identity; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S025](https://www.bis.org/publications/paper-159-advancing-tandem-results-2024-bis-survey-central-bank-digital-currencies-and-crypto.pdf) / `P06-S025-20260915` — CBDC definitions; relation=contradicts.
  - [P06-S011](https://tether.to/public/Relevant_Information_Document_-_Tether_International,_S.A._de_C.V..pdf) / `P06-S011-20260915` — issuer and primary/secondary market description; relation=contradicts.
- **reasoning / confidence / limits:** The debtor and the legal structure differ; the technology may partly overlap.

## P06-C042

- **module_ids:** 6.4; **claim_kind:** `product`; **status:** `open`.
- **claim:** A specific crypto→fiat route is permissible and available to a specific company.
- **jurisdiction / conditions:** specific legal entity / account; **as_of:** 2026-09-15; **effective_from:** not_applicable.
- **evidence:**
  - [P06-S018](https://docs.stripe.com/payments/stablecoin-payments) / `P06-S018-20260915` — eligibility and country limitations:context; relation=context.
  - [P06-S020](https://apidocs.bridge.xyz/platform/orchestration/more/cutoffs) / `P06-S020-20260915` — rail support/invitation conditions:context; relation=context.
- **reasoning / confidence / limits:** The register, contract, customer type, recipient, bank access and a legal review were not checked. Not used as a fact in the chapter.

## P06-C043

- **module_ids:** 6.5; **claim_kind:** `empirical`; **status:** `confirmed`.
- **claim:** The FATF 2026 summary reports persisting gaps in the practical implementation of licensing/registration and supervision.
- **jurisdiction / conditions:** FATF Global Network, assessment by the report's author; **as_of:** 2026-09-15; **effective_from/to:** not_applicable.
- **evidence:** [P06-S034](https://www.fatf-gafi.org/en/publications/Fatfrecommendations/targeted-updated-virtualassets-vasps-2026.html) / `P06-S034-20260915` — body paragraph beginning However, significant gaps remain; relation=supports.
- **reasoning / confidence / limits:** Direct reading of the web summary; the full PDF and the underlying data were not checked; no numerical or individual licensing conclusions.
