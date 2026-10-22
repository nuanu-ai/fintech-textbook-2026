---
title: "Claims for Chapter 7"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

[← AI agent payments](README.md) · [Contents](../README.md) · [All sources and fact-checks](../../Fact-check/README.md)

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../../Methodology/Edition-record.md).

# Claims for Chapter 7

**v0.1 · 2026-09-15 · private · independently_reviewed_draft · independent_review=see_REVIEW.md.**

Fact-checking of the original edition was completed on 2026-09-17. The relationship between the original version and the public copy, the scope of adaptation and the current navigation are described in the edition record.

Common fields: `as_of=2026-09-15`; `last_checked_at=2026-09-15, Asia/Makassar (UTC+08:00)`; `reviewer=part_07_research`; `review_status=author_checked; independent_scope=see_REVIEW.md`; `effective_from/effective_to=not_applicable` for technical and teaching conclusions. For legal questions, this file does not establish when any specific obligation enters into force. `confirmed` means consistency with the source as read within the stated scope, not an independent check of an implementation or legal approval. All sources are disclosed in [Sources](Sources.md), which gives versions, the scope actually read and limitations.

`review_trigger`: a new specification/release, a change in product documentation/availability, a new provider agreement, a change in applicable law, or a discovered mismatch with the primary source. For teaching controls: a change in the underlying assumptions. In the absence of a specific conflict, `conflicts=none_identified_within_reviewed_scope`; this is not a promise that no external contradictions exist.

## P07-C001

- **module_ids:** 7.1, 7.3; **claim_kind:** definition; **status:** confirmed.
- **claim:** HTTP 402 is reserved in RFC 9110; the code by itself does not define a complete payment protocol.
- **jurisdiction / conditions:** HTTP semantics, RFC 9110.
- **evidence / locator / relation / reasoning:**
  - [P07-S001](Sources.md#p07-s001) / `P07-S001-20260915`; §15.5.3; `supports`: The normative meaning of the code is limited to reserved for future use.
- **confidence_basis / limitations / resolution:** The parameters of a specific implementation come from a separate specification; the code does not prove a transfer of money.

## P07-C002

- **module_ids:** 7.1; **claim_kind:** hypothesis; **status:** working_hypothesis.
- **claim:** Quote, principal consent, rail authorization, settlement and fulfillment should be tracked as separate states.
- **jurisdiction / conditions:** Teaching commerce/payment architecture; the sequence depends on the method.
- **evidence / locator / relation / reasoning:**
  - [P07-S002](Sources.md#p07-s002) / `P07-S002-20260915`; §§6–7 flows; `context`: Different x402 processing sequences.
  - [P07-S014](Sources.md#p07-s014) / `P07-S014-20260915`; Status Lifecycle Values; `context`: Checkout status reflects its own lifecycle.
  - [P07-S040](Sources.md#p07-s040) / `P07-S040-20260915`; status; `context`: PaymentIntent has separate payment states.
- **confidence_basis / limitations / resolution:** This is the author's synthesis, not a universal normative state machine.

## P07-C003

- **module_ids:** 7.2; **claim_kind:** product; **status:** confirmed.
- **claim:** Visa Intelligent Commerce describes agentic card infrastructure, but the public overview does not establish universal production availability.
- **jurisdiction / conditions:** Public Visa developer overview as of the reading date.
- **evidence / locator / relation / reasoning:**
  - [P07-S026](Sources.md#p07-s026) / `P07-S026-20260915`; Disclaimer; How does it work?; Controls; `supports`: There is a caveat about ongoing development and changes in availability.
- **confidence_basis / limitations / resolution:** Eligibility, onboarding and the contractual terms of a specific program are needed; the card infrastructure remains in place.

## P07-C004

- **module_ids:** 7.2, 7.6; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** Visa Trusted Agent Protocol describes recognition of signed agent requests at the merchant boundary.
- **jurisdiction / conditions:** Public Visa TAP merchant specification; version number not established.
- **evidence / locator / relation / reasoning:**
  - [P07-S027](Sources.md#p07-s027) / `P07-S027-20260915`; Introduction; Participants; Trust Model; Agent Recognition; `supports`: The roles and the trusted agent check are described by the protocol owner itself.
- **confidence_basis / limitations / resolution:** This is not standalone proof of authority for any purchase and not a study of production security.

## P07-C005

- **module_ids:** 7.2; **claim_kind:** product; **status:** confirmed.
- **claim:** Visa ICC was announced on 9 April 2026 as work with select partners and a pilot, which by itself does not prove general availability in September.
- **jurisdiction / conditions:** Historical Visa statement of 2026-04-09.
- **evidence / locator / relation / reasoning:**
  - [P07-S028](Sources.md#p07-s028) / `P07-S028-20260915`; Main announcement; pilot description; `supports`: The pilot scope is preserved in the wording.
- **confidence_basis / limitations / resolution:** Subsequent GA was not established in this research.

## P07-C006

- **module_ids:** 7.2; **claim_kind:** product; **status:** confirmed.
- **claim:** In its public materials, Mastercard describes agent registration, tokenization and passing on the context of an agentic purchase.
- **jurisdiction / conditions:** Mastercard 2025 framework article; not a full scheme rulebook.
- **evidence / locator / relation / reasoning:**
  - [P07-S029](Sources.md#p07-s029) / `P07-S029-20260915`; Framework; agent registration; tokenization; contextual data; `supports`: The company's publicly described approach.
- **confidence_basis / limitations / resolution:** No region-wide liability shift, mandatory status or production eligibility is inferred.

## P07-C007

- **module_ids:** 7.2; **claim_kind:** product; **status:** confirmed.
- **claim:** Mastercard announced Agent Pay for Machines on 10 June 2026; the publication does not confirm that any developer can connect.
- **jurisdiction / conditions:** Mastercard press release of 2026-06-10.
- **evidence / locator / relation / reasoning:**
  - [P07-S030](Sources.md#p07-s030) / `P07-S030-20260915`; Headline; How it works; Partnering; `supports`: Confirms the announcement and the described partner chain.
- **confidence_basis / limitations / resolution:** Contracts, endpoint access and the specific implementation were not checked.

## P07-C008

- **module_ids:** 7.2; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** Stripe SPT uses amount/expiry/seller context restrictions; a token by itself does not constitute a capture.
- **jurisdiction / conditions:** Shared payment tokens, seller documentation.
- **evidence / locator / relation / reasoning:**
  - [P07-S022](Sources.md#p07-s022) / `P07-S022-20260915`; Sellers: How it works; restrictions; using a token; `supports`: An SPT conveys a limited payment capability.
  - [P07-S040](Sources.md#p07-s040) / `P07-S040-20260915`; status; `context`: PaymentIntent reflects the subsequent outcome.
- **confidence_basis / limitations / resolution:** The restrictions of the specific token and the API version must be checked before execution.

## P07-C009

- **module_ids:** 7.2; **claim_kind:** product; **status:** confirmed.
- **claim:** The Private preview label on the Stripe agentic-commerce overview applies to the Agents section, not automatically to the whole page of capabilities.
- **jurisdiction / conditions:** Stripe overview as of 2026-09-15.
- **evidence / locator / relation / reasoning:**
  - [P07-S024](Sources.md#p07-s024) / `P07-S024-20260915`; Agents — Private preview; `supports`: The status was read together with the heading of the relevant section.
- **confidence_basis / limitations / resolution:** Availability may change; this does not replace the documentation of a specific feature.

## P07-C010

- **module_ids:** 7.2, 7.3; **claim_kind:** product; **status:** confirmed.
- **claim:** ACP is described by its owners as beta; for this chapter the released specification 2026-04-17 was chosen, not the unreleased one.
- **jurisdiction / conditions:** ACP repo pin 7fdd78d, released path spec/2026-04-17.
- **evidence / locator / relation / reasoning:**
  - [P07-S010](Sources.md#p07-s010) / `P07-S010-20260915`; README status/versioning; CHANGELOG; `supports`: The repository distinguishes the published version from current work.
- **confidence_basis / limitations / resolution:** A repository pin is not the same as the deployed API version.

## P07-C011

- **module_ids:** 7.2; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** ACP checkout represents a commercial session; delegate payment is a separate contract for issuing a limited payment token.
- **jurisdiction / conditions:** ACP release 2026-04-17.
- **evidence / locator / relation / reasoning:**
  - [P07-S011](Sources.md#p07-s011) / `P07-S011-20260915`; checkout session operations and schema; `supports`: The operations manage the checkout.
  - [P07-S012](Sources.md#p07-s012) / `P07-S012-20260915`; POST /agentic_commerce/delegate_payment; Allowance; `supports`: A separate allowance/token flow is described.
- **confidence_basis / limitations / resolution:** It is not assumed that all sellers implement both interfaces.

## P07-C012

- **module_ids:** 7.2; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** ACP Delegate Payment defines the fields max_amount, currency, merchant_id, expires_at and Idempotency-Key for the corresponding request.
- **jurisdiction / conditions:** Released delegate_payment OpenAPI 2026-04-17.
- **evidence / locator / relation / reasoning:**
  - [P07-S012](Sources.md#p07-s012) / `P07-S012-20260915`; Allowance, lines 520–559; IdempotencyKeyHeader, lines 251–255; `supports`: The fields and the header were read in the schema.
- **confidence_basis / limitations / resolution:** That requests refer to the same business order cannot be inferred from the presence of a field: the implementation must store the link.

## P07-C013

- **module_ids:** 7.2; **claim_kind:** product; **status:** confirmed.
- **claim:** Supporting the open checkout contract does not guarantee acceptance of a product feed and distribution in ChatGPT.
- **jurisdiction / conditions:** OpenAI Get Started, public onboarding description.
- **evidence / locator / relation / reasoning:**
  - [P07-S025](Sources.md#p07-s025) / `P07-S025-20260915`; Approved partners; product feeds; onboarding; `supports`: The documentation describes selection and separate onboarding.
- **confidence_basis / limitations / resolution:** The current status of a specific merchant account was not checked.

## P07-C014

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** The x402 v2 HTTP transport uses PAYMENT-REQUIRED, PAYMENT-SIGNATURE and PAYMENT-RESPONSE.
- **jurisdiction / conditions:** Pinned x402 v2 HTTP transport.
- **evidence / locator / relation / reasoning:**
  - [P07-S003](Sources.md#p07-s003) / `P07-S003-20260915`; Payment Required; Payment Payload; Payment Response; `supports`: The header formats are defined in the transport.
- **confidence_basis / limitations / resolution:** Other transports or v1 cannot be treated as the same wire contract.

## P07-C015

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** In x402, checking a payment payload via verify is not the same as a completed settlement.
- **jurisdiction / conditions:** x402 v2 core and exact EVM.
- **evidence / locator / relation / reasoning:**
  - [P07-S002](Sources.md#p07-s002) / `P07-S002-20260915`; Facilitator API /verify and /settle; `supports`: The contract contains separate operations.
  - [P07-S004](Sources.md#p07-s004) / `P07-S004-20260915`; EIP-3009 phases 2 and 3; `supports`: Verification and submission are separated.
- **confidence_basis / limitations / resolution:** An external facilitator does not automatically become a guarantor that the goods will be delivered.

## P07-C016

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** The current x402 v2 allows different orderings of resource execution and settlement depending on the scheme/assetTransferMethod.
- **jurisdiction / conditions:** Pinned core v2; selected flows.
- **evidence / locator / relation / reasoning:**
  - [P07-S002](Sources.md#p07-s002) / `P07-S002-20260915`; Authorization/Upfront/Escrow execution flow; `supports`: The document presents different sequences.
- **confidence_basis / limitations / resolution:** A single tutorial flow cannot be carried over to all schemes.

## P07-C017

- **module_ids:** 7.3, 7.5; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** An EIP-3009 exact payment binds the transfer authorization to the transfer parameters and nonce, but not automatically to the whole business order.
- **jurisdiction / conditions:** x402 exact EVM, EIP-3009 branch.
- **evidence / locator / relation / reasoning:**
  - [P07-S004](Sources.md#p07-s004) / `P07-S004-20260915`; PaymentPayload; authorization fields; verify/settle phases; `supports`: The signed transfer fields are limited to this contract.
  - [P07-S005](Sources.md#p07-s005) / `P07-S005-20260915`; Purpose; Specification; `context`: A separate extension introduces an application payment identifier.
- **confidence_basis / limitations / resolution:** The meaning of the SKU, fulfillment and application retry requires separate correlation.

## P07-C018

- **module_ids:** 7.3, 7.5; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** The x402 payment-identifier extension is intended for correlation and idempotent handling of repeated payment requests.
- **jurisdiction / conditions:** Pinned payment_identifier.md.
- **evidence / locator / relation / reasoning:**
  - [P07-S005](Sources.md#p07-s005) / `P07-S005-20260915`; Purpose; Requirements; Example flow; `supports`: The extension describes storing and re-presenting the ID.
- **confidence_basis / limitations / resolution:** The extension has to be negotiated and implemented; having a nonce does not replace it.

## P07-C019

- **module_ids:** 7.3; **claim_kind:** definition; **status:** confirmed.
- **claim:** The MPP core draft-httpauth-payment-01 is an Internet-Draft published on 9 September 2026, not an adopted RFC.
- **jurisdiction / conditions:** IETF draft metadata/status, expiry 2027-03-13.
- **evidence / locator / relation / reasoning:**
  - [P07-S006](Sources.md#p07-s006) / `P07-S006-20260915`; Document metadata; Status of This Memo; `supports`: The status and dates are available in the published draft.
- **confidence_basis / limitations / resolution:** Intended Standards Track does not mean a finished standard.

## P07-C020

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** The MPP Payment challenge specifies the payment method and the intent separately; the response carries a credential in the negotiated authentication header.
- **jurisdiction / conditions:** MPP core draft01.
- **evidence / locator / relation / reasoning:**
  - [P07-S006](Sources.md#p07-s006) / `P07-S006-20260915`; Payment Challenges; Payment Credentials; header selection; `supports`: The protocol separates the action from the method used to carry it out.
- **confidence_basis / limitations / resolution:** Settlement guarantees and refund capabilities cannot be treated as identical across all methods.

## P07-C021

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** MPP Stripe charge uses SPT and Stripe PaymentIntent; therefore a machine HTTP interface does not eliminate the processor.
- **jurisdiction / conditions:** Pinned draft-stripe-charge-00.
- **evidence / locator / relation / reasoning:**
  - [P07-S007](Sources.md#p07-s007) / `P07-S007-20260915`; Overview; Flow; Payment Processing; `supports`: The description explicitly involves a Stripe token and server-side payment processing.
- **confidence_basis / limitations / resolution:** This is a specific payment method, not the whole of MPP.

## P07-C022

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** MPP Solana charge describes pull with a signed transaction and push with a transaction signature; consumed signatures must be recorded atomically.
- **jurisdiction / conditions:** Pinned draft-solana-charge-00.
- **evidence / locator / relation / reasoning:**
  - [P07-S009](Sources.md#p07-s009) / `P07-S009-20260915`; Abstract; Replay Protection; Pull Mode Settlement; `supports`: Both credential forms and the replay protection requirements were read directly.
- **confidence_basis / limitations / resolution:** Finality/Token2022/confidential profiles were not fully checked; the SDK was not run.

## P07-C023

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** MPP Tempo session uses a deposit/channel and cumulative vouchers to account for sequential consumption.
- **jurisdiction / conditions:** Pinned draft-tempo-session-00, introduction and session flow.
- **evidence / locator / relation / reasoning:**
  - [P07-S008](Sources.md#p07-s008) / `P07-S008-20260915`; Overview; Session flow; cumulative voucher model; `supports`: The model separates top-up from the accumulated amount claimed.
- **confidence_basis / limitations / resolution:** The chapter's numbers are synthetic; closing/challenge timing was not audited.

## P07-C024

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** UCP release v2026-08-25 describes commerce capabilities and payment handlers as different elements.
- **jurisdiction / conditions:** UCP tag cd78fb3.
- **evidence / locator / relation / reasoning:**
  - [P07-S013](Sources.md#p07-s013) / `P07-S013-20260915`; Overview; Discovery; Capability/Extension Model; `supports`: The composition of commerce capabilities is described.
  - [P07-S015](Sources.md#p07-s015) / `P07-S015-20260915`; Purpose; Participants; Processing; `supports`: The payment handler is responsible for the selected payment method.
- **confidence_basis / limitations / resolution:** Neither the compatibility of any two implementations nor the mandatory use of a specific rail is proven.

## P07-C025

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** In UCP, complete_in_progress is not completed and must not contain an order; completed means a placed order, not delivered goods.
- **jurisdiction / conditions:** UCP Checkout Capability release v2026-08-25.
- **evidence / locator / relation / reasoning:**
  - [P07-S014](Sources.md#p07-s014) / `P07-S014-20260915`; Status Lifecycle Values; Complete checkout; `supports`: The statuses and the presence of an order are distinguished in the contract.
- **confidence_basis / limitations / resolution:** Final fulfillment is tracked separately from checkout.

## P07-C026

- **module_ids:** 7.3; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** UCP allows continuation via continue_url, including a required human action.
- **jurisdiction / conditions:** UCP checkout and payment authentication extension.
- **evidence / locator / relation / reasoning:**
  - [P07-S014](Sources.md#p07-s014) / `P07-S014-20260915`; Continue URL; requires_escalation; `supports`: The contract includes a handoff to human action.
  - [P07-S016](Sources.md#p07-s016) / `P07-S016-20260915`; Runtime flow and example; `context`: Payment authentication is negotiated separately.
- **confidence_basis / limitations / resolution:** A browser-assisted flow does not guarantee a right to bypass a challenge or arbitrary merchant coverage.

## P07-C027

- **module_ids:** 7.4; **claim_kind:** product; **status:** confirmed.
- **claim:** Stripe Machine payments describes crypto agent pay with fiat proceeds in the Stripe balance and limited geographic availability.
- **jurisdiction / conditions:** Stripe Machine payments documentation on 2026-09-15.
- **evidence / locator / relation / reasoning:**
  - [P07-S023](Sources.md#p07-s023) / `P07-S023-20260915`; Availability; settlement; supported methods; `supports`: The full short page was read, including US except NY and requests for other regions.
- **confidence_basis / limitations / resolution:** Not confirmed: eligibility of a specific account, bank payout or an unconditional SLA.

## P07-C028

- **module_ids:** 7.4; **claim_kind:** hypothesis; **status:** working_hypothesis.
- **claim:** Stablecoin→fiat conversion and the merchant's receipt of fiat are additional money operations that an HTTP payment challenge does not perform by itself.
- **jurisdiction / conditions:** Teaching crypto→fiat model; depends on the provider agreement.
- **evidence / locator / relation / reasoning:**
  - [P07-S023](Sources.md#p07-s023) / `P07-S023-20260915`; Settlement to Stripe balance; `context`: An example of a provider with a separate balance.
  - [P07-S002](Sources.md#p07-s002) / `P07-S002-20260915`; Core scope and participant model; `context`: The HTTP/core protocol does not define the whole bank payout.
- **confidence_basis / limitations / resolution:** The chapter's diagrams and money figures are the author's synthesis, not a real fee schedule.

## P07-C029

- **module_ids:** 7.4, 7.5; **claim_kind:** experience; **status:** confirmed.
- **claim:** The author of deX402 stated on X that there are no payment processors; this is not a universal property of x402/MPP and not a verified product result.
- **jurisdiction / conditions:** The exact public deX402 post of 12 April 2026.
- **evidence / locator / relation / reasoning:**
  - [P07-S037](Sources.md#p07-s037) / `P07-S037-20260915`; Main post; `supports`: Confirms the fact of the author's own statement.
  - [P07-S007](Sources.md#p07-s007) / `P07-S007-20260915`; Stripe charge flow; `contradicts`: A universal reading is incompatible with a processor-backed method.
  - [P07-S023](Sources.md#p07-s023) / `P07-S023-20260915`; Machine payments processing; `context`: An example of a financial intermediary in a real product description.
- **confidence_basis / limitations / resolution:** The post is promotional; the author's actual operations were not observed.

## P07-C030

- **module_ids:** 7.3; **claim_kind:** experience; **status:** confirmed.
- **claim:** Solana publicly announced MPP support; the chapter did not run its own test of the announced SDKs.
- **jurisdiction / conditions:** X @solana, 25 March 2026, main plus two author continuations.
- **evidence / locator / relation / reasoning:**
  - [P07-S036](Sources.md#p07-s036) / `P07-S036-20260915`; Main post and visible continuations; `supports`: The chapter author independently read the original via the Chrome UI.
  - [P07-S009](Sources.md#p07-s009) / `P07-S009-20260915`; Pinned method specification; `context`: The technical form of the method is confirmed separately.
- **confidence_basis / limitations / resolution:** The announcement does not prove availability of all SDKs, token variants and merchants.

## P07-C031

- **module_ids:** 7.2, 7.5; **claim_kind:** experience; **status:** confirmed.
- **claim:** A Reddit author described problems with a test-mode SPT integration; this is a useful reproduction lead, not a measured failure rate.
- **jurisdiction / conditions:** r/fintech post 1vtl49r; exact date unknown.
- **evidence / locator / relation / reasoning:**
  - [P07-S038](Sources.md#p07-s038) / `P07-S038-20260915`; Main post, test-mode points 1–4; `supports`: The self-report was read; the code was not run.
- **confidence_basis / limitations / resolution:** Statistics and production behavior were not established; the claimed AU availability was not accepted in place of official eligibility.

## P07-C032

- **module_ids:** 7.5; **claim_kind:** empirical; **status:** confirmed.
- **claim:** AgentDojo studies prompt injection in dynamic tool-use tasks; the benchmark does not measure losses in payment systems.
- **jurisdiction / conditions:** NeurIPS 2024 benchmark, arXiv:2406.13352v3 of 2024-11-24, re-checked on 2026-09-17.
- **evidence / locator / relation / reasoning:**
  - [P07-S033](Sources.md#p07-s033) / `P07-S033-20260917`; §§3.4, 4.1–4.3; task/attack construction; `supports`: The evaluation methods and limitations were read, not only the abstract.
- **confidence_basis / limitations / resolution:** The 97 tasks and 629 security cases describe the test environment; carrying the results over to new models and to payments requires verification. The original reading on 15 September has no saved snapshot; the confirmation above applies to the explicitly pinned v3.

## P07-C033

- **module_ids:** 7.5; **claim_kind:** empirical; **status:** confirmed.
- **claim:** Formal Analysis of Agent Payment Protocols applies Tamarin and explicitly separates symbolic models, traces and implementation evidence.
- **jurisdiction / conditions:** arXiv 2609.00060v1, submitted 2026-08-30, preprint.
- **evidence / locator / relation / reasoning:**
  - [P07-S034](Sources.md#p07-s034) / `P07-S034-20260915`; §§III–VII; threat model; evaluation; limitations; `supports`: The model, evidence levels and limitations were read.
- **confidence_basis / limitations / resolution:** No replication was performed, and production exploits on the versions pinned in this chapter are not proven.

## P07-C034

- **module_ids:** 7.5; **claim_kind:** empirical; **status:** confirmed.
- **claim:** Beyond the Mandate studies AP2 in its own testbed/scanner setting; no conclusion about every current deployment follows from this.
- **jurisdiction / conditions:** arXiv 2608.23858v1, submitted 2026-08-24, preprint.
- **evidence / locator / relation / reasoning:**
  - [P07-S035](Sources.md#p07-s035) / `P07-S035-20260915`; §§3–9, especially threat model, demos, CDSE, ablations, limitations; `supports`: The experimental conditions and boundaries were studied, not only the abstract.
- **confidence_basis / limitations / resolution:** The authors' systems and the selected implementations are not the whole market; there is no independent replication.

## P07-C035

- **module_ids:** 7.5; **claim_kind:** hypothesis; **status:** working_hypothesis.
- **claim:** An uncertain settlement after broadcast must be reconciled using the original rail/provider ID before any decision on a new payment.
- **jurisdiction / conditions:** Proposed operational control for money-moving requests.
- **evidence / locator / relation / reasoning:**
  - [P07-S004](Sources.md#p07-s004) / `P07-S004-20260915`; settlement_pending; transaction and network fields; `context`: The protocol provides stable identifiers for an uncertain outcome.
  - [P07-S005](Sources.md#p07-s005) / `P07-S005-20260915`; Idempotency requirements; `context`: A retry must preserve the link to the earlier operation.
- **confidence_basis / limitations / resolution:** This is a safe recovery design; the specific time limit/operator procedure is set by the provider and the contract.

## P07-C036

- **module_ids:** 7.5; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** x402 v2 allows a non-terminal settlement_pending with a transaction hash and network when confirmation is uncertain.
- **jurisdiction / conditions:** Pinned x402 exact EVM and core v2.
- **evidence / locator / relation / reasoning:**
  - [P07-S004](Sources.md#p07-s004) / `P07-S004-20260915`; Settlement response; settlement_pending; `supports`: The outcome is not marked as a final fail.
  - [P07-S002](Sources.md#p07-s002) / `P07-S002-20260915`; SettleResponse handling; `context`: Core distinguishes settlement outcomes.
- **confidence_basis / limitations / resolution:** A hash does not prove finality: reconciliation against the relevant network is required.

## P07-C037

- **module_ids:** 7.5; **claim_kind:** hypothesis; **status:** working_hypothesis.
- **claim:** Two parallel agents can jointly exceed a budget if each checks the same earlier balance without an atomic reservation.
- **jurisdiction / conditions:** Synthetic example: shared budget=10, reservations 6+6.
- **evidence / locator / relation / reasoning:**
  - [P07-S020](Sources.md#p07-s020) / `P07-S020-20260915`; Budget/recurrence constraints; `context`: The constraints require tracking prior presentations.
  - [P07-S021](Sources.md#p07-s021) / `P07-S021-20260915`; Server-side validation and replay considerations; `context`: Checks must be performed on the trusted side.
- **confidence_basis / limitations / resolution:** A conclusion from arithmetic and concurrent execution, not incident statistics.

## P07-C038

- **module_ids:** 7.6; **claim_kind:** definition; **status:** confirmed.
- **claim:** RFC 8693 distinguishes delegation and impersonation; actor identity by itself does not define the full trust model of a financial operation.
- **jurisdiction / conditions:** RFC 8693 §§1, 1.1, 4.1.
- **evidence / locator / relation / reasoning:**
  - [P07-S031](Sources.md#p07-s031) / `P07-S031-20260915`; Scope; Delegation vs. Impersonation; act; `supports`: The trust model and specific token security semantics are bounded by the RFC's scope.
- **confidence_basis / limitations / resolution:** A payment requires separate consent/authority and enforcement.

## P07-C039

- **module_ids:** 7.6; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** A DPoP proof is not a standalone authentication/access control mechanism and does not prove consent to the goods.
- **jurisdiction / conditions:** RFC 9449 §§4,4.1,7.1.
- **evidence / locator / relation / reasoning:**
  - [P07-S032](Sources.md#p07-s032) / `P07-S032-20260915`; DPoP Proof JWTs; checking proofs; binding access tokens; `supports`: The proof is used together with the token and the resource server's checks.
- **confidence_basis / limitations / resolution:** A correct signature does not fix the absence of a right to make a recurring purchase.

## P07-C040

- **module_ids:** 7.6; **claim_kind:** definition; **status:** confirmed.
- **claim:** RATS separates attester, verifier and relying party; attestation evidence does not replace a payment instruction.
- **jurisdiction / conditions:** RFC 9334 Informational architecture.
- **evidence / locator / relation / reasoning:**
  - [P07-S041](Sources.md#p07-s041) / `P07-S041-20260915`; §4.1; §5.2; §7; §8.5; `supports`: The relying party applies a policy to the result of the appraisal of the environment.
- **confidence_basis / limitations / resolution:** The last point, about the boundary of payment consent, is the author's conclusion from the difference in scopes.

## P07-C041

- **module_ids:** 7.6; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** AP2 v0.2 uses Checkout and Payment mandates, which allow open/closed forms; older terminology must not be mixed in without stating the version.
- **jurisdiction / conditions:** AP2 repo v0.2.0 changelog, pinned e1ea56d.
- **evidence / locator / relation / reasoning:**
  - [P07-S017](Sources.md#p07-s017) / `P07-S017-20260915`; Mandates; Human-present and autonomous flows; CHANGELOG 0.2.0; `supports`: The terms and flows match the stated version.
- **confidence_basis / limitations / resolution:** This is not a claim of compatibility with all earlier SDKs.

## P07-C042

- **module_ids:** 7.6; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** AP2 agent authorization describes User Credential and Trusted Agent Provider models for confirming consent.
- **jurisdiction / conditions:** AP2 current agent_authorization.md.
- **evidence / locator / relation / reasoning:**
  - [P07-S018](Sources.md#p07-s018) / `P07-S018-20260915`; Introduction; User Credential; Trusted Agent Provider; `supports`: Different trust arrangements are described in the primary source.
- **confidence_basis / limitations / resolution:** Neither model is declared a universal legal identification of the customer.

## P07-C043

- **module_ids:** 7.6; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** In AP2, the Checkout mandate is bound to the merchant-signed checkout through checkout_hash.
- **jurisdiction / conditions:** AP2 Checkout Mandate v0.2.
- **evidence / locator / relation / reasoning:**
  - [P07-S019](Sources.md#p07-s019) / `P07-S019-20260915`; Usage; Type; Checkout Hash; `supports`: The link to a specific checkout is defined by the structure.
  - [P07-S017](Sources.md#p07-s017) / `P07-S017-20260915`; Autonomous flow; `context`: Closed mandates are checked against the agreed open mandates.
- **confidence_basis / limitations / resolution:** The merchant's signature does not prove the quality of the goods.

## P07-C044

- **module_ids:** 7.6; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** The AP2 Payment Mandate defines payee/instrument/amount/date constraints and optional recurrence/budget; repeated presentations require tracking.
- **jurisdiction / conditions:** AP2 Payment Mandate v0.2.
- **evidence / locator / relation / reasoning:**
  - [P07-S020](Sources.md#p07-s020) / `P07-S020-20260915`; Constraints; Budget; Recurrence; Allowed Payees/Instruments; `supports`: The list of constraints and the conditions for checking them were read.
- **confidence_basis / limitations / resolution:** Dynamic constraints cannot be checked from the syntax of a single signature alone.

## P07-C045

- **module_ids:** 7.6; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** In the contract that was read, the AP2 Checkout Mandate line-items check does not support splitting one open mandate across several checkouts.
- **jurisdiction / conditions:** AP2 checkout_mandate.md v0.2.
- **evidence / locator / relation / reasoning:**
  - [P07-S019](Sources.md#p07-s019) / `P07-S019-20260915`; Line Items constraint; `supports`: The restriction is stated explicitly.
- **confidence_basis / limitations / resolution:** It is not claimed that a future extension is impossible in principle; agent-to-agent delegation is also outside the reviewed core.

## P07-C046

- **module_ids:** 7.5, 7.6; **claim_kind:** mechanism; **status:** confirmed.
- **claim:** AP2 security guidance places the checking of consent/mandates outside the model's untrusted instructions and describes a trusted surface.
- **jurisdiction / conditions:** AP2 Security and Privacy Considerations v0.2.
- **evidence / locator / relation / reasoning:**
  - [P07-S021](Sources.md#p07-s021) / `P07-S021-20260915`; Consent; deterministic verification; Trusted Surface; privacy; `supports`: The fully read file sets the boundaries of the checks.
- **confidence_basis / limitations / resolution:** A recommendation in a specification does not prove that a specific runtime is correct.

## P07-C047

- **module_ids:** 7.6; **claim_kind:** legal; **status:** confirmed.
- **claim:** The 2021 FATF guidance serves as context for VASP functions and the Travel Rule; the publication page itself warns of later changes to the standards.
- **jurisdiction / conditions:** Only the scope of the FATF publication page; not a legal opinion.
- **evidence / locator / relation / reasoning:**
  - [P07-S039](Sources.md#p07-s039) / `P07-S039-20260915`; Publication overview and update warning; `supports`: The full PDF was not read; obligations in force in individual countries are not inferred.
- **confidence_basis / limitations / resolution:** The current rule and a classification of the role in the chosen jurisdiction are required; effective dates of this specific legal obligation are unknown.

## P07-C048

- **module_ids:** 7.5, 7.6; **claim_kind:** legal; **status:** open.
- **claim:** The full allocation of agentic liability among the principal, vendor, merchant and financial provider in a chosen country is not established here.
- **jurisdiction / conditions:** Real-world application requires contracts and applicable law.
- **evidence / locator / relation / reasoning:**
  - [P07-S026](Sources.md#p07-s026) / `P07-S026-20260915`; Public scope/disclaimer; `context`: The overview does not replace contracts.
  - [P07-S029](Sources.md#p07-s029) / `P07-S029-20260915`; Framework public description; `context`: Not a full rulebook.
  - [P07-S017](Sources.md#p07-s017) / `P07-S017-20260915`; Dispute-resolution scope; `context`: Evidence and the dispute mechanism have different scopes.
- **confidence_basis / limitations / resolution:** The chapter's RACI is a design model of ownership, not a legal opinion.

## P07-C049

- **module_ids:** 7.3, 7.5; **claim_kind:** mechanism; **status:** rejected.
- **claim:** The claim "any x402 payload means a completed sale" is rejected.
- **jurisdiction / conditions:** Universal claim.
- **evidence / locator / relation / reasoning:**
  - [P07-S002](Sources.md#p07-s002) / `P07-S002-20260915`; Verify/settle and response model; `contradicts`: Authorization and settlement are separated.
  - [P07-S014](Sources.md#p07-s014) / `P07-S014-20260915`; Checkout lifecycle; `context`: Order and fulfillment are also separate.
- **confidence_basis / limitations / resolution:** A sale requires the corresponding money and goods evidence in the specific model.

## P07-C050

- **module_ids:** 7.6; **claim_kind:** mechanism; **status:** rejected.
- **claim:** The claim "a known agent identity automatically grants the right to spend the principal's funds" is rejected.
- **jurisdiction / conditions:** Universal claim.
- **evidence / locator / relation / reasoning:**
  - [P07-S018](Sources.md#p07-s018) / `P07-S018-20260915`; Agent Authorization; `contradicts`: A separate consent model is required.
  - [P07-S031](Sources.md#p07-s031) / `P07-S031-20260915`; Trust-model scope; delegation semantics; `contradicts`: The actor/subject structure does not define all rights.
  - [P07-S032](Sources.md#p07-s032) / `P07-S032-20260915`; Proof is not authentication/access control; `context`: A key proof by itself is not enough.
- **confidence_basis / limitations / resolution:** Authority must be tied to the purchase, the limits and the validity period.

## P07-C051

- **module_ids:** 7.2; **claim_kind:** definition; **status:** confirmed.
- **claim:** UCP governance designates the Governing Council as the owner of UCP assets, Google as the custodian of the domain, and Google and Shopify as founding organizations with permanent seats.
- **jurisdiction / conditions:** Universal-Commerce-Protocol governance policy, separate repo pin ced53b98c2064d472b41a5aff1c20b8261e6dd91 of 2026-09-15.
- **evidence / locator / relation / reasoning:** [P07-S042](Sources.md#p07-s042) / `P07-S042-20260915`; Governing Council; `supports`: the allocation of roles is stated explicitly in the project's policy.
- **confidence_basis / limitations / resolution:** This describes the project's own bodies; adoption of a law, independent certification and absence of vendor influence cannot be inferred from it.
