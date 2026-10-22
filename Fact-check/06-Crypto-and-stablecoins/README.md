---
title: "Independent factual audit — Chapter 6"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Sources and fact-check](../README.md) · [Read the chapter](../../Textbook/06-Crypto-and-stablecoins/README.md)

> Public edition of 2026-09-18. Review dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Independent factual audit — Chapter 6

2026-09-17 · Asia/Makassar (UTC+8) · auditor deep_audit_06_07_08_09 · private

## Result and closed findings

The full CHAPTER/SOURCES/CLAIMS were read; 43 claims and 34 source cards were assessed individually. One major and four minor findings were closed after the editor's corrections; the original grounds are preserved below. There is no open confirmed critical/major finding.

- **F06-01, major, closed — C026/S024, CHAPTER§6.6.** The original thesis "Gross transfer volume does not equal the volume of retail purchases" attributed to BIS a specific passage on own-wallet/arbitrage/retail measurement. An independent reading of the full [HTML BIS AER2026](https://www.bis.org/publications/iii-anchoring-trust-money-innovation-beyond-stablecoins) and a search for all occurrences of gross/arbitrage/retail did not find this locator. Graph7.B refers to gross cross-border inflows 2022–23. The editor removed relation=supports and replaced the evidence with an explicitly synthetic 100/300 example; the wording is now "does not by itself establish". The final §6.6, C026 and S024 were reread: **non_factual**; the conclusion is not presented as empirical statistics.
- **F06-02, minor, closed — CHAPTER§6.1.** The original "approximately 103.092784… before rounding" had already rounded 100/0.97. Independent calculation: 103.092783505…; rounded up to 6 decimal places, 103.092784. Both values are now explicitly separated. The signal came from root; the arithmetic was checked independently.
- **F06-03, minor, closed — S010.** On PDF p.1, Deloitte & Touche LLP and the signature of 2026-08-27 were visually confirmed. The editor specified the signatory and separated signature_date from the unknown public posting date. Rereading the card confirms the correction.
- **F06-04, minor, closed — S020.** The current heading Processing windows & cutoff times differed from the short Cutoffs. The card keeps the new heading and the history of the original observation.
- **F06-05, minor, closed — S021/C023 locator.** After the official PDF was recovered, ¶203–204 were read separately: obtaining data from the customer and no transmission to a private individual. The editor added the locator printed p65/PDF p66 and an alternative official URL. The final SOURCES/CLAIMS were reread after this last correction.

## Material claims outside the register, and calculations

The synthetic depeg, native/bridged, refund and treasury examples were rechecked. In §6.7, the total of 25,782.80 USD and the profit of 182.80 USD are consistent with the initial 25,600 USD; the EUR balance by itself is not the whole profit. In §6.1 and §6.4, rounding is separated from the exact ratio. The algorithmic redemption example is explicitly hypothetical and is not presented as a reconstruction of Terra. A funds_received/compliance_pending record proves neither a loss of money nor a violation by the customer.

The Circle MiCA policy was independently read in its 2026-09-15 version: §§8.4–8.5 allow stress deferrals beyond the usual time limits of §4. The chapter/C003–C004 do not promise an unconditional time limit; there is no new major finding on this point. Native/bridged rights, point-in-time reserve assurance and liquidity are kept separate.

## Limitations

The original body of the BI Garuda release could not be obtained: C031=partial, based only on the official index. C042=unverifiable remains an honestly open question about a specific payment route. C039–C041 are literal false theses that the author already rejects; the verdict contradicted does not mean new errors in the chapter. Studies and announcements were not replicated. Dynamic pages as of 17 September are not archives of 15 September; new dates do not replace the historical record. Details for each source are in SOURCE_AUDIT.md.

## Coverage and verdict counts

Claims: 43; source cards: 34. Every ID has one matrix row.

- verified: 26
- verified_as_reported: 10
- non_factual: 2
- partial: 1
- contradicted: 3
- unverifiable: 1

## Final recheck and hashes

All the corrections listed were reread after the editor's provisional freeze; P06-S021/C023 were reread after the last locator was added. The hashes below were calculated from the actual content of the final files. The previous review was used only as a pointer to risk, not as evidence.

final_verdict: reviewed_with_limitations

open_critical: 0

open_major: 0

| File | SHA-256 |
|---|---|
| [CHAPTER.md](../../Textbook/06-Crypto-and-stablecoins/README.md) | 6a61993e4ca74acc7c47355a1b67af9fbddc80e1fe4d5bcdfff22be6106f9722 |
| [Sources](../../Textbook/06-Crypto-and-stablecoins/Sources.md) | 6ba20179d0cf59b08760fea3832c67b1e5e52e7ebd92c678ffed485def69164e |
| [Claims](../../Textbook/06-Crypto-and-stablecoins/Claims.md) | 00fb3cc5cf943daabbe778d9bab82fffb097a808cfe923e61ec2fa5cfd522cfe |
