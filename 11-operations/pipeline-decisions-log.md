---
id: pipeline-decisions-log
title: Pipeline decisions log — what was decided, when, and in whose words
type: system
status: approved
confidence: verified
source: email "Pipeline Stages" (Karlie, 19 Aug 2025); Karlie's brief "TLS GHL Lead to Retention Process" (7 Aug 2026); Granola transcripts 26 Aug, 4 Sep and 9 Sep 2026; Granola notes 10 Aug and 18 Aug 2026; Ariki's summary email 18 Aug 2026; Asana transcription of Salestrekker pipelines (19 Aug 2026); live build state from the GoHighLevel API (read-only, 11 Sep 2026)
as_of: 2026-09-11
owner: Tumai (Team OS)
tags: [operations, pipelines, decisions, stages, design-input, internal]
---

# Pipeline decisions log

The raw material for designing the dream pipeline. Decisions are listed in order, because
several were later reversed — **the latest entry on a topic wins**, and the superseded ones are
kept so nobody re-proposes them by accident.

---

## The three versions of "the pipeline" that exist

| Version | Source | Status |
|---|---|---|
| **A · Salestrekker as-is** | Screenshots transcribed 19 Aug 2026 | The real legacy system. See [pipelines](pipelines.md) |
| **B · Karlie's "minimal" ideal** | Email, 19 Aug 2025 | Superseded by C, but shows her instinct |
| **C · The OS build** | Meetings 26 Aug – 9 Sep 2026; **live account read 11 Sep 2026** | Current. Differs from what the meetings described — see "Live state vs the decisions" and [ghl-account-map](ghl-account-map.md) |

### B · Karlie's minimal ideal (19 Aug 2025)

> Ideally we can minimise the workflows to be like this

`Application → Prelim Issued → AOL → Submitted / MIRS → Conditional Approval → Formal Approval →
Docs Issued → Settlement Booked → Settled → Audit`

Ten stages, one pipeline, lender-process vocabulary. It starts at "Application" — nothing
before the application exists in it.

### Karlie's brief (7 Aug 2026)

A four-stage process flow she commissioned before restarting:

1. **Lead capture and qualification** — lead enters GHL · auto-tag and instant reply
   **within 60 seconds** · lead scoring · broker assigned by **round robin**
2. **Nurture to application** — booking link sent · discovery call · fact find sent ·
   pre-approval docs requested via secure upload checklist · application submitted. *If a lead
   misses the call or isn't ready, a nurture drip re-offers the booking link.*
3. **Settlement to retention loop** — lodged in GHL · synced to Salestrekker · settled in
   Salestrekker · client profile returns to GHL · **post-settlement tag triggers retention**
   (anniversary, review, referral)
4. **Broker performance and commission tracking** — settled and tagged · tiered commission
   calculated · KPI dashboard · quarterly review report to broker and director

Full text: [tls-ghl-lead-to-retention-brief](../99-source-material/client-documents/tls-ghl-lead-to-retention-brief-RAW.md).
**Several of its assumptions were later overturned** — see "Reversals" below.

---

## Decisions, in order

### 10 Aug 2026 — scope
- **OS is customer-centric; Salestrekker stays deal-centric for home loans only.**
  **Commercial and asset finance live entirely in OS.**
- Build order: migration → pipelines, forms, automations → client portal later.
- Pre-approval document collection with reminders, post-settlement loop, and broker KPI
  tracking were all in the original scope.

### 18 Aug 2026 — data model
- **Contact-first architecture.** Every pipeline and dashboard builds up from the contact.
  Monday.com couldn't trigger off contacts, which broke its reporting.
- **Trail income and commissions stay in Excel**, managed by Michelle. *(Conflicts with the
  brief's commission workflow and the OS KPI board's commission fields — unresolved.)*
- **Fresh start:** load the active trail book (Salestrekker retention 2.0), not 10 years of history.
- End-state vision: OS captures and qualifies → deals enter Salestrekker already serviced and
  documented → settled status loops back → post-settlement tasks at **30 days, 6 months, 12 months**.

### 26 Aug 2026 — the flow, in Karlie's words
> Lead comes in, then the next stage would be customer contacted… then you would then have
> gathering documents, fact find sent out to clients… the next stage then is like client
> qualified. And that stage is, that gets moved into sales tracker. Otherwise… client doesn't
> qualify, goes on to hold for three months or six months until they do qualify or goes into,
> like, the dead, the dead basket.

> I don't want in sales tracker all of the clients that are not even leading like what we've
> got now. Like all of these on holds all need to be closed off because they're not going
> anywhere.

**Decision:** everything before qualification happens in OS; **Salestrekker only receives deals
that will be submitted.** A non-qualifying client goes to a 3- or 6-month hold, or is closed as dead.

On retention, Karlie at the time:
> The retention workflow we've got in sales tracker is deal based. This is customer based. So
> that information is going to be in the customer tile anyway. So it's possibly not even
> something that we need in OS.

*(Reversed on 9 Sep — a post-settlement pipeline is wanted.)*

### 4 Sep 2026 — lean stages, tags, one tile per customer
Agreed Pre-Submission sequence *(Granola summary)*:
`New Lead → Initial Conversation → Fact Find Sent → Fact Find Received → Document Collection →
Deal Qualifies → Submit to Sales Tracker → Settled`

Principles set in that call:
- **Lean stages.** *"Every stage dictates an automation."* Add a stage only for a real
  customer-journey milestone.
- **One OS tile per customer or couple.** Two Salestrekker deals can map to one OS tile, with
  notes naming each deal. Karlie: *"Think OS is the customer. Think sales tracker is the deal."*
- Don't force a two-loan customer's tile to one stage — move it when it makes operational sense.
- **Two note levels.** Contact notes for non-deal interactions; deal notes for deal activity.
- **Master tag list defined by Karlie, locked, no improvised variants** ("refi" vs "refinance"
  silently splits reports).
- **All brokers use the intake form** as the single entry point, even for back-of-a-napkin calls.
- Colour-coding by loan type (Salestrekker habit) is replaced by **saved list views** per type.
- Probability percentages per stage to be set by Team OS (New Lead ~1%, AOL submission ~90%).
- **Future pipelines flagged:** marketing / lead gen, and referral / post-settlement retention.

### 9 Sep 2026 — credit guide becomes a stage; retention becomes a lifecycle
Karlie's OS Pre-Submission as read out on the call:
`New Lead → Credit Guide Sent → Initial Conversation → Fact Find → Document Collection`

Then, per the automation walkthrough:
- **Servicing** — no automation; manual in Quickli.
- **Document Collection** — manual requests; no reminder sequence for now.
- **On Hold** — parking while a deal is shaped or placed.
- **Credit Guide Sent** — its own stage; the tile cannot leave until the guide is signed.

Karlie on client communication:
> I don't want clients notified every single time the tile moves along just the milestones.

Post-settlement redesigned as a **hybrid retention + advocacy pipeline**: **30-day broker call →
90-day check-in → 6-month SMS → 12-month review**, plus review, video testimonial and referral
asks, and a pre-emptive rate review "before they think to shop around". Tasks are generated off
the **settlement date**, replacing Salestrekker's month columns.

The "Clients" template pipeline is likely to be deleted. *(The API later showed it holds 282
migrated tiles — it can't be deleted without a merge.)*

---

## Live state vs the decisions — API read, 11 Sep 2026

What was decided, against what the sub-account actually contains. IDs in
[ghl-account-map](ghl-account-map.md); data detail in [ghl-data-audit](ghl-data-audit.md).

| Decision | Built? |
|---|---|
| Lean Pre-Submission (4 Sep, 9 Sep) | **Yes, 8 stages:** New Lead → Credit Guide Sent → Initial Conversation → Fact Find → Document Collection → Quickli/Servicing → Deal Qualifies → Pushed to Sales Trekker |
| Credit guide as its own gated stage (9 Sep) | **Stage exists; the gate doesn't.** The stage workflow is a draft |
| On Hold stage (9 Sep); 3- and 6-month holds (26 Aug) | **Not built** |
| Approvals and Settlements | **One pipeline**, "2 \| Approval - Settlements", ending at Audit |
| Hybrid post-settlement lifecycle, 30d · 90d · 6m · 12m (9 Sep) | **Not built.** Post Settlement has 3 stages; the Clients template is closer |
| Delete the Clients template (9 Sep) | **Can't yet** — it holds 282 migrated tiles |
| One OS tile per customer (4 Sep) | **Not applied** — 79 contacts hold more than one; duplicates allowed |
| Master tag list, locked (4 Sep) | **Not applied** — 189 tags, `rfi` vs `refinance` |
| Milestone-only client comms (9 Sep) | **Nothing sends yet** — no client-comms workflow is published |
| Manual settlement update in OS (26 Aug – 4 Sep) | **Not started** — `Date Settled` empty on all 416 |
| Commissions stay in Excel (18 Aug) | **Contradicted** — Broker KPI's object holds 54 commission records |

---

## Reversals — don't re-propose these

| Earlier position | Replaced by | When |
|---|---|---|
| Automated doc-chasing reminder sequence | **Manual requests** (*"I might change my mind in six months"*) | 9 Sep |
| No retention pipeline needed in OS | **Hybrid post-settlement lifecycle pipeline** | 9 Sep |
| Settlement data flows back from Salestrekker automatically | **Manual update in OS** from the bank's settlement email — SFG won't allow data out | 26 Aug – 4 Sep |
| Fact find sent at first contact | **Fact find after the initial conversation** | 4 Sep |
| Credit guide attached to the welcome email only | **Its own stage**, signed before anything else proceeds | 9 Sep |
| 30 / 60 / 90-day post-settlement | **30-day call · 90-day check-in · 6-month SMS · 12-month review** | 9 Sep |
| Lead scoring at intake (brief, Stage 1) | **Not built**; measurement requirements not yet confirmed | 27 Aug |
| Automated tiered commission workflow (brief, Stage 4) | **Commissions stay in Excel** (18 Aug) — but the KPI board has commission splits (9 Sep). *Unresolved* | — |

---

## Open design questions for the dream pipeline

1. **Where does Pre-Submission end?** "Deal Qualifies → Submit to Sales Tracker → Settled" (4 Sep)
   was the plan. *As built (API, 11 Sep):* it ends at "Pushed to Sales Trekker", and settled deals
   live in "2 | Approval - Settlements". Confirm that's the design, not an accident of the build.
2. **Stage order: credit guide before or after the initial conversation?** SFG wants it signed
   at first interaction; Karlie says it must be signed before submission and before payslips.
3. **One pipeline or audience-specific paths?** Karlie's first home buyers want updates;
   commercial clients must not be bombarded. Tumai suggested separate pipelines per audience.
4. **Stage-gated checklists:** Salestrekker's prelim stage has ~9 items and *"nothing moves ahead
   to the next stage until the checklist is completed."* Enforce in OS, or task-based?
5. **"Referred by" means two things.** Michelle enters the *broker who brought the loan in*;
   Ariki's spec says the *referring client's name*. Needs two fields. *Live:* "Referred By" exists
   only on the Broker KPI's object (5 of 54 filled). The contact's "Referral Source", "Who referred
   you?" and "Where did you hear about us?" are empty on every contact.
6. **Hold and dead:** 3-month / 6-month re-qualification holds and a "deadpool" were described on
   26 Aug. **No stage exists — confirmed by the API** — and no opportunity carries a lost reason.
7. **Commissions:** in the CRM or not? *In practice, yes* — the Broker KPI's object holds 54
   commission records.
8. **Pre-approval lifecycle (30/60/75/expired) and construction drawdowns** exist in
   Salestrekker. Construction was rebuilt in OS stage for stage; **no pre-approval stage or pipeline
   exists**.
9. **Marketing / lead-gen pipeline** for the cold list, lead magnets and Instagram DMs — parked. A
   template "Marketing Pipeline" holds 2 test tiles.
10. **Where does retention live?** Post Settlement (3 stages, 91 tiles) or the Clients template
    (8 lifecycle stages, 282 tiles)? 69 clients are in both.
11. **Clean the migrated data before or during the redesign?** Duplicates, empty settlement dates,
    ownership and tags all block automations — see [ghl-data-audit](ghl-data-audit.md).

## Related

- [current-build-state](current-build-state.md) · [automation-requirements](automation-requirements.md)
- [pipelines](pipelines.md) — the legacy Salestrekker structure
