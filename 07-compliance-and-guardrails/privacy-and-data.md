---
id: privacy-and-data
title: Privacy, data handling and the referral-partner disclosure boundary
type: compliance
status: approved
confidence: verified
source: theloanssuite.com.au/privacy-policy (last updated 12 Jul 2024); Privacy Act 1988 (Cth)
as_of: 2026-08-26
owner: Karlie Scharfenberg
tags: [privacy, data, referral-partners, compliance]
---

# Privacy, data handling and the referral-partner boundary

## What the published policy commits to

The Loans Suite complies with the **Privacy Act 1988 (Cth)** and the **Notifiable Data
Breach** scheme. The policy is dated **12 July 2024**.

Material commitments any asset must stay consistent with:

- Personal information collected includes credit information, and is exchanged with
  **credit reporting bodies** (Equifax, Experian, Dun & Bradstreet are named).
- Information may be disclosed to lenders — **Adelaide Bank, ANZ Bank, Bankwest and Pepper
  Money** are named explicitly — as well as CRBs, mortgage and title insurers, the client's
  own advisers, and referral partners.
- **Offshore processing:** service providers and employees in the **Ukraine** and the
  **Philippines** assist with processing and reviewing credit applications and technical
  support. The policy states offshore personnel are **not** used for marketing or sales.
  Data hosting also touches the US, and third parties operate in India and the UK.
- **E-consent:** submitting any online form, application, calculator or query consents to
  receiving notices by email.
- Direct marketing is permitted with an opt-out on every channel.

## The referral-partner disclosure boundary

This is the sharpest live risk in the business's marketing model, because the
[referral-partner network](../02-offer-and-lending/referral-partner-network.md) and the
partner milestone notifications in [11-operations](../11-operations/funnel-architecture.md)
both involve telling a third party something about a client.

**The rule:** a referral partner may be told the *status of the referral they made*, not the
*contents of the client's file*.

| Safe to send a partner | Never send a partner |
|---|---|
| "The client you referred has been in touch and we've had our first conversation." | The client's income, expenses, debts or credit file |
| "Their application has progressed." | The lender's name, unless the client has consented |
| "This one has settled — thanks for the introduction." | The loan amount, rate, LVR or property address |
| A generic thank-you or commission/relationship update | Any reason a file was declined |

Milestone automation must be built to this boundary. A webhook that fires
*"John's loan formally approved with [Lender]"* to a partner discloses both the lender and
the outcome, and needs the client's express consent before it can run. Treat consent
capture as a **prerequisite to launching partner notifications**, not a later fix.

## Rules for this repository

- **Never commit** customer lists, lead exports, CRM records, contact spreadsheets, call
  recordings containing client detail, credit files, or API keys.
- `.gitignore` excludes `.env*` from the first commit.
- Testimonials are stored at the attribution level already published (first name + last
  initial). Never enrich them with a full name found elsewhere.
- The repo is **private**. It holds positioning, competitor intelligence and operational
  detail.

## A defect worth flagging to the client

The published privacy policy contains **copy-paste artifacts from another business** — it
refers to *"Domain Loan Finder"* and *"domainloanfinder.com.au"* in two places, and several
contact fields are blank (`Tel:`, `Email:`, `Post:`, and multiple "please contact us at ."
sentences with no address).

This is a real compliance exposure: a privacy policy that names the wrong entity and omits
the contact point for access, correction and complaints is weak under APP 1. It is on the
[enrichment roadmap](../00-start-here/ENRICHMENT-ROADMAP.md) as a client action, not a
marketing task.

## Related

- [guardrails](guardrails.md) · [approval-rules](approval-rules.md)
- [referral-partner-network](../02-offer-and-lending/referral-partner-network.md)
