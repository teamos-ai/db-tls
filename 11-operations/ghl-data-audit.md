---
id: ghl-data-audit
title: GHL data audit — what the migrated data actually looks like
type: system
status: approved
confidence: verified
source: GoHighLevel API, read-only, location vAX1ry0bjuYiAzEYFS9X, 11 Sep 2026 — all 1,882 contacts, 416 opportunities, 402 custom fields, 189 tags and 3 custom objects, aggregated. No record-level data is committed; the exports stay outside the repository.
as_of: 2026-09-11
owner: Tumai (Team OS)
tags: [operations, ghl, data-quality, migration, tags, fields, internal]
---

# GHL data audit

**The migration landed, but the data can't yet drive automations or reporting.** Five things
block the dream pipeline: duplicate client tiles, no settlement dates, deal ownership that isn't
per broker, tangled tags, and a consent field with the wrong entity and CRN.

**Internal only.** Counts only — no client is named anywhere in this file.

## Contacts — 1,882

| | Count |
|---|---|
| Added Aug 2026 (the migration) | 1,866 |
| With an email / with a phone | 965 (51%) / 1,011 (54%) |
| Tagged `client` | 726 — 721 with email and phone; 285 linked to an opportunity |
| Tagged `employer` | 314 — **148 look like organisations**, 17 have an email, 8 have an opportunity |
| No tags at all | 752 — 164 with an email |
| Linked to at least one opportunity | 331 |
| Assigned to a user | 342 (Karlie 332 · Kaiden 7 · Jess 3) — **1,540 unassigned** |
| Contact `source` filled | 408 |
| **Company name = "The Loans Suite Group Australia"** | **1,826 (97%)** |
| Do-not-disturb | 3 |

**What that means:**

1. **TLS's own entity was written into the company name on 97% of contacts.** Any
   `{{contact.company_name}}` merge prints it back to the client. Clear it, or map the real business.
2. **The `employer` records are not clients** — they're employers and HR contacts carried over from
   Salestrekker applications. Keep them out of every client list and campaign; they have no consent
   basis for marketing.
3. **752 contacts have no segment at all.**

## Opportunities — 416

| Pipeline | Opps | Status | Value recorded |
|---|---|---|---|
| 1 \| Pre-Submission | 7 | open | $4.05M |
| 2 \| Approval - Settlements | 23 | 16 open · 5 lost · 2 won | $10.55M |
| 3 \| Post Settlement | 91 | 89 open · 2 won | $4.72M |
| 4 \| Construction Loans | 11 | open | — |
| 5 \| Clients | 282 | open | — |
| Marketing Pipeline | 2 | 1 won · 1 abandoned | $5K |

| Owner | Opps |
|---|---|
| Karlie Scharfenberg | **367 (88%)** |
| Kaiden Harrison | 7 |
| Jessica Didovich-Lasalo | 5 |
| Unassigned | **37** — Clients 23 · Post Settlement 8 · Approval-Settlements 4 · Marketing 2 |

- **Broker ownership wasn't migrated.** Kaiden settled 30 loans in 2026 YTD
  ([settlement-data-baseline](settlement-data-baseline.md)) but owns 7 opportunities. Per-broker
  reporting can't work until owners are set.
- **A dollar value is set on 27 of 416.** Pipeline-value reporting is meaningless until amounts are in.
- **No opportunity carries a lost reason.**
- **Source:** Existing client 306 · Family friend 27 · Client referral 22 · Partner referral 22 ·
  blank 22 · Walk in 8 · others ≤ 2. "Existing client" looks like the migration default.

### Duplicate tiles, quantified

- Duplicate opportunities are **allowed** at account level.
- **79 contacts hold more than one opportunity** (up to 3).
- **69 have a tile in both Post Settlement and Clients.** 218 Clients tiles are named "… retention" —
  the Salestrekker retention-workflow cards, imported on 25 Aug alongside the Post Settlement tiles.
- Also: Construction + Clients (5), Post Settlement + Construction + Clients (3), Pre-Submission +
  Clients (4, including 2 that are also in Post Settlement), and one contact with two Post Settlement
  tiles.

This is the duplicate Michelle ran into on 4 Sep. The agreed rule — one tile per client — isn't
applied yet.

### Settlements not imported

Karlie's two workbooks hold **302 settlement rows** (176 for 2025, 126 for 2026 YTD). The Settled stage holds **9**.

## Custom fields — 402

| Object | Fields |
|---|---|
| Contact | 275 |
| Opportunity | 92 |
| Staff & Brokers · TLS Mentoring · Broker KPI's | 13 · 8 · 14 |

### Opportunity fields — well designed, almost empty

The 92 fields cover the full deal:
- **Loan structure:** 3 splits, each with lender, product, amount, rate type, rate, term, IO and fixed terms, repayment, fees and offset.
- **Securities:** 2, each with address, state, type, value, valuation method, ownership, use and rent.
- **Deal metrics:** LVR, DTI, serviceability surplus, LMI, stamp duty.
- **Milestone dates:** Submitted, Conditional Approval, Formal Approval, Settled, Declined, Not Proceeding.
- **Decision and fit:** Not Proceeding Reason, Lenders Considered, Recommendation Rationale (a best-interests record), First Home Buyer.

**Only 15 of the 92 hold a value on any opportunity.** Sec 1 address and postcode (165 each), Split 1
product and rate type (130 each), Loan Purpose (38), and a handful below 20.

- **`Date Settled` is empty on all 416.** The retention cadence runs off the settlement date, so
  **no migrated client can trigger it** until the date is back-filled from the workbooks.
- **`Loan Purpose` mixes purpose with occupancy:** Purchase · Refinance · Construction ·
  **Investment** · Debt consolidation · Other. 37 of its 38 values are "Investment".
- **Lender is free text on every split** — the source of the spelling variants in the workbooks.
  "Lenders Considered" offers only 13 lenders plus Other.
- **Missing for reporting:** no broker CRN, no new/existing client flag and no loan-type category
  (resi · commercial · asset · SMSF · personal). All three are required by
  [reporting-and-dashboard-requirements](reporting-and-dashboard-requirements.md).

### Contact fields — the fact find is complete, plus clutter

**Fact-find coverage:**
- Identity and driver licence
- Household and residency
- Address history
- Two employments (32 fields)
- Other income, and self-employed income for two financial years
- Entity (12 fields)
- Four assets and four liabilities (52 fields)
- 21 expense categories and HEM
- Adverse credit, guarantor, super, HELP, SMSF LRBA status
- A compliance block: credit guide issued, credit report authority, privacy acknowledgement, e-comms
  consent, marketing consent, lender disclosure, declaration, signed fact find URL and document
  checklist

**Clutter.** Roughly **50 template fields** from the Team OS template:
- Career-coaching and business-coaching quiz questions
- The billing address block
- Program dates
- Instagram
- "OpenAI Prompt", "Bot Status", "Voice OS | Call …"

**Duplicates and near-duplicates:**
- Residency vs Residency Status (different options)
- Gender vs What is your gender?
- Two "lived here longer than 3 years" fields
- Four "Add Asset?" and four "Add Liability (copy)…" toggles
- Referral Source vs Who referred you? vs Where did you hear about us?
- Application ID on both the contact and the opportunity
- An "Annualy" typo in Emp 2's frequency options

**Migrated numbers are mostly zeros.** The import wrote 0 where Salestrekker was blank:

| Field | Filled | Of which 0 |
|---|---|---|
| Total Assets | 1,010 | 780 |
| Total Liabilities | 1,010 | 847 |
| Emp 1 Net Base Income | 1,010 | 824 |
| Dependants Count | 1,009 | 930 |
| Total Declared Expenses | 983 | 922 |
| HEM Variance | 405 | 321 |

**Any "field is empty" condition will misfire.** Treat 0 as unknown until the data is cleaned.

### The consent field names one entity and one CRN — compliance

The fact find's privacy consent checkbox (its field name ends "(copy)") states the business is
*"Queens of Finance Pty Ltd trading as The Loans Suite (ABN 38 676 457 337), Credit Representative
477350 under Australian Credit Licence 387025"*, with overseas disclosure to the Philippines, the United States, India and the
United Kingdom.

1. **It names Queens of Finance.** Which entity holds the authorisation is unresolved — see
   [licensing-and-entity](../01-company/licensing-and-entity.md).
2. **It hardcodes Karlie's CRN for every client**, including Kaiden's (570030) and Jess's (576563).
   The rule is the deal owner's CRN — see [automation-requirements](automation-requirements.md).
3. **Its overseas list is a third version**, matching neither the website privacy policy nor the SFG
   credit guide — see [privacy-and-data](../07-compliance-and-guardrails/privacy-and-data.md).

**No consent is recorded for anyone.** Every compliance field is empty on all 1,882 contacts:
- `credit_guide_issued` and its date
- `credit_report_authority`
- `privacy_notice_acknowledged`
- `electronic_comms_consent`
- `marketing_consent`
- `lender_disclosure_authority`
- `declaration_accurate`

So are `referral_source` and `who_referred_you`. For migrated clients the evidence lives in
Salestrekker, so **OS can't yet gate a stage or a marketing send on consent.**

## Tags — 189 defined, 80 in use

**Most used:**

| Tag | Contacts |
|---|---|
| `client` | 726 |
| `employer` | 314 |
| `oo` | 133 |
| `rfi` | 79 |
| `contact for valuation` | 64 |
| `purchase` | 59 |
| `macquarie` | 58 |
| `inv` | 38 |
| `nab` | 27 |
| `new lending - kaiden` | 25 |

| Family | What exists | Problem |
|---|---|---|
| Purpose | `rfi`, `purchase`, `cashout`, `bridging`, `construction` and `construction loan`; `refinance` defined but unused | `rfi` vs `refinance` is exactly the split the locked master list (4 Sep) was meant to stop |
| Occupancy | `oo`, `inv`, `investment` | Abbreviation and full word both |
| Lender | 24 lender tags, including `macquarie`/`maq` and `bankaustralia`/`bank aus` | Lender belongs on the deal as a picklist, not on the person |
| Broker | `new lending - karlie/kaiden/emily`, `tls - karlie`, `jess referral`, `jess referral partner`, `michelle referral` | Ownership belongs in the assigned user; "referral" carries two meanings |
| Client status | `client`, `existing tls client`, `existing tls lending`, `new tls lending`, `active client`, `inactive client`, `off boarded client` | Seven ways to say "is a client" |

There are also about **100 template tags**, covering sales calls, courses, community, webinars, payments and AI calls. Two are exact
near-duplicates: `funnel opt-in` / `funnel optin` and `website opt-in` / `website optin`.

## Custom objects — in use

| Object | Records | What it shows |
|---|---|---|
| **Staff & Brokers** | 7 — 3 brokers, 3 broker support, 1 ops manager | Compliance dates (MFAA, AFCA, PI, AML) are **mostly empty** — a staff-expiry alert would have nothing to fire on |
| **TLS Mentoring** | 53 — 43 settled · 5 approved · 2 settlement booked · 3 in progress | Lender is a picklist here, with 20 values — the only structured lender list in the account |
| **Broker KPI's** | 54 — 52 commission paid | Full comms, split, broker comms, clawback, HQ surcharge, referral partner comms. **Settlement date filled on 23 of 54.** Commissions are already in the CRM |

## Account hygiene

- **13 of 15 users are admins**, including an external login (Dylan) and a duplicate Jordan Li login.
- GHL **sample data** is still present: an "(Example) Dunder Mifflin" company record.
- **All 79 custom values are empty.** These include the privacy policy link, the T&Cs link and the
  legal business name used for SMS registration.

## Fix before automations go live — ranked

1. **Merge the 69 duplicate clients** and choose one retention pipeline. Clients holds 282 tiles, so it
   can't simply be deleted.
2. **Back-fill `Date Settled`**, plus amount, lender and broker, from the settlement workbooks.
3. **Fix the fact-find consent text:** the entity, a per-broker CRN merge, and one overseas list.
4. **Set owners:** 37 unassigned opportunities, and Kaiden's and Jess's books.
5. **Clear company name** on 1,826 contacts, and separate the 314 `employer` records.
6. **Lock the master tag list and migrate** (`rfi` → refinance and so on). Move lender and broker out
   of tags.
7. **Treat migrated zeros as blanks.** Remove the ~50 template fields and the duplicate fields.
8. **Turn off duplicate opportunities**, or enforce one tile per client in the workflow.
9. **Cut admin roles** to those who need them.

## Related

- [current-build-state](current-build-state.md) · [ghl-account-map](ghl-account-map.md)
- [pipeline-decisions-log](pipeline-decisions-log.md) · [settlement-data-baseline](settlement-data-baseline.md)
