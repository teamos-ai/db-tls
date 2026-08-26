---
id: pipelines
title: The six pipelines — Karlie's production workflow
type: system
status: approved
confidence: verified
source: Karlie Scharfenberg's live GoHighLevel / Salestrekker configuration, inspected Aug 2026 and documented in database-blueprints/ghl-operational-database.md (see 99-source-material). Stage names are hers.
as_of: 2026-08-26
owner: Karlie Scharfenberg
tags: [operations, pipelines, ghl, salestrekker, workflow]
---

# The six pipelines

Extracted from the live CRM configuration. **These are the business's real stage names**,
including the informal ones — they are reproduced faithfully because they are how the team
actually talks, and because a marketing automation that uses different names will not match
what operations sees.

> **Internal only.** No pipeline stage name appears in client-facing copy. "The Shitshow" is
> a real stage in a real system and must never leave this repo.

## 1 · Leads & Inbound Qualification

Triage inbound web enquiries, paid-social leads and partner introductions — target **within
five minutes**.

1. `New Lead Set up` — missed-call text-back and instant SMS qualification fire
2. `Contact Made / Discovery Booked` — 15-minute qualification call scheduled
3. `Credit Guide Sent` — Credit Guide dispatched by SMS/email
4. `Credit Guide Signed / Fact Find Issued` — digital Fact Find and 100-point ID link sent
5. `On Hold / Nurture` — unserviceable now, or a long-term deposit saver

**Marketing hooks:** stage 1 is where speed-to-lead lives — the difference between a 5-minute
and a 30-minute response is the difference between a booked call and a lost lead. Stage 5 is
the **nurture pool**, and it is the most valuable underused asset in the business: people who
wanted to buy, couldn't yet, and will.

## 2 · Loan Submission & Strategy Formulation

File packaging, expense scrubbing and desk allocation.

1. `Jess Clients` — allocated to Jessica Didovich-Lasalo
2. `Kaiden Clients` — allocated to Kaiden Harrison
3. `Karlie Clients` — retained by Karlie (VIP, high-net-worth, complex commercial)
4. `Reema Files` — dedicated packaging desk
5. `The Shitshow` — stalled or complex files needing a policy exception or BDM escalation
6. `Prelim Pre / AOL Setup` — serviceability run in **Quickli**, living expenses reconciled,
   **ApplyOnline** draft started
7. `Karlie Mentor Check` — principal QA before submission
8. `AOL Submission` — formally lodged with the lender

**Note:** `Reema Files` names a packaging resource **not listed among the six published team
members**. Confirm whether Reema is staff, contractor or offshore support before any content
references team size. See [team](../01-company/team.md).

**The `Karlie Mentor Check` stage is a genuine proof point** — every file passes principal QA
before lodgement. That is a real quality-control claim, and it is not on the website.

## 3 · Approval & Settlement Engine

1. `Submitted / In Queue` — automated SMS: *"Your application is in the queue with [Lender]"*
2. `MIR's (More Information Required)` — assessor query, high-priority task raised
3. `Approved - Pending (Conditional / AIP)` — valuation ordered, inspection tracked
4. `Formal Approval (Unconditional)` — celebration SMS and conveyancer update
5. `Loan Docs Issued / Signed`
6. `Settlement Booked` — **PEXA** workspace open, funds-to-complete verified
7. `Settled` — drawdown complete, settlement gift dispatched
8. `Audit & Compliance Check` — BID file note archived for aggregator compliance
9. `30 Day Calls` — first-repayment check-in
10. `HOLD / NPW (Not Proceeded With)`

**Marketing hooks:** stages 4 and 7 are the **peak-emotion moments** in the entire
relationship — the single best time to ask for a review or a referral. The review gap against
Borro's 215+ Google reviews is solved here, not by a campaign.
Stage 10 is a re-engagement pool.

## 4 · Pre-Approval Lifecycle

Tracking house hunters through a 90-day pre-approval window.

1. `Pre-Approval Active`
2. `30 Days Check-in` — *"How is the property search going? Any contracts of sale to review?"*
3. `60 Days Check-in` — property report / auction guide sent
4. `75 Days Expiry Warning` — payslips must be refreshed before day 90
5. `Expired / Extension Requested`

**A ready-made three-touch nurture sequence with built-in deadlines.** Pre-approved buyers are
the warmest audience the business has and the easiest to lose to a competitor at day 91.

## 5 · Construction Loans Workflow

Ten staged drawdowns.

1. `Settled Construction Not Started` · 2. `Deposit / Pool Stage` ·
3. `Progress Claim 1 - Base` (slab) · 4. `Progress Claim 2 - Frame` ·
5. `Progress Claim 3 - Enclosed` (lock-up) · 6. `Progress Claim 4 - Fixing` ·
7. `Progress Claim 5 - Practical Completion` · 8. `Landscaping Payments` ·
9. `Final Hand Over` · 10. `Repricing / Post-Build Valuation`

**Ten stages over months = ten natural contact points.** The best nurture-sequence opportunity
in the business. Stage 10 — revaluing the completed home to reduce LVR — is a genuine,
concrete piece of client value almost nobody talks about, and a strong content angle.

## 6 · Client Retention & Refinance Shield

Protecting the trail book.

1. `Month 6 Check-in` — offset optimisation
2. `Month 10 Rate Health Check` — lender pricing request to match front-book discounts
3. `Month 18 Equity Review` — automated equity report to the borrower
4. `Month 23 Refinance Window Open` — full market comparison offered

**This pipeline is the [Loan Health Check](../01-company/how-we-work.md) made operational**,
and it is entirely invisible to prospects. That is a missed positioning opportunity: *"we
check your rate at month ten so you don't have to"* is a differentiated promise no competitor
makes.

> **Compliance boundary.** The commercial driver behind the 24-month cycle is commission
> clawback. **That must never appear in client-facing copy.** The client-facing framing is the
> service itself — a proactive rate review — which is genuine value regardless of motive.
> See [fee-model-and-economics](../02-offer-and-lending/fee-model-and-economics.md).

## Systems referenced

**GoHighLevel** (marketing automation, pipelines) · **Salestrekker** (loan workflow) ·
**Quickli** (serviceability) · **ApplyOnline / AOL** (lodgement) · **PEXA** (settlement).

**No GHL location ID, workflow ID, calendar ID or form ID is recorded.** Capturing them is
a prerequisite for specifying any automation work. Roadmap item.

## Related

- [calendars-and-routing](calendars-and-routing.md) · [funnel-architecture](funnel-architecture.md)
- [how-we-work](../01-company/how-we-work.md) · [email-sequences](../08-channels-and-playbooks/email-sequences.md)
