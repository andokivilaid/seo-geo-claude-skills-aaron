# Technical SEO Audit — insly.com

**Skill**: technical-seo-checker (v9.9.10) · **Date**: 2026-06-14 · **Mode**: Tier 1 (manual data; no GSC/CrUX/paid crawler)
**Scope**: Crawlability, indexing, robots, sitemap, canonicals, URL structure, redirects, structured data, AI-crawler handling.
**Labeling**: Measured = from `00-data/` capture files; Estimated = model inference; N/A = not measurable with current connectors.

---

## Scorecard

| Area | Score /10 | Verdict |
|------|:---------:|---------|
| Crawlability | 6 | Open robots, sitemap declared — but heavy tag-page crawl waste |
| Indexability | 4 | **Duplicate `/en/` vs non-`/en/` URLs both return 200** |
| URL structure | 4 | Two live copies of every commercial page; no enforced canonical host path |
| Sitemap | 7 | 523 valid URLs, all with lastmod — but inflated by 272 tag pages |
| Canonicals | 6 | `/en/` pages self-canonical OK; non-`/en/` duplicates' canonical not captured |
| Redirects | 8 | Clean root → `/en/` 301; no chains observed |
| Structured data | 7 | Org + WebSite + Breadcrumb present, 0 parse errors |
| AI-crawler handling | 8 | All AI bots allowed, 0 disallow — GEO-open (a deliberate-stance check) |
| Core Web Vitals | **FAIL** (Measured, 2nd pass) | CrUX field `pass:false`: TTFB 2.2s + FCP 3.7s SLOW, LCP ~4.0s. Site-wide. Detail → `06-enrichment/core-web-vitals.md` |
| **Overall (measurable areas)** | **6.0** | Healthy base, two real duplication/index risks |

---

## 1. Crawlability (6/10)

- **robots.txt**: HTTP 200, **0 disallow rules**, 1 group, sitemap declared at `https://insly.com/en/sitemap_index.xml` (Measured, `robots.json`: `rules_total: 0`). Nothing is blocked from crawling. Clean, permissive baseline.
- **Crawl waste — tag pages**: the sitemap's 468 "blog" URLs are **only 196 real posts + 272 `/blog/tag/` taxonomy pages** (Measured, `sitemap.json`). WordPress tag archives are typically thin, near-duplicate, low-value pages. Submitting 272 of them in the sitemap spends crawl budget and dilutes the index with thin pages. *Fix (P1)*: `noindex, follow` the tag archives and remove them from the sitemap (keep them crawlable for link-flow, out of the index).
- **40-page crawl**: all 40 sampled pages returned 200 at depth 1 (Measured, `crawl.json`, `linkgraph.json` `max_depth: 1`). No 4xx/5xx in the sample. Flat, fully-reachable architecture — good for crawl efficiency.

## 2. Indexability & duplication (4/10) — **top technical risk**

**Duplicate URL structure: every commercial page is live at BOTH `/en/<slug>/` and `/<slug>/`, and both return HTTP 200** (Measured, `crawl.json`). Confirmed pairs in the crawl:

| `/en/` version | Non-`/en/` duplicate | Both 200? |
|----------------|----------------------|:---------:|
| `/en/mga-insurance-software/` | `/mga-insurance-software/` | Yes |
| `/en/insurance-software/` | `/insurance-software/` | Yes |
| `/en/insurance-broker-software/` | `/insurance-broker-software/` | Yes |
| `/en/insurance-product-builder/` | `/insurance-product-builder/` | Yes |
| `/en/insurance-product-distribution/` | `/insurance-product-distribution/` | Yes |
| `/en/accounting-reporting-insurance-mga/` | `/accounting-reporting-insurance-mga/` | Yes |
| `/en/claims-management-software/` | `/claims-management-software/` | Yes |
| `/en/about-us/`, `/en/about-us/contact/`, `/en/insly-in-the-media/` | non-`/en/` equivalents | Yes |

The homepage `https://insly.com/` 301-redirects to `https://insly.com/en/` (Measured, `onpage-home.json` `redirect_chain`) — so the **root** is handled correctly. But the inner commercial pages are **not** redirected: both path variants serve a live 200 response. This creates duplicate-content pairs competing for the same keywords, splitting link equity and potentially causing Google to pick the wrong canonical.

- **Canonical evidence gap**: the `/en/` pages self-canonicalize correctly (Measured, `onpage-*.json` canonical = own `/en/` URL). The non-`/en/` duplicates' canonical tag was **not captured** (`crawl.json` does not record per-page canonical; `canonical: ""` there means "not extracted", not "absent"). **Cannot confirm** whether `/mga-insurance-software/` canonicalizes to `/en/mga-insurance-software/`. *Action*: fetch each non-`/en/` duplicate with `onpage.py` to read its canonical before deciding the fix.

**Fix (P0), two options:**
- **Preferred** — 301-redirect every non-`/en/` commercial URL to its `/en/` counterpart (consolidates equity, removes ambiguity). The root already does this; extend the same rule to inner paths.
- **If both must stay live** — ensure every non-`/en/` duplicate carries `<link rel="canonical">` pointing to the `/en/` version, and keep only the `/en/` URLs in the sitemap.

Either way, **only the canonical (`/en/`) variants belong in the sitemap** — confirm the current sitemap does not list both.

## 3. URL structure (4/10)

- Locale-prefixed `/en/` is the declared primary path (homepage canonical, sitemap host). Reasonable for a multi-locale roadmap — **but hreflang is empty** on all audited pages (Measured, `onpage-*.json` `hreflang: []`). With only `/en/` content today, that's acceptable; if other locales launch, hreflang + `x-default` become required.
- The non-`/en/` duplicates (§2) are the core URL-structure defect.
- Trailing slashes are consistent; no uppercase or parameter pollution observed in the 40-page sample.

## 4. Sitemap (7/10)

- `https://insly.com/en/sitemap_index.xml`, **523 URLs**, 4 child sitemaps, not truncated, **100% have `lastmod`** (Measured, `sitemap.json`). `lastmod` coverage is a strong freshness signal and powers the refresh plan.
- Breakdown (Measured): 196 blog posts, 272 blog tag pages, 25 glossary terms, ~30 product/company/resource pages.
- *Fix (P1)*: remove the 272 tag pages (see §1) so the sitemap declares only indexable, valuable URLs.

## 5. Redirects (8/10)

- Root `https://insly.com/` → `https://insly.com/en/`, single 301 hop, no chain (Measured, `onpage-home.json`). Clean.
- Historical context (Measured, `wayback.json` status codes across 19,785 captures): 685× 301, 77× 302, 1,729× 404 over the site's lifetime — normal for a 13-year-old WordPress site, not a current-state signal. No live redirect chains found in the 40-page crawl.

## 6. Structured data (7/10)

- Homepage JSON-LD: 5 blocks, **0 parse errors**; Organization and BreadcrumbList recognized; WebPage/ImageObject/WebSite flagged "not in linter ruleset" (generic-check only, not errors) (Measured, `schema-home.json`). RDFa also detected on page.
- Solid base. *Opportunity (P2)*: add `SoftwareApplication`/`Product` schema to the commercial pages and `FAQPage` where Q&A exists — improves rich-result and AI-answer eligibility. No `Offer`/pricing schema on the pricing page (would support price rich results). Run Google's Rich Results Test UI as the final eligibility check (no public API).

## 7. AI-crawler handling (8/10)

- **All major AI crawlers allowed** with 0 disallow rules: GPTBot, ClaudeBot, Google-Extended, CCBot, PerplexityBot, Bytespider — all `allowed: true` via the `*` group (Measured, `robots.json`). This is a **GEO-friendly, default-open** posture: Insly's content is fully available for AI retrieval and training.
- **Decision flag (not a defect)**: default-open means content is also available for model *training*, not just retrieval. If Insly wants retrieval (citations in ChatGPT/Perplexity answers) but to opt out of training, that requires a *split* stance (e.g., allow PerplexityBot/OAI-SearchBot retrieval, disallow GPTBot/CCBot/Google-Extended training). No stance was specified for this run — current posture is recorded as deliberate-open. Confirm with the owner before changing.

## 8. Orphan subdomain — ai.insly.com

- `https://ai.insly.com/` returns 200 but is **completely isolated** in the link graph: in:0, out:0, pagerank 0.0038 (lowest of all nodes), 0 links on the page itself (Measured, `linkgraph.json`, `crawl.json` `links=0`). It is on a separate subdomain, not in the main sitemap, and not internally linked. From a discovery standpoint it is invisible to the crawl path. Covered in depth in the internal-linking audit; flagged here because subdomain isolation is also a crawl/index concern. *Action*: confirm it should be indexed; if yes, link to it from the main nav/footer and add it to (or cross-reference) the sitemap; if no, `noindex` it.

## 9. Core Web Vitals — FAIL (Measured, 2nd pass with API key)

**Resolved.** PSI was re-run with a PageSpeed API key on 2026-06-14. CrUX real-user field data (origin-level, what Google ranks on): **`core_web_vitals_pass: false`**.

| Metric | Field value | Verdict |
|--------|-------------|---------|
| TTFB | ~2,243 ms | ❌ SLOW (root cause) |
| FCP | ~3,661 ms | ❌ SLOW |
| LCP | 3,967 ms | ⚠️ needs-improvement (at the 4s cliff) |
| INP | 166 ms | ✅ good |
| CLS | ~0.00 | ✅ good |

Lab perf scores (mobile): Home 53 · MGA 49 · Pricing 37. Pattern is identical across pages → **site-wide** (WordPress server response + render-blocking + oversized hero image, `og:image` 4401×1857 PNG). It is a **loading-speed** problem only — CLS/INP already pass.

**Full diagnosis + 5-step fix plan (CWV-1…5, caching/host first):** see `06-enrichment/core-web-vitals.md`. Re-measure with `psi.py … --key <KEY>`; field/CrUX lags ~28 days.

---

## Prioritized fix roadmap

| ID | Priority | Issue (Measured) | Fix | Risk if ignored |
|----|:--------:|------------------|-----|-----------------|
| TS-01 | **P0** | `/en/` and non-`/en/` commercial pages both serve 200 (duplicate URLs) | 301 non-`/en/` → `/en/` (or enforce canonical to `/en/`); keep only `/en/` in sitemap | Keyword cannibalization, split equity, wrong canonical chosen |
| TS-02 | P1 | 272 `/blog/tag/` thin pages in sitemap & index | `noindex, follow` tag archives; drop from sitemap | Crawl waste, thin-content index dilution |
| TS-03 | P1 | `ai.insly.com` orphaned (in:0/out:0), not in sitemap | Decide index intent; if yes, link from nav/footer + sitemap; if no, noindex | Subdomain invisible to crawl & users |
| TS-04 | P1 | Non-`/en/` duplicates' canonical not captured | Fetch each with `onpage.py` to confirm canonical target before TS-01 | Can't verify duplication is mitigated |
| TS-05 | **P1** | **CWV FAIL site-wide** (TTFB 2.2s, FCP 3.7s, LCP ~4.0s — Measured) | Full-page caching + faster host (TTFB<800ms); optimize/preload hero image; defer render-blocking JS/CSS | Ranking signal failing on every page |
| TS-06 | P2 | Commercial pages lack Product/SoftwareApplication/Offer schema | Add product + offer schema; FAQPage where applicable | Missed rich-result & AI-answer eligibility |
| TS-07 | P3 | hreflang empty (`hreflang: []`) | Acceptable while `/en/`-only; add hreflang+x-default when locales launch | Future-locale targeting errors |
| TS-08 | P3 | AI default-open includes training | Confirm stance; adopt split (retrieval-yes/training-opt-out) if desired | Content used for training if unintended |

---

### Handoff Summary

- **Status**: DONE_WITH_CONCERNS
- **Objective**: Technical SEO audit of insly.com — crawl, index, robots, sitemap, canonicals, redirects, structured data, AI-crawler handling.
- **Key Findings / Output**: (1) **Duplicate URL structure** — every commercial page serves 200 at both `/en/<slug>/` and `/<slug>/` (TS-01, P0). (2) Sitemap's "468 blog posts" is really **196 posts + 272 thin tag pages** that are indexed and crawl-wasteful (TS-02). (3) `ai.insly.com` is an orphaned, sitemap-absent subdomain (TS-03). Robots is fully open to all AI crawlers — GEO-friendly (intentional-open recorded). **CWV = N/A (PSI 429).**
- **Evidence**: `robots.json` (0 disallow, 6 AI bots allowed), `crawl.json` (non-`/en/` 200s), `sitemap.json` (523 URLs, 272 tag pages, 100% lastmod), `onpage-home.json` (root 301→/en/), `schema-home.json` (5 blocks 0 errors), `linkgraph.json` (ai.insly.com in:0/out:0), `psi-home.json` (429) — all **Measured**.
- **Assumptions**: Non-`/en/` duplicates' canonical tag not in capture (TS-04 needs a fetch). AI-crawler stance assumed deliberate-open (TS-08 to confirm).
- **Open Loops**: TS-01 redirect/canonical decision; TS-04 confirm duplicate canonicals; TS-05 CWV needs API key/GSC; TS-03 ai.insly.com index intent.
- **Recommended Next Skill**: internal-linking-optimizer (orphan + duplicate-URL link-graph effects), then on-page-seo-auditor for the H1 fix.
- **Priority item IDs**: TS-01 (P0), TS-02, TS-03, TS-04 (P1).
