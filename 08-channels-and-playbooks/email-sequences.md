---
id: playbook-email
title: Playbook — email sequences
type: playbook
status: approved
confidence: verified
source: sequence structure derived from the pipeline stages in 11-operations; voice and claims from the verified layers
as_of: 2026-08-26
owner: Emily Baulch (Marketing)
tags: [playbook, email, nurture, sequences, automation]
---

# Playbook — email sequences

## Purpose

Write an automated email sequence — nurture, onboarding, reactivation or lifecycle — triggered
by a pipeline stage.

## Load order

1. [guardrails](../07-compliance-and-guardrails/guardrails.md)
2. [banned-language](../04-voice-and-messaging/banned-language.md)
3. [brand-voice](../04-voice-and-messaging/brand-voice.md)
4. [messaging-pillars](../04-voice-and-messaging/messaging-pillars.md) — one per sequence
5. The ICP file
6. [11-operations/pipelines](../11-operations/pipelines.md) — **the trigger stage**
7. [09-content-banks/subject-lines](../09-content-banks/subject-lines.md)
8. [faq](../10-faq-and-objections/faq.md)

## Formats and lengths

| Type | Words | Emails | Cadence |
|---|---|---|---|
| Nurture (education) | 200–350 | 5–7 | Every 3–4 days |
| Onboarding (post-settlement) | 150–250 | 5 | Day 1, 7, 30, 180, 300 |
| Lifecycle (pre-approval) | 120–200 | 3 | Day 30, 60, 75 |
| Construction stage updates | 100–180 | Up to 10 | Per drawdown |
| Reactivation | 150–250 | 3 | Day 1, 7, 21 |
| Single broadcast | 250–450 | 1 | — |

**Shorter than instinct suggests.** These are from a broker, not a publisher.

## Universal structure

1. **Subject** — 4–8 words, specific, no clickbait, no emoji
2. **First line** — the reason this email exists. It is also the preview text; make it work
3. **One idea.** One. If there are two, that is two emails
4. **The useful part** — a thing they didn't know, phrased in the client's interest
5. **One CTA** — a link to a calculator, a booking, or a reply. Never three
6. **Sign-off from a person**, not "The Loans Suite Team". Name the broker who owns the file
7. **Footer** — both compliance lines and an unsubscribe

## The sequences the pipelines already justify

These are not hypothetical — each maps to a real stage in
[pipelines](../11-operations/pipelines.md), which means the trigger already exists.

| Sequence | Trigger stage | Why it converts |
|---|---|---|
| **Pre-approval lifecycle** (3) | Pipeline 4, day 30/60/75 | Deadlines are real, the audience is warm, and day 91 is when they're lost |
| **Post-settlement onboarding** (5) | Pipeline 3, `Settled` | Peak emotion. **This is where reviews and referrals come from** |
| **Construction stage updates** (10) | Pipeline 5, each claim | Months of natural contact points, genuinely useful |
| **Nurture pool** (6) | Pipeline 1, `On Hold / Nurture` | People who wanted to buy and couldn't yet. Highest-value neglected list |
| **Rate health check** (3) | Pipeline 6, month 10 | The Loan Health Check, operationalised |
| **NPW reactivation** (3) | Pipeline 3, `HOLD / NPW` | Deals that died for reasons that may have changed |

## Do

- Write from a named broker, in first person
- Lead with what the reader gets, not what we want
- Use the client's real vocabulary — *fast, simple, explained, sorted* — not *strategy, structure, solutions*
- Ask a question that invites a reply. Replies are the cheapest conversion event there is
- Keep the P.S. — it gets read
- Time sends to the pipeline event, not to a calendar

## Don't

- Don't send a "rate update" email implying we have rates
- Don't reference the clawback window as a reason to talk. Ever
- Don't use "Quick question" or "Just checking in" as a subject
- Don't attach anything
- Don't mention a competitor
- Don't send anything to a hardship contact except a support-oriented message
- Don't put more than one CTA in an email

## Pre-send checklist

- [ ] One idea, one CTA
- [ ] Subject under 8 words, no clickbait, no emoji
- [ ] Sent from a named person
- [ ] Zero banned words; no rate, saving or approval language
- [ ] Every claim traces to a `verified` file
- [ ] Trigger stage named, and the sequence exits when the contact moves stage
- [ ] Unsubscribe present; both compliance lines in the footer
- [ ] **Hardship check:** if the audience may include distressed borrowers, the tone is
      supportive and the National Debt Helpline is offered
- [ ] Australian English

## Worked example — post-settlement onboarding, email 1 of 5

**Trigger:** Pipeline 3 → `Settled`. **Pillar 2.** From the broker who owned the file.

---

**Subject:** Your loan has settled

Hi {{first_name}},

That's it — your loan settled today. The property is yours.

A few things worth knowing now that it's done:

Your first repayment will come out on {{date}}. Have a look at the account it's coming from
in the next day or two and make sure it's set up the way you expect — it's the one thing
worth checking early.

Your loan documents and settlement statement are in your portal. Worth keeping somewhere you
can find them.

And that's genuinely all you need to do right now.

One thing I'd ask: if the process worked for you, a short Google review helps other people
find us more than anything else we do. Here's the link — it takes about a minute.
{{review_link}}

If anything looks off, or you have a question in six months, just reply to this. I'd rather
you asked.

{{broker_first_name}}
{{broker_title}}, The Loans Suite
{{broker_phone}}

P.S. We'll check in around the six-month mark to make sure the loan is still doing what it
should. Nothing you need to do — we'll come to you.

---

**Checklist run:** one idea (you've settled, here's what's next) ✓ · one CTA, and it's the
review ask at peak emotion ✓ · named broker ✓ · no rate or claim ✓ · sets up the month-6 touch
so it isn't a cold call later ✓ · invites a reply ✓ · 190 words ✓

**Why the review ask sits here:** the review gap against competitors is the most urgent proof
problem in the business, and settlement day is the moment of maximum goodwill.
See [competitor-borro](../06-competitors-and-market/competitor-borro.md).
