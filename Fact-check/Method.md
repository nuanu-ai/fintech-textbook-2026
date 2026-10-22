---
title: "In-depth fact-check of FinTech 2026 — second pass"
date: "2026-09-17"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Public edition of 2026-09-18. Check dates and source limitations are preserved. Hashes in the historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](../Methodology/Edition-record.md).

# In-depth fact-check of FinTech 2026 — second pass

2026-09-17 · private · audit assignment: a detailed check of facts and sources by separate subagents. The previous sample-based review is not evidence for the new pass.

## Goal

A complete register of check results for all 470 registered claims and all 349 source cards. Each claim gets an individual verdict. For each source, independently try to open it and check the relevant fragment; record unavailability honestly. This is not a promise that all sources are available and that all claims will turn out to be proven. Additionally, read the chapters for significant facts outside CLAIMS.

470/349 is the size of the original snapshot. Records added during corrections also go through a row-by-row check; the final numbers are recorded in REPORT.md and VALIDATION.json. The highest ID number is not the number of cards: there are gaps in the numbering.

The knowledge cutoff remains 2026-09-15. Date the actual accesses of the second pass with the real date and time zone. Do not present new versions as the historical text. Published, adopted, applies, launched, available to an account — these are different facts.

## Inputs and responsibilities

Read source-dataset-schema.md, the relevant part of structure.md, and chapter.md, sources.md and claims.md in full. Use the old REVIEW as a list of risks, not as a substitute for your own evidence. The baseline snapshot is baseline/ and BASELINE.json.

An auditor writes only to their own part-NN folder inside audit-2026-09-17. Root corrects the chapters and earlier reviews. Report material findings to root immediately, with the ID, the exact quotation of the phrase being checked, the primary URL/locator and a specific correction. Do not create new agents. Do not touch Flow, the canon, publication or real payments.

## What to check

1. Each claim: the source really contains this conclusion; the subject, activity, jurisdiction, date, condition and version match; strong and weak conclusions are not glued together.
2. All source cards: existence and authenticity, exact title/author, publication/update date, status/version, effective date, the nature of the actual access. HTTP 200 does not prove that the text was read. If blocked, look for a permitted original, an official PDF/another primary source; label an index as an index.
3. Law, scheme rules, fees, eligibility, finality and financial controls: an independent direct reading of the decisive passage. An FAQ/announcement/consultation does not become law in force; marketing does not become a contractual guarantee.
4. Papers: version/peer review, method/sample/period, actual results, limitations, unjustified causation and transfer to another product. Courses: the lesson/section that is actually accessible.
5. Reddit/X: permalink, author/date and context; only the published message is confirmed, without attributing causes, frequency or fault. If access was not obtained, do not assign verified_as_reported.
6. Read the full text of the chapter for important claims outside the register, contradictions and incorrect generalizations. Re-check the arithmetic when something looks suspicious or the premises are unclear, especially rounding and sources of liquidity. Root separately checks consistency between groups and the links.

## Output for each chapter

- CLAIM_AUDIT.md: a table with a separate row for each claim ID: ID | verdict | independently_read_evidence (URL + exact locator) | checked_scope_and_date | finding/limits. Do not group different IDs in one row.
- SOURCE_AUDIT.md: a separate row for each source ID: ID | original URL | actual access method/status | metadata/version result | scope read/limitations. Do not present a search by title as a check of the original.
- AUDIT.md: summary, date/author, counts, findings with priority and correction, unregistered material facts, limitations and re-check history. At the end, after corrections: final_verdict, open_critical, open_major and SHA-256 of CHAPTER/SOURCES/CLAIMS. Check the actual final text after root's edits.

Allowed claim verdicts: verified (within the exact scope of the primary source), verified_as_reported (only the fact of the statement/declaration is proven), partial (only a part is proven), contradicted (the primary source contradicts it), unverifiable (the original/the relevant fragment was not obtained), non_factual (an explicit hypothesis/normative proposal/synthetic condition, not an external fact). Do not copy the author's confirmed/open/rejected statuses mechanically. Partial/unverifiable does not equal false; if a phrase is honestly bounded, that is a limitation, not necessarily an error. Do not assign verified just because the previous reviewer wrote so.

Critical: an error with a material financial/legal/security consequence. Major: an incorrect mechanism or a significant unproven confident claim. Minor: a local metadata/editorial error that does not change the mechanism. A final reviewed_with_limitations is allowed only with no open critical/major findings after corrections or after the claims are properly bounded. Keep the original finding and its basis, even when it is closed.

Do not introduce a source quota and do not broaden the topic. Check all assigned rows; account honestly for the unavailable ones. The report is not a full legal audit, a replication of research or an operational test.
