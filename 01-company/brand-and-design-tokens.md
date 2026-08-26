---
id: brand-and-design-tokens
title: Brand assets and design tokens
type: company
status: approved
confidence: verified
source: data/computed-design-tokens.json — live computed CSS captured via Playwright, Aug 2026; assets/ directory from the site scrape
as_of: 2026-08-26
owner: Emily Baulch (Marketing)
tags: [brand, design, tokens, colour, typography, assets]
---

# Brand assets and design tokens

Measured from the live site, not from a brand guide. Any asset we produce — social graphic,
landing page, email template, ad — should read from these values.

## Colour

Six colours are used across the entire site. That is the whole palette.

| Token | Hex | RGB | Use |
|---|---|---|---|
| Canvas | `#1A1411` | `26, 20, 17` | Master background — dark warm espresso. **This is the brand's default surface** |
| Cream | `#F2ECE4` | `242, 236, 228` | Inverted light sections and cards |
| Champagne | `#D1BCA0` | `209, 188, 160` | The accent. Eyebrows, highlights, badges, active states |
| White | `#FFFFFF` | `255, 255, 255` | Primary text on dark; modal and input backgrounds |
| Ink | `#1A1411` | — | Text on light surfaces (same as canvas) |
| Muted grey | `#5A5A5A` | `90, 90, 90` | Meta text, legal footnotes, inactive borders |

**The brand is dark-first.** `body` computes to a `#1A1411` background with white text.
An asset built on a white background is off-brand unless it is deliberately an inverted section.

## Typography

Two families, both self-hosted:

- **Canela Thin** — display serif. Stack: `"Canela Thin", "Playfair Display", serif`
- **Stack Sans Text** — body and UI. Stack: `"Stack Sans Text", Roboto, Arial, sans-serif`

Measured scale (desktop, computed):

| Element | Family | Size | Weight | Line height |
|---|---|---|---|---|
| H1 | Canela Thin | **80px** | **100** | 96px (1.2) |
| H2 | Canela Thin | **70px** | **100** | 84px (1.2) |
| **H3** | **Stack Sans Text** | **24px** | 400 | 28.8px (1.2) |
| Body / `p` | Stack Sans Text | 15px | 400 | 21px (1.4) |
| Nav | Stack Sans Text | 15px | 400 | 21px |

Other sizes in use: 40px, 22px, 18px, 16px, 13.125px, 12px.

**Correction:** internal design summaries state H3 is Canela Thin at 36–42px. The live
computed value is **Stack Sans Text at 24px, weight 400**. The serif is reserved for H1 and
H2 only — the display face carries the two largest levels and nothing below them. That
restraint is the identity; a Canela H3 would break it.

## Geometry

**`border-radius: 0px` everywhere.** Body, headings, buttons and nav all compute to zero.
Sharp corners are a deliberate identity choice — rounded cards are off-brand.

`box-shadow: none` on every measured element. The site does not use elevation.

## Assets on hand

In the scrape's `assets/` directory (195 files):

- **Logos:** `TLS-Logo-horiz.svg`, `TLS-Logo-vert-rev-1.svg` — horizontal and vertical
  reversed, both SVG
- **Award badges:** 4 Australian Broking Awards PNGs + 3 Specialist Finance Group PNGs
- **Team portraits:** the `LUZ_*-Edit*.webp` series — professionally shot, ten images
- **Lender logos:** ~30 including ANZ, CBA, NAB, Bankwest, Suncorp, ING, St George,
  BankSA, Bank of Melbourne, Newcastle Permanent, People's Choice, MyState, ME,
  Firstmac, Resimac, Bluestone, La Trobe, Gateway, AMP, MA Money, HomeStart,
  Australian Military Bank, Great Southern Bank
- **Partner logos:** 12
- **Emoji-style icons:** `emoji-happy`, `emoji-indifferent`, `emoji-stress` — used by the
  mortgage stress calculator

## Design rules for produced assets

1. Dark canvas `#1A1411` by default; cream `#F2ECE4` for inverted sections.
2. Champagne `#D1BCA0` is an **accent**, never a background for long-form text.
3. Canela Thin for the headline only, at weight 100 and large. Never bold it.
4. Stack Sans Text for everything else at 15px baseline.
5. Zero border radius. No drop shadows.
6. Generous vertical space — the site runs ~100px section padding on desktop.

## Related

- [brand-voice](../04-voice-and-messaging/brand-voice.md) — the verbal half of this
- [awards](../05-proof-and-evidence/awards.md) — badge usage rules
