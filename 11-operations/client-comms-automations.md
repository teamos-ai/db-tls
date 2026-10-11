---
id: client-comms-automations
title: Client-comms automations — the approved email and SMS copy, and the rules behind it
type: system
status: approved
confidence: verified
source: Copy written and approved with Ariki Meroiti, 11 Oct 2026. Custom fields read back from the GoHighLevel API (location vAX1ry0bjuYiAzEYFS9X) on 11 Oct 2026. Booking links supplied by Ariki and checked live (HTTP 200) on 11 Oct 2026.
as_of: 2026-10-11
owner: Ariki (Team OS)
tags: [operations, automations, email, sms, calendars, credit-guide, fact-find, nurture, ghl, internal]
---

# Client-comms automations

The client-facing emails and texts for three GoHighLevel automations, approved on
**11 Oct 2026**. This file records **what was decided and why**. The copy itself, as
paste-ready HTML and SMS with a review page, lives in **`teamos-ai/ds-tls` at
`docs/automation-copy/`**. That folder is the source of truth for wording. Edit it there and
rebuild (`node build.mjs`), never in GHL alone.

> **Where these rules differ from the playbooks:** the sign-off and the evergreen rule below are
> Ariki's decisions of 11 Oct 2026 for GHL automation emails. They override
> [email-sequences](../08-channels-and-playbooks/email-sequences.md) rule 6 ("sign-off from a
> person") for these messages only. [guardrails](../07-compliance-and-guardrails/guardrails.md)
> and [banned-language](../04-voice-and-messaging/banned-language.md) still apply in full.

## The rules decided on 11 Oct 2026

1. **Team sign-off, one number.** Every automation email signs off as **"The Loans Suite Team"**,
   with **1300 741 077** and the website. No email or text names a staff member, quotes a mobile
   number or gives a personal email address, and no message speaks as "I". Every phone prompt goes
   to 1300 741 077. These are general communications, not one-to-one broker email.
2. **The booked person is named through custom fields.** The only staff name a client sees is the
   person they booked, filled in by merge field (see below).
3. **No Credit Guide button.** The Credit Guide goes out automatically by e-signature (Documents
   & Contracts), **one email per applicant**. Some files have two signers. The automation emails
   therefore say "your Credit Guide is already in your inbox". They cover how to find it, joint
   applicants, and calling 1300 741 077 if it hasn't arrived.
4. **Cold Archive Nurture is evergreen.** It runs for years, so it carries **no market statistic,
   rate, date, scheme, price cap or figure of any kind**. Dated market news belongs in the
   [newsletter](../08-channels-and-playbooks/newsletter.md). Each email is a conversation starter:
   its job is to get an archived contact with a new need to reply, book or make a new request.
   The ds-tls build fails if any digit other than 1300 741 077 or the National Debt Helpline gets
   into this sequence.
5. **Copy gates.** The build rejects banned language, staff names, a broker speaking as "I",
   personal contact details and non-GSM characters in SMS. It also flags subjects outside 4–8
   words.

## The three automations

### A · Calendar bookings — all six personal calendars

Replaces the actions in the published workflow **"Recipe – Appointment Confirmation + Reminder"**
(`e951e18c-96e8-4b8f-a7c9-608efb248c89`).

| # | When | Channels | Subject |
|---|---|---|---|
| A1 | On booking, after a 1-minute wait (so the custom fields are filled) | Email + SMS | You're booked in with {{contact.booked_with_first_name}} |
| A2 | 24 hours before the start | Email + SMS | See you tomorrow at {{appointment.only_start_time}} |
| A3 | 2 hours before the start | SMS (email optional) | You're on at {{appointment.only_start_time}} today |

No documents are asked for: the Credit Guide must be signed before payslips
([automation-requirements](automation-requirements.md) §4). Each email has reschedule and cancel
links, plus add-to-calendar links in A1. Workflow goals: appointment cancelled, or marked no-show.

### B · Cold Archive Nurture — four emails, one every 90 days

A new workflow, **"Cold Archive Nurture"**, triggered by the tag `cold-archive-nurture`.

| # | Day | Subject | The question it asks |
|---|---|---|---|
| B1 | 0 | Still here when you need us | Has anything changed? (job, family, plans) |
| B2 | 90 | Is your loan still pulling its weight? | Three self-check questions; carries the hardship referral |
| B3 | 180 | What's next on your list? | What are you planning? A one-line reply is enough |
| B4 | 270 | Should we keep in touch? | One click on "Keep me posted" adds the tag `newsletter`; silence ends marketing email |

Goals (exit): reply, booking, form submission or new opportunity, each with a task for the owner.
Any button click creates the task "Warm signal — call within 1 business day".

**Never enrol** ([privacy-and-data](../07-compliance-and-guardrails/privacy-and-data.md)):

- Dylan's ~250 leads from another broker (no Spam Act consent)
- The 314 `employer` contacts
- Hardship contacts, DND or unsubscribed contacts, and anyone with an open opportunity

### C · Pre-Submission — one workflow per stage

Rebuilds the draft **"Pre-Submission⚡️"** (`cd7dbb10-1eb1-40ea-add8-e84e33e424aa`). The stage
change is the trigger, so dragging a card fires the right messages.

| # | Stage | When | Channels | Subject |
|---|---|---|---|---|
| C1 | New Lead⚡️ | Immediately; SMS within 5 minutes | Email + SMS | We've got your enquiry |
| C2 | New Lead⚡️ | 1 minute after C1 | Email | Welcome to The Loans Suite |
| C3 | Credit Guide Sent | 2 minutes after the e-signature email | Email + SMS | Your Credit Guide is in your inbox |
| C3·R1 | Credit Guide Sent | 2 business days, if unsigned | Email + SMS | Your Credit Guide still needs signing |
| C3·R2 | Credit Guide Sent | 4 business days, if unsigned; then a task to call | SMS | — |
| C4 | Fact Find | On stage change | Email + SMS | Next step: your fact find |
| C4·R1 | Fact Find | 2 business days, if not submitted | SMS + email | Your fact find is still open |
| C4·R2 | Fact Find | 5 business days, if not submitted; then a task to call | SMS | — |

Two chases at most, on weekdays in business hours. The C4 button goes to the "Full Fact Find"
survey: `https://client.theloanssuite.com.au/widget/survey/XR1IVxjsKXiQNj6ANtmI`. The card leaves
Credit Guide Sent only when **every** applicant has signed.

This set supersedes the four Pre-Submission messages drafted in ds-tls section 26 on 9 Oct 2026.
That draft was never committed.

## Custom fields — created 11 Oct 2026

Ariki created these on 11 Oct 2026, and they were read back from the API the same day. All three
are contact-level text fields in folder `A4HpqzPw3KcBxor1QKS8`.

| Field | ID | Merge field | Set by |
|---|---|---|---|
| Booked With | `Y3mubeUpZX4l1Alu0ZiS` | `{{contact.booked_with}}` | Six "Booked With · <name>" workflows, one per calendar |
| Booked With First Name | `8barqSygN4me0K6RKG9g` | `{{contact.booked_with_first_name}}` | Same six workflows |
| Broker Booking Link | `GfnFLyXvJukfBLBpQT0s` | `{{contact.broker_booking_link}}` | Cold Archive Nurture, from the assigned user (Karlie's link if unassigned) |

**The six "Booked With" workflows** were built by Ariki on 11 Oct 2026. Each one works like this:

- **Trigger:** Customer Booked Appointment, with an *In calendar* filter for one calendar.
- **Action:** Update Contact Field, setting both Booked With fields.
- **Setting:** Allow re-entry turned on.

The calendar's own name ("Karlie Scharfenberg's - Book a Call") reads badly mid-sentence, which is
why plain-name fields exist at all.

**One limit:** the fields hold the most recent booking. If one contact books two different people
at the same time, the earlier booking's reminders name the later person.

**Existing fields that are *not* used here:**

- `contact.calendar_id`: a 2025 snapshot leftover
- `contact._booking_status`: holds only Not Booked or Booked Appointment
- `contact.ic_broker`: lists the three brokers with CRNs only

## Staff booking calendars — values for the fields

| Calendar | Calendar ID | Booked With | First name | Booking link |
|---|---|---|---|---|
| Karlie Scharfenberg's - Book a Call | `ttBIJ9ZcPx4pglw13n5L` | Karlie Scharfenberg | Karlie | `https://client.theloanssuite.com.au/widget/booking/ttBIJ9ZcPx4pglw13n5L` |
| Kaiden Harrison - Book A Call | `9Ks6X3xXgrxG6lOglBw2` | Kaiden Harrison | Kaiden | `https://client.theloanssuite.com.au/widget/booking/9Ks6X3xXgrxG6lOglBw2` |
| Jessica Didovich-Lasalo - Book A Call | `tmWq7uVnHvixxtKnhqup` | Jessica Didovich-Lasalo | Jess | `https://client.theloanssuite.com.au/widget/booking/tmWq7uVnHvixxtKnhqup` |
| Michelle Cairncross - Book A Meeting | `WUsx2yheYHdBD9jhEei7` | Michelle Cairncross | Michelle | `https://client.theloanssuite.com.au/widget/booking/WUsx2yheYHdBD9jhEei7` |
| Emily Baulch - Book A Meeting | `bOgn4uPigM2KwhgzTQAG` | Emily Baulch | Emily | `https://client.theloanssuite.com.au/widget/booking/bOgn4uPigM2KwhgzTQAG` |
| Reema Maharjan - Book A Meeting | `QDzyrEK3XqWTakIj7DnJ` | Reema Maharjan | Reema | `https://client.theloanssuite.com.au/widget/booking/QDzyrEK3XqWTakIj7DnJ` |

The booking links use the `/widget/booking/<calendarId>` form. Ariki supplied them on 11 Oct 2026,
and all six returned HTTP 200 that day.

## Assets

- **Email header logo:** the reversed horizontal lockup as a PNG, hosted in the GHL Media Library
  at `https://assets.cdn.filesafe.space/vAX1ry0bjuYiAzEYFS9X/media/6acb17acc478ac55359bde8e.png`.
  It is a PNG because Gmail and Outlook drop SVG.
- **Meet the team** (welcome email button): `https://theloanssuite.com.au/about/`.

## Open before go-live

- **Meeting locations.** None of the six calendars has one, so the "Where" row in A1–A3 is blank
  until it is set ([calendars-and-routing](calendars-and-routing.md), defect 1).
- **1300 741 077 must be answered or forwarded.** It was untested on 9 Sep, and every automation now
  points at it.
- **Time zones.** NSW moved to daylight saving on 4 Oct 2026. Set Jess's and Michelle's calendars to
  Australia/Sydney.
- **SFG question.** The 26 Aug rule was "attachment *and* link". The e-signature email now provides
  the link. Confirm with SFG whether a PDF attachment is still expected.
- **Fact find consent text** still names Queens of Finance and hard-codes CRN 477350
  ([ghl-data-audit](ghl-data-audit.md)).
- **Booking consent line.** It is still GHL's default marketing-consent wording
  ([privacy-and-data](../07-compliance-and-guardrails/privacy-and-data.md)).
- **"Keep me posted" trigger link.** It needs creating in GHL before B4 goes live.

## Related

- [automation-requirements](automation-requirements.md) · [pipeline-decisions-log](pipeline-decisions-log.md)
- [ghl-account-map](ghl-account-map.md) · [calendars-and-routing](calendars-and-routing.md)
- [email-sequences](../08-channels-and-playbooks/email-sequences.md) · [sms](../08-channels-and-playbooks/sms.md)
