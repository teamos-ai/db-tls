---
id: source-material-readme
title: 99-source-material — read me first
type: source
status: approved
confidence: verified
source: n/a
as_of: 2026-08-26
owner: Tumai (Team OS)
tags: [sources, raw, quarry]
---

# 99-source-material

**Raw, unedited source material. Never generate from this folder.**

Everything here is the quarry. The curated files in folders 00–11 were cut from it and are
re-verified against it. Generating directly from raw source skips the truth tiering, the
compliance layer and the normalisation that make this a database rather than a folder.

## What's here

| Item | What it is |
|---|---|
| [source-register](source-register.md) | **Start here.** Every source, its authority, its date, and what no source covers |
| `website-scrape/` | 71 markdown extractions of every published page, August 2026 |
| `ghl-operational-database-RAW.md` | Karlie's pipeline configuration plus proposed funnel, calendar and AI designs. **Mixed tiers — see the register** |
| `computed-design-tokens.json` | Live computed CSS, measured via Playwright |
| `sitemap-inventory.json` | Complete route inventory |

## If you are looking for a fact

Go to [00-start-here/INDEX.md](../00-start-here/INDEX.md) instead. If the fact you want is
here but not in a curated file, that is a gap — add it to the curated file with a tier and a
source, then use it.
