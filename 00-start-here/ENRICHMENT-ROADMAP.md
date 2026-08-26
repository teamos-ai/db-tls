---
id: enrichment-roadmap
title: Enrichment roadmap — every gap, ranked by leverage
type: system
status: approved
confidence: verified
source: gap analysis from the S1 source harvest and the S9 audit of this database
as_of: 2026-08-26
owner: Tumai (Team OS)
tags: [roadmap, gaps, enrichment, priorities, interview-agenda]
---

# Enrichment roadmap

**An honest list of what this database doesn't know.** Ranked by leverage — what would most
improve the quality of generated assets, not what is easiest.

**Current truth tiers:** 59 files `verified` · 22 `inferred` · 0 `assumed` in publishable
files. Every `assumed` item found in the sources was quarantined rather than written into a
usable file. The concentration of `inferred` is in **03-audience-and-icp** and that is the
central weakness of this build.

---

## The top three

### 1 · Record and transcribe ten discovery calls

**What it fixes:** every one of the six ICP files, `buyer-psychology`, `objections`,
`objection-turns` and `sales-scripts` is `inferred` — reasoned from the client's own
marketing copy rather than from a prospect's mouth. That is the single largest quality
ceiling on this database.

**Why it matters:** the business's own testimonials already prove the point. Customers say
*fast, simple, explained, supported*. They never say *strategy, structure, solutions,
architect*. The brand's vocabulary is seller language; the customer vocabulary is different,
and right now we only have five sentences of it.

**What closes it:** ten recorded discovery calls, transcribed. One pass would upgrade nine
files from `inferred` to `verified`.

**Effort:** low. The calls are already happening.

---

### 2 · Get written permission on the five testimonials — starting with Samantha G

**What it fixes:** [testimonials](../05-proof-and-evidence/testimonials.md) is `status: review`.
Five testimonials with unknown permission status cannot be used in paid advertising, which
blocks the strongest proof asset from the channel that needs it most.

**Samantha G's is the one that matters:**
> After the bank cancelled our unconditional approval, Karlie worked overnight and over a few
> days to save us from losing our new house and deposit.

That is the only piece of evidence the business owns that demonstrates something a comparison
site and a bank branch **structurally cannot do.** With permission it becomes a case study, a
video, an ad, and the anchor of the "why not just go to the bank" argument.

**Also:** export every existing Google and Facebook review. Free, immediate, and it would
multiply available proof several times over. The closest competitor publishes **215+ Google
reviews** against The Loans Suite's five testimonials — the most visible competitive gap in
the business.

**Effort:** low. A phone call and an export.

---

### 3 · Resolve the four factual contradictions on the live site

Four facts currently cannot be used at all because the site disagrees with itself:

| Contradiction | Where | Resolution needed |
|---|---|---|
| **Karlie's experience: "over 20 years" vs "over 30 years"** | Her bio vs Kaiden's bio | Karlie confirms, and the site is corrected |
| **Mortgage stress threshold: 35% vs 30%** | Two live calculators | Consolidate to one calculator |
| **Brand name: "The Loans Suite" vs "The Loan Suite"** | `/calculators/mortgage-stress/` uses the singular twice | Fix the page |
| **Broker market share: 69.6% (2023)** presented as current | A live blog headline | Update to 81.0% or date it prominently |

**Effort:** low. High return — an experience figure is a genuine credibility asset and it is
currently unusable.

---

## Ranked next

### 4 · Confirm the sub-broker commercial terms

`/join-us/` recruits brokers but publishes **no commission split, no answer on leads, no
costs, and no aggregator arrangement.** Those are the first four questions any experienced
broker asks. **A recruitment campaign cannot run credibly until they are answered** — it would
waste every click it earned. See [sub-broker-offer](../02-offer-and-lending/sub-broker-offer.md).

### 5 · Capture the GHL system IDs

No location ID, workflow ID, calendar ID or form ID is recorded anywhere. Without them, no
automation work can be specified precisely — only described. See
[systems-and-ids](../01-company/systems-and-ids.md).

### 6 · Consolidate booking onto one system

Three brokers across Calendly (two separate accounts) and TidyCal. **No round-robin is
possible**, no load balancing, and any paid campaign driving to "book a call" is guessing
which calendar to use. One public Calendly slug contains a live typo (`loanstratergy`).
**This is a prerequisite for paid acquisition**, not a nice-to-have.

### 7 · Fix the compliance defects on live pages

Three live pages carry language that breaches the guardrails:

- The equity calculator promises *"Unlock our best home loan rates"* and *"Get free advice
  from a lending specialist"* — we have neither rates nor advice to give
- The personal loans page states *"Personal loans can be approved"*
- The **privacy policy contains copy-paste artifacts from another business** — it refers to
  *"Domain Loan Finder"* and *"domainloanfinder.com.au"*, and its contact fields for access,
  correction and complaints are **blank**. That is a genuine APP 1 exposure

**Client action, not a marketing task.** See
[privacy-and-data](../07-compliance-and-guardrails/privacy-and-data.md).

### 8 · Confirm the aggregator and the marketing approval chain

ACL 387025 traces to **Mortgage Specialists Pty Ltd t/a Specialist Finance Group**, corroborated
by the three SFG badges on the site — but this is `inferred`, not confirmed by the client. Most
aggregators also require sign-off on outward-facing use of the licensee's details, which would
change [approval-rules](../07-compliance-and-guardrails/approval-rules.md) from `inferred` to
`verified`.

### 9 · Attribute the individual awards

*Residential Broker of the Year* and *Loan Administrator of the Year* are **individual**
categories. The sources do not record who was nominated. Right now they can only be stated as
business-level shortlistings, which is weaker than the truth probably is.

### 10 · Write the first case study

There are **zero**. Not one written client story. A single de-identified, structural,
figure-free case study — challenge, obstacle, what got solved — would serve the business-owner
and complex-borrower audiences, where the proof gap is widest. Requires client permission and
Karlie's sign-off on what can be said.

### 11 · Build the missing pages

Things the business sells or promotes with nowhere to land:

- **A refinance page.** The highest commercial-intent term in the category, with no page.
  A worked brief is in
  [website-and-page-copy](../08-channels-and-playbooks/website-and-page-copy.md)
- **Local pages.** The closest competitor runs suburb-level pages for Redcliffe, Clontarf,
  Kippa-Ring and Margate. The Loans Suite has none, despite two physical offices
- **A Loan Health Check page.** A named offer with no page, no promise and no funnel
- **The two Suite hub pages** are empty shells

### 12 · Re-verify the ageing facts

| Fact | Status |
|---|---|
| SMSF residential restriction "from 10 August 2026" | **The date has passed.** Check current state before any SMSF asset |
| Stamp duty rates | As at 1 July 2025 |
| First Home Super Saver caps | Check the ATO |
| Payday Super detail | Legislative — confirm before campaigning |
| Redcliffe median house price | `inferred` from secondary reporting. Verify or cut |

### 13 · Re-do the Loan Market Aqua teardown manually

The competitor's site blocked automated access, so
[competitor-loan-market-aqua](../06-competitors-and-market/competitor-loan-market-aqua.md)
is built from search summaries. It is the thinnest file in folder 06 and is marked `draft`.

### 14 · Decide on the generational story

Karlie since 2016, Kaiden through Cert IV at seventeen and now broking, Michelle studying hers
now. A family business that develops its own people is a real differentiator against franchise
networks — and it currently appears only on one bio. It is not a messaging pillar yet because
it needs Karlie's decision on how public the family story should be.

---

## The interview agenda — what to ask Karlie

The fastest route through most of the above is one focused conversation. In priority order:

**Facts to resolve**
1. Twenty years or thirty? *(unblocks an experience claim)*
2. Who was nominated for Residential Broker of the Year and Loan Administrator of the Year?
3. Is Specialist Finance Group the aggregator, and do they need to approve marketing?
4. Who is Reema? *(named as a packaging desk in Pipeline 2, not among the six published team)*
5. What year did the business actually start?

**Commercial terms**
6. What is the sub-broker commission split, and are leads provided?
7. Are there referral fee arrangements with any of the twelve partners?

**The material only she has**
8. Who do you turn away, and why? *(the [disqualifiers](../03-audience-and-icp/disqualifiers.md)
   file is `inferred` — and what a business refuses is usually the sharpest thing about it)*
9. What is the objection that kills most deals?
10. What do competitors say that is simply wrong?
11. What does a great client look like twelve months after settlement?
12. What will you never say in public?

**Decisions**
13. How public do you want the family story?
14. Can we have permission on the five testimonials, starting with Samantha G?
15. Are you comfortable publishing that every file passes a principal quality check before
    lodgement? *(a real, unclaimed proof point from Pipeline 2)*

---

## What is deliberately not on this list

**More content.** The business has 171 blog posts, seven calculators and a twelve-partner
directory. It does not have a content problem — it has a **proof, routing and local-SEO
problem.** Adding more articles before fixing the review gap, the booking routing and the
missing refinance page would be building on sand.
