---
id: calculators-and-tools
title: Calculators and tools
type: offer
status: approved
confidence: verified
source: theloanssuite.com.au/calculators/* (seven pages) and /home-loan-comparison/, /movinghub/
as_of: 2026-08-26
owner: Karlie Scharfenberg
tags: [calculators, tools, lead-magnets, funnels, disclaimers]
---

# Calculators and tools

Seven calculators plus two utilities. These are the business's **only lead magnets** — there
are no guides, ebooks or checklists anywhere on the site. Every top-of-funnel campaign has to
run through one of these or through a booking.

## The seven calculators

| Tool | Route | Captures a lead? | Best audience |
|---|---|---|---|
| **Equity Cashout** | `/calculators/equity-cashout-calculator/` | **Yes — full gated report** | Existing owners, investors |
| **Borrowing Power Check** | `/calculators/borrowing-power-check/` | **Yes — callback form** | First home buyers, upgraders |
| **Mortgage Stress Check** | `/calculators/mortgage-stress-check/` | No | Refinancers under pressure |
| **Mortgage Stress Calculator** | `/calculators/mortgage-stress/` | No | (duplicate — see below) |
| **Stamp Duty** | `/calculators/stamp-duty/` | No | First home buyers, interstate investors |
| **Loan Repayments** | `/calculators/loan-repayments/` | No — but has **Download PDF** | Everyone |
| **Annualised Income** | `/calculators/annualised-income/` | No | Casual, contract, self-employed |

## The two that actually capture leads

**Equity Cashout** is the strongest asset in the business. It gates the result behind a full
form and offers, verbatim:

> Your equity cash out report is ready! Enter your details to secure your personalised home
> loan equity cash out results and access your FREE report PLUS:
> Unlock our best home loan rates · Get free property reports · Get free advice from a lending specialist

**Compliance problem in that copy:** *"Unlock our best home loan rates"* and *"Get free
advice"* both breach [guardrails](../07-compliance-and-guardrails/guardrails.md) — we do not
have rates, and we do not give advice. **Do not reproduce those two lines.** Flag them to
Karlie as a live page needing amendment.

Its intent question is genuinely good segmentation and should be reused in any funnel we
build: *Buy investment · Refinance · Debt consolidation · Renovate · Not sure, just checking
what I have.*

**Borrowing Power Check** captures first name, last name, email, mobile, and property purpose
(home to live in / investment) via a "Request a Callback" modal.

## The duplicate — a real defect

Two mortgage stress calculators exist with **different stress thresholds**:

| | `/mortgage-stress-check/` | `/mortgage-stress/` |
|---|---|---|
| Threshold | *"results 35 per cent or higher are assumed to be deemed mortgage stress"* | *"Results of debt to income higher than 30 per cent are assumed to be in mortgage stress"* |
| Income basis | Pre-tax, no tax modelling | Pre-tax with approximate **2023 tax rates** applied |
| Zones | 20% / 34% / 60% bands | Single threshold |

**The 35% version is the one to reference.** It is the newer, more complete page, it matches
the widely used industry benchmark, and the 30% version is running on 2023 tax rates.
**Never quote both.** Flag the duplicate for consolidation.

## Disclaimers — non-negotiable

Every calculator page carries one, and any asset promoting a calculator must carry an
equivalent. The essential clauses:

> The results from this calculator should be used as an indication only. Results do not
> represent either quotes or pre-qualifications for the product.

> All calculations are estimates – they are not guarantees that you'll be able to afford a
> particular home loan repayment and are not pre-qualifications or pre-approvals for borrowing.

Borrowing Power's assumption, worth knowing because it explains why its numbers run high:
it *"assumes up to 35% of household income may be available for loan repayments"* and does
**not** account for existing debts, credit card limits, living expenses or dependants.

Stamp Duty is current as at **1 July 2025** — re-verify before promoting it.

## Two useful facts the calculators surface

- **Lender serviceability buffer:** *"Lenders typically assess mortgage applications using a
  **3% interest rate buffer** above the actual rate when determining borrowing capacity."*
  (APRA's serviceability floor.) This is a genuinely useful, non-obvious fact for content.
- **The equity worked example:** *"if your home is worth $900,000 and your loan balance is
  $500,000, your equity is approximately $400,000."* A clean, safe illustration.

## The two utilities

**MovingHub** at `/movinghub/` — utility connection and energy comparison, two embedded
Utilihub widgets. A settlement-moment value-add and a natural post-settlement touchpoint.

**Home Loan Finder** at `/home-loan-comparison/` — a comparison tool behind an
*"I Want to Refinance / I Want to Buy a Home"* fork.

## Related

- [funnels-and-landing-pages](../08-channels-and-playbooks/funnels-and-landing-pages.md)
- [guardrails](../07-compliance-and-guardrails/guardrails.md)
