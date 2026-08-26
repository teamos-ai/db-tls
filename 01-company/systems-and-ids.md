---
id: systems-and-ids
title: Systems, platforms and IDs
type: company
status: approved
confidence: verified
source: theloanssuite.com.au raw HTML — link and script extraction across 71 pages (Aug 2026)
as_of: 2026-08-26
owner: Karlie Scharfenberg
tags: [systems, ids, stack, integrations, booking, crm]
---

# Systems, platforms and IDs

Extracted from the live site's markup. Anything not observable in the markup is marked.

## Website

| Item | Value |
|---|---|
| Platform | **WordPress multisite**, hosted/managed by **BrokerKit** (`brokerkit.com.au/tlsa/`) |
| Page builder | **Breakdance** 2.8.1 |
| SEO plugin | **Yoast** |
| Analytics | **Google Tag Manager** |
| Uploads path | `/wp-content/uploads/sites/110/` — this brand is **site 110** on the BrokerKit network |
| Fonts | Self-hosted **Canela Thin** and **Stack Sans Text** |

`tlsa` = The Loans Suite Australia. Practical consequence: **the site is on a broker-vertical
managed platform, not a bespoke build.** Anything we want to change on it goes through
BrokerKit's constraints, not a developer.

## Booking

| Broker | Tool | Link |
|---|---|---|
| Karlie Scharfenberg | Calendly | `calendly.com/loanstratergy/loan-strategy-session` |
| Kaiden Harrison | Calendly | `calendly.com/kaiden-tlsga/30min` |
| Jessica Didovich-Lasalo | TidyCal | `tidycal.com/1kg2ygy/initial-client-meeting-sydney-broker` |

**Two booking tools across three brokers, on two different accounts.** The Calendly slug
`loanstratergy` contains a typo that is live and public. Consolidating booking is a real
operational improvement and a prerequisite for any round-robin routing —
see [11-operations/calendars-and-routing](../11-operations/calendars-and-routing.md).

## Client-facing applications

| System | URL | Purpose |
|---|---|---|
| **Own Your Loan** | `app.ownyourloan.com.au/theloanssuite` | Client portal / fact find — the "Start your application here" destination |
| **MovingHub** (Utilihub) | `au-apps.utilihub.io/form-builder-widgets/connect/BH7VKH7YSA/tls` and `.../EBJ31RV85C/tls` | Utility connections and energy comparison, embedded at `/movinghub` |
| **Vision Abacus** | `visionabacus.net/Tools/B3/SuiteA/A100/Income_Annualisation_Calculator/FBAA` | Third-party calculator engine behind the annualised income tool |

Two distinct MovingHub widget IDs are embedded — one for "Compare Energy Plans", one for
"Moving House".

## CRM and operations

**GoHighLevel** and **Salestrekker** run the pipelines; the loan workflow also touches
**Quickli** (serviceability), **ApplyOnline / AOL** (lodgement) and **PEXA** (settlement).
None of this is visible in the website markup — it comes from Karlie's production systems.
Full detail in [11-operations/pipelines](../11-operations/pipelines.md).

**No GHL location ID, calendar ID, form ID or workflow ID is recorded anywhere in the
sources.** Capturing them is a roadmap item — without them, no automation work can be
specified precisely.

## Social

- Instagram **@the.loans.suite**
- Facebook **facebook.com/theloanssuitesydney**

No LinkedIn, TikTok or YouTube in the sources.

## Blog taxonomy

Six live categories, from the navigation markup:
`finance-101` · `home-loans` · `business-finance` · `investing` · `saving-tips` · `smsfs`

Plus four **partner/service** archives used to group referral partners:
`services/accounting` · `services/conveyancing` · `services/credit` · `services/real-estate`

**171 blog posts** are indexed on the site. See
[blog-and-seo](../08-channels-and-playbooks/blog-and-seo.md).

## Related

- [site-map-and-routes](site-map-and-routes.md) · [11-operations/pipelines](../11-operations/pipelines.md)
- [calculators-and-tools](../02-offer-and-lending/calculators-and-tools.md)
