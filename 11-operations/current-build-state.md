---
id: current-build-state
title: Current build state — what exists in the OS sub-account
type: system
status: approved
confidence: verified
source: Granola meetings 10 Aug, 18 Aug, 26 Aug, 4 Sep and 9 Sep 2026; tlsga.com.au email threads Aug–Sep 2026; Asana project "The Loan Suite - Karlie Scharfenberg - Finance OS CRM Onboarding" (read 2026-09-11). The GHL sub-account itself was NOT read — no access token was available.
as_of: 2026-09-11
owner: Tumai (Team OS)
tags: [operations, os-platform, ghl, build-state, onboarding, internal]
---

# Current build state

> **How this was reconstructed.** Everything here comes from what the team said in meetings,
> what was sent by email, and the Asana onboarding board. **Nobody has read the live
> sub-account through the API yet.** Treat stage names and counts as "as described on
> 9–10 Sep 2026" and re-verify the moment GHL access exists. Items marked *(observed)* were
> seen on screen during a recorded call.

**Internal only.** Nothing in this file is marketing material.

## The platform

- **OS = GoHighLevel, white-labelled** as the Team OS platform. Login `app.teamos.ai`;
  hosted widgets on `link.teamos.ai`. TLS is a sub-account named **"The Loans Suite"**.
- Karlie also opened a **separate, empty GoHighLevel trial account** in Aug 2026. Decision
  (10 Aug): cancel it and recover the charge. It holds nothing.
- Billing was to switch from annual to monthly before the next cycle (10 Aug action).

## Engagement timeline

| When | What happened |
|---|---|
| Aug–Sep 2025 | First engagement. Pipeline stages built, contact list (~2,000 rows) merged and tagged **"TLS Loan Book"** / **"QOF Loan Book"**, AI chat widget trained on the website, intranet set up for Jess |
| 20 Oct 2025 | Paused at Karlie's request for 4–5 months — SFG was consolidating systems at the end of December and TLS was hiring |
| Late 2025–mid 2026 | Karlie went down a **Monday.com** path (~$8K spent, limited results) and resolved a legal dispute over her trail and client database |
| 7 Aug 2026 | Karlie restarts: wants workflows built "the same as you have done for Maryanne" before any customer data moves |
| 10 Aug 2026 | Planning session. Fresh onboarding project opened |
| 18 Aug → 9 Sep 2026 | Data migration, pipelines, forms, phone, domains, calendars, automation planning |

## Pipelines in OS — "locked" as at 10 Sep 2026

Asana, 10 Sep: *"Pipelines have all be delivered and locked down."*

| Pipeline | Status |
|---|---|
| **Pre-Submission** | Live. Stage order still being finalised — see [pipeline-decisions-log](pipeline-decisions-log.md) |
| **Approvals** | Live |
| **Settlements** | Live |
| **Post-Settlement** | Live. Contains duplicate tiles from migration |
| **Construction Loans** | Live |
| **Clients** | Pre-built template. Karlie and Michelle to confirm deletion — it duplicates post-settlement |
| **Lead Gen** / **Qualification** | Left in place, **parked**, out of scope for now |

The legacy Salestrekker pipelines these were modelled on are in [pipelines](pipelines.md).

## Forms and surveys

| Asset | State |
|---|---|
| **"Speak with a Broker" booking widget** | Built 27 Aug. Automation live: completion tags the contact and adds them to the pipeline. Waiting on Dylan to embed on the website |
| **Short fact find** (form) | Built 2 Sep. Review notes: no "next of kin" in AU practice; liabilities need amount, term, rate, repayment; assets were missing |
| **Full fact find** (10-page survey) | Built 3 Sep in TLS design tokens. Includes second employment, self-employment, and terms of engagement. **Mandatory fields not yet set.** Dylan prefers a direct link over DNS to an iframe |
| **Pre-approval document collection** form | Built 2 Sep |
| Website, advertisement, referral and event lead forms | Listed as sub-tasks; no evidence they are finished |

Karlie's fact find field list is in [automation-requirements](automation-requirements.md).

## Automations

- **Stage automations were imported with the pipelines.** Warning given on 26 Aug: dragging a
  card between stages fires them immediately. The team needs to know what is active before
  going live.
- **Lead ingestion automation** (form → contact + opportunity → confirmation) built 27 Aug.
  Asana note: *"No qualification or lead scoring setup."*
- **Missed-call text-back is live.** Verbatim SMS: *"Hi this is The Loans Suite, I saw that we
  just missed your call how can I help?"*
- **Instagram keyword DM automation** (a ManyChat replacement; keyword e.g. "lending" →
  reply → capture name and mobile → send lead magnet) is **built but not connected** to TLS's
  Instagram.
- A **stage-by-stage automation planning tool** was built by Tumai and shared on 9 Sep.
  Michelle and Karlie are filling in triggers, goals and steps — **due close of business
  Friday 11 Sep 2026**.

## Calendars and booking

- Outlook connected for most of the team by 7 Sep; **Kaiden outstanding** (on leave, back
  Wed 16 Sep).
- Teams video conferencing needs Microsoft admin approval via TLSGA's IT provider
  (**Trisarmi**), which charges roughly **$55 per call**. Plan: approve the whole team in one
  session.
- Per-broker booking types to configure: **online, phone, face-to-face** (office address).
  **Jess (NSW)** gets a **mobile / travel-to-client** option. A **round-robin** calendar with a
  staff dropdown is planned.
- Asana "Calendar(s) Setup" still open, due 11 Sep.

The live booking links and the routing gap are in
[calendars-and-routing](calendars-and-routing.md).

## Phone and SMS

- A new number was purchased after an ASIC-document regulatory bundle was approved.
- **Forwarding to the 1300 number does not work** — calls go to voicemail. GHL may not support
  forwarding to 1300 toll-free numbers (feature request open). Interim: forwarding to the
  Penrith landline, which connected. Follow-up task open.
- SMS cost quoted to the client as a fraction of a cent per message; can be disabled.
- An IVR / AI call-answering agent was floated and **deferred**.

## Domains — all four verified 8 Sep 2026

| Subdomain | Purpose |
|---|---|
| `os.tlsga.com.au` | Mailbox / sending |
| `discover.theloanssuite.com.au` | Pages and funnels |
| `app.theloanssuite.com.au` | Client portal |
| `client.theloanssuite.com.au` | Branded links |

DNS is controlled by **Dylan Kemp** (BrokerKit).

## Data migration

- Salestrekker only allowed an **all-or-nothing export** of contacts and opportunities, so the
  data was cleaned row by row. ~5% of opportunities failed first upload and were fixed.
- **Stages did not map cleanly.** Unmatched deals were parked in **On Hold** for Karlie and
  Michelle to move.
- **Duplicate tiles exist** — some clients came in twice (one "retention", one named). Rule
  agreed: one opportunity per client in post-settlement; delete the duplicate.
- **Kaiden's broker KPI data was missing** after migration; re-import task closed 5 Sep.
- Contact count seen on screen varied: **1,877** (26 Aug) and **1,118** (4 Sep) *(observed)*.
  Unreconciled — verify via API.
- Pending: Karlie to send **2025 and 2026 YTD settled loans** in one dedicated email titled
  "Migration" for import into the Settled stage. Two workbooks arrived on 4 Sep — see
  [settlement-data-baseline](settlement-data-baseline.md).
- Scope decision (18 Aug): **don't import 10 years of history.** Start from the Salestrekker
  retention workflow (the active trail book) as the live client base.

## Fields, boards and lists

- Custom contact and opportunity fields built from the fact find: identity, household,
  dependants, loan requirements, property and security, loan structure, deal metrics.
- **Broker KPI board** in OS, filtered by broker, used by Michelle from 8 Sep. Commission
  split percentages are set too high and need correcting.
- **"Referred by"** field on opportunities and **"How did you hear about us?"** on contacts.
- Referral partners are uploaded as tagged contacts with a smart list, not a separate board.
- **Mentor deals** (Jess's and Kaiden's mentoring obligation) tracked by tag: broker, amount,
  mentor status. Internal KPI only.

## Team access and rollout

Rollout order agreed: **Michelle and Emily first**, then Jess and Kaiden. Training videos live
in the platform's "Base" / "Start Here" academy. Karlie wants a **test client** run through
before go-live. A WhatsApp group (Karlie, Michelle, Ariki, Tumai) handles quick questions.

## Onboarding progress — Asana, 11 Sep 2026

**52 of 88 tasks complete.** Done: payment, prep, workspace, branding, kickoff, most core
setup, contacts migration, custom fields, tags, email, domains, phone number, pipelines,
database, design system.

**Still open:** Forms & Surveys · Automation · Newsletter · Salestrekker pipelines ·
Calendar setup · Custom settings · Install tracking tools · Verify form routing · Enable live
chat · Validate lead tagging · Confirm ad tracking · **every "Automations Active" task**
(review workflows, triggers and timing, test email/SMS, simulate lead flow, enable AI agent) ·
**every QA task** · **every go-live task**.

## Open issues worth carrying into the pipeline design

1. **Contact-first vs deal-first confusion.** Michelle lost a tile and found a "retention" duplicate.
2. **Salestrekker's retention workflow is organised as month columns (Jan–Dec)** holding 45–60
   clients each. OS replaces that with date-triggered tasks, and Michelle needs a look-ahead
   view, not just day-of tasks.
3. **US date picker** annoys staff; a backend setting is to be changed.
4. **Relationship links** (spouse, company directors) need a custom field under the contact.
5. **"Referred by" carries two meanings** — see [pipeline-decisions-log](pipeline-decisions-log.md).
6. **Website form still posts to Salestrekker**, not OS, until Dylan switches it.

## Related

- [pipeline-decisions-log](pipeline-decisions-log.md) · [automation-requirements](automation-requirements.md)
- [reporting-and-dashboard-requirements](reporting-and-dashboard-requirements.md)
- [sfg-salestrekker-integration](sfg-salestrekker-integration.md) · [systems-and-ids](../01-company/systems-and-ids.md)
