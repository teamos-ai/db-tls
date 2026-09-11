---
id: current-build-state
title: Current build state — what exists in the OS sub-account
type: system
status: approved
confidence: verified
source: GoHighLevel API, read-only, location vAX1ry0bjuYiAzEYFS9X (11 Sep 2026) — pipelines, opportunities, workflows, forms, surveys, calendars, users, fields, tags, objects, phone, funnels, knowledge bases. History, domains, rollout and anything the API cannot see from Granola meetings 10 Aug – 9 Sep 2026, tlsga.com.au email and the Asana onboarding board.
as_of: 2026-09-11
owner: Tumai (Team OS)
tags: [operations, os-platform, ghl, build-state, onboarding, internal]
---

# Current build state

> **Read from the live sub-account on 11 Sep 2026.** The first version of this file was
> reconstructed from meetings and got several things wrong — see "What the meetings got wrong".
> Items marked *(meetings)* can't be seen through the API. IDs are in
> [ghl-account-map](ghl-account-map.md); data quality is in [ghl-data-audit](ghl-data-audit.md).

**Internal only.** Nothing here is marketing material.

## The platform

- **OS = GoHighLevel, white-labelled.** Login `app.teamos.ai`. Sub-account **"The Loans Suite"**,
  location `vAX1ry0bjuYiAzEYFS9X`, created **11 Aug 2025**, timezone **Australia/Brisbane**.
- **15 users:** the 7 TLS staff, Dylan Kemp, and 7 Team OS logins. 13 are admins.
- Karlie's separate empty GoHighLevel trial: decision 10 Aug was to cancel it *(meetings)*.

## Engagement timeline

| When | What happened |
|---|---|
| Aug–Sep 2025 | First engagement. Sub-account created 11 Aug 2025; appointment reminder recipe published; chat widget test page; contacts tagged "TLS Loan Book" / "QOF Loan Book" *(those tags no longer exist)* |
| 20 Oct 2025 | Paused at Karlie's request — SFG consolidating systems, TLS hiring |
| Late 2025–mid 2026 | Monday.com path (~$8K, limited results); legal dispute over trail and database resolved *(meetings)* |
| 7–10 Aug 2026 | Restart and planning session |
| 25 Aug 2026 | **Bulk migration** — 282 Clients and 91 Post Settlement tiles created that day |
| 18 Aug → 9 Sep 2026 | Pipelines, forms, phone (4 Sep), domains (8 Sep), calendars, automation planning |

## What the meetings got wrong

| Described in meetings or Asana | Live account, 11 Sep 2026 |
|---|---|
| Separate Approvals and Settlements pipelines | **One pipeline — "2 \| Approval - Settlements"** |
| Unmatched deals parked in **On Hold**; On Hold for deals being shaped | **No On Hold stage exists** in any pipeline |
| "Clients" template to be deleted | **It holds 282 migrated tiles** — 225 in Retention & Repricing, 57 in General / Active. Deleting it loses them |
| Lead Gen / Qualification pipelines parked | **Neither exists.** A template "Marketing Pipeline" and an empty "Partners" pipeline do |
| Post-settlement 30-day · 90-day · 6-month · 12-month | **Three stages**, and 88 of 91 tiles sit in the first |
| Stage automations imported — dragging a card fires them | **Both stage workflows are drafts.** 2 of 21 workflows are published |
| Contact count 1,877 or 1,118 | **1,882** |
| Commissions stay in Excel | **The Broker KPI's object holds 54 commission records** |
| Calendars with online / phone / face-to-face options | Six live calendars, **none with a meeting location**, no notifications, no round-robin |
| A "Referred by" field on opportunities | **No opportunity field of that name.** "Referred By" is on the **Broker KPI's** object (filled on 5 of 54) |

## Pipelines — live

| Pipeline | Stages | Opps |
|---|---|---|
| **1 \| Pre-Submission⚡️** | New Lead → Credit Guide Sent → Initial Conversation → Fact Find → Document Collection → Quickli/Servicing → Deal Qualifies → Pushed to Sales Trekker | 7 open |
| **2 \| Approval - Settlements 💰** | Submitted / MIRS → Conditional Approval → Formal Approval → Docs Issued → Settlement Booked → Settled → Audit | 23 — 16 open · 5 lost · 2 won |
| **3 \| Post Settlement** | 30-Day Post-Settlement Check In → Annual Review / Check-Ins → Year Review / Check-Ins | 91 — 89 open · 2 won |
| **4 \| Construction Loans** | Salestrekker's ten construction stages, copied exactly | 11 open, none valued |
| **5 \| Clients 🫶** *(template)* | General / Active → First 3-Month Check-In → Annual Review / RBA Check → Mid-Term Refinance Opportunity → Life Event Trigger → Retention & Repricing → Referral Loop → 5-Year+ Milestone Review | 282 open |
| **6 \| Partners 💎** *(template)* | Leads → Follow Up → New Users → Active Users → New Partners → Active Partners | 0 |
| **Marketing Pipeline** *(template)* | New Lead → Contacted → Qualified → Proposal Sent → Negotiation → Closed | 2 |

- **Pre-Submission** matches Karlie's 9 Sep read-out for stages 1–5, then adds servicing,
  qualification and the Salestrekker hand-off. **Settled deals live in pipeline 2**, not in
  Pre-Submission.
- **Post Settlement's** stages 2 and 3 appear to mean the same thing.
- *Design observation (`inferred`):* the **Clients template's** stages — 3-month check-in, annual/RBA
  review, mid-term refinance, life event, repricing, referral loop, 5-year review — sit closer to the
  9 Sep hybrid retention-and-advocacy lifecycle than the purpose-built Post Settlement pipeline does.
- Stage names mix numbering styles ("1.", "1 |", "13 | Audit") and spell Salestrekker "Sales Trekker".

## Automations — 21 workflows, 2 published

| Workflow | Status | Last saved |
|---|---|---|
| Form to Deal Automation | **published** | 27 Aug 2026 (v5) |
| Recipe - Appointment Confirmation + Reminder | **published** | 25 Sep 2025 (v4) — 2025 engagement |
| Pre-Submission⚡️ | draft | 27 Aug 2026 (v9) |
| Approval - Settlements 💰 | draft | 9 Sep 2026 (v4) |
| Karlie Scharfenberg \| Discovery Call Automation💰 | draft | 27 Aug 2026 (v14) |
| 16 Team OS template workflows (001–013, Partners OS 1–3) | draft | untouched since 11 Aug 2025 |

- **No workflow exists** for Post Settlement, Construction, credit guide signing or retention.
- **The API doesn't expose triggers or steps.** "Form to Deal" is described as form → contact +
  opportunity → confirmation, with no lead scoring *(meetings, 27 Aug)*.
- **Missed-call text-back** is reported live *(meetings)* but is not one of the 21 workflows — most
  likely the phone number's own setting. Not API-verifiable.
- **Instagram keyword DM:** "built, not connected" *(meetings)*. No TLS-named workflow matches; the
  template "001 | IG Comments & DM's" is the likely base (`inferred`).
- **No SMS or email templates** exist. All 15 email-builder folders are Team OS template sets, so
  Karlie's welcome email isn't in the account yet. 0 campaigns.
- Stage-by-stage automation planning tool with Michelle and Karlie, due COB Fri 11 Sep *(meetings)*.

## Forms and surveys

| Asset | Live state |
|---|---|
| **Speak with a Broker** (form) | Exists. Website embed waiting on Dylan; the website form still posts to Salestrekker *(meetings)* |
| **Fact Find** — 10 forms, "01 Applicant details" → "10 Consent and declaration" | Exist. 2 contacts have come through form 01 |
| **Full Fact Find** (survey) and **Full Fact Find - Duplicate** | Both exist. 1 contact through the survey. **The form series and the survey overlap — pick one** |
| Fact Find Form \| Short Form · 01 Primary Identification | Exist |
| 12 template forms, 2 template surveys | Team OS clutter |

Mandatory fields not yet set *(meetings, 3 Sep)*. **The fact find's privacy consent names Queens of
Finance and hardcodes CRN 477350**, and **no contact has any credit guide or consent field
recorded** — see [ghl-data-audit](ghl-data-audit.md).

## Calendars

**Six active**, one each for Karlie, Kaiden, Jess, Michelle, Emily and Reema; 12 inactive template or
staff calendars. **No round-robin calendar is active.** Settings and defects:
[calendars-and-routing](calendars-and-routing.md).

Outlook sync is connected for most of the team, with Kaiden outstanding until 16 Sep. Teams needs Microsoft admin approval via
Trisarmi, at ~$55 per call *(meetings)*.

## Phone and SMS

- **+61 485 088 933** — mobile, SMS/MMS/voice, the default number, added 4 Sep 2026, labelled
  "The Loan Suite". **Forwards to the Penrith landline (02 4733 4417)** — the interim fix, confirmed.
- Forwarding to the 1300 number fails (GHL toll-free limitation); IVR/AI answering deferred *(meetings)*.

## AI, funnels and domains

- **4 knowledge bases**: "The Loans Suite" (updated 7 Sep 2026), "Updated TLS KB" (28 Aug 2026), two
  older "Existing knowledge base" sets. A "Test The Loan Suite Custom Chat Widget" page exists (Sep 2025).
- **13 funnels/sites:** 11 Team OS templates, the chat-widget test page, and an **empty site named
  "www.theloanssuite.com.au" (0 pages)**. **No TLS funnel or landing page has been built.**
- **79 custom values, all empty** template placeholders; **22 trigger links**, all template.
- Domains verified 8 Sep *(meetings — mappings aren't API-readable)*: `os.tlsga.com.au` (mailbox) ·
  `discover.theloanssuite.com.au` (pages) · `app.theloanssuite.com.au` (portal) ·
  `client.theloanssuite.com.au` (branded links). DNS controlled by Dylan Kemp (BrokerKit).

## Data migration — what actually landed

- **1,882 contacts** (1,866 added Aug 2026) and **416 opportunities** (403 created Aug 2026).
- Salestrekker allowed only an all-or-nothing export; data cleaned row by row; ~5% failed first
  upload *(meetings)*. Scope: active trail book, not 10 years of history (18 Aug).
- **69 clients have a tile in both Post Settlement and Clients.** The one-tile rule (4 Sep) isn't applied.
- **The 302 settlements in Karlie's two workbooks aren't imported** — Settled holds 9.
- **`Date Settled` is empty on every opportunity**, so no retention task can be generated from it.
- **Karlie owns 88% of opportunities**; 37 are unassigned.

Detail and fix order: [ghl-data-audit](ghl-data-audit.md).

## Fields and objects

- **402 custom fields** — 275 contact, 92 opportunity, 35 across custom objects. The fact-find field
  set is complete; the opportunity deal fields are well designed but **77 of 92 are empty on every
  opportunity**.
- **Custom objects in use:** Staff & Brokers (7 records), TLS Mentoring (53), Broker KPI's (54).
  Michelle has used the KPI board since 8 Sep; commission split percentages are set too high *(meetings)*.
- Referral partners as tagged contacts with a smart list *(meetings)*.

## Team access and rollout

Rollout order: **Michelle and Emily first**, then Jess and Kaiden. Training in the platform's
"Base" / "Start Here" academy. Karlie wants a **test client** run end to end before go-live. A
WhatsApp group (Karlie, Michelle, Ariki, Tumai) handles quick questions *(meetings)*.

## Onboarding progress — Asana, 11 Sep 2026

**52 of 88 tasks complete.** Still open: Forms & Surveys · Automation · Newsletter · Salestrekker
pipelines · Calendar setup · Custom settings · tracking tools · form routing · live chat · lead
tagging · ad tracking · **every "Automations Active", QA and go-live task**.

## Open issues to carry into the pipeline design

1. **Retention has two homes.** Post Settlement (3 stages, 91 tiles) and Clients (8 stages, 282
   tiles), with 69 clients in both. Pick one and merge.
2. **No hold or not-proceeding path.** No On Hold stage, and **0 of 416 opportunities carry a lost
   reason** — the "Not Proceeding Reason" picklist exists but is unused.
3. **Stage automations exist only as drafts** — the design can start clean.
4. **Back-fill `Date Settled`** before any retention automation.
5. **Calendars** need meeting types, notifications and a round-robin.
6. **Contact-first vs deal-first confusion** — Michelle's lost tile is explained by the duplicates.
7. US date picker; a relationship-link field for spouses and directors; "Referred by" carrying two
   meanings *(meetings)*.
8. **Website form still posts to Salestrekker** until Dylan switches it.

## Related

- [ghl-account-map](ghl-account-map.md) · [ghl-data-audit](ghl-data-audit.md)
- [pipeline-decisions-log](pipeline-decisions-log.md) · [automation-requirements](automation-requirements.md)
- [reporting-and-dashboard-requirements](reporting-and-dashboard-requirements.md)
- [sfg-salestrekker-integration](sfg-salestrekker-integration.md) · [systems-and-ids](../01-company/systems-and-ids.md)
