---
id: ai-voice-and-chat
title: AI voice agent and chat widget — designed, not live
type: system
status: draft
confidence: inferred
source: AI agent design from Karlie's GHL planning documentation (Aug 2026). No chat widget or voice agent is present on theloanssuite.com.au as scraped.
as_of: 2026-08-26
owner: Karlie Scharfenberg
tags: [ai, voice-agent, chat, operations, proposed, compliance-critical]
---

# AI voice agent and chat widget

> **Tier note:** `inferred` — **designs, not live systems.** No chat widget appears in the
> site markup. Do not describe either as existing.

> **This is the highest-compliance-risk item in the entire database.** An AI answering a
> credit question incorrectly is a credit-assistance event under the NCCP Act, attributable
> to the credit representative. Read
> [guardrails](../07-compliance-and-guardrails/guardrails.md) and
> [chat-widget-and-voice-agent-spec](../10-faq-and-objections/chat-widget-and-voice-agent-spec.md)
> before any build.

## Designed: chat widget

- Bottom-right, champagne gold `#D1BCA0` pill with Karlie's avatar
- Greeting: *"Hi there! Looking to check your borrowing capacity or review your current home
  loan rate? Ask me anything or request a call."*
- Two qualifying questions — purchase vs refinance, and contact number — before handing to SMS

**Assessment.** The two-question qualification is right. **"Ask me anything" is not** — it
invites exactly the open-ended credit questions the agent must never answer. Replace with a
scoped invitation: *"Ask about our process, or request a call."*

## Designed: voice agent — "Sophie"

- **Role:** inbound calls during consultations, after hours (post 5:30pm AEST), and weekends
- **Voice:** warm, professional, Australian, calm
- **Intents:**
  - **A — New enquiry.** Identify purchase vs refinance and approximate budget; book a
    discovery call
  - **B — Existing client status.** Look up pipeline stage and reassure
  - **C — Urgent settlement or finance-clause issue.** Escalate to Karlie immediately

**Stated guardrails, which are correct as far as they go:** never provides specific credit
advice, never quotes rates as guaranteed, never commits to approval amounts. Qualifies and
schedules only.

## Where the design needs hardening before launch

**1. Disclosure.** The caller must be told they are speaking to an automated assistant, at
the start. Not doing so is both an ethical and a consumer-law problem.

**2. Intent B leaks confidential information.** The designed response —
*"Your application is currently under formal assessment with the lender's credit team; Jess
will send your daily update at 4:00 PM"* — discloses application status and the lender's
stage to **whoever is holding the phone**, with no identity verification. A voice on a call is
not authentication. Either verify identity properly or restrict Intent B to *"I'll have your
broker call you back"*.

**3. It must never state a figure.** No rate, no borrowing capacity, no repayment, no
timeframe. "Approximate budget" may be *captured*, never *assessed*.

**4. Hardship must route to a human, always.** Any signal of distress — missed payments,
"I can't afford", hardship — ends the automation and escalates. Never a booking prompt.
The National Debt Helpline (**1800 007 007**) is the correct referral.

**5. It must be able to say "I don't know."** The single most important behaviour. Every
answer it cannot ground in this database becomes *"That's a question for one of our brokers —
let me get someone to call you."*

**6. Complaints route to the published IDR path**, then AFCA. See
[nccp-and-best-interests-duty](../07-compliance-and-guardrails/nccp-and-best-interests-duty.md).

## The naming question

"Sophie" reads as human. If the agent is named and voiced as a person, the disclosure
obligation gets **stronger**, not weaker. A name is fine; a name plus an undisclosed
non-human identity is not.

## The prerequisite

**An AI agent can only be as accurate as what grounds it.** That grounding is
[10-faq-and-objections/faq](../10-faq-and-objections/faq.md) and the compliance folder.
**Build the FAQ before building the agent** — an agent pointed at nothing improvises, and
improvisation on a regulated product is the failure mode this whole database exists to prevent.

## Related

- [chat-widget-and-voice-agent-spec](../10-faq-and-objections/chat-widget-and-voice-agent-spec.md)
- [approval-rules](../07-compliance-and-guardrails/approval-rules.md)
