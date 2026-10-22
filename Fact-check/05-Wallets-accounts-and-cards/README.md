---
title: "Detailed independent audit — Chapter 5"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Sources and fact-check](../README.md) · [Read the chapter](../../Textbook/05-Wallets-accounts-and-cards/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Detailed independent audit — Chapter 5

2026-09-17 · Asia/Makassar · private · auditor `deep_audit_00_01_05`.
The book's knowledge cutoff is 2026-09-15. The date of the present access attempts is 2026-09-17.

## Summary

All **45 claims and 33 source cards** were checked. CHAPTER, CLAIMS, SOURCES and the corresponding part of the structure were read in full. A separate row for each ID was made in [CLAIM_AUDIT.md](Claim-check.md) and [SOURCE_AUDIT.md](Source-check.md). A local cross-reference was corrected; in addition, the change in the observed version of the Circle policy is now clearly recorded. No open critical/major findings were identified.

| Verdict | Count |
|---|---:|
| verified | 14 |
| verified_as_reported | 20 |
| partial | 3 |
| unverifiable | 2 |
| non_factual | 5 |
| contradicted | 1 |
| Total | 45 |

`contradicted` for C018 refers to **the myth explicitly rejected by the author** that MPC by itself establishes noncustody. Rejecting the myth is correct and is not an error in the book. `verified_as_reported` means a statement by a provider, a study or a user that was read; it does not prove the product's availability for a specific user, the effectiveness of recovery, an actual payout or the cause of a failure.

## Method and scope of the check

[AUDIT_BRIEF.md](../Method.md) and the source schema were applied. Previous reviews and the root's general URL check were not used as evidence. All cards were independently checked for access, source type, version and the scope read. Where URLs repeat, the text the auditor obtained was used, with a separate row for each ID. Recovered alternative primary URLs are given next to the original ones.

The claim-relevant sections of NIST, ERC-4337, FATF, MiCA custody/application/transition, FDIC pass-through, UK safeguarding, the cardholder agreement, the EPC rulebook, Stripe issuing/refunds, Marqeta JIT and Circle redemption were read directly. This is a selection of the decisive provisions, not a claim that every page of each legal document was read. Provider documentation and the contractual model are not equated with the execution of a specific transaction.

## Findings and re-check

### P05-F001 — minor, closed: a cross-reference led to a different topic

**Original location:** CHAPTER §5.3, the paragraph "Redemption with the issuer", the link "for more, see 6.2". Section 6.2 is about accepting crypto; a more detailed discussion of redemption is in 6.3.

**Fix:** the root changed the label to "6.3". The final paragraph was independently re-read and checked against the topic of the neighboring chapter. Legal eligibility is also covered separately in §6.1; this link is not presented as a full classification of the holder.

### P05-O001 — version limitation clarified, historical error not proven

S033 previously recorded the Circle policy update date as 2026-07-13. On independent access on 17 September, the [Circle MiCA Redemption Policy](https://www.circle.com/legal/mica-redemption-policy) page showed **2026-09-15**. Without a saved July copy, it is impossible to determine the exact difference or to declare the earlier observation wrong.

The root added both actual observation dates and the limitation to CHAPTER §5.3, SOURCES S033 and CLAIMS C045. The current §§1.4, 2.1–2.3, 3 were independently re-read: for qualifying EEA Retail Holders, a separate path via a form, checks and an EEA IBAN is described. This is enough for the narrow current claim; worldwide eligibility, actual execution of a request and the historical identity of the two editions are not proven. `effective_from/to` were not invented from Last Updated.

### P05-O002 — recovering originals without substitution

For S005, direct reading was recovered via the [official FDIC PDF](https://www.fdic.gov/system/files/2024-05/pass-through.pdf), printed pp.77–80. The conditions on the principal's ownership, records of the agency relationship and identification of interests were read, as well as aggregation with direct deposits of the same owner in the same bank and category. The original HTML URL is kept in SOURCE_AUDIT; the PDF is explicitly linked to C012–C013. The neighboring S004 on third-party apps remained inaccessible and is not declared proven by this narrower document.

## Key checks of the chapter, including statements outside the register

- **Custody and MPC.** NIST IR8214A, the executive summary and §1, were read in the original PDF: threshold computation differs from simply reconstructing a shared secret. The 2020 document does not confirm certification of any specific wallet. Privy owner/admin controls and Fireblocks recovery describe the capabilities of the mechanisms; they do not replace legal classification, an independent right of the client or a practical recovery test.
- **MiCA.** Checked directly: art.75(7) segregation and 75(8) liability for an incident attributable to the CASP, with its cap and exemption condition, art.149 dates and art.143(3) transition. The existence of a rule does not prove the status of a specific provider. The specific URLs of all three articles are given in SOURCE_AUDIT.
- **Issued cards.** Authorization hold, capture/clearing, expiration, transaction/refund and bank settlement were compared. Stripe product states are not presented as universal rules of any network; the unsupported capture control and the specifics of the Basil version are not hidden. The Marqeta JIT messages that were read distinguish requests, responses and later notifications; force capture/stand-in are not turned into a promise that a negative result is impossible.
- **The client's legal claim.** Ledger balance, actual bank funds, FBO/pass-through conditions, safeguarding and deposit insurance are distinguished. A separate client account or a technical restriction is not declared to be a standalone guarantee of insurance coverage.
- **Historical research.** [McCorry, Shahandashti, Hao, ePrint 2016/024](https://eprint.iacr.org/2016/024.pdf) was read directly in these parts: abstract, §2.2, §§4–5.2: the BIP70 refund attack, the method, the selected merchant cases and the proposed binding of refund authorization to the original payment. This is historical research from 2016, without replication and without proof of a current vulnerability at Stripe/Coinbase. The method does not estimate the current market frequency of such incidents; venue/peer review were not exhaustively checked against the publisher's proceedings.
- **Reddit.** The [original post](https://www.reddit.com/r/Coinbase/comments/1e50vp4/do_not_use_coinbase_debit_card_they_arent/) by RandyMachoManSavage and the relevant comments, including radman430 and OhmazingJ, were read directly. The publication of the complaints and the disagreement about the route for raising them are confirmed. Fault, systemic frequency or the actual cause are not proven; the visible relative date "2y ago" does not independently establish the exact day of publication.

## Arithmetic and assumptions

- Wallet: 800 = 550 + 250, available after a hold of 120 = 430; with own funds of 90, bank balance 890. Clients' money and own money are kept separate in the model.
- FDIC: 240,000 + 40,000 = 280,000; given the same owner/bank/category, 30,000 remains above 250,000. The exercise 180,000 + 90,000 gives 20,000 above the limit. This is a hypothetical calculation, not an individual opinion on coverage.
- On-ramp: 995/1.005 − 0.5 = 989.549751; effective price about 1.01056. Off-ramp: 998 − 3 − 2 = 993 to the bank; a separate gas fee of 0.2 gives an economic result of 992.8.
- Refund: 100/0.98 = 102.040816…; rounding up to 6 decimal places gives 102.040817. For 75/0.90, ordinary rounding to 83.333333 differs from the required ceiling of 83.333334. The distinction is kept in the chapter.
- Issuing: 500 with a hold of 180 gives 320 available; clearing of 170 leaves 330 of obligation to the client and 170 to settle; after settlement, cash 330; after a refund of 20 — 350. Credit model: limit 1,000 − debt 200 − hold 150 = 650; a capture of 170 gives debt 370/available 630.
- Unit economics: 2,000 × 10 × 50 = 1,000,000 and 20,000 transactions; 14,000 × 70% = 9,800, costs 7,400, result 2,400. Fraud at 0.5% gives −600; 0.35% in the exercise gives 900. The refund reserve of 30,000 reflects a liquidity need, not automatically a final cost.

No material arithmetic errors were found. The rates and shares in these models are given assumptions, not a provider's current commercial offer.

## Remaining limitations

C001–C002 (EBA Q&A) and C021 (EBA Travel Rule release) are `partial` because the decisive text is available only through the official index; the primary source was not obtained directly. C011 (FDIC third-party apps) remains `unverifiable`. C044 is honestly left open: the user's contract, eligibility and actual recovery were not checked. Cryptographic properties and access documentation do not prove that recovery is independent in practice.

Providers' dynamic terms may have changed; the current agreement is not declared to be the agreement of the Reddit participant in 2024. There were no wallet/card tests, research replication, real payouts, API calls with a financial result or analysis of an individual contract. The historical access limitations of 15 September are kept separate from the new attempts of 17 September.

## Re-check and version binding

After the root's corrections, §5.3, S033 and C045 were re-read; the corrected link was found to match and both version observations were found to be reflected. Individual matrix rows and the recovered URLs were checked. The old REVIEW and its hashes are kept as a historical snapshot; the present result applies only to the following files.

final_verdict: `reviewed_with_limitations`  
open_critical: `0`  
open_major: `0`  
final_recheck: `2026-09-17 Asia/Makassar`

| File relative to chapters/part-05 | SHA-256 of the final checked version |
|---|---|
| CHAPTER.md | `90611402e14f39f81b04842b676ec45a95c057dc337725c413170c4ab45bc020` |
| SOURCES.md | `916e36690452c6c4fc457aaa0050699c07e6d767de5fa0fa75572b083bb0df35` |
| CLAIMS.md | `87fb4e408acdb7731273f31f12056c169dd79c51a22521029b0d4dbf135d49d9` |
