---
title: "Независимый аудит источников — часть 04"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Публичная редакция от 18.09.2026. Даты проверки и ограничения источников сохранены. Хеши в исторических аудитах относятся к исходной рукописи; публичные изменения и текущие хеши — в [паспорте издания](../../edition.md).

# Независимый аудит источников — часть 04

17.09.2026 · Asia/Makassar (UTC+08) · auditor: deep_audit_02_03_04. Все 24 original URL самостоятельно попытался получить. Доступ к содержимому подтверждается указанным прочитанным разделом; HTML 200 сам по себе недостаточен. Недатированные страницы не объявлены неизменной копией 15 Sep. Большие документы прочитаны выборочно в существенных местах, не целиком; исследования не реплицированы.

| ID | original URL | actual access method/status | metadata/version result | independently read scope / limits |
|---|---|---|---|---|
| P04-S001 | [Original](https://www.fca.org.uk/firms/consider-if-you-provide-payment-services) | direct HTML200 | FCA Payment services for businesses; 6 June 2019, updated 22 March 2023 | Marketplace and exclusion context; no individual perimeter determination. |
| P04-S002 | [Original](https://www.mastercard.com/content/dam/mccom/shared/business/support/rules-pdfs/mastercard-rules.pdf) | direct403; web original PDF recovered | Mastercard Rules, 2 June 2026, 503 pages | §§7.6.5–7.6.5.1 and 5.8.1; delegation, responsibility, reporting. Regional modifiers not exhaustively audited. |
| P04-S003 | [Original](https://docs.stripe.com/connect/merchant-of-record) | direct HTML200 | Stripe Connect merchant-of-record docs; undated rolling page | Direct, indirect and on_behalf_of configurations; negative-balance liability. Product-specific model. |
| P04-S004 | [Original](https://www.paddle.com/legal/terms) | direct HTML200 | Paddle MSA updated 8 October 2025; new suppliers immediately, existing suppliers after 30 days | Reseller §2.1, set-off §8, refunds and chargebacks §§10.1–10.4. Individual order form absent. |
| P04-S005 | [Original](https://developer.spreedly.com/docs/routing-rules-1) | direct HTML200 | Spreedly Routing Rules; undated documentation | Static, split-volume and conditional rules; no measured uplift or downstream contract approval. |
| P04-S006 | [Original](https://docs.stripe.com/connect/identity-verification) | direct HTML200 | Stripe Connect identity verification; undated documentation | Country/capability/risk factors, later requirements, pauses and independent legal-duty warning. No account inspected. |
| P04-S007 | [Original](https://squareup.com/help/us/en/article/6832-reserves-faq) | direct HTML200 | Square US reserves help; undated page | Ownership, release, chargebacks and risk factors. No specific reserve percentage or term inferred. |
| P04-S008 | [Original](https://docs.stripe.com/payouts) | direct HTML200 | Stripe payouts; rolling documentation | Timing and payout failures; paid can become failed. No bank statement or real payout evidence. |
| P04-S009 | [Original](https://docs.adyen.com/reporting/settlement-reconciliation/transaction-level/settlement-details-report/) | direct HTML200 | Adyen Settlement details report; undated specification | Entries, references and columns 11–14. Report definition is not an actual financial record. |
| P04-S010 | [Original](https://help.adyen.com/knowledge/finance/invoices/how-do-i-reconcile-my-invoice) | direct HTML200 | Adyen invoice reconciliation; undated help page | Processing and authorization-scheme fee event bases, including cancellations/refusals/retries. Contract pricing absent. |
| P04-S011 | [Original](https://stripe.com/connect/pricing) | direct HTML200 | Stripe Connect pricing; US page read 17 September | You handle pricing, active-account definition and separate processing fees. Exact historical 15 September bytes unavailable. |
| P04-S012 | [Original](https://docs.stripe.com/payments/stablecoin-payments) | direct HTML200 plus official Markdown200 | Stripe Stablecoin payments; current undated docs | Properties, Business locations, Limitations and Refunds. Markdown exposes private-preview prose and broader country list; exact eligibility remains unresolved. |
| P04-S013 | [Original](https://stripe.com/legal/restricted-businesses) | direct HTML200 | Stripe Prohibited and Restricted Businesses; updated 13 May 2026, en-de response locale | Crypto exchanges/wallets and financial-service restrictions. No individual service approval established. |
| P04-S014 | [Original](https://support.triple-a.io/knowledge/what-services-does-triple-a-provide) | direct HTML200 | Triple-A What services does Triple-A provide; undated FAQ | Four published service descriptions, including fiat/crypto invoice receipt. No full token, jurisdiction or licence matrix. |
| P04-S015 | [Original](https://support.triple-a.io/knowledge/i-didnt-receive-my-payment-what-can-i-do) | direct HTML200 | Triple-A I did not receive my payment FAQ; undated | 3000 USD-equivalent automatic local-currency withdrawal threshold and timing caveat; no guaranteed individual SLA. |
| P04-S016 | [Original](https://www.federalreserve.gov/pubs/feds/2009/200923/) | direct official HTML 200 | FEDS 2009-23; Prager, Manuszak, Kiser, Borzekowski; 13 May 2009 | Executive summary and interchange/two-sided economics; literature results depend on assumptions. No new 2026 empirical estimate. |
| P04-S017 | [Original](https://tse-fr.eu/sites/default/files/medias/doc/wp/2002/platform.pdf) | direct official author PDF 200 | Rochet–Tirole, Platform Competition in Two-Sided Markets; author draft 13 December 2002 | §2/2.1: linear prices, no fixed usage costs, exogenous benefits, independence and profit function. Journal version not substituted; no replication. |
| P04-S018 | [Original](https://www.bis.org/publications/working-paper-1163-interchange-fees-access-pricing-and-sub-acquirers-payment-markets.pdf) | direct official PDF 200 | BIS Working Paper 1163; sole Jose Aurazo; January 2024 | Abstract, introduction, §3 and §6. Six agents, upstream access and no bypass; theoretical cases, not actual sponsor rates. |
| P04-S019 | [Original](https://www.federalreserve.gov/frrs/guidance/interagency-guidance-on-third-party-relationships.htm) | direct official HTML 200 | Fed/OCC/FDIC Interagency Guidance on Third-Party Relationships; 6 June 2023 | A and C: retained bank responsibility, lifecycle, audit/information rights, termination. Not a new licence; statutes not exhaustively read. |
| P04-S020 | [Original](https://developer.visa.com/capabilities/visanet-connect-issuing/docs-getting-started) | direct HTML200 | VisaNet Connect – Issuing, Getting Started; undated | Eligibility, Next Steps, issuer duties: sponsorship, production project and review distinct from sandbox. Region icons not treated as country matrix. |
| P04-S021 | [Original](https://www.centralbank.ie/regulation/industry-market-sectors/electronic-money-institutions/passporting) | direct HTML200 | Central Bank of Ireland EMI passporting; undated guidance | Home authorization, branches/agents/distributors and cross-border notification. Historical/typographic page quirks are not consolidated law. |
| P04-S022 | [Original](https://www.centralbank.ie/regulation/industry-market-sectors/payment-institutions/passporting) | direct HTML200 | Central Bank of Ireland PI passporting; undated guidance | Authorized services and notification under Irish PSD2 arrangements. Full consolidated EU law not read. |
| P04-S023 | [Original](https://www.reddit.com/r/fintech/comments/10kwnbp/bin_sponsorship_vs_payment_facilitator/) | direct 200 empty Reddit shell; web original substantive | u/songtu-staygold on r/fintech; relative four years, exact date unknown | OP, first answer and acquiring clarification read; commenter contract claims not adopted. |
| P04-S024 | [Original](https://docs.stripe.com/connect/separate-charges-and-transfers) | direct HTML200 and exact Markdown variant 200 | Stripe Separate charges and transfers; exact web/Checkout/stripe-hosted Markdown also read | Opening fee/balance bullets, Issue refunds and Reverse transfers. No actual bank arrival or successful recovery inferred. |

Official readable variants: [Stablecoin Markdown](https://docs.stripe.com/payments/stablecoin-payments.md); [exact Checkout/stripe-hosted transfer Markdown](https://docs.stripe.com/connect/separate-charges-and-transfers.md?platform=web&integration=checkout&ui=stripe-hosted).
