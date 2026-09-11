---
id: source-register
title: Source register
type: source
status: approved
confidence: verified
source: this file documents the sources; the inventory itself was compiled 2026-08-26
as_of: 2026-09-11
owner: Tumai (Team OS)
tags: [sources, provenance, register, audit]
---

# Source register

Everything this database was built from, what it covers, how far it can be trusted, and its
date. **Never generate directly from this folder** — it is the quarry the curated files were
cut from and are re-verified against.

## In this repository

| Source | What it is | Authority | Date |
|---|---|---|---|
| `website-scrape/` — 71 markdown files | Clean text extraction of every published page: 9 solution pages, 7 calculators, 6 team bios, 12 partner pages, 20 blog posts, privacy policy, contact, about, home | **Primary.** The client's own published words | Aug 2026 |
| `computed-design-tokens.json` | Live computed CSS captured via Playwright at three breakpoints | **Primary.** Measured, not described | Aug 2026 |
| `sitemap-inventory.json` | Complete route inventory | **Primary** | Aug 2026 |
| `ghl-operational-database-RAW.md` | Pipelines, funnel designs, calendar and AI agent specification | **Mixed** — see below | Aug 2026 |

## Held outside this repository

At `~/Desktop/the-loan-suite-website-scrape/`:

| Source | What it is | Why it isn't committed |
|---|---|---|
| `html/` — 71 raw snapshots | Full markup: navigation, embedded systems, image references | Large, and everything useful is extracted into `01-company/systems-and-ids.md` |
| `assets/` — 110 images | 7 award badges, ~30 lender logos, 2 logo SVGs, 10 team portraits, 12 partner logos | Binary. Referenced by filename in `01-company/brand-and-design-tokens.md` |
| `css/` — 85 stylesheets | Production CSS | Superseded by the computed tokens |
| `screenshots/` — 40 captures | Desktop, tablet, mobile across 10 routes | Binary |
| `DESIGN.md`, `README.md` | Summary documents written during the scrape | **Derived, and contain errors** — see below |

## The GHL operational document — how it is tiered

`ghl-operational-database-RAW.md` mixes two very different kinds of content, and this
database splits them:

| Section | Content | Tier | Landed in |
|---|---|---|---|
| §2 Pipelines | Six pipelines with real stage names from Karlie's live GoHighLevel / Salestrekker configuration | **verified** | [11-operations/pipelines](../11-operations/pipelines.md) |
| §3 Funnels | Two funnel designs | **inferred** — designs, not live systems | [11-operations/funnel-architecture](../11-operations/funnel-architecture.md) |
| §5 Calendars | Routing design | **inferred** — target state. The live booking links are verified separately | [11-operations/calendars-and-routing](../11-operations/calendars-and-routing.md) |
| §6 AI agents | Chat widget and voice agent | **inferred** — designs. No widget exists on the site | [11-operations/ai-voice-and-chat](../11-operations/ai-voice-and-chat.md) |
| §4, §7 | Newsletter and social strategy | **inferred** — proposals | Informed the playbooks in 08 |
| "$50M+ trail book" | An unsourced figure | **assumed — unusable** | [what-we-cannot-claim](../05-proof-and-evidence/what-we-cannot-claim.md) |
| "Redcliffe / Newport offices" | Contradicted by the site | **corrected** to Rothwell QLD and Penrith NSW | [offices-and-contact](../01-company/offices-and-contact.md) |

## Errors found in the derived summary documents

The scrape's own `README.md` and `DESIGN.md` were written as summaries and **disagree with
the primary sources in four places.** In every case the primary source wins:

1. **Team titles.** `README.md` lists Karlie as "Managing Director", Jess as "Senior Broker",
   Phoebe as "Client Concierge". The website says **Commercial & Residential Broker**,
   **NSW Residential Broker**, **Broker Support Officer**. Full table in
   [team](../01-company/team.md).
2. **Awards.** `README.md` lists four Australian Broking Awards and **misses the three
   Specialist Finance Group 2024 badges entirely.** All seven were read directly from the
   badge artwork. See [awards](../05-proof-and-evidence/awards.md).
3. **Typography.** `DESIGN.md` states H3 is Canela Thin at 36–42px. The computed CSS says
   **Stack Sans Text at 24px, weight 400.** See
   [brand-and-design-tokens](../01-company/brand-and-design-tokens.md).
4. **Brand name.** Both documents use "The Loan Suite" (singular). The business is
   **The Loans Suite** / The Loans Suite Australia.

## External research

| Source | Used for | Researched |
|---|---|---|
| MPA / MFAA / Cotality — March 2026 quarter market share | The 81.0% broker market share figure and its supporting detail | 2026-08-26 |
| Public ACL register search — ACL 387025 | Identifying the licensee as Mortgage Specialists Pty Ltd t/a Specialist Finance Group (`inferred`) | 2026-08-26 |
| Australia Post | Confirming Rothwell QLD 4022 | 2026-08-26 |
| aussie.com.au, borro.com.au, lendi.com.au | Competitor teardowns, quoted directly with URLs | 2026-08-26 |

Every external figure is recorded with its source in
[statistics-and-sources](../05-proof-and-evidence/statistics-and-sources.md).

## What no source covers

The gap list that shaped the [enrichment roadmap](../00-start-here/ENRICHMENT-ROADMAP.md):

- **No recorded client calls or transcripts.** Every ICP file is `inferred` as a result
- ~~No CRM export~~ — **closed 11 Sep 2026** by the read-only GHL API pass (IDs and aggregates only)
- **No Google or Facebook review export**
- **No client interview.** Nothing in this database came from Karlie's mouth directly
- **No commercial terms** — no commission rates, no sub-broker split, no partner arrangements
- **No case studies** and no permission status on the five testimonials
- **No campaign history, ad account data or email performance data**

## Added 11 Sep 2026 — client-side sources

**Not committed** where they contain client personal information. They stay in their home systems.

| Source | What it gave | Committed? |
|---|---|---|
| **Granola** — "Tumai & Karlie" 10 Aug · "Data Management – CRM" 18 Aug · "OS Platform" 26 Aug · "OS Meeting TLSGA" 4 Sep · "Tumai Karlie & Michelle" 9 Sep 2026 · Audrey's "The Loan Suite meeting" 9 Sep | Decisions, pipeline and automation requirements, reporting needs, verbatim principal quotes. **Transcripts of 26 Aug, 4 Sep and 9 Sep read in full** | No — client names and deal detail |
| **Gmail (tumai@oscale.ai), tlsga.com.au threads Aug 2025 – Sep 2026** | Pipeline stages (2025), dashboard requirements (2025, 2026), fact find spec, welcome email, SFG integration thread, DNS, forms, 2025 pause, Maryanne introduction | No |
| `TLS_GHL_Lead_to_Retention_Process.pdf` (Karlie, 7 Aug 2026) | Her four-stage target process and GHL setup checklist | **Yes** — `client-documents/tls-ghl-lead-to-retention-brief-RAW.md` |
| `SFGconnect_API_Integration_Checklist_and_Indemnity.pdf` (SFG, 9 Sep 2026) | Integration security requirements and indemnity | **Yes** — `client-documents/sfgconnect-api-checklist-RAW.md` |
| `1. Credit Guide and Privacy Consent.docx` (SFG template v102025) | Credit guide structure, 59-lender panel, referral-fee and privacy disclosures | **Yes** — `client-documents/sfg-credit-guide-template-v102025-RAW.md` |
| `2025 Settlements.xlsx` · `2026 Settlements YTD.xlsx` (Karlie, 4 Sep 2026) | Volume, mix, broker CRNs, data-quality defects | **No** — client names. Aggregates only, in `11-operations/settlement-data-baseline.md` |
| `Dashboard Results.pdf` — Monday.com export, 4 Sep 2026 | The dashboard layout Karlie wants replicated, and its errors | No — described in the reporting requirements |
| **Asana** — "The Loan Suite – Karlie Scharfenberg – Finance OS CRM Onboarding" | Build progress (52/88), Salestrekker stage transcription, form status, phone routing | No |
| **ASIC company extracts** for TLSGA and Queens of Finance (3 Sep 2026, via Asana) | Former name, registered office localities, registration dates | No — summarised in `01-company/licensing-and-entity.md` |
| **GoHighLevel API** — sub-account "The Loans Suite", location `vAX1ry0bjuYiAzEYFS9X`, read-only Private Integration Token (11 Sep 2026) | Location, 15 users, 7 pipelines and 48 stages, 416 opportunities and 1,882 contacts (aggregated), 21 workflows, 25 forms, 4 surveys, 18 calendars with settings, 402 custom fields, 189 tags, 79 custom values, 3 custom objects, 4 knowledge bases, 13 funnels, phone number | **No** — record-level exports contain client PII. IDs and aggregates only, in `11-operations/ghl-account-map.md` and `ghl-data-audit.md`. The token is not stored in the repository |

**Unavailable:** Gmail connectors for the other mailboxes (expired authorisation); Google reviews
(bot-blocked). **The GHL API does not expose** workflow triggers or steps, domain mappings, the
missed-call text-back setting, social accounts or custom menus.

**Correction triggered by the API read:** the meeting-based `current-build-state.md` got the pipeline
structure wrong in several places — approvals and settlements are one pipeline, there is no On Hold
stage, the Clients template holds 282 tiles, and the stage automations are drafts. The file was
rewritten from the API.

**Correction triggered:** the `ghl-operational-database-RAW.md` §2 pipelines were previously treated
as verified. Salestrekker screenshots show that document **embellished stage names and described
automations that weren't running**. `11-operations/pipelines.md` was rewritten from the screenshots.

## Maintenance

- **Re-scrape the site** when it visibly changes, and at least twice a year
- **Re-verify every regulatory and rate-sensitive figure before each publication**, not annually
- **Re-run competitor research annually**, or when a competitor relaunches
- Keep this folder unedited. Corrections belong in the curated files, not here
