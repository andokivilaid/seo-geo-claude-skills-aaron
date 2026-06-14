# Internal Linking Audit — insly.com

**Skill**: internal-linking-optimizer (v9.9.10) · **Date**: 2026-06-14 · **Mode**: Tier 1 (link graph from local crawl; no analytics)
**Scope**: 40-page crawl link graph (`linkgraph.json`, `crawl.json`). Architecture, authority flow, orphans, anchor strategy.
**Labeling**: degrees/pagerank/orphans are Measured; traffic-weighted priorities are N/A (no analytics) and labeled Estimated where inferred.

---

## Step 1 — Current structure

| Metric | Value | Source |
|--------|-------|--------|
| Pages crawled | 40 | Measured, `linkgraph.json` |
| Total internal links | 1,177 | Measured |
| Avg links/page | ~29 | Measured (1177/40) |
| Max click depth | 1 | Measured (`depth_histogram: {"1": 40}`) |
| Deep pages (>3 clicks) | 0 | Measured |
| Orphans flagged | 4 | Measured |
| In-degree on most pages | 38 | Measured (header/footer template) |

**Architecture model**: flat hub-and-spoke. Every main page is linked from a shared header/footer, giving ~38 inbound internal links and depth-1 reachability. For a ~550-URL site this is excellent for crawl efficiency and link-equity distribution — there is no deep-burial problem.

**Structure score: 70/100** (start 100; −10 per orphan ×3 effective = −30; the 4th "orphan" is a self-reference artifact). The score is held down almost entirely by orphans and the isolated subdomain, **not** by depth or distribution, which are healthy.

**The flip side of flat-and-even**: PageRank is almost perfectly uniform — nearly every page sits at **~0.0337** (Measured, `pagerank`). The header/footer links every page to every page, so there is **no contextual authority sculpting**: the site cannot signal which pages are most important because they all receive identical link equity. Money pages (MGA, Insurers, Pricing) get no more internal authority than utility pages (history, careers, media). This is the second-order issue to fix after orphans.

---

## Step 2 — Orphan pages & isolated nodes

`linkgraph.json` flags 4 orphans:

```
https://ai.insly.com/   ← genuine orphan (separate subdomain, in:0 out:0)
https://insly.com/en/   ← appears 3× (homepage self-reference / crawl-seed artifact)
```

**Disposition:**

1. **`ai.insly.com/` — genuine orphan, highest-priority.** in:0, out:0, pagerank 0.0038 (lowest node, ~9× below the ~0.0337 site norm), 0 on-page links (Measured, `linkgraph.json` + `crawl.json` `links=0`). This is the AI agent-builder product (per project brief) living on a separate subdomain with zero internal links in or out. It is invisible to anyone navigating from insly.com and starved of authority. **This is the single most valuable linking fix.** *Disposition: keep + integrate* (assuming it should be public — confirm). Add it to the main nav/footer and link from the AI-relevant commercial pages.

2. **`https://insly.com/en/` (homepage) listed as orphan ×3 — artifact, not a real orphan.** The homepage shows in:0 out:36 in the degree table, but that in:0 is because it is the crawl seed (no crawled page "links to" the seed in the recorded direction) — the header/footer demonstrably links every page back to the homepage in practice. Real-world inbound is high. **No action**; this is a measurement artifact of seed-based crawling, not a defect. (The on-page audit's homepage internal-link score of 9/10 reflects the true state.)

**Low-PageRank real pages worth noting** (Measured, not orphans but under-linked relative to the ~0.0337 norm — these are non-`/en/` duplicate or blog URLs):
- `/claims-management-software/` (non-`/en/`): in:7, pagerank 0.0081
- 3 customer-story blog posts: in:4–12, pagerank 0.0055–0.0119

These low scores are mostly a **symptom of the duplicate-URL problem** (technical audit TS-01): equity is split between `/en/` and non-`/en/` copies. Fixing the duplicates (301/canonical) will consolidate this automatically — do TS-01 first, then re-measure before adding manual links to these.

---

## Step 3 — Anchor text distribution

**N/A (not captured).** The crawl recorded link *counts* and the link *graph*, but not anchor text strings. Anchor distribution, over-optimization, and generic-anchor ratio cannot be scored from `linkgraph.json`. *To score*: re-crawl capturing `<a>` anchor text. Anchor recommendations below are therefore prescriptive (what anchors to use), not a measured audit of current anchors.

---

## Step 4 — Topic cluster strategy

Insly's commercial pages form clear clusters that the flat template does not currently express through *contextual* (in-body) links — only through global nav. Recommended pillar → cluster contextual linking:

- **Pillar: `/en/insurance-software/`** (insurers) → clusters: product-builder, product-distribution, accounting-reporting, claims-management.
- **Pillar: `/en/mga-insurance-software/`** (MGAs) → clusters: same four solution pages + pricing + a relevant customer story.
- **Pillar: `/en/insurance-broker-software/`** (brokers) → clusters: same solution pages.
- **AI cluster** (new): `ai.insly.com` ← linked from insurance-software, mga, and any "Insurance Copilot / AI agent" content.

The goal is to add *in-body contextual* links (not just header/footer) so authority flows along topical lines and breaks the uniform-PageRank flatness.

---

## Step 5 — Contextual link recommendations (source → target → anchor)

Priorities are by structural impact (Measured graph position); traffic weighting is N/A (Estimated where noted).

| # | Priority | Source page | Target page | Recommended anchor | Rationale |
|---|:--------:|-------------|-------------|--------------------|-----------|
| IL-01 | **P0** | Main nav + footer (template) | `ai.insly.com/` | "AI Agent Builder" / "Insurance Copilot" | Resolve the genuine orphan; give the subdomain its first inbound links |
| IL-02 | **P0** | `/en/insurance-software/` body | `ai.insly.com/` | "build your own AI agent" | Topical bridge from money page to AI product |
| IL-03 | P1 | `/en/mga-insurance-software/` body | `ai.insly.com/` | "AI-powered automation for MGAs" | Same bridge for the MGA audience |
| IL-04 | P1 | `/en/insurance-software/` body | `/en/insurance-product-builder/` | "insurance product builder" | Pillar → cluster contextual link (currently nav-only) |
| IL-05 | P1 | `/en/insurance-software/` body | `/en/claims-management-software/` | "claims management software" | Pillar → cluster |
| IL-06 | P1 | `/en/mga-insurance-software/` body | `/en/pricing/` | "MGA pricing from €5,000/month" | Push a high-intent commercial page from its strongest referrer |
| IL-07 | P2 | Top customer-story posts | `/en/mga-insurance-software/` | "MGA insurance software" | Lift under-linked stories (in:4–12) and reinforce money page |
| IL-08 | P2 | `/en/blog-posts/` hub | 3 newest customer stories | descriptive titles | Distribute equity to low-in-degree stories |
| IL-09 | P2 | Glossary terms (25) | relevant commercial pages | exact-term anchors | Convert glossary into a topical link layer into money pages |

**Do IL-01/IL-02 first** — they fix the only genuine orphan and cost minutes (a nav/footer entry + one in-body link).

---

## Step 6 — Navigation & footer

- The shared header/footer is doing heavy lifting (~38 inbound links/page) — strength, not a problem. **Do not** strip it.
- **Add `ai.insly.com` to the footer** (and ideally a "Products → AI" nav item) — currently absent (Measured: in:0).
- **Gap**: contextual (in-body) links are under-used relative to template links, which is *why* PageRank is uniform. The fix is additive in-body links (Step 5), not nav changes.
- **Tag-page interaction**: the 272 `/blog/tag/` pages (technical audit TS-02) also leak link equity into thin pages. `noindex, follow` keeps their link-flow while removing them from the index — coordinate this fix with TS-02.

---

## Step 7 — Implementation plan

**Phase 1 (P0, this week)** — IL-01, IL-02: link `ai.insly.com` from footer/nav + one money page. Resolves the genuine orphan.
**Phase 2 (P1, this sprint)** — depends on technical TS-01 (de-duplicate URLs) landing first, then IL-03 to IL-06: add pillar→cluster and →pricing/AI contextual links to break uniform PageRank.
**Phase 3 (P2, backlog)** — IL-07 to IL-09: lift customer stories and wire the glossary into commercial pages.
**Tracking**: re-run `crawl.py | linkgraph.py` after each phase; success = ai.insly.com in-degree > 0 and pagerank variance increases (money pages pull ahead of utility pages).

**Sequencing note**: TS-01 (duplicate-URL consolidation) should precede Phase 2 — adding links before de-duplication just splits the new equity across both URL copies again.

---

### Handoff Summary

- **Status**: DONE_WITH_CONCERNS
- **Objective**: Internal link architecture audit of insly.com from the measured 40-page link graph.
- **Key Findings / Output**: Architecture is healthy (depth-1, ~38 inbound/page, 0 deep pages) but has **one genuine orphan: `ai.insly.com` (in:0/out:0, pagerank 0.0038)** — top fix (IL-01/IL-02). The 3 "homepage orphan" flags are a crawl-seed artifact, not real. Second-order issue: **uniform PageRank (~0.0337 everywhere)** from template-only linking means no money-page authority sculpting — fix with in-body pillar→cluster links (IL-04 to IL-06).
- **Evidence**: `linkgraph.json` (4 orphans, max_depth 1, 1177 links, pagerank table), `crawl.json` (ai.insly.com links=0) — all **Measured**. Anchor text **N/A** (not captured). Traffic weighting **N/A** (no analytics).
- **Assumptions**: `ai.insly.com` assumed should-be-public (confirm). Homepage in:0 treated as seed artifact based on observed header/footer linking. Low-in-degree non-`/en/` pages attributed to the duplicate-URL split (technical TS-01).
- **Open Loops**: IL-01/IL-02 (orphan fix); anchor-text re-crawl needed; Phase 2 depends on TS-01 landing first; confirm ai.insly.com index intent.
- **Recommended Next Skill**: technical-seo-checker (TS-01 duplicate URLs must land before Phase 2) — then re-run this audit.
- **Priority item IDs**: IL-01, IL-02 (P0); IL-04, IL-05, IL-06 (P1).
