---
id: playbook-sms
title: Playbook — SMS
type: playbook
status: approved
confidence: verified
source: SMS trigger points from the pipeline stages in 11-operations; Spam Act 2003 (Cth) requirements; voice from the verified layers
as_of: 2026-08-26
owner: Emily Baulch (Marketing)
tags: [playbook, sms, automation, transactional]
---

# Playbook — SMS

## Purpose

Write an SMS — transactional (a pipeline event) or promotional (a campaign). **They follow
different rules.** Get the category right before writing a word.

## Load order

1. [guardrails](../07-compliance-and-guardrails/guardrails.md)
2. [privacy-and-data](../07-compliance-and-guardrails/privacy-and-data.md) — consent
3. [brand-voice](../04-voice-and-messaging/brand-voice.md)
4. [11-operations/pipelines](../11-operations/pipelines.md) — the trigger
5. [09-content-banks/ctas](../09-content-banks/ctas.md)

## The two categories

| | Transactional | Promotional |
|---|---|---|
| Trigger | A pipeline event on **their** file | A campaign |
| Consent | Implied by the engagement | **Express consent required** |
| Opt-out | Good practice | **Mandatory** (Spam Act 2003) |
| Sender ID | Must identify the business | **Must identify the business** |
| Timing | As the event happens | Business hours only, never weekends |
| Frequency | As needed | Rare. Once a month at most |

**If in doubt, it is promotional.** Add the opt-out.

## Format

- **160 characters is one message.** Aim for one. Two is the ceiling
- **Name the business in the first message of any thread.** They don't have you saved
- **One link maximum**, and only where it does real work
- **No emoji** in transactional. At most one in promotional, and rarely
- **First name only.** Never a surname, an address, or a loan detail

## Universal structure

`[Who] + [What happened or what's on offer] + [What they do next] + [Opt-out if promotional]`

## The transactional moments the pipelines already define

| Moment | Stage |
|---|---|
| Instant lead response — **within 5 minutes** | Pipeline 1, `New Lead Set up` |
| Missed-call text-back | Pipeline 1 |
| Application lodged with the lender | Pipeline 3, `Submitted / In Queue` |
| More information required | Pipeline 3, `MIR's` |
| **Formal approval** | Pipeline 3 — the highest-emotion message we send |
| Settlement booked / settled | Pipeline 3 |
| Pre-approval check-ins at 30/60/75 days | Pipeline 4 |
| Construction stage released | Pipeline 5 |

The five-minute lead response is the highest-value SMS in the business. Speed, not wording,
is what makes it work.

## Do

- Get to the point in the first seven words
- Write like a person texting, not a system broadcasting
- Use their first name
- Name the broker who is actually going to call
- Make the next step a single, obvious action
- Send transactional messages the moment the event happens

## Don't

- Don't state a rate, a figure, an approval or a saving
- Don't say "approved" unless the **lender** has formally approved, and then attribute it:
  *"The lender has issued formal approval"*
- Don't send promotional SMS without express consent and an opt-out
- Don't send outside business hours or on weekends
- Don't use link shorteners that hide the destination — they read as spam and get filtered
- Don't chase more than twice
- Don't send anything promotional to a hardship contact
- Don't include a client's information in a message to a **partner**. See
  [privacy-and-data](../07-compliance-and-guardrails/privacy-and-data.md)

## Pre-send checklist

- [ ] Category identified — transactional or promotional
- [ ] If promotional: express consent held, opt-out included, business hours
- [ ] Business identified in the first message of the thread
- [ ] Under 160 characters where possible
- [ ] No rate, figure, saving or approval language
- [ ] No client detail beyond a first name
- [ ] One link maximum, full domain visible
- [ ] Named broker where a call is promised
- [ ] Australian English, no emoji in transactional

## Worked examples

**Five-minute lead response** *(transactional, 138 chars)*
> Hi Sarah, it's Kaiden from The Loans Suite. Just got your enquiry about buying your first
> home. Are you free for a quick call today or tomorrow?

**Missed call text-back** *(transactional, 129 chars)*
> Hi, sorry we missed you — The Loans Suite here. Reply with a good time and one of our
> brokers will call you back today.

**Lodged with lender** *(transactional, 144 chars)*
> Hi Tom, Jess here. Your application is now with the lender and in their assessment queue.
> I'll let you know the moment I hear anything.

**Formal approval** *(transactional, 152 chars)*
> Hi Tom — the lender has issued formal approval on your loan. Congratulations. I'll call
> shortly to talk through what happens between now and settlement. Jess

**Pre-approval day 75** *(transactional, 158 chars)*
> Hi Sarah, Kaiden here. Your pre-approval expires in about 2 weeks. If you're still looking
> I'll need fresh payslips to extend it. Reply and I'll sort it out.

**Promotional — rate health check** *(promotional, 2 messages)*
> Hi Tom, Karlie from The Loans Suite. Your loan's been running about 10 months now — it's a
> good time to check the rate is still competitive. It costs nothing and takes 15 min. Want me
> to look? Reply STOP to opt out.

---

**Checklist run on "Formal approval":** transactional ✓ · approval attributed to the lender,
not us ✓ · no figure ✓ · named broker ✓ · 152 chars ✓ · the one place "approval" is correct
because the lender issued it
