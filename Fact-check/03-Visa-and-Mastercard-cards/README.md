---
title: "Independent fact-check results — Chapter 3"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Sources and fact-check](../README.md) · [Read the chapter](../../Textbook/03-Visa-and-Mastercard-cards/README.md)

> Public edition of 2026-09-18. Check dates and source limitations have been preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Independent fact-check results — Chapter 3

2026-09-17 · Asia/Makassar (UTC+08) · auditor: `deep_audit_02_03_04` · private. Knowledge cutoff: 2026-09-15; repeat access and corrections — 2026-09-17. The later reading is not called a historical snapshot.

## Result and coverage

CHAPTER.md, CLAIMS.md and SOURCES.md were read in full. [CLAIM_AUDIT.md](Claim-check.md) contains 75 individual verdicts; [SOURCE_AUDIT.md](Source-check.md) contains 48 individual entries, including the new S048. The auditor independently attempted to open all original URLs. For S022, S023 and S040, the original regional/global pages were not obtained in full; official alternatives and the index are kept separate from the original. The remaining originals yielded substantive material within the stated scope. A full reading of all 923 pages of the Visa rules or of all restricted Standards is not claimed.

The previous REVIEW was used only as a pointer to risks. All of root's final changes were compared with the baseline and separately rechecked against primary sources. Contradicted for C062 refers to the universal rule that the author explicitly rejected, not to the chapter's current advice.

| Verdict | Claims |
|---|---:|
| verified | 55 |
| verified_as_reported | 7 |
| partial | 2 |
| contradicted | 1 |
| unverifiable | 8 |
| non_factual | 2 |
| **Total** | **75** |

## Findings and recheck

New findings: **6 minor, 0 major, 0 critical**. All six are closed. Historical versions were not silently replaced with current ones.

| Finding | Priority | Original exact phrase / location | Independent basis | Correction and outcome |
|---|---|---|---|---|
| P03-A01 | minor | S011: `newer Use Cases v2.3` without draft status | [EMVCo landing](https://www.emvco.com/emv-technologies/payment-tokenisation/), documents: Use Cases v2.3_DRAFT 2 April 2026, comments end 1 May; Technical Framework v2.4 final 9 July 2026 | Root explicitly separated draft and final. The metadata was reread; no full new framework is claimed. Closed. |
| P03-A02 | minor | S019 title: `Evolution of Compelling Evidence: External FAQs` | [Visa PDF](https://usa.visa.com/content/dam/VCOM/regional/na/us/support-legal/documents/evolution-of-compelling-evidence-external-faqs.pdf), October 2022 cover — Client FAQs | Title corrected; the filename with external-faqs is explained separately. The cover and the relevant questions were read independently. Closed. |
| P03-A03 | minor | S024 title: `Visa Stored Credential Transaction Framework` | [Visa PDF](https://usa.visa.com/content/dam/VCOM/global/support-legal/documents/stored-credential-transaction-framework-vbs-10-may-17.pdf), cover | The exact title was replaced with Improving Authorization Management for Transactions with Stored Credentials; the historical 2017 status was kept. The cover and definitions were read. Closed. |
| P03-A04 | minor | S034 `J/Secure2.0`; C047 and the chapter table `J/Secure 2.0` | [JCB FAQ](https://www.global.jcb/en/products/security/jsecure/faq/), current title J/Secure™ FAQ for Merchants, Q1–Q4 | The text confirms the EMV3DS mechanism but not the exact 2.0 release. Root corrected the title/audience and removed the unconfirmed version from the card, the claim and the chapter. The current C047 is verified; the mechanism is unchanged. Closed. |
| P03-A05 | minor | S039: `José Aurazo et al.` | [BIS WP1163 page](https://www.bis.org/publications/working-paper-1163-interchange-fees-access-pricing-and-sub-acquirers-payment-markets), Authors | José Aurazo is now given as the sole author. The author block was read independently; the model was also checked against the PDF in Chapter 4. Closed. |
| P03-A06 | minor | C012: `PAR ... is not a standalone payment credential`; the original S008/S010 gave linkage/context without a sufficiently direct basis for the whole phrase | [PCI SSC FAQ1374](https://www.pcisecuritystandards.org/faqs/1374/), full answer, especially ¶3, January 2016 | Root added S048 and references to it in C012/the chapter; the point about consent is set apart as a separate teaching conclusion. The FAQ was read independently in full: PAR alone does not initiate authorization/capture/clearing/settlement. C012 partial → verified. Closed. |

## Decisive checks of rules, versions and boundaries

- Visa Rules 18 April 2026: §§1.7.3–1.7.6 separate authorization/clearing/settlement; §4.1.7 links a virtual account to a product/program BIN. §11.2.3, pp.671–673, table 11-2 and fn7 were read directly: acquirer pre-arbitration response 30 calendar days, Tanzania domestic 10; issuer arbitration 10 from processing response. These are not universal merchant deadlines.
- VAMP: the entire public one-page table was read, with the formula TC40+TC15 / TC05, exclusions and the conditions on extraction, merchant count, region and portfolio. The 150 bps threshold from 1 April 2026 is not presented as the only condition for any merchant.
- Mastercard Rules 2 June 2026, TPR 9 June 2026, SPME 4 August 2026 and Switch Rules 16 December 2025 were checked for applicability, license/Area of Use, single/dual, C/M taxonomy, GMAP/ECP and settlement. The current ECM/HECM thresholds were not reconstructed from old figures in the absence of the Data Integrity manual.
- MCC 5815–5818 were checked against the Quick Reference Booklet pp.162–164: 5818 requires at least two of the listed categories; no size condition was added. Visa table 7-9 crypto/NFT and Mastercard §9.4.9 were checked separately; MCC, TCC and registration do not replace a local license.
- The Visa USA exempt/regulated debit rows and the fraud-prevention footnote were checked in the 18 April 2026 table. Mastercard Canada is specifically the May 2026 edition, Core Digital Commerce 1.67% / Standard 1.96%, with the publisher's caveat about contractual terms. These rows were not turned into a PSP price or a universal rate.
- EMVCo Use Cases v2.2.1: roles, characteristics and guest checkout, including table 11.12 with Used/Not Used cryptogram, were read in the historical version. CIT/MIT/COF, token credential and account updater are not conflated with consent. BOE RTS Article 14/38 and the Spanish corrigendum were read; IFR Article 8(6) allows a holder override among accepted options, with the applicability date in Article 18.

## Research and facts outside the register

The entire chapter was read, including the unregistered examples of funding/payout, FX refund, fee waterfall, guest checkout scenarios, token migration, crypto/off-ramp and partner selection questions. The synthetic schemes do not prove permission for access, the success of a rollout or agent consent. No new material facts outside the register requiring correction were found.

Recalculated: 100 + 2 = 102; purchase FX 100 EUR × 1.10 = 110 and refund × 1.08 = 108; Visa 100 USD fee 1.80, regulated 0.26 or 0.27 under the stated condition; Canada difference 0.29 per 100 CAD. All amounts correspond to the stated input assumptions, not to a forecast.

For Who Pays Whom, the abstract/introduction, the §3.3 threat model and the comparison table were read. The author version with the HAL deposit of 29 January 2025 contains trust models and a restriction on joint corruption of issuer/proxy; these assumptions were not turned into a proven property of VTS/MDES. Full proofs were not reproduced, and deployment was not established. C064 is therefore verified_as_reported.

Reddit DCC: the original post by u/gbcox and a later message by the same author about the bank crediting the exchange-rate difference were read. This clarifies the history of the statement itself; it does not confirm a legal finding of fraud. The chapter ties the unresolved outcome specifically to the initial post, so its narrow wording does not need correction. C073 is a fact of publication, C074 is unverifiable; the exact day was not established from the relative UI date.

## Limitations

- **C038/C039 partial:** Ethoca global pages returned 403/timeout. [US Consumer Clarity](https://www.mastercard.com/us/en/business/cybersecurity-fraud-prevention/dispute-management/ethoca-consumer-clarity.html) and the [official API PDF 4.0.0](https://static.developer.mastercard.com/content/consumer-clarity/uploads/ethoca-merchant-digital-api-integration-guide.pdf), §1, confirm the limited scope. The Smart Subscriptions original was not read in full; the index is not presented as the full text. The current exact API version and the coverage of each issuer were not established.
- **C032:** the [official US Move page](https://www.mastercard.com/us/en/business/payments/mastercard-move/payments-to-businesses.html) recovered the public offer with market/product caveats; the original Europe page is completely unavailable. Verified_as_reported confirms the description, not that the route works.
- **C010, C030, C042, C051, C061, C063, C071, C074 unverifiable:** there are no relevant statistics, full contracts/Standard, full new specification or primary bank/court decision. The chapter's open questions remain open.
- Public rules have exceptions and may be subordinate to the full member Standards. This is not a full legal audit, a check of every local modification, an account test, a payout, or a reproduction of cryptographic proofs. Changing pages were not saved as full archives.

## Final version check

The independent check of the sources and the final text was performed within research scope; this entry describes the audit of 2026-09-17. Changes to the canonical files were made by root; this auditor writes only the reports for its own part.

`final_verdict=reviewed_with_limitations` · `open_critical=0` · `open_major=0` · `open_minor=0`.

The actual final CHAPTER/SOURCES/CLAIMS were rechecked after root's notice that the edits were complete. The SHA-256 below refers to these files, not to the old REVIEW and not to the bytes of external sites. Any later edit requires updating the check and the hashes.

| Final canonical file | SHA-256 |
|---|---|
| [chapters/part-03/CHAPTER.md](../../Textbook/03-Visa-and-Mastercard-cards/README.md) | `868ad139cde16574406f15626c8de9ed5a70f49bdce94c1059ff2c7940f14e20` |
| [chapters/part-03/SOURCES.md](../../Textbook/03-Visa-and-Mastercard-cards/Sources.md) | `6e9af557851aac41ed517199f3de73bce24f263cfc083eb310cf59a71faf32f5` |
| [chapters/part-03/CLAIMS.md](../../Textbook/03-Visa-and-Mastercard-cards/Claims.md) | `5de7b8a86b091b7cae732f8471664e300d601d2e5b082233cd635631a9c486a7` |

