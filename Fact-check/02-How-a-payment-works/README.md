---
title: "Independent fact-check results — Chapter 02"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Sources and fact-check](../README.md) · [Read the chapter](../../Textbook/02-How-a-payment-works/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Independent fact-check results — Chapter 02

2026-09-17 · Asia/Makassar (UTC+08) · auditor: `deep_audit_02_03_04` · private. Knowledge cutoff: 2026-09-15. New accesses and corrections date from 2026-09-17; the historical bytes of changing web pages as of 15 September were not restored.

## Result and scope

CHAPTER.md, CLAIMS.md and SOURCES.md were read in full; each of the 57 claim IDs and 43 source IDs has its own row in [CLAIM_AUDIT.md](Claim-check.md) and [SOURCE_AUDIT.md](Source-check.md). The new S043 was included after the correction. I attempted to retrieve all 43 original URLs myself. Substantive text was obtained for 41 sources; S024 and S038 remain unavailable for a decisive check. This does not mean that every multi-page PDF was read in full.

Large documents were checked directly in the decisive sections. The earlier REVIEW served as a risk map, not as evidence. A separate re-check of root's final edits against the saved baseline was performed. The author's confirmed/open/rejected statuses were not copied into the verdict automatically. The five contradicted verdicts concern incorrect statements that the author had already rejected, not five unresolved errors in the chapter.

| Verdict | Claims |
|---|---:|
| verified | 47 |
| verified_as_reported | 1 |
| partial | 0 |
| contradicted | 5 |
| unverifiable | 4 |
| non_factual | 0 |
| **Total** | **57** |

## Findings and corrections

Total new findings: **3 minor, 0 major, 0 critical**. All three were closed after root's correction and an independent re-read. The access limitations below are not hidden in this count.

| Finding | Priority | Original exact phrase / location | Independent basis | Correction and outcome |
|---|---|---|---|---|
| P02-A01 | minor | S015: `document month February 2025` | [FAPI 2.0 Final](https://openid.net/specs/fapi-security-profile-2_0-final.html), front matter: publication 22 February 2025; approval and publication are different events | The card now gives the exact publication day and, separately, the approval date; an independent cross-check was performed. This refines the precision of the metadata; it is not a version change. Closed. |
| P02-A02 | minor | S032: `Interests unknown`; C049 and §2.3 are linked | [Original Reddit post](https://www.reddit.com/r/fintechdev/comments/1tfi95l/why_a_valid_pain001_file_can_still_be_rejected_by/), the closing paragraphs promote the author's own validator/explainer | Root explicitly noted the self-promotion in the card, the register and the chapter. The context was re-read; C049 remains verified_as_reported. Commercial terms and bank incidents are not proven. Closed. |
| P02-A03 | minor | C018: `nostro/vostro are different perspectives on the account relationship`; §2.3 defines one account from two positions, but the S035 citation did not give an explicit definition | [Federal Reserve manual](https://www.federalreserve.gov/boarddocs/supmanual/cbem/7000.pdf), §7010.1, Vostro account, physical PDF p.30 / printed p.26 | Root added S043 and citations in C018/the chapter. The original was opened independently, and the entry that explicitly establishes the reciprocal definitions was read. C018 changed from partial to verified. The mixed dates of the compilation are retained; the full manual is not declared as read. Closed. |

## Decisive mechanism checks

- Finality, message, return and payout are kept separate. Read: PFMI Principle 8, Mastercard TPR §2.18.1, and the FedNow OC8 in force, with the cover Effective 1 April 2026: §§2.39, 7.1, 9.1.16, 9.6–9.8. A return is a new operation; a nonvalue message does not create a journal entry. The pre-launch S007 was not used as the current OC8.
- For ACH, the grounds for a sender-error reversal and the five banking days were read; for SDD, the Core/B2B differences, eight weeks and 13 months. BoE FPS round-the-clock processing is not equated with three netting cycles per business day. EPC SCT Inst was checked against the landing page; the full rulebook and all recall deadlines were not read.
- Stripe/Adyen hold, capture and capture failure were cross-checked against the documentation; partial capture, extension and refund were not reduced to a universal rule. A notification or refund_id is not declared to be the customer's receipt of money.
- SCA, 3DS and tokenization are not equated with authorization of the transaction or with the absence of any disputes. Google Pay Web PAN_ONLY/CRYPTOGRAM_3DS and the contents of ECv2 were checked separately; Apple DAN/security code and PCI FAQ 1326 are not generalized to all wallets or to PCI scope.
- In the EBA/ECB report, the method and period were checked: six half-years 2022–2024, EU/EEA reporters with a full series, issuer perspective for cards. The association of SCA with lower fraud is not called a causal experiment. CFPB BNPL: five companies, 2019–2021, pay-in-four; not all loans and not 2026 law.

## Facts outside the register and arithmetic

The whole chapter was also read for important statements outside CLAIMS: payment states and fulfillment, the correspondent FX model, the fee waterfall, the fraud confusion matrix, QRIS and BNPL. No new material unsupported generalizations were found. The conditions of the teaching exercises are labeled as synthetic; they are not a specific customer's rates and not evidence of a route.

Independently recalculated: 80 × 2.9% + 0.30 = 2.62 and net 77.38; netting positions (−20,+10,+10) and (−110,+60,+50), both summing to zero; FX net 1,085; fee 3.20; precision 21.0526%, recall 80%, FPR 3.0303%; fraud effect 500; dispute net −18.20 and 81.80 after the return of principal; QRIS fee 1,050 and net 148,950; BNPL merchant net 190 and funding gap 140. The arithmetic answers to the exercises, 4.45%, 20% and 80%, were also checked. These calculations do not confirm that the input assumptions are realistic.

## Limitations and remaining questions

- **C038 / S024 Worldpay:** the original PDF was obtained neither by direct request nor via web; the title/version and the ISO8583 fields were not confirmed in this pass. The unverifiable verdict means the absence of new evidence, not established falsity. The historical link and the earlier reading do not substitute for this gap.
- **C050 / S038:** EUR-Lex returned an empty 202 and a short shell. The exact consolidated SCA exemptions table in force is not confirmed. The BOE original/corrigendum in Chapter 03 do not close this full gap; the chapter keeps it open.
- **C051:** the permissibility of a specific combination of BNPL and crypto-in at a provider is not established. **C052:** the synthetic decline/capture trace does not confirm a real live payment; actual logs are absent. Full member rules, ISO schemas, live transactions and legal opinions were not checked.
- **S026 Apple:** my direct request to the original en-ca URL returned 200 with content; for root, the same URL returned 404. The intermittent access is recorded explicitly; root recovered an [official alternative address](https://support.apple.com/guide/security/paying-with-cards-using-apple-pay-secfbd5c0e54/web). My confirmation rests on the original that I read, not on someone else's access.
- Undated provider pages remain an observation as of the access date. Full external copies were not saved; there is no guarantee that their bytes can be reproduced later. Reddit proves the published description, not the frequency of errors, identity or causality.

## Final version check

The independent check of the sources and the final text was performed at research scope; this record describes the audit of 2026-09-17. Changes to the canonical files were made by root; this auditor writes only the reports for its own part.

`final_verdict=reviewed_with_limitations` · `open_critical=0` · `open_major=0` · `open_minor=0`.

The actual final CHAPTER/SOURCES/CLAIMS were re-checked after root's notice that the edits were complete. The SHA-256 values below refer to these files, not to the old REVIEW and not to the bytes of external sites. Any subsequent edit requires an updated check and updated hashes.

| Final canonical file | SHA-256 |
|---|---|
| [chapters/part-02/CHAPTER.md](../../Textbook/02-How-a-payment-works/README.md) | `37f8ea34db6ed78f94ea005c33ce191e1bf78c1993f31eed978a081542a94bdc` |
| [chapters/part-02/SOURCES.md](../../Textbook/02-How-a-payment-works/Sources.md) | `36f8c98403eedc68dfc3eb0255ccc221d9ea51733ca5c3ec58ddaf3254096d05` |
| [chapters/part-02/CLAIMS.md](../../Textbook/02-How-a-payment-works/Claims.md) | `5a846e042266976106c27e014004451f4de97e5481860ae3440154648a63ba6d` |

