---
id: settlement-data-baseline
title: Settlement data baseline — anonymised aggregates (INTERNAL ONLY)
type: system
status: approved
confidence: verified
source: Karlie's workbooks "2025 Settlements.xlsx" and "2026 Settlements YTD.xlsx" (emailed 4 Sep 2026), aggregated 2026-09-11 with client names and loan references excluded; Karlie's verbal figure from Granola transcript 4 Sep 2026; Monday.com "Dashboard Results" export 4 Sep 2026
as_of: 2026-09-04
owner: Karlie Scharfenberg
tags: [operations, settlements, data, baseline, kpi, internal-only, not-publishable]
---

# Settlement data baseline

> **INTERNAL ONLY — NOT PUBLISHABLE.** These are the business's own volume figures. They exist
> now, but [what-we-cannot-claim](../05-proof-and-evidence/what-we-cannot-claim.md) still
> applies: **no figure here may appear in marketing, an ad, a website page or an award entry
> without Karlie's explicit sign-off**, and any use must state its scope (which brokers, which
> CRNs, which period).
>
> **No client names, addresses or loan references are recorded in this repository.** The source
> workbooks stay in email.

## Headline figures

| Period | Settlements | Value | Scope |
|---|---|---|---|
| **Calendar 2025** | **176** | **$113.5M** | All brokers in the workbook, **including Maryanne (360 Suite, CRN 490945): 23 / $17.1M** |
| Calendar 2025, TLS brokers only | **153** | **$96.4M** | Karlie + Kaiden CRNs |
| **2026 YTD** (to 4 Sep) | **126** | **$77.3M** | Karlie, Kaiden, Jess |

**Karlie's own verbal figure for 2025** (4 Sep 2026): *"we've settled 187 loans and it was 114
million dollars"* — the Monday.com figure. The workbook reconciles to **$113.5M across 176 rows**
(it includes $0 insurance rows). **The $114M includes the 360 Suite's $17.1M.** A TLS-only 2025
claim is about **$96M**. That distinction is the single biggest claims trap in this file.

**Run rate:** $77.3M over roughly 8 months is ~**$9.5M a month**, consistent with Karlie's *"around
$10M per month without active lead generation"* (10 Aug 2026). Annualised, about **$114–116M
against the $120M group target.**

## 2025 by settlement month (all CRNs)

| Jan | Feb | Mar | Apr | May | Jun | Jul | Aug | Sep | Oct | Nov | Dec |
|---|---|---|---|---|---|---|---|---|---|---|---|
| $4.9M | $5.6M | $6.0M | $6.1M | $9.6M | $9.5M | $14.9M | $10.3M | $12.5M | **$15.4M** | $11.3M | $7.1M |

A clear second-half step-up: H1 $41.8M, H2 $71.5M.

## By broker

| Broker | CRN | 2025 | 2026 YTD |
|---|---|---|---|
| **Karlie Scharfenberg** | 477350 | 145 / $90.2M | 87 / $54.0M |
| Karlie — CRN typos in data | 447350, 47730 | 1 / $0.1M | 2 / $2.0M |
| **Kaiden Harrison** | 570030 | 7 / $6.2M | **30 / $16.2M** |
| **Jessica Didovich-Lasalo** | 576563 | — | 7 / $5.0M |
| Maryanne (360 Suite) | 490945 | 23 / $17.1M | — |

Kaiden's growth is the standout: 7 settlements in all of 2025, 30 in the first eight months of 2026.

## 2026 YTD mix — what the book actually is

**By loan type**

| Type | Count | Value | Share of value |
|---|---|---|---|
| Home loans | 98 | $70.2M | 91% |
| Commercial | 9 | $5.6M | 7% |
| Asset finance | 14 | $1.3M | 2% |
| Personal loans | 3 | $0.08M | — |
| Business loans | 1 | $0.04M | — |

**By purpose**

| Purpose | Count | Value | Share of value |
|---|---|---|---|
| **Refinance (RFI)** | **60** | **$42.3M** | **55%** |
| Purchase | 39 | $24.2M | 31% |
| Bridging | 4 | $6.0M | 8% |
| Construction | 5 | $3.5M | 5% |
| Car loans | 13 | $1.1M | 1% |

**By client relationship**

| | Count | Value | Share of value |
|---|---|---|---|
| **Existing clients** | **66** | **$48.3M** | **62%** |
| New clients | 60 | $29.0M | 38% |

## What the mix says — design implications

1. **This is a refinance-and-retention business.** Refinances are 48% of settlements and 55% of
   value; existing clients are 52% of settlements and 62% of value. The post-settlement pipeline
   is where most revenue originates. This upgrades
   [icp-refinancer](../03-audience-and-icp/icp-refinancer.md) from reasoning to data.
2. **2025 skewed new:** new clients were 102 of 153 TLS settlements ($67.3M). **2026 flipped to
   existing** — likely the consolidated trail book being worked.
3. **Commercial is small by count but large per deal** (~$625K average in 2026) — a
   low-frequency, high-touch path that shouldn't share a high-frequency comms sequence.
4. **Asset finance and car loans are high count, low value** — a fast, light-touch path.
5. **Bridging** ($6.0M across 4 deals) is material and has no page, product file or pipeline path.

## Lenders

**39 distinct lenders used in 2026 YTD; 36 in 2025** (TLS brokers). **Macquarie** is the most-used
lender in both years (45 settlements in 2025, 23 in 2026 YTD), followed in 2026 by NAB, Westpac
(recorded as both "WBC" and "Westpac"), St.George, CBA, Suncorp and ING.

Named lenders in the data outside SFG's residential panel list include asset and commercial
funders (e.g. Assetline Capital, Metro, Angle Finance) and insurers recorded as "lenders"
(Allianz). See [lender-panel](../02-offer-and-lending/lender-panel.md).

## Data-quality defects — the reason reporting needs picklists

Found while aggregating. **Every one silently breaks a dashboard:**

| Defect | Example |
|---|---|
| **CRN typos** | 447350 and 47730 entered for 477350 |
| **Columns swapped** | 360 Suite rows have loan type and transaction type reversed ("Refinance" as loan type, "Home loan" as transaction) |
| **Spelling variants** | Homeloan / Home loan / Homelon · New / New. · WBC / Westpac |
| **Numbers in text fields** | "123", "213", "224" in Transaction Type |
| **Subtotal rows embedded in data** | Month-total rows in the Broker column — naive sums double the total |
| **Non-loans mixed in** | Insurance and deposit bond rows at $0 or non-loan amounts |
| **Missing column** | 2026 workbook has **no settlement date** |
| **Undated rows** | One 2025 row with no settlement date |
| **Monday.com under-reported** | Showed $26.6M / 46 loans on 4 Sep vs $77.3M / 126 in the workbook |

**Rule for the build:** broker, CRN, loan type, purpose, lender and new/existing must be
**controlled picklists**; settlement date must be required on the Settled stage; insurance and
deposit bonds must be a separate record type or excluded from loan totals.

## Related

- [reporting-and-dashboard-requirements](reporting-and-dashboard-requirements.md)
- [what-we-cannot-claim](../05-proof-and-evidence/what-we-cannot-claim.md) · [claims-policy](../07-compliance-and-guardrails/claims-policy.md)
