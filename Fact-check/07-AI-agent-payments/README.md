---
title: "Independent factual audit — Chapter 7"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← Sources and fact-check](../README.md) · [Read the chapter](../../Textbook/07-AI-agent-payments/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Independent factual audit — Chapter 7

2026-09-17 · Asia/Makassar (UTC+8) · auditor deep_audit_06_07_08_09 · private

## Result and findings

The full CHAPTER/SOURCES/CLAIMS were read; 51 claims and 42 source cards were assessed individually. No new errors in payment mechanisms were confirmed. One minor finding on source rights has been closed.

- **F07-01, minor, closed — S042.** The full pinned GOVERNANCE.md has no copyright/license header. The Apache-2.0 notice previously attributed to this file is not supported. The editor removed the attribution and stated license coverage unknown. The final card was re-read; the substantive C051 on council/domain/founding seats is confirmed.
- **L07-01, metadata limitation — S036.** X shows 2026-03-24 18:18; the earlier card had 25 March 02:18 with an unknown timezone. The 8-hour difference is consistent with display in different time zones and does not prove a different event date. The post itself and the continuations were read; the SDKs were not tested.
- **L07-02, historical version limitation.** AgentDojo v3 was read independently; NeurIPS 2024 Datasets and Benchmarks is separately confirmed by the [official proceedings record](https://proceedings.neurips.cc/paper_files/paper/2024/hash/97091a5177d8dc64b1da8bf3e1f6fb54-Abstract-Datasets_and_Benchmarks_Track.html). There is no 15 September archive for the earlier unpinned reading; this is recorded in S033.

## Versions and checked mechanisms

The GitHub API independently confirmed the commits: x402 6b930… 2026-09-15 14:04:22Z; MPP a938… 2026-09-09 21:20:04Z; ACP 7fdd… 2026-07-18 04:51:51Z; UCP cd78… 2026-08-25 13:47:10Z; AP2 e1ea… 2026-04-29 16:51:41Z; governance ced53… 2026-09-15 07:55:35Z. The UCP tag v2026-08-25 resolves to cd78…. Full hashes are present in the original URLs of the matrix. The exact release publication timestamp was not replaced with the commit timestamp.

In x402, the following were checked: three resource/settlement orderings, readonly verify, the EIP3009 branch, the optional payment identifier and non-terminal pending. In MPP, the draft status, the Stripe/Tempo/Solana branches and the atomic consumed-signature registry were read. In ACP/UCP, session/order/complete states and separate payment handlers were checked. In AP2 v0.2, the current Checkout/Payment names, trusted surface, deterministic validation, checkout hash and cumulative budget presentations were checked. No specification was taken as a compatibility certificate for a working product.

## Papers, social and important unregistered conclusions

AgentDojo: 97 tasks/629 security cases, utility and attack success in a controlled benchmark; not a payment-loss rate. Formal Analysis: symbolic Tamarin traces are kept separate from implementation checks; the 86 cases are not called 86 live vulnerabilities. Beyond the Mandate: testbed/scanner and raters are not equivalent to a production field study. Peer review of the two 2026 preprints has not been established.

The full chapter was checked for unregistered leaps identity→authority, verify→settlement, settlement→delivery, protocol→liability. No such leaps are asserted. The synthetic budget 6+6>10 and the reconciliation rules are formulated as the author's normative constructs, so C002/C028/C035/C037/C048 are rated non_factual rather than being mechanically marked verified. The X/Reddit posts confirm only that the authors published those words.

## Limitations

Not performed: live payments, SDK conformance tests, reproduction of the security papers and a separate legal opinion on liability. Dynamic vendor docs were observed on 17 September; their historical sameness on 15 September is not proven. The Reddit HTTP 200 shell was not counted as reading: the original body was obtained by a separate web extraction. Visa/Mastercard promotional promises did not become contractual guarantees.

## Coverage and verdict counts

Claims: 51; source cards: 42. Every ID has one matrix row.

- verified: 38
- non_factual: 5
- verified_as_reported: 8

## Final recheck and hashes

All the corrections listed were re-read after the editor's provisional freeze. The hashes below were calculated from the actual content of the final files. The previous review was used only as a risk pointer, not as evidence.

final_verdict: reviewed_with_limitations

open_critical: 0

open_major: 0

| File | SHA-256 |
|---|---|
| [CHAPTER.md](../../Textbook/07-AI-agent-payments/README.md) | 255aeb73f4b56c114bce54fe29219a3f801e70ed25feeaa298ae8a87e010faf8 |
| [Sources](../../Textbook/07-AI-agent-payments/Sources.md) | e83e77f5d2da6b4c0465ac9e84e6ad756c0bd6d77227041777df6922ea708f57 |
| [Claims](../../Textbook/07-AI-agent-payments/Claims.md) | d997c5631a66b4f2c09650169d92be38ac4dee4ffbf70198b123ad14e1669ea1 |
