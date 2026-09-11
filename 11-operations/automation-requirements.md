---
id: automation-requirements
title: Automation requirements — rules the client has already set
type: system
status: approved
confidence: verified
source: Granola transcripts 26 Aug, 4 Sep and 9 Sep 2026; Karlie's emails "Login Portal" (fact find spec, 26 Aug 2026) and "Welcome Email" (9 Sep 2026); Asana onboarding tasks; Salestrekker credit guide template v102025
as_of: 2026-09-11
owner: Tumai (Team OS)
tags: [operations, automations, workflows, credit-guide, retention, comms-rules, internal]
---

# Automation requirements

The constraints any automation for TLS must respect, captured from the client's own words.
Stage structure is in [pipeline-decisions-log](pipeline-decisions-log.md).

> **Compliance runs through this file.** The credit guide rules are regulatory, and messaging
> rules are subject to [guardrails](../07-compliance-and-guardrails/guardrails.md).

## 1 · The step vocabulary

Tumai deliberately restricted the automation builder the client sees to a small set of step types:

**send email · send SMS · create task · send document · wait · decision · notify team ·
assign person · move to stage**

Every stage automation is specified as **trigger (top) → steps → goal (bottom)**. The client
defines trigger, goal and steps; Team OS builds, brands and tests.

**Wait steps are encouraged** — *"design things so that it looks like somebody is sending the
email, then they waited for a little bit, then they sent the text message."*

**Go-live protocol:** publish → run about a week with Michelle checking every send → review →
then add the advanced layer (signatures, documents, webhooks, invoicing).

## 2 · Client communication rules

**Milestones only.**
> I don't want clients notified every single time the tile moves along just the milestones.
> — Karlie, 9 Sep 2026

**Audience matters.**
> First home buyers. Yes, that's really good for them because they like to be in the loop. But a
> lot of my clients are not first time buyers… I could have commercial clients going through
> here as well. And the last thing they want is to be bombarded with reminders and SMSs and emails.

Design consequence: **frequency must vary by segment.** First home buyers get more updates;
commercial, investor and repeat clients get fewer. Suggested mechanisms: a segment field that
decision steps check, or separate paths.

**Internal notifications are fine at every stage** — one card drag can email the client, SMS the
client and notify the broker.

## 3 · Lead intake

- **Entry points:** the intake form (website or shared link), a booking on a broker calendar,
  or a manual "Add Opportunity". All three create the contact and the opportunity.
- **Standard:** brokers use the intake form even for phone enquiries.
- **New Lead trigger:** form completed. **Goal:** data captured, contact saved, moved to next stage.
- **Steps agreed 9 Sep:** confirmation email ("we got your enquiry") → **wait 1 minute** →
  **welcome + credit guide email**.
- **Brief target:** auto-reply within **60 seconds**.
- **Booking follow-up (proposed):** a preparation video after booking so clients arrive with
  payslips and ID.

## 4 · The credit guide — regulatory, non-negotiable

| Rule | Source |
|---|---|
| **Signed before any application is submitted** | Karlie, 4 Sep and 9 Sep |
| **Signed before the client sends payslips** | Karlie, 9 Sep |
| SFG (aggregator) wants it **signed at the very first interaction** | Michelle, 9 Sep: *"hi client… You need to sign a credit guide before we have another conversation."* |
| Date on the guide = **the date the client signed**, and it must precede submission | Karlie, 4 Sep |
| Deliver as **both attachment and link** — if the PDF fails to attach and there's no link, that's a breach | Tumai, 26 Aug |
| "From memory the law is that they've had **access** to the credit guide, not necessarily received it" | Michelle, 9 Sep — *unverified legal reading; confirm with SFG* |
| The tile **cannot leave Credit Guide Sent until the guide is signed**; the sent email is kept as timestamped evidence | Agreed, 9 Sep |

**Merge fields:** the current guide is a Salestrekker template (SFG version 102025) that merges
the **deal owner's** credit representative details. A rebuild must merge the **assigned broker's
CRN**, not hardcode the website footer's 477350:

| Broker | CRN (from settlement records) |
|---|---|
| Karlie Scharfenberg | 477350 |
| Kaiden Harrison | 570030 |
| Jessica Didovich-Lasalo | 576563 |

Template text: [sfg-credit-guide-template-v102025](../99-source-material/client-documents/sfg-credit-guide-template-v102025-RAW.md).

## 5 · Welcome email — client's existing template, verbatim

Currently sent from Salestrekker with the credit guide and privacy disclosure attached.
`{ticket.firstNameOfContacts}` is a **Salestrekker merge tag** and must be remapped
(e.g. `{{contact.first_name}}`).

> Hi {ticket.firstNameOfContacts},
>
> Welcome to The Loans Suite we're so excited to have you on board! 🥳
>
> Thank you for trusting us to guide you on your finance journey. Attached are our Privacy
> Disclosure and Credit Guide for your records. There's no need to print these documents, as
> we'll send you a digital version to review and sign shortly.
>
> A member of our team will be in touch with you soon to outline the documents we'll need and to
> book an appointment with one of our brokers to get things underway.
>
> We're here to make the process smooth, simple, and maybe even a little bit fun. Yes, finance can
> be fun — especially with us. 😄
>
> If you have any questions or need a hand with anything in the meantime, simply reply to this
> email or give us a call. We've got your back every step of the way.
>
> Cheers,
>
> Karlie, Kaiden, Jess, Michelle, Reema, Emily & Phoebe
> The Loans Suite Team

**Voice note:** this is the client's own transactional register — warmer and more playful
(two emoji, "finance can be fun") than the marketing guidance in
[brand-voice](../04-voice-and-messaging/brand-voice.md). Use it as the model for onboarding and
milestone emails. It also uses "journey", which marketing copy avoids; in client transactional
email it's the client's own word and acceptable.

## 6 · Fact find — Karlie's required fields (26 Aug 2026)

Sent **after** the initial conversation, not at first contact. The client fills it in via a link,
**signs the credit guide electronically at the end**, and the system generates a **downloadable
PDF**. Whether the PDF goes to the client or stays internal is undecided.

First / middle / last name · DOB · phone · email · address and date moved in · driver licence
(number, card number, expiry) · next of kin · dependants · employment (PAYG or self-employed,
start date, employer, job title, HR contact) · assets (house, car, super, bank accounts) ·
liabilities (home loan, credit cards, personal loans, HECS, other) · expenses (food/groceries,
clothing, phone, entertainment, childcare, eating out, sickness & life insurance, health
insurance, house insurance, motor insurance, primary residence running costs, other)

*Internal review (2 Sep) corrected this: next of kin isn't standard AU practice; liabilities need
amount, term, rate and repayment.*

## 7 · Servicing, documents, hold

- **Servicing:** manual in **Quickli**. Future goal: send deal data to Quickli automatically and
  get the result back in ~5 minutes.
- **Document collection:** **manual requests for now.** When built, the checklist must be
  **conditional on borrower type** (investor vs self-employed vs PAYG owner-occupier) via tick
  boxes, and must stop reminding once documents arrive another way.
- **Uploads land on the contact record** via forms, so documents stop getting stuck on laptops.
  OneDrive remains the document store for Salestrekker submission.
- **On Hold** parks deals being shaped or placed. Non-qualifying clients: 3- or 6-month hold,
  or closed.

## 8 · Stage checklists

> The thing is nothing moves ahead to the next stage until the checklist is completed. — Karlie

The Salestrekker prelim stage carries about **nine checklist items**, e.g. add pricing to the
client folder, credit guide signed, ID certified. Karlie will refine the list before import.
Purpose beyond compliance: a new admin can take over within days.

## 9 · Post-settlement and retention

**Manual settlement update (decided):** when the bank's settlement email arrives, admin
(Phoebe or Michelle) updates the OS tile — **date, loan amount, account number, interest rate,
settlement details** as a running-log note — and closes the file. Banks' email formats differ,
so parsing isn't reliable. The manual touch doubles as an audit and contact-details check.

**Cadence (9 Sep):** 30-day broker call · 90-day check-in · 6-month SMS · 12-month review,
generated from the **settlement date** and surfaced as dashboard tasks.

**Look-ahead required** — Michelle:
> Can I then go into what's coming up in the next 30 days and give myself a task of the retention
> leads?… If I'm not notified till the day of that might be tricky.

**Advocacy layer:** Google review request, video testimonial request, referral ask, and a
**pre-emptive rate review** before the client shops around.

**Why it matters — Michelle's ActivePipe story (26 Aug):**
> I had noticed a client had… clicked in and open the latest RBA rate… twice. So I kind of said to
> Karlie… give her a ring… She actually had gone direct to the bank and fixed for two years.

Engagement signals (email opens, page visits) should trigger a broker call **before** the client
calls their bank. Engagement scoring is not yet built.

## 10 · Marketing automations already requested

| Request | State and constraint |
|---|---|
| **Cold list of ~250 leads** (from Dylan, generated by another broker, never contacted, Australia-wide) | Karlie: *"I'm not going to sit here and ring 250 clients to get told no by 249 of them."* Wants SMS/email to surface the interested ones. Keep in a **separate smart list**. Recommended: 4-email breakup sequence over two weeks with open/click branching, from a **warmed separate mailbox**. **Compliance blocker — see [privacy-and-data](../07-compliance-and-guardrails/privacy-and-data.md): these people haven't consented to TLS messages** |
| Instagram keyword DM → lead magnet | Built, not connected |
| Post-booking prep video | Proposed |
| Staff compliance alerts (MFAA, CPD, licence expiry) on staff profiles, visible to Karlie and Michelle only | Discussed 18 Aug |
| Manually posted Instagram content logged in the Social Planner as "✅ Posted Manually" drafts | Process sent to Emily, 5 Sep |

## 11 · Data entry conventions the automations depend on

- **Opportunity name = customer name**, not "Refi".
- **Tags only from Karlie's master list** (examples: Refinance, Commercial, SMSF, Investment,
  Construction, Asset Finance; LVR bands such as +80% suggested).
- **Business name / ABN fields** for self-employed and company borrowers; a commercial loan in a
  company name links back to the individual.
- **Couples:** one opportunity; each person is a separate contact.
- Notes auto-timestamp and attribute — no manual date logging.

## 12 · What the live account can't support yet — API read, 11 Sep 2026

Check these before specifying any automation. Detail: [ghl-data-audit](ghl-data-audit.md).

- **Retention off the settlement date** — `opportunity.date_settled` is **empty on all 416
  opportunities**. Back-fill it first.
- **The credit guide CRN merge** — there's no broker CRN field, and the fact find's consent text
  hardcodes 477350 under Queens of Finance.
- **The credit guide gate** — `contact.credit_guide_issued` and every other consent field are empty
  on all 1,882 contacts. For existing clients the evidence sits in Salestrekker.
- **"Field is empty" branches** — migrated financial fields hold 0 instead of blank.
- **Per-broker routing and notifications** — 88% of opportunities are owned by Karlie; 37 are unassigned.
- **Tag-triggered workflows** — the master tag list isn't applied; `rfi` and `refinance` both exist.
- **"Opportunity name = customer name"** — 218 tiles are named "… retention".
- **Stage triggers** — both stage workflows are drafts, and only 2 of 21 workflows are published, so
  the build can start clean.

## Related

- [ghl-account-map](ghl-account-map.md) — workflow, stage and field IDs
- [pipeline-decisions-log](pipeline-decisions-log.md) · [current-build-state](current-build-state.md)
- [nccp-and-best-interests-duty](../07-compliance-and-guardrails/nccp-and-best-interests-duty.md)
- [email-sequences](../08-channels-and-playbooks/email-sequences.md) · [sms](../08-channels-and-playbooks/sms.md)
