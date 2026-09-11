---
id: funnel-architecture
title: Funnel architecture — designed, not yet live
type: system
status: draft
confidence: inferred
source: funnel designs from Karlie's GHL planning documentation (Aug 2026). These are proposed builds, not live funnels — nothing matching them appears on theloanssuite.com.au.
as_of: 2026-09-11
owner: Karlie Scharfenberg
tags: [funnels, operations, design, proposed, partners]
---

# Funnel architecture

> **Tier note:** `inferred` — **these are designs, not live systems.** Nothing matching them
> exists on the website today. Treated as the intended target state, not as fact. Do not
> describe them to anyone as existing.

## Funnel 1 — Mortgage Stress & Rate Check

**Traffic:** Google local search, Meta ("Mortgage Repayment Reality Check"), organic SEO.

**Mechanism:** a four-step micro-commitment form:

1. Current estimated property value?
2. Approximate remaining loan balance?
3. Current interest rate? *(<5.8% · 5.8%–6.4% · >6.4% · Not sure)*
4. Where should we send your report? *(name, email, mobile)*

**Then:** estimate the annual interest difference, send a dynamic SMS report, open a booking
slot for a 15-minute strategy call.

**Assessment.** The micro-commitment ladder is right — three low-stakes questions before
asking for contact details is far better than a form wall, and it maps to the
**explore → talk → apply** ladder the site already uses.

**Compliance problems to fix before build:**
- **"Rate Savings Report"** frames a saving as an outcome. Rename to a *comparison* or
  *review*, never a *savings* report. See [guardrails](../07-compliance-and-guardrails/guardrails.md).
- **Any calculated figure must carry the calculator disclaimer.** An SMS containing a dollar
  figure with no disclaimer is worse than a web page with one.
- **A high-stress result must offer the National Debt Helpline (1800 007 007)**, not only a
  sales call. See [disqualifiers](../03-audience-and-icp/disqualifiers.md).
- The rate bands hard-code an interest-rate environment and will date. Build them editable.

**Note:** the business already has two mortgage stress calculators with **conflicting
thresholds** (35% vs 30%). Consolidate before building a funnel on top of them.
See [calculators-and-tools](../02-offer-and-lending/calculators-and-tools.md).

## Funnel 2 — B2B Referrer Portal

**Target:** the existing partner network — real estate agents, conveyancers, accountants,
credit specialists.

**Mechanism:** co-branded landing pages at `/partners/[partner-name]` — **these routes already
exist** as partner profile pages, which makes this the cheapest funnel to stand up.

**Designed behaviour:** when a partner submits a lead, GHL tags it with the partner's ID and
sends automated milestone notifications back to the partner as the file progresses.

**Assessment.** Strategically the strongest of the two. It activates an asset the business
already published and gives partners the one thing they actually want — visibility without
chasing. See [icp-referral-partner](../03-audience-and-icp/icp-referral-partner.md).

> **Blocking compliance issue.** The design includes a notification of the form
> *"John's loan formally approved with [Lender]"*. **That discloses the client's identity,
> outcome and lender to a third party.** It cannot ship without the client's express,
> recorded consent.
>
> The safe default is a status update on *their referral*, with no client detail:
> *"The client you referred has progressed to formal approval."*
>
> **Consent capture is a prerequisite for launch, not a later fix.** Read
> [privacy-and-data](../07-compliance-and-guardrails/privacy-and-data.md) before building.

**Also unresolved:** no commercial terms for partner referrals are documented anywhere. A
portal that implies an arrangement which does not exist creates a problem. Confirm with Karlie.

## The funnels that should exist and are not designed

Three gaps, ranked by opportunity:

1. **Equity release.** The equity cashout calculator is already the best lead-capture asset in
   the business, with intent segmentation built in — and there is no funnel around it.
   Existing owners in two growth markets are the warmest cold audience available.
2. **First home buyer.** The highest-volume search intent, three named government schemes, two
   relevant calculators, and the warmest copy on the site — and no funnel.
3. **Sub-broker recruitment.** A completely separate business model on one unsupported page.
   See [sub-broker-offer](../02-offer-and-lending/sub-broker-offer.md).

## Status update — 11 Sep 2026

- Neither designed funnel has been built. The **lead-gen and qualification pipelines are parked**.
- What exists instead: the "Speak with a Broker" booking widget, short and full fact finds, a
  pre-approval document form, and a built-but-unconnected Instagram keyword DM automation. See
  [current-build-state](current-build-state.md).
- The **cold-list outreach** Karlie asked about has a consent blocker — see
  [privacy-and-data](../07-compliance-and-guardrails/privacy-and-data.md).
- The referrer-portal milestone notifications remain blocked on client consent, as above.

## Related

- [funnels-and-landing-pages](../08-channels-and-playbooks/funnels-and-landing-pages.md)
- [pipelines](pipelines.md) · [calendars-and-routing](calendars-and-routing.md)
