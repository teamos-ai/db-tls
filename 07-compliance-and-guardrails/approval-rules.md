---
id: approval-rules
title: Approval rules — what needs sign-off before it publishes
type: compliance
status: approved
confidence: inferred
source: reasoned from the regulatory posture in guardrails.md and standard aggregator practice; NOT yet confirmed with Karlie or Specialist Finance Group
as_of: 2026-08-26
owner: Tumai (Team OS)
tags: [approval, sign-off, workflow, compliance]
---

# Approval rules

> **Tier note:** this file is `inferred`. The thresholds below are a defensible default
> drawn from the regulatory posture, not a policy Karlie has confirmed. Confirming the
> actual sign-off chain — and whether Specialist Finance Group requires aggregator review
> of outward-facing marketing — is a top-three item on the
> [enrichment roadmap](../00-start-here/ENRICHMENT-ROADMAP.md).

## Ship without sign-off

- Social posts, blog articles and newsletter sections built **only** from `verified` files
  in this database, using existing site claims, with no new number and no client story.
- Reformatting or re-cutting copy already live on theloanssuite.com.au.
- Internal drafts, briefs and strategy documents.

## Needs Karlie's sign-off

- Anything naming a **client** or using a **testimonial** in a new context.
- Anything stating a **business figure** — volumes, counts, years, panel size changes.
- Any **new offer, package, guarantee or price** framing.
- **Recruitment / sub-broker** copy — it makes commercial promises about splits and support.
- Any asset for the **SMSF** line, given the 10 August 2026 residential restriction.
- Any **paid ad** — spend plus regulated product plus platform policy.

## Needs a compliance check beyond Karlie

- Anything reproducing or paraphrasing the **licensing block**, or using the licensee's
  name or ACL outside the standard footer.
- Any **lender name** used outside the privacy policy's disclosure context.
- Any **calculator** embedded on a page we build, which must carry its disclaimer.
- Any **AI agent** — chat widget or voice — before it goes live to the public. A model that
  answers a credit question incorrectly is a credit-assistance event.
  See [chat-widget-and-voice-agent-spec](../10-faq-and-objections/chat-widget-and-voice-agent-spec.md).

## Never ships, regardless of sign-off

The items in [guardrails](guardrails.md). Client approval does not create compliance
headroom — Karlie cannot authorise the word "guaranteed" onto a credit product.

## Related

- [guardrails](guardrails.md) · [claims-policy](claims-policy.md)
