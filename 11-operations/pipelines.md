---
id: pipelines
title: Legacy Salestrekker pipelines — the verified stage structure
type: system
status: approved
confidence: verified
source: Tumai's transcription of Salestrekker pipeline screenshots, posted to Asana task "⚡ Pipelines" on 19 Aug 2026; Karlie's "Pipeline Stages" email (19 Aug 2025); Granola transcripts 4 Sep and 9 Sep 2026. Corrected 2026-09-11 against the earlier GHL planning document.
as_of: 2026-09-11
owner: Karlie Scharfenberg
tags: [operations, pipelines, salestrekker, legacy, stages, internal]
---

# Legacy Salestrekker pipelines

The pipelines TLS actually ran in Salestrekker (SFG v2) before the OS build. **This is the
as-is baseline** for designing the dream pipeline. The current OS build is in
[current-build-state](current-build-state.md); decisions since are in
[pipeline-decisions-log](pipeline-decisions-log.md).

> **Internal only.** Stage names are the team's own, including informal ones. "The Shitshow" is a
> real stage name and must never appear in anything client-facing.

> **Correction, 11 Sep 2026.** An earlier version of this file was built from the
> `ghl-operational-database-RAW.md` planning document. Checked against the stage names Tumai
> transcribed directly from Salestrekker screenshots, **that document embellished**. It added
> stages (e.g. "Contact Made / Discovery Booked"), merged others, and described automations —
> "5-minute SMS", "celebration SMS", "settlement gift" — **that were never observed running**.
> The stage lists below are the verified ones. Automation descriptions from that document are
> **not** evidence of what exists.

## 1 · Leads

1. New Lead Set up
2. On Hold
3. Credit Guide Sent
4. Credit Guide Signed

Four stages. The credit guide was already a pipeline gate in the old system, which is why the
OS build restored it as a stage on 9 Sep.

## 2 · Loan Submission

1. Jess Clients
2. Kaiden Clients
3. Karlie Clients
4. The Shitshow — stalled or complex files
5. Reema Files — the credit packaging desk
6. Prelim Pre/AOL
7. Karlie Mentor Check — principal quality check before lodgement
8. AOL Submission

**Stages 1–3 are broker queues, not journey stages.** Ownership was encoded as position. In OS
that becomes an assigned-user field plus saved views, which frees the stages to describe progress.

**Stage 7 is a real quality gate**: Karlie reviews files (notably for the mentored brokers) before
they're lodged. The prelim stage carries a checklist of about nine items, and *"nothing moves
ahead to the next stage until the checklist is completed."* See
[automation-requirements](automation-requirements.md).

## 3 · Approval — Settlements

1. Submitted
2. MIR's (more information required)
3. Approved — Pending
4. Formal Approval
5. Loan Docs
6. Settlement Booked
7. Settled
8. Audit
9. 30 Day Calls
10. HOLD/NPW (not proceeded with)

Settlement, audit and the first retention touch all live in one pipeline here. In OS they're split
across Approvals, Settlements and Post-Settlement.

## 4 · Pre-Approval

1. Pre-Approval
2. 30 Days
3. 60 Days
4. 75 Days
5. Expired

A time-based lifecycle for pre-approved buyers still searching. **No equivalent has been
confirmed in the OS build** — flagged as an open design question.

## 6 · Construction Loans

1. Settled Construction Not Started
2. Deposit/Pool Stage
3. Progress Claim 1 — Base
4. Progress Claim 2 — Frame
5. Progress Claim 3 — Enclosed
6. Progress Claim 4 — Fixing
7. Progress Claim 5 — Practical
8. Landscaping Payments
9. Final Hand Over
10. Repricing — Valuation

Rebuilt in OS as the Construction Loans pipeline. The final stage — revaluing the finished home to
reduce LVR — is genuine client value and a content angle.

*(There is no pipeline 5 in the Salestrekker navigation.)*

## 7 · Retention Workflow

Organised as **month columns, January to December**, each holding 45–60 clients. Michelle, 9 Sep:
> We're using that like, I'd say filing cabinet for the customer. So we have an original tile that
> we know is there. We can jump into. We know what their last lending was.

Also used to **price a client's existing loan without opening a live deal**. Karlie, 4 Sep: *"we
can put the details in there to get pricing and stuff like that for that initial conversation
without actually loading up an active deal."*

**This keeps running in Salestrekker** for pricing lookups. The OS replacement is an action-based
lifecycle driven off settlement dates — see [automation-requirements](automation-requirements.md).

## Karlie's earlier "minimal" version (19 Aug 2025)

`Application → Prelim Issued → AOL → Submitted/MIRS → Conditional Approval → Formal Approval →
Docs Issued → Settlement Booked → Settled → Audit`

## What the legacy structure teaches the redesign

1. **Ownership lived in stages** (Jess / Kaiden / Karlie Clients). Move it to fields.
2. **Exceptions lived in stages** (The Shitshow, On Hold, HOLD/NPW). Keep one hold and one
   closed-lost, with a reason field, so stalled work is reportable rather than invisible.
3. **Quality gates were real** (Credit Guide Signed, Karlie Mentor Check, Audit). Preserve them as
   gated stages or required checklists.
4. **Time-based lifecycles** (pre-approval 30/60/75, retention months) are better as date-triggered
   tasks than as columns.
5. **The deal/customer split is structural.** Salestrekker is deal-based and stays mandatory for
   home loans; see [sfg-salestrekker-integration](sfg-salestrekker-integration.md).

## Related

- [pipeline-decisions-log](pipeline-decisions-log.md) · [current-build-state](current-build-state.md)
- [calendars-and-routing](calendars-and-routing.md) · [funnel-architecture](funnel-architecture.md)
