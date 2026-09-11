---
id: reporting-and-dashboard-requirements
title: Reporting and dashboard requirements
type: system
status: approved
confidence: verified
source: Karlie's emails "Dash Board" (18 Aug 2025) and "2026 Settlements YTD" (4 Sep 2026, with Monday.com "Dashboard Results" export); Granola transcripts 26 Aug and 4 Sep 2026; Granola notes 18 Aug and 9 Sep 2026; Karlie's brief (Stage 4)
as_of: 2026-09-11
owner: Tumai (Team OS)
tags: [operations, reporting, dashboard, kpi, awards, settlements, internal]
---

# Reporting and dashboard requirements

**Why reporting matters to Karlie:** award submissions. *"It's hard enough to put a submission in,
but then to try and find the data as well."* The Adviser Australian Broking Awards and the Better
Business Awards both ask how many loans settled in the calendar year, their dollar value, and
the loan book value.

**Sequencing rule (Audrey, 9 Sep):** pipelines locked → data centralised and feeding correctly →
tags clean → **then** build reporting. Reporting built on dirty tags is wrong.

---

## 1 · Karlie's list — 18 Aug 2025

1. Dollar value settled per month and per calendar year
2. Number of deals **submitted** per month
3. Number of deals settled per month
4. Number of deals settled per year
5. Asset finance — dollar value settled
6. Asset finance — number settled
7. Commercial — dollar value settled
8. Commercial — number settled

> I need all this info to be easily accessible to know how we are tracking year on year and also
> for awards submissions.

## 2 · Karlie's list — 4 Sep 2026

- **Year-on-year** results
- Breakdown by **Karlie, Kaiden and Jess**
- **Resi** — number and dollar value settled
- **Asset finance, including personal loans** — number and dollar value
- **Commercial** — number and dollar value
- **Pie chart of lenders used** (%)
- **Purpose: refinance or purchase**
- **Yearly comparison by loan type** (e.g. home loans settled in 2024 vs later years)
- **Target gauges:** **Group settlements $120M per annum** · individual target **$40M** · individual
  target **$40M**
- A **team view** and an **individual view** per broker

> I have attached a sample of what Mondays used to look like. Can this be created?

## 3 · The Monday.com dashboard she wants replicated (export dated 4 Sep 2026)

| Row | Widgets |
|---|---|
| Value tiles | **Resi Settlements** · **Asset Finance Settlements** · **Commercial Settlements** · **SMSF Settlements** |
| Count tiles | Number of Resi / Asset Finance / Commercial / SMSF loans |
| Targets | **Group Lending Target** gauge (actual vs $120M) · **Total Group Settlements** · **Total Group Loans** |
| Mix | **Lenders Used in Group** donut · **Purpose of Lending** pie (RFI, Purchase, Construction, Car Loan, Asset Finance, SMSF, Cash Out, Bridging) |
| Individual | **Kaiden Annual Target** gauge |

**It was wrong in two visible ways — don't replicate the defects:**
1. It showed **$26.6M group settlements / 46 loans** on the same day her YTD workbook showed
   **$77.3M / 126 settlements**. Monday was missing most of the data.
2. The **Kaiden target gauge** compared a $24.88M "actual" (the group resi figure) against a
   **36K** target — misconfigured.

Also note **SMSF was a separate category** in Monday but isn't in either email list. Confirm
whether SMSF stays a reporting category, given the residential SMSF borrowing ban.

## 4 · Requirements raised in meetings

**Karlie (18 Aug, 4 Sep, 9 Sep):**
- Loans settled YTD and by calendar year; total dollar value
- Breakdown by type: commercial, resi, SMSF, asset finance
- **Loan book value at any point in time**
- **Settled by broker, filterable by new vs existing client** — including any future broker
- Broker KPIs: settlements per broker, **referrals passed to insurance partners (e.g. Tower)**
- **Submitted counts**
- One-click pipeline visibility: low-hanging fruit, stalled or on-hold deals, which broker owns what
- Drill-down: why a settlement was blocked, why credit approval took long
- *Doesn't* need deep historical segmentation ("all investors on 95% LVR over 5 years") — build
  moderate depth, don't over-engineer

**Michelle (4 Sep):**
- Her **daily settlement tracker** (Broker Point Excel): broker, CRN, new/existing, loan type,
  lender, amount, settlement date; **recalculated every morning** into a running monthly total
  for Karlie's morning message (*"we're at 12 million. We're now at 14 and a half million"*)
- **Upcoming settlements by date**, including deals slipping to next month
> this is literally the most important part that I use.
- Parallel run: keep the Excel tracker until OS data is trusted; an OS → spreadsheet sync was
  offered as a backup
- Broker KPI reporting per quarter for each broker; a report of **all loans settled**

**Emily:** marketing view — calendar bookings, social engagement, lead magnet downloads.

**Karlie's brief (Stage 4):** settled + tagged → commission tier applied → KPI dashboard
(volume, new clients, referrals) → **quarterly review auto-report to broker and director**.
Activity metrics (lender sessions, insurance referrals, networking events) need a self-report form.

## 5 · Role dashboards

| User | View |
|---|---|
| **Karlie** | Pipeline pulse and value by stage · stage distribution · approvals · settled YTD and by year · by loan type · by broker (new vs existing) · group and individual target gauges · lender mix · purpose mix · loan book value |
| **Michelle** | Today's and upcoming settlements · month-to-date running total · loan book snapshot · retention tasks due in the next 7 and 30 days · broker KPI entries |
| **Brokers** | Their own pipeline · their tasks · their settlements vs target |
| **Emily** | Bookings · social · lead magnets · form submissions |
| **Phoebe** | Audit queue · 30-day call tasks |

Mobile app view of pipeline and revenue was demonstrated.

## 6 · Fields every settled deal must carry

Derived from Michelle's tracker and Karlie's settlement workbooks:

**Broker** (owner) · **Broker CRN** · **New / Existing client** · **Loan type** (picklist) ·
**Transaction type / purpose** (picklist) · **Lender** (picklist) · **Amount** · **Settlement date** ·
**Loan / application reference** · tags

**Make every one of these a picklist or validated field, not free text.** The existing workbooks
show why — CRN typos, swapped columns, spelling variants and embedded subtotal rows. See
[settlement-data-baseline](settlement-data-baseline.md).

**In OS today (API, 11 Sep 2026):**
- **Already exist:** amount (`Total Loan Amount`), settlement date (`Date Settled`), purpose (`Loan
  Purpose`, which wrongly includes "Investment"), lender (`Split 1 Lender`, **free text**) and
  reference (`Application ID`).
- **Don't exist:** Broker CRN, New / Existing client, and a loan-type category.
- **Empty everywhere:** `Date Settled` is blank on all 416 opportunities, and Karlie owns 88% of them.

Nothing on this dashboard is buildable until those gaps are fixed — see
[ghl-data-audit](ghl-data-audit.md).

## 7 · Unresolved

1. **Commissions in the CRM or not?** Out of scope per 18 Aug; the KPI board has commission splits
   (9 Sep); the brief wants a tiered commission workflow.
2. **Loan book value** — the source of truth is trail statements, which stay in Excel. How does it
   reach the dashboard?
3. **Targets** — $120M group; two $40M individual targets named without saying whose. Kaiden's
   Monday gauge said 36K.
4. **Does the 2025 baseline include the 360 Suite (Maryanne) volume?** The 2025 workbook does —
   $17.1M of $113.5M. Award submissions for TLS need a decision.
5. **Settlement date** is missing from the 2026 workbook — required for monthly reporting.

## Related

- [settlement-data-baseline](settlement-data-baseline.md) · [pipeline-decisions-log](pipeline-decisions-log.md)
- [awards](../05-proof-and-evidence/awards.md) · [what-we-cannot-claim](../05-proof-and-evidence/what-we-cannot-claim.md)
