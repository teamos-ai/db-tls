---
id: enrichment-roadmap
title: Enrichment roadmap — the gap map
type: system
status: approved
confidence: verified
source: S1 gap analysis, the S9 audit, and a deep research pass conducted 2026-08-27
as_of: 2026-08-27
researched: 2026-08-27
owner: Tumai (Team OS)
tags: [roadmap, gaps, enrichment, priorities, interview-agenda]
---

# Enrichment roadmap — the gap map

**An honest map of what this database knows, what research closed, and what only the client can
answer.**

**Truth tiers: 61 `verified` · 21 `inferred` · 0 `assumed` in publishable files.**

---

## Part 1 — closed by research, 27 August 2026

Nine gaps from the first build are now filled from primary and public sources.

| Was a gap | Now | Landed in |
|---|---|---|
| **Who was nominated for the 2024 individual awards?** | **Karlie Scharfenberg** — Residential Broker of the Year. **Jessica Didovich-Lasalo** — Loan Administrator of the Year. Verified against The Adviser's own records | [awards](../05-proof-and-evidence/awards.md) |
| **Is the 2023 award real?** | **Verified.** Winner, Independent Office of the Year, 13th Australian Broking Awards, The Star Sydney, 11 Aug 2023 — **and an eighth placement nobody knew about**: Karlie, finalist, Finance Broker of the Year 2023 | [awards](../05-proof-and-evidence/awards.md) |
| **Who is the aggregator?** | **Verified.** Mortgage Specialists Pty Ltd, ACN 050 601 093, ACL 387025 approved 18 Nov 2010, registered business name **Specialist Finance Group**, Subiaco WA | [licensing-and-entity](../01-company/licensing-and-entity.md) |
| **What is the ACN / registration date?** | **Both companies found.** The Loans Suite Group Australia Pty Ltd (ACN 667 838 146, from 9 May 2023) and Queens of Finance Pty Ltd (ACN 676 457 337, from 10 Apr 2024) | [licensing-and-entity](../01-company/licensing-and-entity.md) |
| **Is the SMSF restriction still pending?** | **No — in force since 10 Aug 2026.** And critically: **refinancing existing residential LRBAs is still permitted**, as is commercial | [regulatory-changes-2026](../06-competitors-and-market/regulatory-changes-2026.md) |
| **Are the scheme figures current?** | **Three of four were stale.** 5% Deposit Scheme expanded 1 Oct 2025 (uncapped, no income caps, higher price caps). Help to Buy open since 5 Dec 2025. Payday Super is **7 business days**, not calendar. FHSSS caps confirmed unchanged | [regulatory-changes-2026](../06-competitors-and-market/regulatory-changes-2026.md) |
| **Is the APRA buffer still 3%?** | **Yes.** Confirmed 23 Jul 2025, maintained through 2026 | [statistics-and-sources](../05-proof-and-evidence/statistics-and-sources.md) |
| **Local market data** | Redcliffe ~$1.0M (+21–23%), Rothwell ~$1.03M, Penrith ~$880k–$1.1M. Ranges, not points | [market-context](../06-competitors-and-market/market-context.md) |
| **The Loan Market competitor** | **Read directly.** And it overturned an assumption — see below | [competitor-loan-market-aqua](../06-competitors-and-market/competitor-loan-market-aqua.md) |

### The three findings that changed the strategy

**1 · Panel size is not a local differentiator.** Loan Market Aqua, on the same Moreton Bay
footprint, claims **100+ lenders** against our 60+, and leads with it. The first build treated
60+ as an advantage. It beats Aussie (25+) and Borro (30+); it loses locally. **Lead with the
range of finance types and with independence instead.**

**2 · There are two companies, and the privacy policy may name the wrong one.**
The Loans Suite Group Australia Pty Ltd holds the *"The Loans Suite"* business name, is
GST-registered, and is the entity The Adviser recorded as the 2023 award winner. Queens of
Finance Pty Ltd — the entity named in the published privacy policy as the credit representative
— holds *"The Property Suite"* and is **not** GST-registered. Both can be legitimate at once.
**Until Karlie confirms, name no company in any disclosure block.** The footer *numbers* remain
safe.

**3 · The brand is older than both companies.** A Word of Mouth review dated November 2019 shows
The Loans Suite trading at a Penrith address four years before the earliest current company was
registered. **There is still no publishable founding year.**

---

## Part 2 — the top three, unchanged

### 1 · Record and transcribe ten discovery calls

**Still the largest quality ceiling on this database.** Every ICP file, `buyer-psychology`,
`objections`, `objection-turns` and `sales-scripts` remains `inferred` — reasoned from the
client's own marketing copy rather than from a prospect's mouth.

The six testimonials prove the problem. Customers say *fast, simple, explained, supported*. The
brand says *strategy, structure, architects*. We have six sentences of customer language and
tens of thousands of words of seller language.

**One transcription pass upgrades nine files.** Effort: low — the calls already happen.

### 2 · Export the Google reviews

**Now the single most visible competitive weakness.** Borro publishes **215+ Google reviews**;
The Loans Suite publishes six testimonials.

**Automated retrieval is blocked** — Google serves a bot check to any automated request, so this
has to be exported by someone signed in to the Business Profile. A search snapshot on 27 Aug
2026 surfaced further review text naming *"Karlie, Jess, Lisa and Carms"* and *"Karlie and
Jess"*, so more reviews demonstrably exist. Neither was readable at source, so neither is usable.

Pair the export with a review request at **Pipeline 3 → `Settled`** — the peak-emotion moment.
See [email-sequences](../08-channels-and-playbooks/email-sequences.md).

### 3 · Resolve the entity question, then the contradictions

**New top-three item.** Which entity holds credit representative 477350? It determines what
belongs in the footer of every page we build.

Then the four site contradictions from the first build, three of which are unchanged:

| Contradiction | Status |
|---|---|
| Karlie's experience — "over 20 years" vs "over 30 years" | **Open.** No experience figure is publishable |
| Mortgage stress threshold — 35% vs 30% on two live calculators | **Open.** Use 35% |
| "The Loan Suite" singular on `/calculators/mortgage-stress/` | **Open** |
| 2023 blog headlining "70% of home buyers" | **Open.** Now 81.0% |

---

## Part 3 — content and correction backlog, ranked

### 4 · Fix the three stale scheme pages

The most fixable content on the website, and all three are now researched and ready to write:

- **Help to Buy** — the page says *"Limited information available on this one!"* The scheme has
  been open since December 2025, has 10,000 places, raised income caps on 1 July 2026, and has
  **exactly one broker-accessible lender**. That last fact is a positioning opportunity.
- **5% Deposit Scheme** — generic copy predating uncapped places, removed income caps and higher
  price caps. And the local angle: **Redcliffe's median has converged on the $1M QLD cap.**
- **SMSF** — written as though the ban is forthcoming. It is in force, and **refinancing is
  still permitted**, which is an addressable market nobody local is speaking to.

### 5 · Fix the two factual errors in published content

- The blog says Payday Super requires payment within *"seven calendar days"*. It is **seven
  business days**, and the change is in force, not upcoming.
- The 2023 market-share blog headline reads as current.

### 6 · Confirm the sub-broker commercial terms

`/join-us/` recruits brokers but publishes no split, no answer on leads, no costs, no aggregator
arrangement. **A recruitment campaign cannot run credibly until those are answered.**

### 7 · Fix the compliance defects on live pages

- Equity calculator promises *"Unlock our best home loan rates"* and *"Get free advice"*
- `/personal-loans/` states *"Personal loans can be approved"*
- The **privacy policy contains copy-paste artifacts from "Domain Loan Finder"** with blank
  contact fields for access, correction and complaints — an APP 1 exposure

### 8 · Consolidate booking, and the two Facebook pages

Three brokers across Calendly (two accounts) and TidyCal — **no round-robin, so paid acquisition
cannot route.** One public slug carries a live typo (`loanstratergy`).

And **two Facebook pages** — `theloanssuitesydney` (linked from the site) and
`theloanssuiteaustralia` (found 2026-08-27). Followers, reviews and history are split across
both.

### 9 · Claim the stale directory listings

An **unclaimed Localsearch listing** shows The Loans Suite in **Wollongong NSW** with zero
reviews. A 2019 citation carries a **former Penrith address** (Suite 2, 20-24 Castlereagh St).
Inconsistent NAP data across directories is a standard local-SEO drag.

### 10 · Capture the GHL system IDs

No location, workflow, calendar or form ID is recorded. Without them, automation can only be
described, not specified.

### 11 · Build the missing pages

- **A refinance page** — highest commercial intent in the category, no page. Brief ready in
  [website-and-page-copy](../08-channels-and-playbooks/website-and-page-copy.md)
- **Local pages** — Borro runs suburb pages across Redcliffe, Clontarf, Kippa-Ring and Margate.
  The Loans Suite has none despite two offices
- **A Loan Health Check page** — a named offer with no page and no promise
- **The two Suite hub pages** are empty shells

### 12 · Write the first case study

Still zero. A single de-identified, structural, figure-free story would serve the business-owner
and complex-borrower audiences, where the proof gap is widest.

### 13 · Add attribution capture to the contact form

Loan Market's form asks *"How did you find us?"*. Ours does not. One field, and it tells you
which channel is actually working.

### 14 · Enter the 2026 awards

**No 2025 placement exists** — verified against The Adviser's records. The most recent is 2024.
If awards matter to positioning, entering is an action, not a marketing task.

### 15 · Decide on the generational story

Karlie since 2016, Kaiden through Cert IV at seventeen, Michelle studying hers now. A real
differentiator against franchise networks, mentioned only on one bio. Needs Karlie's decision on
how public the family story should be.

---

## Part 4 — what only Karlie can answer

Research has taken this database as far as public sources allow. Everything below needs her.

**Facts**
1. Which entity holds credit representative 477350 — The Loans Suite Group Australia, or Queens
   of Finance?
2. Is "The Property Suite" a separate venture or a legacy registration?
3. Twenty years or thirty?
4. Who is **Reema**? Named as a packaging desk in Pipeline 2, not among the six published team.
5. Who are **Lisa**, **Carms** and **Emma**, named in customer reviews but not on the team page?
6. What year did the business actually start trading? *(It was operating in 2019.)*
7. What is SFG's total lender panel size?

**Commercial terms**
8. What is the sub-broker commission split, and are leads provided?
9. Are there referral fee arrangements with any of the twelve partners?
10. Does SFG require sign-off on outward-facing marketing?

**The material only she has**
11. Who do you turn away, and why? *([disqualifiers](../03-audience-and-icp/disqualifiers.md) is
    `inferred` — and what a business refuses is usually the sharpest thing about it.)*
12. What is the objection that kills most deals?
13. What do competitors say that is simply wrong?
14. What does a great client look like twelve months after settlement?
15. What will you never say in public?

**Decisions**
16. How public should the family story be?
17. Can we publish that every file passes a principal quality check before lodgement?
    *(A real, unclaimed proof point from Pipeline 2 — `Karlie Mentor Check`.)*

---

## What is deliberately not on this list

**More content.** 171 blog posts, seven calculators, a twelve-partner directory. This business
does not have a content problem. It has a **proof, routing, entity-clarity and local-SEO
problem** — and three stale scheme pages that are wrong today. Fix those before writing
anything new.
