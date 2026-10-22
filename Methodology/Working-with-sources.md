---
title: "Sources and claims — schema v0.1"
date: "2026-09-15"
status: "draft"
visibility: "public"
knowledge_as_of: "2026-09-15"
published_on: "2026-09-18"
tags: ["kind/research", "fintech-2026"]
---

> Public edition of 2026-09-18. Verification dates and source limitations are preserved. Hashes in historical audits refer to the original manuscript; public changes and current hashes are in the [edition record](Edition-record.md).

# Sources and claims — schema v0.1

2026-09-15 · private · working editorial standard for this knowledge base.

Goal: from every material claim in a chapter, be able to go to a specific place in a source and understand the limits of its applicability. A list of references at the end of the book does not provide this.

## 1. Two linked registers

A **source** describes a document or post. A **claim** describes what we conclude from it. One document supports several claims; one claim may require several independent documents. Start with two CSVs and Markdown cards; a separate database is not needed at this stage.

### Source register: one row per specific snapshot

| Field | Content |
|---|---|
| `source_id`, `snapshot_id`, `supersedes` | Permanent document ID, for example `SRC-0001`, and a separate snapshot/version ID; a new version does not overwrite the previous one |
| `title`, `author`, `publisher` | Title, author, organization; anything unknown — `unknown` |
| `source_class` | `law`, `regulator`, `scheme`, `standard`, `vendor`, `research`, `course`, `analysis`, `social`, `internal` |
| `document_kind` | For example, law, consultation, FAQ, rulebook, documentation, advertising, working paper, journal article, lecture, post |
| `url`, `canonical_url`, `doi`, `language`, `locale` | Original and canonical link, language/local version; DOI, if one exists |
| `published_at`, `updated_at` | Dates of the source itself, not the date of search indexing |
| `effective_from`, `effective_to` | For rules: entry into force/end; separate from publication; `unknown` and `not_applicable` are allowed |
| `accessed_at`, `date_precision` | Actual reading date with time zone; precision of the source's dates. Keep a relative "7mo ago" literally; the exact day is `unknown` |
| `version`, `status` | Version/commit and draft, adopted, effective, superseded, retracted, preview, GA, etc.; with a link to the confirmation |
| `jurisdiction`, `activity`, `product`, `audience` | Scope; do not assume global applicability |
| `access_status` | `full_text`, `partial_text`, `abstract_only`, `metadata_only`, `blocked`, `removed` |
| `access_method` | `direct_page`, `official_pdf`, `search_index`, `mirror`; do not declare an index/mirror to be a direct reading of the original |
| `reviewed_scope` | What was actually read: the whole short page, specific sections or only the abstract |
| `local_path`, `sha256` | If a copy was lawfully saved; the hash confirms the file, not the truth of its content |
| `rights`, `rights_basis_url` | Separately: storing a copy, quoting, illustrations, distribution; basis/terms. `unknown` does not mean permission |
| `origin_source_id`, `independence_group` | The common primary source of reprints and reposts; different pieces of evidence for one claim may belong to different groups |
| `interests`, `limitations` | Funding, vendor interest, sample limitations, incomplete access |
| `reviewer`, `reviewed_at` | Who checked the card and when |

Do not mix up the type of medium and the evidentiary role: an official company post on X is `source_class=social`, with the official author stated. It is primary for the fact of the company's own announcement, but it is not independent proof of the product's effectiveness.

### Claims register

| Field | Content |
|---|---|
| `claim_id`, `module_ids` | Permanent ID and the modules where the claim is used |
| `claim` | One verifiable claim, without gluing several different conclusions together |
| `claim_kind` | `definition`, `mechanism`, `legal`, `empirical`, `product`, `experience`, `hypothesis` |
| `status` | `confirmed`, `working_hypothesis`, `open`, `rejected`; only within the stated scope |
| `jurisdiction`, `as_of`, `conditions` | Where, when and under what conditions it applies |
| `evidence` | A list of `source_id + snapshot_id + locator + relation + reviewer_note`; relation = supports/contradicts/context |
| `locator` | Article/paragraph of a law, page and section of a PDF, HTML heading/anchor, lecture timecode, URL of a specific post/comment |
| `effective_from`, `effective_to` | If applicable: the dates during which the specific provision is in effect, which may differ from the dates of the document as a whole |
| `reasoning` | How the source supports the claim; our own interpretation is marked separately |
| `confidence_basis` | Why the conclusion can be trusted and what is missing; not an arbitrary percentage |
| `conflicts`, `resolution` | Contradictions, their grounds and an explanation of the editorial decision; check independence by groups of related sources |
| `last_checked_at`, `review_trigger` | Check date and the event after which the conclusion becomes outdated |
| `reviewer`, `review_status` | Review by another agent: pending/checked/needs_revision |

For a simple CSV, long lists can be stored in a linked Markdown card `claims/CLM-0001.md`. Do not introduce extra infrastructure until it is needed.

## 2. How to read different classes

- **Law and regulators:** jurisdiction, the exact subject/activity, the version, the date of entry into force; a consultation and an FAQ are not the same as the law. Financial/legal conclusions for real-world use require a specialist review.
- **Schemes and standards:** document owner, version, region, whether it is mandatory. Mark closed specifications as unavailable; a primer does not replace the technical specification.
- **Company:** documentation and contracts confirm the company's own model as described. Read marketing figures together with their methodology and the author's interest; do not extend them to the whole market.
- **Academic paper:** DOI/version, peer-reviewed or preprint/working paper, research question, data and period, method, result and limitations. Correlation does not become causation. An abstract does not count as reading the paper.
- **Course/lecture:** university/author, program, date, specific lesson and timecode; established mechanisms can be studied from an older course, but current rules must be checked separately.
- **Reddit/X:** permalink, public author, date, context of the thread and comment, whether it is first-hand experience/opinion/announcement. A real case is useful as a question to investigate; popularity and the number of likes do not prove frequency or causation. Note self-selection, advertising and unverified details.
- **Internal research:** trace it back to an external primary source. Text previously generated by an agent is not, by itself, confirmation of a fact.

A myth is a type of claim (`rejected` with an explanation), not a separate source class. Reddit and X are needed where they provide substantive cases; do not introduce a quota of posts for the sake of numbers.

## 3. Unavailability, contradictions and dates

1. Record an unavailable page with its access status. A search snippet is only a reason to look for the original; do not cite it as a document that has been read.
2. With a login/paywall, look for a permitted open original, an author's version, a lecture recording or an alternative primary source. Do not bypass access controls and do not buy a subscription without being instructed to.
3. If an X/Reddit post has been deleted or the text is unavailable, keep the metadata/link and the gap; do not reconstruct the author and the replies from memory.
4. For a contradiction, record both versions, the dates, the scope and the primary source. Do not resolve it by a vote of links: ten reprints are one source.
5. For fast-changing legal and product facts, check the status before releasing each new version of a chapter. The PDF cover shows the cutoff date; the text shows separate dates for legal/product cards.

## 4. What it looks like in a chapter

A significant claim is followed by a clickable footnote `[SRC-0001, §3]` with a direct link. The bibliography gives the title, author/organization, version/publication date, reading date and the specific location. The locator format must match the register.

We write explanations in our own words. Short, necessary quotations are clearly marked; a translated quotation is marked as a translation. We do not reproduce other people's texts, screenshots and illustrations in full without the right to use them. Our own diagram gets the note "compiled from …"; altered numbers are labeled "teaching example", not real figures.

## 5. What is enough to release a chapter

- All key claims have verifiable locations in sources; there are no unexplained conflicts that affect the conclusion.
- Legal and product conclusions are confirmed by a suitable primary source, not just by news or social media.
- For an empirical conclusion, the method and limitations are clear; where possible, there is independent verification. There is no universal rule of "exactly N references".
- Real sources and teaching/hypothetical cases are clearly distinguishable.
- A reviewer has checked that the claims match the sources. The author does not give themselves independent approval.
- Missing materials are shown as gaps, not as completed content.
