---
id: calendars-and-routing
title: Calendars, booking and team routing
type: system
status: approved
confidence: inferred
source: live OS calendar settings from the GoHighLevel API (11 Sep 2026); website booking links extracted from theloanssuite.com.au markup; routing design from Karlie's GHL planning documentation (Aug 2026). The API settings and live links are verified; the routing design is a proposed target state.
as_of: 2026-09-11
owner: Karlie Scharfenberg
tags: [operations, calendars, booking, routing, ghl]
---

# Calendars, booking and team routing

## What exists today — verified

Three brokers, **two different booking tools, on separate accounts**:

| Broker | Tool | Link |
|---|---|---|
| Karlie Scharfenberg | Calendly | `calendly.com/loanstratergy/loan-strategy-session` |
| Kaiden Harrison | Calendly | `calendly.com/kaiden-tlsga/30min` |
| Jessica Didovich-Lasalo | TidyCal | `tidycal.com/1kg2ygy/initial-client-meeting-sydney-broker` |

**Consequences of the current state:**

- **No round-robin is possible.** A "Book a call with a broker" CTA cannot distribute — it has
  to send the visitor to a named person, which means the visitor picks their broker based on
  nothing.
- **No load balancing.** One broker can be booked out while another is idle.
- **The Calendly slug `loanstratergy` contains a live public typo.**
- **Any paid campaign driving to "book a call" is guessing** which calendar to send traffic to.

**Consolidating booking is a prerequisite for paid acquisition**, not a nice-to-have. It is
the cheapest high-impact operational fix available.

## The target state

> **Tier note:** the design below is `inferred` — a proposed target from the operations
> planning, not a live configuration. Confirm before building.

**Appointment types**

1. **15-minute Loan Strategy Discovery Call** (phone or video) — round-robin across Jess,
   Kaiden and Karlie
2. **60-minute Credit Assessment & Scenario Review** — routed to the assigned broker
3. **Settlement document signing & verification** — in office or digital

**Routing rules** — skill and geography based:

- NSW residential → Jessica
- QLD residential → Kaiden
- Commercial, asset finance, SMSF, complex or high-value → Karlie
- Overflow on residential → round-robin

**Buffers and protection**

- 15 minutes before, to review borrowing capacity
- 30 minutes after, for file notes
- A daily cap on discovery calls per broker, to protect packaging blocks

## What this means for marketing

- **Every CTA must know where it routes.** A campaign targeting Penrith should book Jess; a
  Moreton Bay campaign should book Kaiden; a business-finance campaign should book Karlie.
  Today, none of that is possible from a single link.
- **The 15-minute discovery call is the conversion event.** All lead-gen optimises to it.
- **A named, time-bounded offer converts better than "book a call."** The
  **Loan Health Check** — a named offer with no page attached — is the obvious candidate,
  and would answer Borro's "Free Loan Assessment in 30 Minutes" without matching their
  outcome language. See [competitor-borro](../06-competitors-and-market/competitor-borro.md).

## Live OS calendars — verified from the API, 11 Sep 2026

Six calendars are active, one per person. The website still links to Calendly and TidyCal.

| Calendar | Open hours (location time) | Max per day | Look Busy | Books the contact to them |
|---|---|---|---|---|
| Karlie Scharfenberg's - Book a Call | Mon & Fri 10:00–15:00 · Tue–Thu 10:00–19:00 | 2 | off | no |
| Kaiden Harrison - Book A Call | Mon–Fri 9:00–19:00 | 3 | **60%** | no |
| Jessica Didovich-Lasalo - Book A Call | Mon–Fri 9:30–17:30 | 3 | **60%** | no |
| Michelle Cairncross - Book A Meeting | **none set** | 3 | **60%** | **yes** |
| Emily Baulch - Book A Meeting | **none set** | 1 | **60%** | **yes** |
| Reema Maharjan - Book A Meeting | **none set** | 3 | **60%** | **yes** |

**Common to all six:**
- 30-minute slots every 30 minutes, 15-minute buffers before and after.
- Earliest booking **2 days** out; latest **2 weeks** out.
- Auto-confirm on, with reschedule and cancel allowed and Google invites sent.
- No intake form; default details collected.

IDs and slugs: [ghl-account-map](ghl-account-map.md).

**What's wrong with them:**

1. **No meeting location on any calendar.** The client isn't told whether it's a phone call, a video
   call or the office. The decision was online, phone and face-to-face, plus travel-to-client for Jess.
2. **Look Busy hides 60% of open slots** on five of six calendars. Brokers look booked out when they
   aren't.
3. **Two days' minimum notice.** A new lead can't talk to anyone for 48 hours, against the brief's
   60-second response target.
4. **Michelle, Emily and Reema have no open hours set.** They are probably unbookable. `inferred` —
   confirm in the UI.
5. **No calendar notifications.** The one published "Appointment Confirmation + Reminder" workflow
   (Sep 2025) may cover this, but its trigger can't be read through the API.
6. **Booking reassigns the contact to support staff.** Booking Michelle, Emily or Reema makes them
   the contact owner. The broker calendars don't do this.
7. **The booking consent line is GHL's generic default** — *"I confirm that I want to receive content
   from this company…"* — which bundles marketing consent into a booking. See
   [privacy-and-data](../07-compliance-and-guardrails/privacy-and-data.md).
8. **No round-robin is active.** All five round-robin calendars are inactive Team OS templates with no
   members.
9. **Timezone risk** (`inferred`): the account runs on Australia/Brisbane. From 4 Oct 2026, NSW
   clocks move to AEDT, so Jess's and Michelle's hours will display an hour off unless calendar or
   user timezones are set.

Outlook sync is connected for most of the team, with Kaiden outstanding until 16 Sep. Teams video
needs Microsoft admin approval through Trisarmi (~$55 per IT call) *(meetings)*.

Detail: [current-build-state](current-build-state.md).

## Related

- [pipelines](pipelines.md) · [funnels-and-landing-pages](../08-channels-and-playbooks/funnels-and-landing-pages.md)
- [systems-and-ids](../01-company/systems-and-ids.md)
