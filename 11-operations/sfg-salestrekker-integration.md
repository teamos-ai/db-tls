---
id: sfg-salestrekker-integration
title: SFG, Salestrekker and the integration constraint
type: system
status: approved
confidence: verified
source: email thread "Intergration into Sales Trekker" (Karlie ↔ SFG, 26 Aug – 3 Sep 2026); "Re - API Key Request" (SFG, 9 Sep 2026) with attachment "SFGconnect API Integration Checklist & Indemnity"; Granola transcripts 26 Aug, 4 Sep, 9 Sep 2026
as_of: 2026-09-11
owner: Karlie Scharfenberg
tags: [operations, sfg, salestrekker, api, integration, compliance, blocker]
---

# SFG, Salestrekker and the integration constraint

**The single biggest architectural constraint on the dream pipeline.** Read this before
designing any stage that touches submission, approval or settlement.

## The two systems and what each owns

| | **OS (GoHighLevel)** | **Salestrekker (via SFGconnect)** |
|---|---|---|
| Record type | **Customer** — one tile per client or couple | **Deal** — one tile per loan |
| Owns | Lead capture, qualification, credit guide, fact find, documents, comms, retention, marketing, reporting | Loan processing, lender submission, compliance audit, commissions |
| Required by | TLS | **SFG (aggregator) — mandatory for home loans** |
| Commercial and asset finance | **Entirely in OS** (10 Aug decision) | Not used |

Karlie, 4 Sep: *"Think OS is the customer. Think sales tracker is the deal."*

## What SFG will and won't allow

**In (OS → Salestrekker): being approved.**
Karlie to SFG, 2 Sep 2026:
> We are only wanting the API and Integration to go from High Level CRM into Sales Trekker the same
> as we currently have for our website leads to go into Sales Trekker… we don't need the data to
> come out of sales trekker.

**Out (Salestrekker → OS): not requested, and not expected to be allowed.**
Karlie, 26 Aug:
> They just don't want their Brokers having two CRMs. So they're being really difficult with trying
> to get information in and out. We can get information in, but getting it out is just like, no,
> we're not going to do that for you.

**Consequence:** settlement and approval status **will not flow back automatically**. Admin updates
OS manually from the bank's settlement email. Every stage after submission is **manually driven**
in OS.

## Approval process — status as at 11 Sep 2026

| Date | Event |
|---|---|
| 26 Aug | Karlie asks SFG's General Manager (Blake Buchanan) for approval |
| 26 Aug | Referred to the Managing Director (**William Lockett**), who under SFG's new process is **the only person who can approve** |
| 2 Sep | SFG: indemnity wording just settled; document to follow; *"once this document has been executed by you and returned to SFG your request to have high level integrated will be approved accordingly"* |
| 9 Sep | SFG National Operations Manager (Sherifaye Huseyin) sends the **API Integration Checklist & Indemnity**. *"Your request for any integration into SFGconnect is not approved until you have been formally notified by SFG in writing."* |
| 9 Sep | Karlie forwards to Tumai to complete the back pages |

Karlie also advised Maryanne (360 Mortgage Solutions) to request the same agreement.

## The checklist — requirements the integration must meet

**Part 1 · Minimum data security (Yes/No, with evidence)**
1. ISO 27001 or SOC 2 Type II certification, **or actively working towards it within six months**
2. **Penetration test completed within the last 12 months**, with evidence
3. **Data stored in Australia or New Zealand** in a reputable data centre (AWS, Azure, DigitalOcean)
4. The solution **does not use screen scraping, bot technologies or AI agents**
5. The solution **does not store user credentials for any other platform**

**Part 2 · Integration information:** application name · data flow (into, out of, or both) · data
fields pushed or extracted · connection method (direct, middleware, serverless, gateway) · API
call frequency · who performs the integration · other considerations.

**Part 3 · Indemnity** to *Mortgage Specialists Pty Ltd as trustee for The Janet Smith Family Trust
trading as Specialist Finance Group* — covering integration defects, unauthorised access to
SFGconnect data, breach of the Part 1 requirements or misrepresentation, privacy breaches, and
third-party claims. **Continuing, payable on demand, survives termination.**

**Part 4 · Revocation:** SFG may withdraw approval **at any time, at its sole discretion**, effective
immediately on notice; the integration must then be disconnected at the holder's cost.

Full text: [sfgconnect-api-checklist](../99-source-material/client-documents/sfgconnect-api-checklist-RAW.md).

## Risks to resolve before anyone signs — `inferred`, verify

> These are reasoned from the checklist wording, not confirmed. **Karlie personally carries the
> indemnity**, so answer each honestly before signing.

1. **Data residency (item 3).** GoHighLevel is a US-hosted platform. If sub-account data isn't
   stored in AU/NZ, the honest answer is "No" — which may fail the checklist. **Verify HighLevel's
   data residency for this sub-account first.**
2. **"No AI agents" (item 4).** The integration path must not involve an AI agent. OS features AI
   tooling; the integration itself must be a plain API or middleware connection, and the answer
   must reflect that accurately.
3. **Certification and pen test (items 1–2).** Evidence would have to come from the platform
   vendor (HighLevel) and any middleware vendor (Zapier/Make), not from Team OS. Confirm what
   exists and what can be attached.
4. **Middleware credentials (item 5).** A Zapier/Make bridge storing Salestrekker credentials could
   breach this. An API-key connection is not the same as stored user credentials — confirm with SFG.
5. **The indemnity is uncapped and continuing.** It is the client's legal decision. Team OS
   completes technical fields only; it should not advise Karlie to sign.

## Design implications for the pipeline

- **Build the pipeline so it works fully without the integration.** Approval is not guaranteed and
  can be revoked at any time.
- **The handover stage ("Submit to Sales Tracker") is the integration point.** Whether by API or by
  hand, the data pushed is the client front-end — identity, assets, liabilities, expenses (Karlie,
  26 Aug). Everything else the broker already knows.
- **Post-submission stages in OS are status mirrors**, updated manually. Keep them few, and make
  each manual update a task with an owner, not an expectation.
- **Settlement is the re-entry point** into OS automation — the manual settlement update should be
  the trigger for the retention lifecycle.
- The website apply form currently posts to Salestrekker through an existing SFG-approved
  connection that Dylan set up. Moving it to OS first means OS must forward qualified deals, or
  Salestrekker loses its lead feed.

## Related

- [pipeline-decisions-log](pipeline-decisions-log.md) · [automation-requirements](automation-requirements.md)
- [licensing-and-entity](../01-company/licensing-and-entity.md) · [privacy-and-data](../07-compliance-and-guardrails/privacy-and-data.md)
