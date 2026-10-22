---
title: "Chapter 3 — claims register"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Cards: Visa and Mastercard](README.md) · [Contents](../README.md) · [All sources and fact-checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Check dates and source limitations have been preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Chapter 3 — claims register

**v0.1 · 2026-09-15 · private · independently_reviewed_draft · author: part_03_research.**

Fact-checking of the original edition was completed on 2026-09-17. The relationship between the original version and the public copy, the scope of adaptation and the current navigation are described in the edition record.

`confirmed` here means confirmation by the author **within the explicitly stated scope**, not an independent reviewer verdict. All cards have `reviewer=see_REVIEW.md`, `review_status=see_REVIEW.md`. Content that was not read does not receive confirmed status.

## Common fields of every row

- `as_of=2026-09-15`; `last_checked_at=2026-09-15, Asia/Makassar`; `effective_to=unknown` if the row concerns a rule; `not_applicable` for an explanation/example. `effective_from` is given in the row for the dated provision used; otherwise `provision_specific/unknown`, not the cover date.
- A reference of the form `S001: §…` in evidence means `P03-S001 + snapshot_id P03-S001@2026-09-15 + locator + relation=supports`. `context`/`contradicts` are indicated separately. The title and URL are given in [Sources](Sources.md); the nearest link in [CHAPTER.md](README.md) leads directly to the original.
- `reasoning/confidence_basis`: the direct content of the named primary section within scope; for a scholarly/social/educational source, the reading limit is explicitly narrowed. The "Conclusion and limit" field contains the author's own interpretation, if there is one. Synthetic numbers are not presented as empirical observation.
- `conflicts=none_identified_in_reviewed_scope` by default. This is not a statement that there are no contradictions at all. Specific conflicts are described in the rows and below.
- `review_trigger`: a new applicable edition/bulletin or a change of region, product, participant, activity/route; for a product page — a new release/contract before implementation; for a law — an amendment/judicial interpretation/local application; for a story — new primary evidence or an established outcome.
- `jurisdiction/conditions` and `effective_from` in the "Scope and date" column take priority over the general cutoff. Same-type Visa/Verifi and Mastercard/Ethoca pages are not counted as independent confirmations; see the groups in SOURCES.

## 3.1 Institution and rights

| claim_id | module_ids / kind / status | Claim | Scope and date | Evidence / locator | Conclusion and limit |
|---|---|---|---|---|---|
| P03-C001 | 3.1; definition; confirmed | Card scheme and processing entity are different roles | ECB report 2025, EU | S029: §§1–3 | Combining them within one group does not erase the difference between rules and processing |
| P03-C002 | 3.1; definition; confirmed | The four-party model separates issuer and acquirer; the three-party model combines these functions | Teaching model, not a count of all companies; effective n/a | S028: pp. 55–57 | A dated textbook is suitable for the model, not for a current list of participants |
| P03-C003 | 3.1; mechanism; confirmed | Network participation creates mutual value for the sides of the card market | Theoretical explanation | S028: pp. 55–57 context; S039: Focus/Contribution context | The example of 1 million cardholders is the author's own, not proof that the fee is optimal; for BIS only the summary was read |
| P03-C004 | 3.1; legal; confirmed | Mastercard requires the appropriate approval and a License for an Activity | Mastercard global rule with exceptions, edition 2026-06-02 | S002: §1.1 p. 34 | Participation and API access are different things; not a permission for any particular organization |
| P03-C005 | 3.1; legal; confirmed | The Area of Use of a Mastercard license limits Activity, with the exceptions provided for | §1.7/global plus regional variations | S002: §§1.6–1.7.1 pp. 42–43 | To enter another region, check the applicable rights; do not carry over an old approval |
| P03-C006 | 3.1; mechanism; confirmed | Public copies of the rules have limitations of completeness/currentness | Visa public edition and Mastercard public index | S041: Rules impacting processors and merchants; S042: introductory caveats | A public URL does not certify an exhaustive contractual set |
| P03-C007 | 3.1; mechanism; confirmed | A scheme license does not replace the right to carry out a regulated activity | Mastercard eligibility subject to law | S002: §1.1.1 p. 34 | The practical three-layer check is an editorial conclusion, not an individual legal opinion |

## 3.2 Visa

| claim_id | module_ids / kind / status | Claim | Scope and date | Evidence / locator | Conclusion and limit |
|---|---|---|---|---|---|
| P03-C008 | 3.2; product; confirmed | The virtual form of a card and its product category are different attributes | Visa virtual accounts/product schedule | S001: §4.1.7; S016: product tables | Virtual does not equal a separate source of funds; not all combination eligibility was checked |
| P03-C009 | 3.2; mechanism; confirmed | Authorization, clearing and settlement are presented in the rules as separate functions | Visa §1.7, edition 2026-04-18 | S001: §§1.7.3–1.7.6 | Teaching hours/amounts are not a Visa SLA |
| P03-C010 | 3.2; empirical; open | Dual-message dominates in every Visa segment | Share for a specific market/period was not obtained | S001/S016 context, not sufficient | The outline used the word "dominance", but no measurement was found; the chapter does not present it as an established share |
| P03-C011 | 3.2,3.5; product; confirmed | VTS uses token-to-PAN processing with an issuer authorization decision | Fact sheet 2022 illustrative flow | S009: How it works, p. 2 | A general role, not the current full message contract |
| P03-C012 | 3.2,3.5; mechanism; confirmed | PAR makes it possible to link records but is not a standalone payment credential | VTS product/PAR Inquiry | S008: PAR Inquiry; S010: §11.3 context; S048: FAQ 1374, answer paragraph 3, no transaction initiation using PAR alone | The merchant not having the PAN does not mean anonymity or consent |
| P03-C013 | 3.2; definition; confirmed | AFT and OCT describe different sides of a funding/push scenario | Visa Direct for Card | S007: Implementation Overview/Getting Started | The two-leg example 102=100+2 is synthetic; AFT is not mandatory for every payout |
| P03-C014 | 3.2; legal; confirmed | A Visa Direct originator must be a licensed acquirer or work with a sponsor | Visa Direct for Card stated participation | S007: Getting Started | Public documentation does not confirm approval of a specific program |
| P03-C015 | 3.2; product; confirmed | Availability of funds with Visa Direct depends on the receiving institution and other conditions | Account/region/type dependent | S007: funds availability qualifications | Immediate availability cannot be promised to every recipient |
| P03-C016 | 3.2; mechanism; confirmed | DCC requires conversion information and the cardholder's choice | Visa consumer DCC guidance | S014: What to expect | Not proof that DCC is always cheaper/more expensive; social opinion is separate |
| P03-C017 | 3.2,3.3; mechanism; confirmed | Interchange and merchant discount are different price levels | Visa US merchant explainer | S043: Interchange reimbursement fees | Table interchange is not the full MDR; specific fee pass-through is contractual |
| P03-C018 | 3.2; product; confirmed | The selected Visa USA exempt debit e-commerce row equals 1.65% + 0.15 USD | US applicable CPS/e-Commerce Basic Debit, effective 2026-04-18 | S016: p. 4 | 100 USD → 1.80 USD is only a rate illustration, without the other fees |
| P03-C019 | 3.2; product; confirmed | In the selected Visa USA regulated column, 0.05% + 0.21 USD with a possible 0.01 USD adjustment | US qualified regulated debit, effective 2026-04-18 | S016: p. 4 and footnote | 0.26/0.27 USD per 100; not a universal rate for any consumer debit |
| P03-C020 | 3.2; definition; confirmed | Visa dispute categories 10/11/12/13 separate fraud/auth/processing/consumer disputes | Visa public rules 2026-04-18 | S001: §§11.2–11.3 | The classification does not dictate one common deadline |
| P03-C021 | 3.2; legal; confirmed | §11.2.3 contains 30 days for the pre-arbitration response and 10 days for arbitration after the response | Categories 12/13: acquirer response from the processing date of the attempt; Tanzania domestic — 10 days; issuer arbitration from the processing date of the response; edition 2026-04-18 | S001: §11.2.3, pp. 669–673 | These are inter-participant deadlines, not a universal merchant PSP window; applicable exceptions are binding |
| P03-C022 | 3.2; mechanism; confirmed | The historical Visa CE FAQ describes evidence based on two prior undisputed transactions | FAQ October 2022, initiative April 2023 | S019: issuer FAQ 1–7 | Not a promise to win any dispute by IP; current qualification was not reconstructed from the old FAQ |
| P03-C023 | 3.2; product; confirmed | Order Insight describes access for non-Visa issuers through direct integration | Undated Verifi page as read | S020: concluding paragraphs | Visa ownership does not equal exclusive support for Visa; specific banks were not checked |
| P03-C024 | 3.2; mechanism; confirmed | The VAMP ratio uses TC40+TC15 over CNP VisaNet settled TC05 with the stated exclusions | Public 2025 fact sheet | S013: definition/footnotes, p. 1 | Not a raw universal chargeback ratio; data extract timing has an effect |
| P03-C025 | 3.2; legal; confirmed | The Excessive Merchant threshold of 150 bps is stated from 2026-04-01 for AP/Canada/EU/US, subject to other conditions | For AP/Canada/EU/US at least 1,500 counted events; portfolio/country qualifications apply | S013: threshold table and footnotes | 150 bps alone does not prove program entry; full guide beyond sheet not read |

## 3.3 Mastercard

| claim_id | module_ids / kind / status | Claim | Scope and date | Evidence / locator | Conclusion and limit |
|---|---|---|---|---|---|
| P03-C026 | 3.3; product; confirmed | Mastercard/Maestro/ATM and the route require taking different applicability rules into account | Global and Mainland China/regional exceptions, 2026-06-02 | S002: Applicability, pp. 29–31 | A logo is not a sufficient router; no current global Maestro issuance claim |
| P03-C027 | 3.3; mechanism; confirmed | Mastercard supports dual- and single-message processing | Defined systems; guide 2025/TPR 2026 | S021: §§2.1–2.2; S003: §2.2.1 | Adding a second capture every time is not allowed; the duplicate 12+12 example is hypothetical |
| P03-C028 | 3.3; mechanism; confirmed | The Switch Rules describe net/bilateral settlement and separate the message cutoff from funds-transfer finality | Rulebook 2025-12-16 and local transfer law | S004: §§3.1–3.1.2, p. 40 | Finality does not prohibit a future separate compensating message |
| P03-C029 | 3.3; product; confirmed | The MDES/tokenization description includes the issuer's decision and token/cryptographic data | Mastercard public primer 2024 | S012: How does tokenization work/online COF | Public primer not complete merchant MDES API |
| P03-C030 | 3.3,3.5; product; open | VTS and MDES have interchangeable merchant APIs and lifecycle | Exact implementation/country/provider | S008/S009/S012 context; no complete wire specs | Not established, and not claimed in the chapter; a uniform SDK is not proof |
| P03-C031 | 3.3; definition; confirmed | A Mastercard Payment Transaction is not a refund of a previous purchase | Defined Applicability, 2026-06-02 | S002: p. 30 | MoneySend/payment semantics cannot be implemented as an arbitrary refund |
| P03-C032 | 3.3; product; confirmed | The Move portfolio includes payouts to businesses/merchants | Market/product-dependent, page read in 2026 | S040: Use Cases/FAQ/footnotes | The Move portfolio is broader than one Mastercard Send card route; exact coverage not claimed |
| P03-C033 | 3.3; mechanism; confirmed | The Mastercard converter allows for issuer fee/rate divergence and a fallback to the processing rate | Card/bank/transaction dependent | S015: Please Note | The calculator does not explain every actual statement amount |
| P03-C034 | 3.3; mechanism; confirmed | Mastercard settlement currency conversion differs in role from cardholder FX | Switch Rules 2025-12-16 | S004: §3.1.1 | These are different currency relationships, not a double fee by definition |
| P03-C035 | 3.3; mechanism; confirmed | Interchange qualification depends on a combination of processing characteristics | Mastercard US explanatory page | S017: determination/qualification paragraphs | A single digital MCC or product label does not guarantee a rate |
| P03-C036 | 3.3; product; confirmed | In the Canadian table that was read, Digital Commerce Core 1.67%, Standard Core 1.96% | Canada domestic consumer credit May 2026 edition; exact effective unknown | S018: p. 2 | The difference of 0.29 CAD per 100 is an illustration of the edition, not a quote of a current contract |
| P03-C037 | 3.3; mechanism; confirmed | The Mastercard dispute overview provides for second presentment, pre-arbitration and arbitration | Public intro guide 2025 | S021: §§3–5, pp. 7–10 | Not the exhaustive deadlines of the full current Chargeback Guide |
| P03-C038 | 3.3; product; confirmed | Ethoca Consumer Clarity describes transaction details/API integration | Product page, participating network | S022: What makes us different | Effectiveness/specific issuer coverage not measured |
| P03-C039 | 3.3; product; confirmed | On the Smart Subscriptions page, Ethoca is called brand-agnostic | Undated public product statement | S023: Powering the global subscription economy | Does not mean that all cards/banks are already connected |
| P03-C040 | 3.3; legal; confirmed | GMAP is suspended until further notice in SPME 2026-08-04 | Scope current public edition, resumption unknown | S005: §8.2, p. 87 | A later applicable bulletin may change the status; a third-party launch post does not outweigh it |
| P03-C041 | 3.3; mechanism; confirmed | ECP bps divides the current month's chargebacks by the previous month's transactions | SPME §8.3 definition | S005: §8.3, pp. 87–88 | A same-month denominator is a different metric |
| P03-C042 | 3.3; legal; open | Full current ECM/HECM numerical thresholds are established by this chapter | Required Data Integrity Monitoring Program unavailable | S005: §8.3 context/reference | Not established; the old 100/150/300 thresholds were not reproduced |

## 3.4 Other schemes and local routing

| claim_id | module_ids / kind / status | Claim | Scope and date | Evidence / locator | Conclusion and limit |
|---|---|---|---|---|---|
| P03-C043 | 3.4; product; confirmed | Amex OptBlue provides for a third-party provider that sets the merchant rate | USA, eligible merchants | S030: FAQ on provider/pricing | In this channel, the contract is not necessarily directly with Amex |
| P03-C044 | 3.4; product; confirmed | Amex publishes COF and digital-wallet tokenization offerings | Depends on country/registration | S031: Tokenization Services | Full implementation guide not read |
| P03-C045 | 3.4; product; confirmed | Discover publishes Stored Token Services with domain controls | DGN public offer | S032: main description | Not proof of full push/dispute functions |
| P03-C046 | 3.4; product; confirmed | JCB/Adyen announced a COF-tokenization rollout on 2025-05-13 | Announcement for domestic/global merchants | S033: release | The announcement is confirmed; the outcome and independent uplift are unknown |
| P03-C047 | 3.4; product; confirmed | J/Secure describes 3DS authentication | Participating JCB issuers | S034: FAQ | Authentication is not financial authorization/settlement |
| P03-C048 | 3.4; product; confirmed | MoneyExpress describes remittance to UnionPay debit in China with RMB credit | Destination China, eligible accounts | S035: main paragraphs | The full worldwide payout scope and a guaranteed time are not established |
| P03-C049 | 3.4; legal; confirmed | IFR Art. 8 regulates co-badging and the choice of application | EU within the act's scope; Art. 8 applies from 2016-06-09 | S038: Art. 8(6), 18 | Merchant priority may exist; the cardholder retains the choice provided for among the accepted options |
| P03-C050 | 3.4; product; confirmed | The BI overview links the GPN logo on ATM/debit cards with PBI 19/8/PBI/2017 | Indonesia, regulator overview | S036: ATM/debit/GPN | Not proof that GPN is mandatory for every foreign/e-commerce payment |
| P03-C051 | 3.4; empirical; open | There is a comparable assessment of the geographic strength of all six schemes for 2026 | Comparable market share / coverage dataset not obtained | S029 historical context; S030–S035 product context | The table shows the geography of the document/service; shares and rankings were not invented |

## 3.5 Tokens, COF, subscriptions

| claim_id | module_ids / kind / status | Claim | Scope and date | Evidence / locator | Conclusion and limit |
|---|---|---|---|---|---|
| P03-C052 | 3.5; definition; confirmed | CIT presupposes the cardholder's active interaction; MIT is merchant initiation on a previously established basis | Visa 2017 definitions; current MC identifiers | S024: pp. 3–6; S003: pp. 330–333 | A historical definition does not replace current implementation requirements |
| P03-C053 | 3.5; definition; confirmed | A stored card can be used in a CIT | Visa COF framework | S024: pp. 3–6 | COF is not a synonym for MIT; the teaching matrix shows different attributes |
| P03-C054 | 3.5; mechanism; confirmed | A network token can be used in guest checkout | EMVCo illustrative guide v2.2.1 | S010: §11.3, pp. 150–155 | This does not give the merchant permission for any future purchases |
| P03-C055 | 3.5; mechanism; confirmed | Token requestor, TSP, issuer and token user are separate roles | EMVCo guide v2.2.1, selected sections | S010: §§3–7, pp. 15–16/19–20/24/27–28/30; §11.3 | Roles can be combined; the steps do not exhaust all protocol variants |
| P03-C056 | 3.5; mechanism; confirmed | Domain controls restrict token use; the use of a cryptogram depends on the use case | EMVCo guide, guest/table 11.12 | S010: §7; §11.3.4, p. 153 | It is not claimed that there is a cryptogram in absolutely every MIT transaction |
| P03-C057 | 3.5; hypothesis; working_hypothesis | Migrating a provider handle/token requires checking requestor, domain and lifecycle contracts | No specific PSP and route chosen | S010/S024 context | An architectural conclusion and questions for the contract; there is no promise of portability |
| P03-C058 | 3.5; product; confirmed | VAU passes on updated card details and status advices | Participating Visa VAU parties | S026: overview / update types | Not all cards are necessarily covered; consent is not renewed just because new data exist |
| P03-C059 | 3.5; product; confirmed | The MC ABU privacy notice describes the processing of old/new PAN/expiry | Notice effective 2025-10-01 | S027: information types / purposes | A data update does not equal consent management; canceling a subscription is a separate event |
| P03-C060 | 3.5; legal; confirmed | RTS Art. 14 describes SCA at the creation/amendment/first transaction of a series with the same amount and the same payee | Scope of the EU act; general application from 2019-09-14 | S037: Art. 14, 38; S044: Spanish correction | Not a universal exemption for all subscriptions; the full consolidation was not read |
| P03-C061 | 3.5; legal; open | Any MIT is automatically outside SCA | Such a universal claim is not confirmed | EBA Q&A unavailable; S037 context only | Payee-initiated scope and exemption are different questions; the blanket claim was not accepted |
| P03-C062 | 3.5; legal; rejected | Mastercard requires a receipt after every billing from any merchant without exception | Historical FAQ, updated in November 2022 | S025: questions 1–9 contradicts | The change of 2022-10-11 makes this a best practice with an exception for a certain group; not a universal current obligation |
| P03-C063 | 3.5; product; open | The current EMVCo TF 2.4 was fully read by the author | Only metadata of the new edition | S011: metadata only | The chapter uses the old guide that was read to illustrate the roles |
| P03-C064 | 3.5; mechanism; confirmed | Who Pays Whom proposes separate privacy protocols; this is not proof of their VTS/MDES deployment | Author version / HAL 2025-01-29, partial reading | S045: abstract, intro, related work, Appendix B | Only the research question and context; proofs/experiments not checked |

## 3.6 MCC, restrictions and cases

| claim_id | module_ids / kind / status | Claim | Scope and date | Evidence / locator | Conclusion and limit |
|---|---|---|---|---|---|
| P03-C065 | 3.6; legal; confirmed | Mastercard places MCC assignment on the acquirer | Rules 2026-06-02, §5.8.1 | S002: §5.8.1, p. 116 | The merchant application provides information; the final decision does not follow from the field selected |
| P03-C066 | 3.6; definition; confirmed | MCC 5815–5818 distinguish types of digital goods; 5818 covers at least two of the categories 5815/5816/5817, with no merchant size threshold | MC QRG 2026-06-02 | S006: pp. 162–164 | A digital form does not eliminate the difference between goods and a financial asset |
| P03-C067 | 3.6; legal; confirmed | SPME includes certain adult/gambling/games/crypto types in specialty registration | Categories §9.1, edition 2026-08-04 | S005: §9.1, p. 111 | This is not a ban on all games or a recognition that adult content is legal in every country |
| P03-C068 | 3.6; legal; confirmed | MC crypto §9.4.9 provides for registration before processing | Acquirer / sponsored merchant within a certain crypto scope | S005: §9.4.9, pp. 126–127 | Registration does not remove local licensing and partner approval |
| P03-C069 | 3.6; legal; confirmed | MC crypto labeling in §9.4.9 uses MCC 6051/TCC U and TTI P70/P76 by type | P76 for fully fiat-backed stablecoin/CBDC; edition 2026-08-04 | S005: §9.4.9, pp. 126–127 | Including CBDC in reporting does not mean defining all CBDCs as crypto |
| P03-C070 | 3.6; legal; confirmed | Visa Table 7-9 distinguishes crypto/NFT transactions by nature/use case | Visa §7.4.14.1, edition 2026-04-18 | S001: Table 7-9, pp. 563–565 | MC coding cannot be copied into Visa; NFT-as-ticket requires qualification of the specific case |
| P03-C071 | 3.6; legal; open | The full current Visa High-Integrity Risk list is confirmed by this chapter | The separate VIRP guide is unavailable | S001: §10.4.5, pp. 635–636 context | Completeness not established; the closed list was not invented |
| P03-C072 | 3.6; hypothesis; working_hypothesis | A direct sale of a stablecoin and payment for goods through a separate off-ramp may involve different contractual roles | Synthetic models; no specific provider approval | S001/S005 context; editorial conclusion | The difference requires research; no ready-made legal route is claimed |
| P03-C073 | 3.2,3.3; experience; confirmed | u/gbcox published a story about unwanted DCC in Brazil | Original Reddit post; date unknown, label "2y ago" | S047: initial post | The fact of the story is confirmed; the 12%, the circumstances and the outcome were not independently checked |
| P03-C074 | 3.2,3.3; experience; open | DCC at the described restaurant has been legally recognized as fraud | The result of the bank complaint is not established | S047: initial post, not proof of the outcome | The primary receipt, records and a decision are needed; the author's assessment is not accepted |
| P03-C075 | 3.3; legal; confirmed | The Mastercard DCC guide requires a choice without imposing DCC by default | Merchant Version 2025, experience guidance | S046: pp. 31–32 | Does not establish a violation from Reddit; regional thresholds not used |

## Author's calculations and logical conclusions

The inputs of these examples are set in the chapter. The check consists of conservation of money and the meaning of the state, not of a search for market statistics.

| Example / module_ids | Check | Limit |
|---|---|---|
| Visa payout, 3.2 | 102 USD funding = 100 USD payout + 2 USD fee | Does not confirm that the funding is permissible or that the recipient is eligible |
| Fee layers, 3.2 | 100−1.50−0.20−0.40=97.90; reserve 1 → 96.90 today | The reserve is separate from the expense; its release is determined by the contract |
| Real Visa row on a teaching 100 USD, 3.2 | 100×1.65%+0.15=1.80; 100×0.05%+0.21=0.26 (+0.01) | Only the selected US qualified categories |
| VAMP, 3.2 | 1600/100000×10000=160 bps | Status requires counts, exclusions, portfolio and geography |
| Duplicate single-message, 3.3 | 12+12=24 USD of claims | A hypothetical failure model, not a promise that every API behaves the same way |
| MC payout, 3.3 | 80+0.50=80.50 USD outflow | The obligation of 80 is closed upon confirmed delivery |
| FX refund, 3.3 | 100 EUR×1.10=110 USD; ×1.08=108 USD; difference 2 USD | Compensation is determined by the issuer's terms and the applicable rule |
| Canada Core table, 3.3 | 100 CAD×(1.96%−1.67%)=0.29 CAD | Illustration of the edition that was read, not a universal rate |
| ECP, 3.3 | 100/10000×10000=100 bps | A current-month denominator of 5000 would give 200 bps of a different metric |
| Co-badging, 3.4 | (0.22−0.08)×10000=1400 EUR | The arithmetic does not create routing rights or token eligibility |
| Subscription, 3.5 | 3×20=60 EUR; cancellation before the third month → 40 EUR | The contractual assumptions are set explicitly |
| Exercise 2 | 2.90+0.40+0.30=3.60; 200−3.60−4=192.40; total=200 | All rates are synthetic |
| Exercise 4 | 150×1.08×1.015=164.43; 168−164.43=3.57 USD | The real future rate and fees are not predicted |
| Exercise 5 | 160/20000×10000=80 bps; 160/25000×10000=64 bps | ECM status does not follow from a single fraction |

## Conflicts and editorial decisions

1. **GMAP:** old and secondary launch descriptions versus SPME 2026-08-04 §8.2. Decision: assert the suspension in the edition that was read; the resumption date is open. The number of reprints does not change the evidence.
2. **Recurring receipt:** a widely repeated unconditional obligation versus the amended FAQ 2022. Decision: describe a best practice and an exception for a certain group; do not declare the FAQ a complete current mandate.
3. **RTS metadata:** BOE Analysis entry 2018-11-14 versus publication on 2018-03-13 and operative article 38, the next day. Decision: use 2018-03-14 for entry into force and 2019-09-14 for general application; show the metadata error explicitly.
4. **EMV latest:** the new TF 2.4 metadata does not make the old guide a current full specification. Decision: explain the roles based on the v2.2.1 that was read; leave new technical requirements open.
5. **Social case:** the claim DCC=scam versus the official conditions of voluntary DCC. Decision: keep the story as told by its author; do not establish a universal accusation or an outcome without evidence.
6. **Different brands:** the absence of full API/operating guides has not been turned into an absence of functions. The gap is labeled "not verified"; current geographic shares were not invented.
