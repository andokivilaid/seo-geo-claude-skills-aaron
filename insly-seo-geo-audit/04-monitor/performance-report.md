# SEO/GEO Performance Report — Insly

**Skill:** `monitor/performance-reporter` · **Domain:** insly.com · **Prepared:** 2026-06-14
**Reporting period:** Baseline snapshot (first capture) · **Comparison period:** N/A (no prior period)
**Audience:** Executive / stakeholder · **Mode:** Tier 1 (no GA4 / GSC / SEO tool connected)

> **How to read this report.** Sections backed by live repo connectors are **Measured** and populated. Traffic, rankings, conversions, backlinks, and Core Web Vitals require GA4 / GSC / a paid SEO tool that are **not yet connected** — these are marked **N/A — Not yet evaluated**, never fabricated. This is the reusable report **template**: each N/A row activates the moment its connector is attached.

---

## 1. Report parameters

| Field | Value |
|-------|-------|
| Domain | insly.com (canonical `/en/`) |
| Period / comparison | Baseline / N/A — no prior period exists |
| Report type | Full SEO + GEO health baseline |
| Data freshness | 2026-06-14 (single capture) |
| Data sources | Repo connectors: crawl, sitemap, onpage, robots, schema_lint, linkgraph, kg, suggest. **Not connected:** GA4, GSC, Ahrefs/Semrush, PageSpeed (429), AI-monitor |

---

## 2. Executive summary

**Overall rating: Structurally healthy, commercially un-measured.** Insly has a technically sound, content-rich, AI-crawlable site with a clean flat architecture — but **zero performance visibility** because no analytics/search-console data is connected. The highest-leverage actions are not content fixes; they are **(a) connecting GSC+GA4** to make performance measurable and **(b) closing two structural gaps**: the missing homepage H1 and the absent Knowledge-Graph entity.

| Metric at a glance | Value | Source |
|--------------------|-------|--------|
| Organic sessions / users | **N/A — needs GA4** | N/A |
| Conversions / demo requests | **N/A — needs GA4** | N/A |
| Keyword rankings (avg position) | **N/A — needs GSC** | N/A |
| AI citation rate | **N/A — needs AI monitor / manual log** | N/A |
| Domain authority (CITE) | **Not yet evaluated** (needs backlink data + OpenPageRank key) | N/A |
| Content quality (CORE-EEAT) | **Not yet evaluated** (run content-quality-auditor) | N/A |
| Indexable URLs in sitemap | **523** | Measured (sitemap.json) |
| Pages crawled (sample) | **40**, all reachable at depth 1 | Measured (crawl/linkgraph) |
| SEO ROI | **N/A** (no traffic/conversion/revenue inputs) | N/A |

**Top 3 wins (Measured):** (1) robots.txt allows all major AI crawlers with 0 disallow rules — GEO-friendly baseline; (2) deep content (homepage 4,004 words; product pages ~3,700–4,075); (3) flat, strongly interlinked architecture (max depth 1, ~38 internal in-links/page).

**Top 3 watch areas (Measured):** (1) homepage has **0 H1 tags**; (2) **duplicate URL structure** `/en/<slug>/` vs `/<slug>/` on money pages (canonical-split risk); (3) **no Wikidata / Knowledge-Graph entity** — caps AI brand citation.

---

## 3. Organic traffic — **N/A — Not yet evaluated**

Sessions, users, pageviews, engagement/bounce, source/device split, top landing pages: all require **GA4**. None connected — do not infer from page count. *Activates on GA4 connection.*

---

## 4. Keyword rankings — **N/A — Not yet evaluated**

Position ranges, distribution, top movers, SERP features: require **GSC** (real positions) and/or a paid SEO tool (volume/difficulty). None connected. The tracking *design* and target keyword set are defined in `rank-tracker-setup.md`; positions stay N/A until GSC is verified. *For raw position deltas, defer to rank-tracker.*

---

## 5. GEO / AI performance — partially Measured (readiness), citations N/A

| Signal | Status | Source |
|--------|--------|--------|
| AI crawler access (GPTBot, ClaudeBot, Google-Extended, CCBot, PerplexityBot, Bytespider) | **Allowed — all 6, 0 disallow rules** | Measured (robots.json) |
| Sitemap declared for AI/search discovery | Yes — `/en/sitemap_index.xml` | Measured |
| Knowledge-Graph / Wikidata entity | **Absent — `kg.py reconcile "Insly"` → recognized:false, 0 matches** | Measured (kg-insly.json) |
| Schema for entity grounding | Organization + WebSite + BreadcrumbList present and valid | Measured (schema-home.json) |
| Actual AI citation rate (ChatGPT/Perplexity/AIO) | **N/A** — needs manual prompt log or AI-monitor | N/A |

**Read:** Insly's GEO *plumbing* is good (crawlable, schema present), but the **missing entity** is the single biggest GEO ceiling — AI engines cannot confidently disambiguate/cite a brand with no Knowledge-Graph node. This is an observed gap, not a measured citation loss.

---

## 6. Domain authority (CITE) — **Not yet evaluated**

Requires referring-domain data (no backlink tool) and an OpenPageRank key (not set). See `backlink-analysis.md`. CITE dimension scores and veto status (T03/T05/T09) cannot be computed yet.

---

## 7. Content quality (CORE-EEAT) — **Not yet evaluated**

No CORE-EEAT run in this monitor phase. Run `content-quality-auditor` for 8-dimension scoring + veto checks (T04/C01/R10). Content depth is high (Measured), which is a favorable input but not a score.

---

## 8. Backlinks — **N/A — Not yet evaluated**

Referring domains, anchor mix, acquisition trend, competitive position: all N/A (no link database). Framework and deterministic opportunities are in `backlink-analysis.md`.

---

## 9. Content performance — partially Measured (inventory only)

| Signal | Value | Source |
|--------|-------|--------|
| Total indexable URLs | 523 | Measured (sitemap) |
| Blog posts | 468 | Measured |
| Glossary terms | 25 | Measured |
| Product/solution/company pages | ~20 | Measured |
| Per-URL traffic / engagement / conversions | **N/A — needs GA4** | N/A |
| Top / decaying content | **N/A** (no traffic to rank by) | N/A |

A 468-post blog with **no per-page traffic data** is the clearest argument for connecting GA4 — content ROI and refresh prioritization are blind without it.

---

## 10. On-page issues (Measured — current, actionable)

| Issue | Detail | Priority | Owner |
|-------|--------|----------|-------|
| Homepage 0 H1 | Home has 5×H2 + 5×H3 but **no H1** (`onpage-home.json`); product pages each have exactly 1 H1 | High | Web/dev |
| Duplicate URL structure | Money pages live at `/en/<slug>/` **and** `/<slug>/` — canonical-split / dilution risk | High | Web/dev |
| Orphaned subdomain | `ai.insly.com` in:0/out:0 — not in main internal link graph | Med | SEO |
| 4 orphan URLs | Flagged by linkgraph | Med | SEO |
| Entity gap | No Wikidata node → create entity + `sameAs` | High | SEO/Brand |
| CWV unknown | PageSpeed returned HTTP 429 (keyless quota) — **not measured** | Med | needs PAGESPEED_API_KEY or GSC/CrUX |

---

## 11. Recommendations (priority · owner · expected impact)

**Immediate (this week)**
1. **Connect Google Search Console** — owner: SEO/dev · impact: unlocks all ranking + query data (turns §4 Measured). *Highest leverage.*
2. **Connect GA4** — owner: analytics · impact: unlocks traffic, conversions, content ROI (§3, §9).
3. **Add a homepage H1** — owner: web · impact: fixes a clear on-page defect on the top entry page.

**Short-term (this month)**
4. Resolve `/en/` vs `/` duplication via canonical + 301 — owner: dev · impact: consolidates ranking signals on money pages.
5. Create the **Wikidata / Knowledge-Graph entity** + `sameAs` wiring — owner: SEO/brand · impact: raises AI citation ceiling.
6. Integrate `ai.insly.com` into the main link graph — owner: web · impact: recovers orphaned equity.

**Long-term (this quarter)**
7. Set `PAGESPEED_API_KEY` (or read CrUX via GSC) to measure Core Web Vitals — owner: dev.
8. Connect a backlink tool + OpenPageRank key → run CITE authority audit — owner: SEO.
9. Stand up monthly AI-answer logging (ChatGPT/Perplexity/AIO) — owner: SEO. See `alert-config.md`.

**Next-period goals:** GSC + GA4 live; homepage H1 shipped; duplication resolved; first real traffic/ranking baseline captured.

---

## 12. Appendix — data sources & methodology

- **Measured via repo connectors:** crawl.json, sitemap.json, onpage-*.json, robots.json, schema-home.json, linkgraph.json, kg-insly.json, suggest-*.json.
- **Unavailable (marked N/A):** GA4 (traffic/conversions), GSC (rankings/impressions/CTR), backlink tool (links/authority), PageSpeed/CrUX (CWV — 429), AI-monitor (citation rate).
- **Method:** single baseline capture; no period-over-period comparison possible (no prior data). Every metric labelled Measured / N/A; no traffic, ranking, conversion, backlink, or CWV value invented.

---

## Handoff Summary

- **Objective:** Build a stakeholder SEO/GEO performance report for insly.com, populated with what is Measured today and clearly marking traffic/rankings/conversions/authority as N/A pending connectors.
- **Key findings:** Structurally healthy (AI-crawlable, deep content, flat architecture) but commercially un-measured. Real, current defects: homepage 0 H1, `/en/` vs `/` duplication, missing KG entity, orphaned `ai.insly.com`. CWV not measured (PSI 429).
- **Evidence:** sitemap (523 URLs), linkgraph (depth 1, orphans), robots (6 AI bots allowed), schema-home (Org/WebSite/Breadcrumb valid), kg-insly (no entity), onpage-home (0 H1).
- **Open loops → `memory/open-loops.md`:** Connect GSC + GA4 (top priority); fix homepage H1; resolve URL duplication; create KG entity.
- **Status:** DONE_WITH_CONCERNS (report complete; core performance metrics N/A in Tier 1).
- **Next skill:** `alert-manager` — turn these baseline insights into ongoing thresholds. See `alert-config.md`.
