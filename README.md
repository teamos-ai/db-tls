# db-tls — The Loans Suite Australia knowledge database

The grounded source of truth for **The Loans Suite Australia** — a mortgage and finance
brokerage operating as an authorised credit representative in Australia.

Point any AI at this repository and it can produce a publishable landing page, email, SMS,
ad or article in the business's voice, with every claim traceable to a file, without
inventing anything.

**Private repository.** It holds positioning, competitor intelligence, operational detail
and strategy.

---

## Start here

**If you are an AI:** read [`00-start-here/AI-INSTRUCTIONS.md`](00-start-here/AI-INSTRUCTIONS.md)
first, every session. It carries the conflict hierarchy, the load order for every job, and the
nine rules you cannot break.

**If you are a human:** read [`00-start-here/quick-facts.md`](00-start-here/quick-facts.md) for
the facts, then [`00-start-here/ENRICHMENT-ROADMAP.md`](00-start-here/ENRICHMENT-ROADMAP.md)
for what this database still doesn't know.

**Looking for a specific file:** [`00-start-here/INDEX.md`](00-start-here/INDEX.md).

---

## The business, in brief

**Queens of Finance Pty Ltd t/as The Loans Suite** — an authorised credit representative
(**477350**) under **Australian Credit Licence 387025**. It arranges home, investment,
construction, SMSF, commercial, business and asset finance across a panel of **more than 60
lenders**, at **no cost to the client** — the lender pays on settlement. Two offices,
**Rothwell QLD** and **Penrith NSW**, servicing clients Australia-wide. Six people, led by
**Karlie Scharfenberg**. Brand line: **"Your financial architects."**

It is **not** a bank, a lender, a financial adviser or a licensee. It cannot approve, price or
fund anything — and every claim boundary in this database follows from that.

---

## Structure

| Folder | Holds |
|---|---|
| `00-start-here/` | The routing layer — AI instructions, index, quick facts, roadmap |
| `01-company/` | Entity and licensing, team, process, offices, systems, routes, design tokens |
| `02-offer-and-lending/` | 9 product lines in 2 Suites, fee model, lender panel, calculators, partners, sub-broker offer |
| `03-audience-and-icp/` | 6 ICPs, disqualifiers, buyer psychology, voice of customer |
| `04-voice-and-messaging/` | Brand voice, 4 messaging pillars, banned language, positioning |
| `05-proof-and-evidence/` | Awards, testimonials, **what we cannot claim**, sourced statistics |
| `06-competitors-and-market/` | 5 teardowns, comparison matrix, market context, glossary — **internal only** |
| `07-compliance-and-guardrails/` | **Outranks everything.** Guardrails, NCCP & BID, claims policy, privacy, approvals |
| `08-channels-and-playbooks/` | 9 executable playbooks, each with a pre-send checklist and a worked example |
| `09-content-banks/` | Hooks, subject lines, CTAs, proof lines, objection turns, offer angles |
| `10-faq-and-objections/` | Canonical FAQ, objection handling, chat and voice agent spec |
| `11-operations/` | 6 CRM pipelines, calendars and routing, funnel designs, AI agent designs |
| `99-source-material/` | The quarry — 71 page extractions, raw operations doc, measured tokens |

Numbering is the load order: **ground truth → strategy → generation.**

---

## The rules that override everything

1. **Never invent a fact about The Loans Suite.** No client count, settlement volume, trail
   book, approval rate, average saving or years in business — **none of these exist.**
2. **Never write** approved · pre-approved · guaranteed · you qualify · best rate ·
   instant approval · we advise.
3. **Never state a rate, fee, LVR or repayment as an offer.** The business is not the lender.
4. **The panel figure is "more than 60 lenders."** Exactly that.
5. **Never name a competitor** outward-facing.
6. **Every external figure** must be in `05-proof-and-evidence/statistics-and-sources.md`
   first, with source and period.
7. **Hardship is never a sales opportunity.** National Debt Helpline: **1800 007 007**.
8. **When uncertain, leave it out.** "This isn't in the database" is a valid answer.

Full detail: [`07-compliance-and-guardrails/guardrails.md`](07-compliance-and-guardrails/guardrails.md).

---

## Truth tiers

Every file carries `confidence:` in its frontmatter.

- **`verified`** — traces to a primary source: the client's own site, documents or systems.
  Quote-safe, publishable as-is.
- **`inferred`** — reasoned from verified material. Usable for strategy and internal drafts.
  **Must be flagged in any output that relies on it.**
- **`assumed`** — a working placeholder. **Never publishable.** Stays on the roadmap until
  upgraded.

**Current state: 59 verified · 22 inferred · 0 assumed in publishable files.**

The `inferred` files are concentrated in `03-audience-and-icp` — every ICP is reasoned from
the client's marketing copy rather than from a prospect's mouth. That is the central weakness
of this build and the top item on the roadmap.

---

## Sources

| Source | Covers | Date |
|---|---|---|
| theloanssuite.com.au full scrape — 71 pages, 110 assets, computed CSS | All published copy, awards, design tokens, systems | Aug 2026 |
| Karlie's GoHighLevel / Salestrekker configuration | 6 pipelines with real stage names | Aug 2026 |
| Public ACL register, MFAA/Cotality market data, competitor sites | Licensing, market context, teardowns | Aug 2026 |

Full provenance, including **four errors found in derived summary documents**, is in
[`99-source-material/source-register.md`](99-source-material/source-register.md).

---

## Maintenance contract

| Class of fact | Source of truth | Re-verify |
|---|---|---|
| Company facts — team, offer, contact, licensing | **theloanssuite.com.au** | On site change; scrape twice yearly |
| Rates, schemes, regulatory dates | Primary regulator — ATO, APRA, ASIC, state revenue offices | **Before each publication** |
| Market statistics | MFAA / Cotality quarterly releases | Quarterly |
| Competitors | Their published sites | Annually, or on relaunch |
| Pipelines and systems | Karlie's GHL / Salestrekker | On workflow change |
| Testimonials and proof | Karlie, with permission status recorded | On new testimonial |

**Triggers an update:** a site change · a new offer · a new case study or testimonial ·
campaign results · a regulatory change · a quarterly competitor check.

**Five facts are currently ageing** and are listed in
[`00-start-here/quick-facts.md`](00-start-here/quick-facts.md) — the SMSF restriction date has
already passed.

---

## Never commit

Credentials, API keys, customer lists, lead exports, CRM records, contact data, credit files,
or any client's personal information. `.env*` is gitignored from the first commit.
