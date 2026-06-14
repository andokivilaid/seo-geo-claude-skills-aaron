# Rank Tracker — Setup & Baseline Design

**Skill:** `monitor/rank-tracker` · **Domain:** insly.com · **Date:** 2026-06-14
**Mode:** Tier 1 (no SEO tool / GSC connected) · **Run type:** Initial setup — **no baseline exists**

> **Critical:** Insly has **no ranking data connected**. There is no Ahrefs / Semrush / SE Ranking export and no Google Search Console property wired in. Therefore **every position value below is N/A — this run defines the tracking system and the keyword set, it does NOT report positions.** Per the rank-tracker Decision Gate, a setup with no baseline is recorded as the *first snapshot scaffold*; we do not invent a "previous" position. The first real numbers arrive only after a connector (GSC first) is attached.

---

## 1. Tracking configuration

| Parameter | Value | Source |
|-----------|-------|--------|
| Domain | insly.com (canonical locale `/en/`) | Measured (crawl) |
| Market / geo | Global B2B; priority EN markets: **UK, US, Canada, Australia, South Africa, UAE** | Estimated (from `suggest-broker.json` geo-modifiers + Insly's MGA/broker ICP) |
| Device | Desktop primary (B2B SaaS buyers), mobile secondary | Estimated |
| Language | English (`/en/`) | Measured |
| Update frequency | Money terms: **weekly** · long-tail/blog: **monthly** | Recommended |
| Tracking start (baseline) | First GSC connection date — **not yet set** | N/A |
| Competitor watchlist | Applied Systems, Vertafore, Duck Creek, Guidewire, Novidea, Socrates (own sub-brand) | Estimated (category incumbents) |

---

## 2. Tracking keyword set

Grounded in real Insly target pages (crawl/linkgraph) and real Google Autocomplete demand (`suggest-*.json`). **Volume and difficulty are UNAVAILABLE (no SEO tool) — labelled N/A. Do not present these as Measured demand.**

### Tier A — Core money terms (map to existing high-PageRank product pages)

| # | Keyword | Target page (Measured exists) | Volume | Difficulty | Baseline pos | Intent |
|---|---------|-------------------------------|--------|-----------|--------------|--------|
| A1 | mga software | `/en/mga-insurance-software/` | N/A | N/A | N/A | Commercial |
| A2 | mga insurance software | `/en/mga-insurance-software/` | N/A | N/A | N/A | Commercial |
| A3 | insurance software | `/en/insurance-software/` | N/A | N/A | N/A | Commercial |
| A4 | insurance software for insurers | `/en/insurance-software/` | N/A | N/A | N/A | Commercial |
| A5 | insurance broker software | `/en/insurance-broker-software/` | N/A | N/A | N/A | Commercial |
| A6 | insurance claims management software | `/en/claims-management-software/` | N/A | N/A | N/A | Commercial |
| A7 | insurance product builder / no-code insurance product | `/en/insurance-product-builder/` | N/A | N/A | N/A | Commercial |
| A8 | insurance product distribution software | `/en/insurance-product-distribution/` | N/A | N/A | N/A | Commercial |
| A9 | insurance accounting & reporting software | `/en/accounting-reporting-insurance-mga/` | N/A | N/A | N/A | Commercial |
| A10 | low-code insurance software | `/en/insurance-broker-software/` | N/A | N/A | N/A | Commercial |

### Tier B — Demand-grounded expansion (from `suggest-*.json`, real autocomplete)

| # | Keyword | Source file | Best-fit page | Volume | Pos |
|---|---------|-------------|---------------|--------|-----|
| B1 | best insurance broker software | suggest-broker | broker-software (gap: no "best/compare" asset) | N/A | N/A |
| B2 | insurance broker software uk | suggest-broker | broker-software (UK geo gap) | N/A | N/A |
| B3 | commercial insurance broker software | suggest-broker | broker-software | N/A | N/A |
| B4 | insurance broker crm software | suggest-broker | broker-software (CRM angle gap) | N/A | N/A |
| B5 | insurance broker quoting software | suggest-broker | product-builder / broker | N/A | N/A |
| B6 | insurance software for agents | suggest-insurance-software | **gap — no agent page** | N/A | N/A |
| B7 | insurance agency software systems | suggest-insurance-software | **gap** | N/A | N/A |
| B8 | insurance software ai | suggest-insurance-software | Insurance Copilot / ai.insly.com | N/A | N/A |
| B9 | insurance distribution software | suggest-insurance-software | product-distribution | N/A | N/A |
| B10 | insurance automation software | suggest-insurance-software | Copilot / product-builder | N/A | N/A |

> Note: `suggest-mga.json` is **polluted** — most "mga ..." autocompletes are Tagalog ("mga uri ng software", "mga bahagi ng software") where *mga* is a plural article, not Managing General Agent. Use Tier A1/A2 with full qualifiers ("mga software insurance", "mga insurance software") and **do not** track bare "mga software" as a clean Insly signal.

### Tier C — Brand & entity terms (track for AI-answer and brand-defence)

| # | Keyword | Why |
|---|---------|-----|
| C1 | insly | Brand — must rank #1; watch for brand dilution / competitor bidding |
| C2 | insly insurance software / insly reviews / insly pricing | Brand-modifier; pricing page exists |
| C3 | socrates systems / nora / formflow insly | Sub-brand entity coverage |
| C4 | what is insly / is insly good | AI-answer / consideration queries |

---

## 3. Snapshot schema

Each tracking run writes one row per (keyword × device × geo). Suggested CSV / JSON shape so snapshots are diffable over time:

```json
{
  "snapshot_id": "insly-2026-06-14",
  "captured_at": "2026-06-14",
  "is_baseline": true,
  "source": "N/A — no connector yet",
  "rows": [
    {
      "keyword": "mga insurance software",
      "tier": "A",
      "geo": "uk",
      "device": "desktop",
      "target_url": "https://insly.com/en/mga-insurance-software/",
      "position": null,            // integer once GSC/SEO tool connected
      "position_source": "N/A",    // measured | user-provided | estimated | N/A
      "ranking_url_actual": null,  // which URL actually ranks (canonical-dupe check)
      "serp_features_owned": [],   // snippet | paa | sitelinks | video | image | none
      "ai_overview_present": null, // true | false | N/A
      "delta_vs_baseline": null,   // null on first snapshot
      "notes": ""
    }
  ]
}
```

**Delta rules:** first snapshot sets `is_baseline:true`, all deltas null. Subsequent runs compute `delta_vs_baseline` and `delta_vs_previous`; each delta carries its `position_source`. A position change is only reportable if both endpoints share a source type (don't diff a GSC position against an estimate).

**Canonical-dupe watch:** Insly serves the same pages at `/en/<slug>/` **and** `/<slug>/` (Measured). The schema's `ranking_url_actual` field exists specifically to catch Google ranking the non-canonical `/`-variant — a real, current duplication risk for these money pages.

---

## 4. AI-answer (GEO) checks

Run alongside SERP tracking. These are **manual / observational** until an AI-monitor connector exists; mark each Measured (if you actually ran the prompt and logged the screenshot) or N/A.

| Engine | Check prompt(s) | What to log | Cadence |
|--------|-----------------|-------------|---------|
| **ChatGPT** (Search) | "best MGA insurance software", "insurance software for brokers UK", "what is Insly" | Is insly.com cited? Cited URL? Position in answer? Competitors named? | Monthly |
| **Perplexity** | Same 3 prompts + "low-code insurance platform for insurers" | Source list inclusion + rank; is the cited page a `/en/` or `/`-dupe URL? | Monthly |
| **Google AI Overview (AIO)** | Run Tier A queries logged-in; note if AIO appears and whether Insly is a cited source | AIO present (y/n), Insly cited (y/n), citation page | Weekly for Tier A |
| Gemini / Claude | "Recommend insurance software for an MGA" | Brand mention (y/n) — recognition signal | Quarterly |

> GEO baseline context from the audit: robots.txt **allows all AI crawlers** (GPTBot, ClaudeBot, Google-Extended, CCBot, PerplexityBot, Bytespider) — crawl access is not the blocker. The real GEO risk is **no Wikidata / Knowledge Graph entity** (`kg.py` → recognized:false), which suppresses confident AI brand citation. Track AI brand-mention rate as the leading indicator that the entity gap is closing.

---

## 5. What to connect to get real positions

| Connect | Unlocks | Effort | Priority |
|---------|---------|--------|----------|
| **Google Search Console** (verify insly.com property) | **Real average position, impressions, clicks, CTR per query/page** — the single biggest unlock; turns every N/A in Tier A/B into Measured | Free, ~1 day (DNS/HTML verify) | **#1** |
| GSC API export | Automated weekly snapshots into the schema above (vs manual UI export) | Free | #2 |
| Paid SEO tool (Ahrefs / Semrush / SE Ranking MCP) | Volume + difficulty (still N/A today), geo-segmented desktop positions, competitor SoV | Paid | #3 |
| AI-visibility monitor (or manual prompt log) | Automated ChatGPT/Perplexity/AIO citation tracking | Paid / manual | #4 |

Until GSC is connected, this file is the **tracking design + baseline scaffold only**. No position has been measured or estimated.

---

## Handoff Summary

- **Objective:** Design the rank-tracking system for insly.com (keyword set, snapshot schema, AI-answer checks) given zero ranking data.
- **Key findings:** 10 core money terms map cleanly to existing high-PageRank product pages; 10 demand-grounded expansion terms surface real gaps (no "agent/agency" page, no "best/compare" asset, UK geo thin). `suggest-mga.json` is Tagalog-polluted — track qualified MGA terms only. Canonical `/en/` vs `/` duplication must be watched per-keyword. GEO blocker is the missing Wikidata entity, not crawl access.
- **Evidence:** linkgraph.json (target pages + PageRank), suggest-broker/insurance-software/mga.json (demand), robots.json (AI bots allowed), kg-insly.json (no entity).
- **Open loops → `memory/open-loops.md`:** Connect GSC to convert positions from N/A to Measured; resolve `/en/` vs `/` duplication before it splits ranking signals; build agent/agency + "best X" assets for B6/B7/B1.
- **Status:** DONE_WITH_CONCERNS (system designed; no position data measurable in Tier 1).
- **Next skill:** `alert-manager` (initial setup, no baseline → wire thresholds for when positions start flowing). See `alert-config.md`.
