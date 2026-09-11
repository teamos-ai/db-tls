---
id: ghl-account-map
title: GHL account map — every ID in The Loans Suite sub-account
type: system
status: approved
confidence: verified
source: GoHighLevel API v2, read-only, via a sub-account Private Integration Token — location vAX1ry0bjuYiAzEYFS9X, read 11 Sep 2026
as_of: 2026-09-11
owner: Tumai (Team OS)
tags: [operations, ghl, ids, pipelines, calendars, workflows, forms, internal]
---

# GHL account map

The IDs needed to specify an automation precisely, **read from the API**. What they mean for the
build is in [current-build-state](current-build-state.md). Data quality is in
[ghl-data-audit](ghl-data-audit.md).

> **Internal only. No token is stored in this repository.** The PIT sits in the Team OS `ghl` CLI
> config on Tumai's machine. All access has been **read-only** — nothing in the sub-account was
> changed. IDs go stale when assets are rebuilt, so re-read the API before a build session.

## Account

| | |
|---|---|
| Location ID | `vAX1ry0bjuYiAzEYFS9X` |
| Company (agency) ID | `SWxcsGDWoMO4M9RWjngV` |
| Name · created | The Loans Suite · 11 Aug 2025 |
| Address · timezone | 6/11-17 Bremner Road, Rothwell QLD 4022 · **Australia/Brisbane** |
| Account phone | 1300 741 077 (stored as `+611300741077`) |
| Duplicate contacts · duplicate opportunities | Not allowed · **allowed** |
| OS number | **+61 485 088 933** — mobile, SMS/MMS/voice, default, forwards to +61 2 4733 4417 (Penrith) |

## Users — 15

| User | ID | Role |
|---|---|---|
| Karlie Scharfenberg | `KK6vR6q7I11wLnvspOVk` | admin |
| Kaiden Harrison | `IDqc4TFlgpE1kjwZFa4h` | admin |
| Jessica Didovich-Lasalo | `eOlU9NOQY5MonytmuqAN` | admin |
| Michelle Cairncross | `8DsdpukMJpFi5lxRwi8z` | admin |
| Emily Baulch | `X2tOMnH0nF3DbLyfQTkl` | admin |
| Phoebe Guy | `mNJ6we2eecrRuIOaN1BC` | user |
| Reema Maharjan | `dLCrdJxxQRwsH6tFHzUU` | user |
| Dylan Kemp (BrokerKit) | `Xxh0BB91lH01SslqvIkK` | admin |
| Tumai Meroiti (Team OS) | `1pnmgY6xFEdGwuk1VxQG` | admin |
| Ariki Meroiti (Team OS) | `xYXwT2MVlIs6ZmOtIdQK` | admin |
| Audrey Li (Team OS) | `KTf6J2fIoJlh4TEH1B2D` | admin |
| Jaypee Caldamo (Team OS) | `cODutR1gibq84Tih4vMO` | admin |
| Luna Kadusale (Team OS) | `ulwZwbW00pbvTwnkdn0k` | admin |
| Jordan Li (Team OS) — two logins | `SlmPmj7PjnJPKGCWDzJC` · `QNXvq9KYDH6SZmm3IluY` | admin |

## Pipelines and stages

Opportunity counts as at 11 Sep 2026. **Stage names in GHL carry a number prefix** ("1 |", "2.");
it is dropped below for readability.

### 1 | Pre-Submission⚡️ · `91vCXwKGpn23b4ABZeP1`

| # | Stage | Stage ID | Opps |
|---|---|---|---|
| 1 | New Lead⚡️ | `380132b8-7632-4b55-bcb9-eb0a8aaade33` | 1 |
| 2 | Credit Guide Sent | `4b3f6e5b-89ea-48f3-a15e-478dc6cc28e2` | 1 |
| 3 | Initial Conversation⚙️ | `eceea8c0-c039-4c76-b8ee-cdfe2a25b97b` | 2 |
| 4 | Fact Find | `372404ae-35fd-487b-b974-96468db6ddad` | 2 |
| 5 | Document Collection | `85cd7a3e-7f00-4617-96da-1d65a094bff6` | 0 |
| 6 | Quickli/Servicing | `6358fd8e-dc35-4961-a28a-9bef0de701d0` | 0 |
| 7 | Deal Qualifies | `faca11f5-6bb1-4ab8-9d69-d32302915b2d` | 0 |
| 8 | Pushed to Sales Trekker | `3879c709-36d3-4e42-b8b2-e2e5a47fceed` | 1 |

### 2 | Approval - Settlements 💰 · `Z9UZrt1deSq0AIAynj0K`

| # | Stage | Stage ID | Opps |
|---|---|---|---|
| 1 | Submitted / MIRS 🏁 | `068b6355-7cec-45b8-adb5-2af011efd49f` | 7 |
| 2 | Conditional Approval ✅ | `5adfd813-28a7-4004-a4e1-ae6c62470843` | 4 |
| 3 | Formal Approval 💡 | `4cb93abe-3d6d-4ffb-95de-e824bb90f9a3` | 0 |
| 4 | Docs Issued 📄 | `9b4fe805-2ff3-4d5c-9203-49cbc6981c28` | 1 |
| 5 | Settlement Booked ⭐ | `88b367a0-74a4-428f-98c9-757c53dda1ab` | 1 |
| 6 | Settled 👍 | `645c388a-2cd3-47b2-a576-29b496b4cdc0` | 9 |
| 7 | Audit 🔓 *(named "13 \| Audit")* | `59bae9a8-cc9f-4aab-a523-ca4b0a4758ca` | 1 |

### 3 | Post Settlement · `6jhGGMUdFuW2nqQklzEr`

| # | Stage | Stage ID | Opps |
|---|---|---|---|
| 1 | 30-Day Post-Settlement Check In | `6b01e6dc-487a-4382-8c28-d18e9587c922` | 88 |
| 2 | Annual Review / Check-Ins | `24596984-f8b2-4c3b-a36e-a2a3d22c5c24` | 3 |
| 3 | Year Review / Check-Ins | `4c3db2c9-0cac-41a0-bac4-1c8750d8432d` | 0 |

### 4 | Construction Loans · `Nw61LmspiVRs9C3EFUY3`

| # | Stage | Stage ID | Opps |
|---|---|---|---|
| 1 | Settled Construction Not Started | `5135b4f8-43ee-4f04-bf3a-050390e67480` | 8 |
| 2 | Deposit/Pool Stage | `8660e142-ad53-4edc-ba95-7ba8b44182a5` | 1 |
| 3 | Progress Claim 1 -Base | `6e773d73-c7d6-40fe-8602-df24ce4bbcd6` | 1 |
| 4 | Progress Claim 2 - Frame | `06dea05f-1fab-4ad8-b6b1-f71142b5a2af` | 0 |
| 5 | Progress Claim 3 - Enclosed | `f835f11c-17e2-4259-9e11-0cfbaf2c46fe` | 0 |
| 6 | Progress Claim 4 - Fixing | `5f59abd9-ebc8-4b2f-9a32-2b4bea262800` | 1 |
| 7 | Progress Claim 5 - Practical | `4888dc77-20fb-422a-ae84-8a12aed89958` | 0 |
| 8 | Landscaping Payments | `7fe66501-1f92-4c7a-9613-984aa1416e8e` | 0 |
| 9 | Final Hand Over | `26b9ae50-8f75-4d23-95da-012888df68bc` | 0 |
| 10 | Repricing - Valuation *(no prefix)* | `f6ae1173-0b8f-4d00-8a6a-e1bd5ca108a7` | 0 |

### 5 | Clients 🫶 · `J2u2UCygCC6lIkcyGVpv` — Team OS template, holds migrated tiles

| # | Stage | Stage ID | Opps |
|---|---|---|---|
| 0 | General / Active Clients☝️ | `1101a718-9a3b-4e8f-9e7d-7d1b008170f6` | 57 |
| 1 | First 3-Month Check-In 🥳 | `2e07ac4b-1f50-43d1-b59d-4fcea4ca4eca` | 0 |
| 2 | Annual Review / RBA Check 📅 | `1a3aa31b-9e18-4ee9-ad8a-a97e1a8080bf` | 0 |
| 3 | Mid-Term Refinance Opportunity 🙁 | `526d38f5-6aba-4005-994c-5918aa37aa55` | 0 |
| 4 | Life Event Trigger 🤨 | `6410eec2-adb4-475d-978a-4d56a965ae5e` | 0 |
| 5 | Retention & Repricing 🕺 | `d0ffc687-b03d-403e-95c5-1c165d354ba3` | 225 |
| 6 | Referral Loop 💤 | `6fd01d14-c24e-4e3e-a898-b0c8bad77d6d` | 0 |
| 7 | 5-Year+ Milestone Review 💸 | `6184897d-de9f-4b7c-8656-3e745efc5bc5` | 0 |

### Template pipelines with no tiles to move

- **6 | Partners 💎** · `66kADDwcjRxO69HE98pd` — Leads · Follow Up · New Users · Active Users · New
  Partners · Active Partners. 0 opportunities.
- **Marketing Pipeline** · `bJhNnRLPnQwELQOSDzPq` — New Lead · Contacted · Qualified · Proposal Sent ·
  Negotiation (1) · Closed (1).

## Workflows — 21

| Workflow | ID | Status |
|---|---|---|
| Form to Deal Automation | `9c217f64-bb5b-4991-a6d3-7654667a4416` | **published** |
| Recipe - Appointment Confirmation + Reminder | `e951e18c-96e8-4b8f-a7c9-608efb248c89` | **published** |
| Pre-Submission⚡️ | `cd7dbb10-1eb1-40ea-add8-e84e33e424aa` | draft |
| Approval - Settlements 💰 | `673efc05-b228-4ec1-a496-4141858aa09b` | draft |
| Karlie Scharfenberg \| Discovery Call Automation💰 | `58ea23de-57a2-4a52-80cf-bee599e9fe17` | draft |

**Sixteen Team OS template drafts**, untouched since 11 Aug 2025:
- 001 IG Comments & DM's
- 002 Sales Discovery Calls
- 003 Client Onboarding
- 004 Funnel Opt-Ins
- 005 Courses & Products
- 006 Community App
- 007 Payments Received
- 008 Tasks & Projects
- 009 Sites, Leads & Ads
- 010 A.I. Voice
- 011 A.I. Chat
- 012 Store & Shop
- 013 Account Health
- Partners OS 1–3

## Forms — 25

| Form | ID |
|---|---|
| Speak with a Broker | `ICXqX7vIRYgekDsIoBUE` |
| 01 Applicant details \| Fact Find | `yS4VrpnRjMcermjrnEQp` |
| 02 Identity Verification \| Fact Find | `OXyqxOCKBzQIIPUmDJ1Z` |
| 03 Employment \| Fact Find | `fMwXiOhwnLNFzQf0SBRg` |
| 04 Other income \| Fact Find | `yzRdMzk2d02OB6fRc1cu` |
| 05 Assets \| Fact Find | `SHmz4VCSZ6YJ0QsxRFdB` |
| 06 Liabilities \| Fact Find | `2KqSwFSmyZ6DbFajLYPf` |
| 07 Living expenses \| Fact Find | `8D5DwNZQpmCyFKgip1I2` |
| 08 Credit history \| Fact Find | `YEMcpvQaEI1ouQ7hJESL` |
| 09 Business, trust or SMSF \| Fact Find | `4n1PuBU6r835cpwy4Lip` |
| 10 Consent and declaration \| Fact Find | `JNu0lFPk6PqHL0mX69OF` |
| Fact Find Form \| Short Form | `dkCqy9nx6OUgk2W38v65` |
| 01 Primary Identification | `Xi5r0iAT2ag8L77d34R1` |

**Twelve Team OS template forms:**
- 00 Partners Website OS
- 01 Discovery Call Calendar (×2)
- 02 Clients Onboarding Call Calendar
- 03 Link In Bio Newsletter Opt-In
- 04 Lead Magnet
- 05 Funnel
- 06 Community
- 07 Newsletter
- 08 Check In
- 09 Website
- 10 Webinar Registration

## Surveys — 4

| Survey | ID |
|---|---|
| Full Fact Find | `XR1IVxjsKXiQNj6ANtmI` |
| Full Fact Find - Duplicate | `0uM2BnH0DF0LhoBIX9QD` |
| 01 \| Qualifying Application 🤔 *(template)* | `sK3HwdPNg1mYx71eEEBY` |
| 02 \| New Client Questionnaire 🫶 *(template)* | `OD4KzUXQ0tX4bVEYJji9` |

## Calendars — 18

| Active calendar | ID | Widget slug |
|---|---|---|
| Karlie Scharfenberg's - Book a Call | `ttBIJ9ZcPx4pglw13n5L` | `karlie-scharfenberg-personal-calendar-giinzurgm` |
| Kaiden Harrison - Book A Call | `9Ks6X3xXgrxG6lOglBw2` | `kaiden-harrison-personal-calendar-t4h0rhrhu` |
| Jessica Didovich-Lasalo - Book A Call | `tmWq7uVnHvixxtKnhqup` | `jessica-didovich-lasalo-personal-calendar-rbjhx_4pa` |
| Michelle Cairncross - Book A Meeting | `WUsx2yheYHdBD9jhEei7` | `michelle-cairncross-book-a-mee` |
| Emily Baulch - Book A Meeting | `bOgn4uPigM2KwhgzTQAG` | `emily-baulch-book-a-meeting` |
| Reema Maharjan - Book A Meeting | `QDzyrEK3XqWTakIj7DnJ` | `reema-maharjan-book-a-meeting` |

**Inactive template round-robins, all with no members:**
- Discovery Call — `yt6JB46Socoe3icAgESH`, in group "Builders OS" `g9PrastuFpPcCFWXZuHS`
- Onboarding Call — `1vFdaOSt3ytEzsQB1Rfc`
- Template Follow Up — `NYSxssK3YA4qvagqxpmP`
- Template Discovery Call — `WVhNgBps693wx1ywTvY4`
- 1-1 Meeting — `TrQ7w2BFNH5PsvnqRhWH`

**Inactive personal calendars:**
- Tumai Meroiti — `MDKbE6Z4yKnAfZTaEf2m`
- Tumai A.I — `KmeKCkm0miYwClksw2nX`
- Ariki — `hxzO5Hg5Fy4QMqjaF4Jv`
- Audrey — `JMZYFxhgn1rzxe1dAqBT`
- Jordan — `75m3M4l5usTaVrVWaCfz` and `AIJnnSq70MdEoeEn7esL`
- Dylan — `8tTLrQBJiGYkxBCK8hbN`

Settings and defects: [calendars-and-routing](calendars-and-routing.md).

## Custom objects

| Object | Key | Records | Property keys in use |
|---|---|---|---|
| Staff & Brokers | `custom_objects.staff_brokers` | 7 | `staff_broker` `role` `position` `email` `phone` `date_of_joining` `mfaa_exp` `afca` `tlsga__pi` `dkckz_pi` `performance_1st_week` |
| TLS Mentoring | `custom_objects.tls_mentoring` | 53 | `client_name` `app_number` `loan_amount` `lender` `status` `whos_client` `date` |
| Broker KPI's | `custom_objects.broker_kpi_s` | 54 | `broker_name` `client_name` `loan_amount` `full_comms_ex_gst` `commission_split` `broker_comms_amt` `broker_commission_paid` `clawback` `hq_surcharge` `referral_partner_comms` `referred_by` `referral_partner` `date_loan_settled_aest` `date_comms_paid_aest` |

The system Companies object (`business`) holds only GHL's sample record.

## Field keys an automation will need

**402 custom fields:** 275 contact, 92 opportunity, 35 on custom objects. Keys follow `contact.<name>` /
`opportunity.<name>`.

**Opportunity:**
- **Milestone dates:** `date_submitted` · `date_conditional_approval` · `date_formal_approval` ·
  `date_settled` · `settlement_date_required`
- **Outcomes:** `date_declined` · `date_not_proceeding` · `not_proceeding_reason`
- **Deal:** `loan_purpose` · `occupancy_type` · `first_home_buyer` · `total_loan_amount` ·
  `requested_loan_amount` · `split_1_lender` · `lenders_considered` · `lvr` · `application_id` ·
  `refinance_reason`
- **Broker notes:** `recommendation_rationale` · `lender_feedback` · `priority_and_reason`

**Contact — compliance and intake:**
- **Credit guide and credit report:** `credit_guide_issued` · `credit_guide_issued_date` ·
  `credit_report_authority` · `credit_authority_date`
- **Privacy and consent:** `privacy_notice_acknowledged` · `privacy_consent_date` ·
  `electronic_comms_consent` · `marketing_consent` · `lender_disclosure_authority`
- **Fact find:** `declaration_accurate` · `declaration_date` · `signed_fact_find_doc_url` ·
  `doc_checklist_status` · `fact_find_completed_date`
- **Referral and applicants:** `referral_source` · `who_referred_you` · `where_did_you_hear_about_us` ·
  `applicant_role` · `related_applicant_email` · `application_id`
- **Intake:** `what_are_you_looking_for_help_with` (the loan-type picklist) · `_booking_status`

**Every compliance field above is empty on all 1,882 contacts.**

## Other assets

| Asset | State |
|---|---|
| Knowledge bases | The Loans Suite `LDjZ3HwaJ68mZgFOmgPG` · Updated TLS KB `qeg9htO8eVKysYkM5Ea2` · two older "Existing knowledge base" sets (`yB1Ir1PNfLJSdTrql6c8`, `jYdGDfzDo2wqpAy2WKYj`) |
| Funnels and sites | Test The Loan Suite Custom Chat Widget `NyxXEvaQbt2518u6S5m4` · "www.theloanssuite.com.au" site, 0 pages, `gGSB1ZbkgBAzos10cYQ2` · 11 Team OS templates |
| Email builder | 15 folders, all Team OS template sets |
| Custom values · trigger links | 79, all empty · 22, all template |
| Campaigns · SMS/email templates | 0 · 0 |
| Products | "Security Deposit" (Nov 2025) — no TLS use identified |

## Not readable through the API

- Workflow triggers and steps
- Domain mappings
- The missed-call text-back setting
- Conversation AI and chat widget settings
- Social planner accounts
- Custom menus
- Smart lists and dashboards

## Related

- [current-build-state](current-build-state.md) · [ghl-data-audit](ghl-data-audit.md)
- [pipeline-decisions-log](pipeline-decisions-log.md) · [systems-and-ids](../01-company/systems-and-ids.md)
