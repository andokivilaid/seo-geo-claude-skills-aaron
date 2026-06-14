# Content Refresh Plan — insly.com

**Skill**: content-refresher (v9.9.10) · **Date**: 2026-06-14 · **Mode**: Tier 1 (no per-URL traffic/rankings)
**Scope**: 196 blog posts + 25 glossary terms (the real refreshable surface). Decay framework + workflow.
**Labeling**: age/lastmod/cadence are Measured (sitemap + wayback); decay *priority* is **Estimated** (proxy-based — no traffic data). This is a prioritization *framework*, not a per-URL verdict, because the data needed for true decay scoring is not connected.

---

## Data reality check (read first)

The project brief says "468 blog posts." The measured sitemap shows that number is **inflated by taxonomy pages**:

| Type | Count | Source |
|------|------:|--------|
| Real blog posts | **196** | Measured, `sitemap.json` (`/blog/` minus `/tag/`) |
| Blog `/tag/` archive pages | 272 | Measured (thin/auto-generated — do NOT refresh; `noindex` per technical TS-02) |
| Glossary terms | 25 | Measured |
| **True refresh surface** | **~221** | 196 posts + 25 glossary |

Refresh effort targets the **196 posts + 25 glossary terms**, not 468. The 272 tag pages are a technical cleanup item, not content to refresh.

**What's missing for true decay scoring** (all N/A — no connector):
- Per-URL organic traffic & 6-month trend → needs **GSC** or GA4.
- Per-keyword rankings & position deltas → needs **GSC** or Ahrefs/Semrush.
- SERP intent shifts & competitor freshness → needs SERP data.

Without these, "which posts lost the most traffic" is **unanswerable**. We substitute **measured age + dated-claim proxies** to prioritize, and flag every priority as Estimated.

---

## Decay signals we DO have (Measured)

### 1. Age distribution by `lastmod` (196 posts… measured across the 468 blog URLs incl. tags)

Blog-URL `lastmod` buckets relative to today (2026-06-14), Measured from `sitemap.json`:

| Age band | Blog URLs | Decay risk |
|----------|----------:|-----------|
| < 6 months (fresh) | 41 | Low |
| 6–12 months | 36 | Low-Med |
| 12–24 months | 135 | **Med — watch** |
| 24–36 months | 164 | **High — refresh queue** |
| > 36 months (stale) | 92 | **Highest — audit/prune** |

By `lastmod` year (Measured): 2018: 6 · 2021: 46 · 2022: 24 · 2023: 100 · 2024: 160 · 2025: 92 · 2026: 40. **176 blog URLs have a `lastmod` before 2024** (>2.5 years untouched) — that's the primary refresh backlog.

### 2. Wayback capture cadence (Measured, `wayback.json` — 19,785 captures, 2013→2026)

Captures/year: 2016: 1,590 · 2021: 1,691 · 2024: 2,564 · 2025: **5,117** · 2026: 830 (partial). Publishing/change velocity **accelerated sharply in 2024–2025**. Interpretation: Insly is actively shipping *new* content, which means older posts (the 176 pre-2024 ones) are increasingly likely to be outranked by the site's own fresher pages and competitors — classic decay setup. The Wayback record also shows **1,729 lifetime 404s and 685 301s**, evidence of past URL churn — refreshed/moved posts should be checked for broken inbound links.

### 3. Dated-claim proxies (Measured, slug inspection)

8 posts carry an explicit old year in the slug, e.g. `top-insurance-software-products-for-brokers-and-agents-in-2016`, `insly-market-outlook-mga-industry-trends-2023`, `insly-year-in-review-2022`. Year-in-slug = high-confidence staleness signal. The 2016 product round-up is a prime prune/rewrite candidate.

---

## Decay-prioritization framework (proxy scoring, Estimated)

Since traffic is N/A, score each post 0–100 from measured proxies. Higher = refresh sooner.

```
Priority = (Age weight) + (Dated-claim weight) + (Commercial-proximity weight) + (Topic-volatility weight)
```

| Factor | How to score (Measured input) | Max pts |
|--------|-------------------------------|:------:|
| Age (lastmod) | >36mo = 40, 24–36mo = 30, 12–24mo = 15, <12mo = 0 | 40 |
| Dated claim | year-in-slug or "in 20XX" / old stat in title = 25 | 25 |
| Commercial proximity | links to/from a money page or targets a product term = 20 | 20 |
| Topic volatility | regulation/pricing/AI/product topics decay fast = 15 | 15 |

**Tiers:**
- **Tier A — Refresh now (score ≥ 65)**: old + dated + commercial. Start here.
- **Tier B — Queue (40–64)**: 24–36mo posts on evergreen topics.
- **Tier C — Monitor (20–39)**: 12–24mo, stable topics.
- **Tier D — Prune/merge (<20 value, >36mo, off-strategy)**: e.g. the 2016 product round-up — rewrite, redirect, or remove.

**Seed Tier A candidates (Measured age/dated signals; commercial weight Estimated):**
1. `…top-insurance-software-products-for-brokers-and-agents-in-2016` — 2016 round-up, lastmod 2021; **Tier D/A** rewrite or prune.
2. `…insly-market-outlook-mga-industry-trends-2023` — dated outlook; refresh to 2026 outlook.
3. `…top-insurance-software-products…` and the 6 oldest 2018-lastmod posts.
4. The 92 posts in the >36-month band — batch-audit top-of-list first.

(True ranking of all 196 requires GSC traffic to weight by value — see "Data needed" below.)

---

## Refresh workflow (per Tier-A post)

Following the content-refresher 9-step contract, adapted for no-traffic mode:

1. **CORE-EEAT quick score** — estimate the 8 dimensions; flag weak Recency/Referenceability/Experience. Hand veto-level concerns to content-quality-auditor.
2. **Confirm decay drivers** — dated claims, broken links (check against the 1,729 historical 404s), stale stats, intent drift. Evidence-label each.
3. **Define updates** — refresh statistics to 2026, add new sections for gaps (competitor/PAA), fix broken internal/external links, update product names (Insurance Copilot, NORA, FormFlow, Socrates).
4. **GEO pass** — add a 40–60 word definition near the top, 2–3 quotable standalone statements, a short Q&A block, and dated citations. Insly's robots is fully AI-open (technical audit §7), so every refresh is a live citation opportunity for ChatGPT/Perplexity/AI Overviews.
5. **Internal links** — wire the refreshed post to the relevant money page (ties into internal-linking IL-07/IL-09).
6. **Republish-date treatment** (content-refresher Step 8 thresholds):
   - ≥50% rewritten → update published date.
   - 20–50% changed → "last updated" date.
   - <20% → keep original date.
7. **Update `lastmod`** in the sitemap, refresh schema dates, clear cache.
8. **Monitor 4–6 weeks** — **requires GSC** to confirm recovery; until connected, monitoring is N/A and refreshes are shipped on quality judgment, not measured lift.

---

## Glossary terms (25)

Measured `lastmod`: 22 updated in 2024, 2 in 2025, 1 in 2022. Mostly fresh. Glossary/definitional content is **high-GEO-value** (AI engines cite definitions). *Action (P2)*: low decay risk, but run the GEO pass (Step 4) on all 25 — tight 40–60 word definitions + `DefinedTerm`/`FAQPage` schema — to maximize AI-citation capture. Not urgent for decay; valuable for GEO.

---

## Batch plan

| Phase | Target | Action | Blocker |
|-------|--------|--------|---------|
| 0 | 272 tag pages | `noindex` + drop from sitemap (NOT a refresh) | coordinate with technical TS-02 |
| 1 | ~8 dated-slug + 6 oldest posts (Tier A/D) | Rewrite/prune/refresh | none — start now |
| 2 | 92 posts >36mo | Batch-audit, score, refresh Tier A | GSC ideal for value-ranking |
| 3 | 164 posts 24–36mo | Queue (Tier B) | GSC |
| 4 | 25 glossary terms | GEO + schema pass | none |

---

## Data needed to upgrade this from framework → ranked plan

| Need | Unlocks | Source |
|------|---------|--------|
| Per-URL organic traffic + 6mo trend | True "lost-most-traffic" ranking; value-weighting | **GSC** (free) or GA4 |
| Per-keyword position deltas | Decay confirmation, recovery tracking | GSC or Ahrefs/Semrush |
| SERP/competitor freshness | Intent-shift detection, gap sections | SERP tool |
| Per-post word count / content body | Rewrite-vs-refresh threshold (>50% stale) | rendered crawl |

Connect **GSC first** — it is free and unlocks 3 of the 4 gaps.

---

### Handoff Summary

- **Status**: DONE_WITH_CONCERNS
- **Objective**: Build a decay-prioritization framework and refresh workflow for insly.com's content surface without per-URL traffic data.
- **Key Findings / Output**: Real refresh surface is **196 posts + 25 glossary terms** (not 468 — 272 are tag pages). **176 blog URLs have lastmod before 2024**; 92 are >36 months stale (Measured). Publishing velocity spiked in 2024–25 (5,117 Wayback captures in 2025), so old posts are being outpaced. Delivered a 4-factor proxy scoring model (Age/Dated-claim/Commercial/Volatility) with A/B/C/D tiers since traffic is N/A.
- **Evidence**: `sitemap.json` (lastmod buckets, 196 posts vs 272 tags, year histogram), `wayback.json` (19,785 captures, 5,117 in 2025, 1,729 lifetime 404s) — all **Measured**. Per-URL decay priority **Estimated** (proxy-based). Traffic/rankings **N/A**.
- **Assumptions**: Commercial-proximity and topic-volatility weights are Estimated (no link/traffic data per post). Tier-A seeds chosen on measured age + dated-slug signals; full 196-post ranking deferred until GSC connects.
- **Open Loops**: No GSC/GA4 → cannot rank by traffic value or verify post-refresh recovery; Phase 0 tag-page noindex must coordinate with technical TS-02; per-post body word count needed for rewrite-vs-refresh calls.
- **Recommended Next Skill**: content-quality-auditor (CORE-EEAT gate on each refreshed post before republish, per content-refresher's required gate check).
- **Priority item IDs**: Phase 1 (dated-slug + oldest posts), Phase 0 (tag-page noindex), connect-GSC (unblocks ranked plan).
