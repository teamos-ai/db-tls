---
id: bank-subject-lines
title: Bank — email subject lines
type: bank
status: approved
confidence: inferred
source: written to the voice rules in 04-voice-and-messaging and mapped to real pipeline triggers in 11-operations. No open-rate data exists — nothing here is performance-tested.
as_of: 2026-08-26
owner: Emily Baulch (Marketing)
tags: [bank, subject-lines, email]
---

# Bank — email subject lines

**4–8 words. No clickbait. No emoji. No "Quick question".** A subject line from a broker
should read like a subject line from a person who has your file open.

> **Tier note:** `inferred`. There is no send history and no open-rate data. Treat these as
> a starting point to test, not as proven performers.

| Subject | Sequence / trigger | Pillar |
|---|---|---|
| **Transactional — pipeline triggered** | | |
| Your loan has settled | Pipeline 3, `Settled` | 2 |
| Your application is with the lender | Pipeline 3, `Submitted` | 2 |
| The lender needs one more thing | Pipeline 3, `MIR's` | 2 |
| Your first repayment is coming up | Onboarding day 7 | 2 |
| Your pre-approval expires in two weeks | Pipeline 4, day 75 | 2 |
| Your build has reached frame stage | Pipeline 5 | 2 |
| **Nurture and education** | | |
| The part of your loan nobody compares | Nurture 1 | 1 |
| What the 3% buffer does to your borrowing power | Nurture 2 | 1 |
| Why your bank prices new customers better | Nurture 3 | 2 |
| Offset, redraw, and which one you actually need | Nurture 4 | 1 |
| What "usable equity" really means | Equity nurture | 1 |
| Pre-approval is not approval. Here's the difference | First home nurture | 1 |
| **Rate health check — month 10** | | |
| Time to check your rate | Pipeline 6, month 10 | 2 |
| Your loan is ten months old | Pipeline 6, month 10 | 2 |
| Worth a look at your rate? | Pipeline 6, month 10 | 2 |
| **Reactivation** | | |
| Still thinking about buying? | Nurture pool | 3 |
| Things have changed since we last spoke | NPW reactivation | 4 |
| Your deposit goal — where are you up to? | Nurture pool, savers | 3 |
| **First home buyer** | | |
| Three schemes most first home buyers miss | FHB nurture 1 | 3 |
| How much deposit do you actually need? | FHB nurture 2 | 3 |
| What stamp duty will cost you in {{state}} | FHB nurture 3 | 3 |
| **Investor** | | |
| The equity you haven't counted | Investor nurture 1 | 1 |
| Why lender number two said no | Investor nurture 2 | 4 |
| Structuring property three before you buy property two | Investor nurture 3 | 1 |
| **Business** | | |
| Super comes out with wages from July | Business, Payday Super | 1 |
| One adviser for the business and the house | Business nurture | 1 |
| What lenders ask for, before they ask | Business nurture | 2 |
| **Newsletter** | | |
| What the 81% figure actually tells you | Newsletter | — |
| What the RBA decision means for your repayment | Newsletter | — |
| **Referral partner** | | |
| Your client settled today | Partner notification | 2 |
| A quick update on the client you sent us | Partner notification | 2 |

## Banned in a subject line

**approved · pre-approved · guaranteed · you qualify · best rate · lowest rate · save $X ·
act now · urgent · last chance · RE: or FW: on a cold send · any emoji · any figure implying
an outcome**

Also banned: anything implying knowledge of their financial position —
*"Struggling with repayments?"*, *"Your rate is too high"*. We do not know that, and saying it
is both a claim and a platform violation.

## Related

- [email-sequences](../08-channels-and-playbooks/email-sequences.md) · [banned-language](../04-voice-and-messaging/banned-language.md)
