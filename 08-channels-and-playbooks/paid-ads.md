---
id: playbook-paid-ads
title: Playbook — paid ads
type: playbook
status: approved
confidence: verified
source: platform financial-services advertising policies (Meta, Google — as at Aug 2026); the verified compliance and offer layers
as_of: 2026-08-26
owner: Emily Baulch (Marketing)
tags: [playbook, paid, meta, google, advertising, compliance-critical]
---

# Playbook — paid ads

> **Every paid ad needs Karlie's sign-off.** Spend plus a regulated product plus platform
> policy — three ways to get it wrong. See
> [approval-rules](../07-compliance-and-guardrails/approval-rules.md).

## Purpose

Write ad copy for Meta or Google search, driving to a landing page or booking.

## Load order

1. [guardrails](../07-compliance-and-guardrails/guardrails.md)
2. [banned-language](../04-voice-and-messaging/banned-language.md)
3. The ICP for the target audience
4. [funnels-and-landing-pages](funnels-and-landing-pages.md) — **the destination must exist first**
5. [11-operations/calendars-and-routing](../11-operations/calendars-and-routing.md) — where the booking goes
6. [09-content-banks/hooks-and-openers](../09-content-banks/hooks-and-openers.md)

## The platform layer of risk

Financial services advertising carries platform restrictions **on top of** Australian credit
regulation:

- **Meta** restricts financial-services ads and prohibits ads implying knowledge of a user's
  financial situation. **Never write "Struggling with repayments?"** as targeting copy —
  it implies personal financial knowledge and gets accounts restricted, not just ads rejected.
- **Google** requires advertiser verification for financial services in Australia and
  restricts certain personalised-advertising categories.
- Both prohibit unsubstantiated financial claims. Every guardrail in
  [guardrails](../07-compliance-and-guardrails/guardrails.md) is also a platform rule.

**Practical effect:** the mortgage-stress angle, which is strategically strong, is
**advertising-restricted**. Rework it from the reader's implied distress to a neutral
service framing: not *"Struggling with your repayments?"* but *"A 15-minute review of your
current home loan."*

## Formats

| Platform | Element | Limit |
|---|---|---|
| Meta | Primary text | 125 chars before truncation |
| Meta | Headline | 40 chars |
| Meta | Description | 30 chars |
| Google | Headline ×15 | 30 chars each |
| Google | Description ×4 | 90 chars each |
| Google | Sitelinks | 25 chars + two 35-char lines |

## Universal structure — Meta

`[Situation, neutrally stated] + [What we do] + [What it costs — nothing] + [One CTA]`

## Universal structure — Google

Headlines should cover: the service, the differentiator (60+ lenders), the cost (no cost),
the location (Brisbane / Sydney), and the action. Descriptions carry the hedged detail.

## Do

- State the service, not the reader's problem
- Lead with "costs you nothing" on cold traffic — Pillar 3 is the cold-traffic pillar
- Use "more than 60 lenders" as the differentiator. It is the strongest verifiable number
- Name the location for local campaigns
- Match the ad's promise to the landing page's headline, word for word
- Run the destination page through
  [funnels-and-landing-pages](funnels-and-landing-pages.md)'s checklist first

## Don't

- Don't imply knowledge of the reader's finances — a platform-level violation
- Don't state a rate, a saving, a repayment or an approval
- Don't use "pre-approved", "you qualify", "guaranteed", "instant"
- Don't use countdowns or false scarcity on a credit product
- Don't paraphrase a testimonial into our voice — a customer may say "approved", we may not.
  Quote verbatim or not at all. See [testimonials](../05-proof-and-evidence/testimonials.md)
- Don't run ads to the generic contact page
- Don't target by inferred financial hardship

## Pre-send checklist

- [ ] **Karlie has signed off**
- [ ] No implication of knowledge of the reader's financial situation
- [ ] No rate, saving, repayment figure, approval or guarantee
- [ ] Zero banned words
- [ ] Destination page exists, matches the promise, and carries both compliance lines
- [ ] Booking routes to the right broker by product and state
- [ ] "more than 60 lenders" written exactly
- [ ] Any testimonial used is verbatim and attributed as published, not paraphrased
- [ ] Character limits respected
- [ ] Australian English
- [ ] Disclosure visible on the destination if not in the ad

## Worked example — Meta, cold, equity

**Audience:** homeowners 35–60, Moreton Bay and western Sydney. **Pillar 3 → 2.**
Destination: the Equity Check funnel.

---

**Primary text:**
> Most people have no idea how much equity they've built up — or how much of it they could
> actually use.
>
> It takes about a minute to get an estimate. Then a broker can tell you what's realistically
> usable, based on your income and the lender's criteria.
>
> Costs you nothing. We're paid by the lender if and when a loan settles.

**Headline:** `How much equity have you got?` *(29)*
**Description:** `Estimate it in a minute` *(23)*
**CTA button:** Learn More

---

## Worked example — Google search, refinance

**Keywords:** "mortgage broker brisbane", "refinance home loan brisbane", "home loan broker near me"

**Headlines:**
`Mortgage Broker Brisbane` · `More Than 60 Lenders Compared` · `No Cost To You` ·
`Refinance With Less Hassle` · `Loan Health Check` · `Brisbane & Sydney Brokers` ·
`We Handle The Paperwork` · `Award-Winning Broking Team`

**Descriptions:**
> We compare home loans from more than 60 banks, credit unions and non-bank lenders. No cost
> to you.

> From application to settlement, we handle the paperwork and liaise with the lender. Book a
> 15-minute call.

---

**Checklist run:** no rate or saving ✓ · no implication of the reader's finances ✓ ·
"more than 60 lenders" exact ✓ · fee model correctly stated ✓ · "Award-Winning" supported by
the 2023 win, and the landing page carries the exact wording ✓ · character limits ✓
