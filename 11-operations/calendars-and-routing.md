---
id: calendars-and-routing
title: Calendars, booking and team routing
type: system
status: approved
confidence: inferred
source: appointment design from Karlie's GHL configuration (Aug 2026); live booking links extracted from theloanssuite.com.au markup. The live links are verified; the routing design is a proposed target state.
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

## Status update — 11 Sep 2026

The OS calendar build is under way and supersedes much of the "target state" above:

- **Outlook sync** connected for most of the team; Kaiden outstanding until he returns 16 Sep.
- **Teams video** blocked pending Microsoft admin approval through Trisarmi (~$55 per IT call) —
  plan is one whole-team approval session.
- **Booking types per broker:** online, phone, face-to-face at the office address. **Jess (NSW)**
  gets a travel-to-client option.
- **Round-robin** calendar with a staff dropdown is being configured.
- **"Speak with a Broker" booking widget** is live on `link.teamos.ai`, tagging and pipelining new
  bookings. Waiting on the website embed.
- The Calendly and TidyCal links remain in use on the website until then.

Detail: [current-build-state](current-build-state.md).

## Related

- [pipelines](pipelines.md) · [funnels-and-landing-pages](../08-channels-and-playbooks/funnels-and-landing-pages.md)
- [systems-and-ids](../01-company/systems-and-ids.md)
