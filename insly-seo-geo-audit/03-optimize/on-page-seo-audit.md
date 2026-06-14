# On-Page SEO Audit — insly.com

**Skill**: on-page-seo-auditor (v9.9.10) · **Date**: 2026-06-14 · **Mode**: Tier 1 (manual data, no SEO tool connected)
**Scope**: Homepage + 3 product/commercial pages, audited from real `onpage-*.json` captures in `00-data/`.
**Labeling**: every metric is tagged Measured / Estimated / N/A. Search volume, difficulty, rankings, and CTR are N/A (no Ahrefs/Semrush/GSC connected).

---

## Pages audited

| # | Page | URL | Title | Words | H1 count |
|---|------|-----|-------|------:|:--------:|
| P1 | Homepage | `https://insly.com/en/` | Insly - Low-Risk Insurance Software | 4004 | **0** |
| P2 | MGA software | `https://insly.com/en/mga-insurance-software/` | MGA Software \| Low-Risk Insurance Software – Insly | 3973 | 1 |
| P3 | Insurance software | `https://insly.com/en/insurance-software/` | Insurance Software for Insurers \| Launch Faster with Insly | 4075 | 1 |
| P4 | Pricing | `https://insly.com/en/pricing/` | Insly Pricing | 3750 | 1 |

All four return HTTP 200; all self-canonicalize to their `/en/` URL (Measured, `onpage-*.json`). Inferred target keywords (no keyword tool connected, labeled Estimated): P1 "insurance software", P2 "MGA insurance software", P3 "insurance software for insurers", P4 "insurance software pricing".

---

## Scorecard (/10 per element, evidence-based)

| Element | P1 Home | P2 MGA | P3 Insurers | P4 Pricing |
|---------|:------:|:-----:|:----------:|:---------:|
| Title tag | 7 | 9 | 9 | 4 |
| Meta description | 8 | 9 | 9 | 7 |
| Header structure | **2** | 7 | 7 | 5 |
| Content structure | 8 | 8 | 8 | 7 |
| Keyword placement | 5 | 8 | 8 | 4 |
| Internal links | 9 | 8 | 8 | 8 |
| Images | N/A* | N/A* | N/A* | N/A* |
| Page-level tags (canonical/schema/slug) | 6 | 7 | 7 | 7 |
| **Overall** | **5.6 (D+)** | **8.0 (B)** | **8.0 (B)** | **5.7 (D+)** |

\* Image alt-text/filenames/lazy-load are N/A: the `onpage-*.json` captures only expose OG/Twitter images, not in-body `<img>` alt attributes. Needs a rendered crawl (Screaming Frog, or `crawl.py` extended to capture `<img>`) to score. Do not assume images are unoptimized — mark N/A and re-run.

---

## P1 — Homepage (Overall 5.6, D+)

**Title** (7/10) — "Insly - Low-Risk Insurance Software", 35 chars (Measured). Brand-led, clear, but short — 35 of the available ~60 chars used. Leaves ~25 chars of SERP real estate unused and omits the high-intent head term "insurance software for MGAs / insurers". *Fix*: `Insurance Software for MGAs & Insurers | Insly` (~46 chars) — leads with the category keyword, keeps brand.

**Meta description** (8/10) — 125 chars (Measured), in the 150-160 sweet spot's lower band, includes "insurance software", "MGAs", "insurers", "AI-powered". Slight keyword repetition ("for MGAs and insurers" appears twice). No explicit CTA. *Fix*: trim the repeat, add a soft CTA ("See how it works"); push toward 150 chars.

**Header structure** (2/10) — **CRITICAL: 0 H1 tags** (Measured, `onpage-home.json` `headings.h1_count: 0`, `h1: []`). This is the single most important on-page defect on the site. The homepage — the highest-authority, most-linked URL — has no H1, so neither search engines nor AI extractors get a primary topical signal from the strongest heading slot. Compounding it: the five H2s are navigation labels ("By company type", "By Solution") that repeat (3× "By company type", 2× "By Solution") and carry zero topical meaning. The five H3s are descriptive and good ("Low-risk system that can be implemented in a matter of weeks", etc.). *Fix (P0)*: add exactly one H1, e.g. `Low-Risk Insurance Software for MGAs and Insurers`. *Fix (P1)*: convert the repeated nav-label H2s to real section headings or demote them out of the heading hierarchy (`<div>`/`<span>` styled, or `aria-label`ed nav), so the H2 layer carries topic structure.

**Keyword placement** (5/10) — primary term "insurance software" is in title, meta, and (per word count) body, but absent from the H1 (because there is no H1) and buried under meaningless nav-label H2s. Fixing the H1/H2 issue directly lifts this score.

**Internal links** (9/10) — out-degree 36 (Measured, `linkgraph.json`); strong hub. (Note the in-degree=0 anomaly is a graph artifact covered in the internal-linking audit, not an on-page authoring defect.)

**Page-level tags** (6/10) — canonical `https://insly.com/en/` (self, correct). JSON-LD present: WebPage, BreadcrumbList, WebSite, Organization (Measured, `schema-home.json`: 5 blocks, 0 parse errors, 2 recognized). No `noindex`. The duplicate non-`/en/` URL serving 200 is a technical-layer issue (see technical audit), not authored here.

---

## P2 — MGA Software (Overall 8.0, B)

**Title** (9/10) — 50 chars (Measured), keyword-front-loaded ("MGA Software"), pipe-separated, brand at end. Good.
**Meta** (9/10) — 137 chars (Measured), specific and benefit-led with real numbers ("Go live in 7–14 days from €5,000/month"). Strong, quotable, GEO-friendly. Slightly under 150 — room to extend.
**Headers** (7/10) — 1 H1 "Low-risk MGA Insurance Software" (Measured) — keyword-rich, correct. But the same repeated nav-label H2 pattern ("By company type" ×3, "By Solution" ×2) appears here too — a **site-template defect** that suppresses the H2 topical layer on every page. H3s are strong feature headings. *Fix*: same H2 template fix as P1.
**Keyword placement** (8/10) — "MGA insurance software" in title, H1, meta, body. Good.
**Page-level tags** (7/10) — canonical self-referential and correct; `og:type: article` (Measured) is slightly off for a product/landing page (`website` or `product` fits better) but low-impact.

---

## P3 — Insurance Software for Insurers (Overall 8.0, B)

**Title** (9/10) — 58 chars (Measured), keyword + value prop + brand. Strong, near the 60-char ceiling without truncation risk.
**Meta** (9/10) — 135 chars (Measured), benefit-dense ("100% accounting accuracy", "simplify underwriting"). Good; room to 150.
**Headers** (7/10) — 1 H1 "Low-risk Insurance Software" (Measured). Same repeated nav-label H2 template defect; good H3s.
**Keyword placement** (8/10) — consistent across title/H1/meta/body.
**Page-level tags** (7/10) — canonical correct; same `og:type: article` minor mismatch.

---

## P4 — Pricing (Overall 5.7, D+)

**Title** (4/10) — "Insly Pricing", **13 chars** (Measured). Far too short — uses 13 of ~60 chars, no qualifying keyword, no differentiation. *Fix (P1)*: `Insly Pricing: Insurance Software Plans from €5,000/mo` (~52 chars) — adds the category term and a real anchor number that sets expectations and improves CTR.
**Meta** (7/10) — 107 chars (Measured), accurate and specific ("based on system scope, implementation and GWP transacted"). Short; could extend toward 150 and add a CTA.
**Headers** (5/10) — 1 H1 "Insly Pricing" (Measured) — present and correct but generic; **0 H3s** (Measured) and the same repeated nav-label H2s, so the page has almost no meaningful internal heading structure for a 3,750-word page. *Fix*: add descriptive H2/H3s for pricing components (system scope, implementation, GWP-based fees) — both for SEO structure and for AI answer-extraction.
**Keyword placement** (4/10) — "insurance software pricing" / "insurance software cost" appears weakly; title and H1 are brand-only. Lifts directly once the title/H1 are made descriptive.
**Page-level tags** (7/10) — canonical correct; reading time "2 minutes" (Measured, Twitter card) vs 3,750 words is inconsistent and suggests most of that word count is shared template/footer chrome rather than unique pricing copy — worth a manual content check.

---

## Cross-page pattern findings (template-level)

1. **Repeated nav-label H2s on every page** (Measured, all 4 JSONs): "By company type" and "By Solution" occupy the H2 layer sitewide. These are navigation widgets, not section headings. They waste the most valuable mid-level heading signal on every page. **Single template fix → sitewide lift.**
2. **High word counts (3,750–4,075) with thin unique heading structure** — the gap between word count and meaningful headings suggests heavy shared template/footer content inflating counts. Validate unique-vs-boilerplate ratio with a rendered crawl.
3. **Meta descriptions consistently 107–137 chars** — all under the 150-char target; a 10-20 char extension per page is free CTR/keyword surface.

---

## Prioritized fix table

| ID | Priority | Page | Issue (Measured) | Fix | Effort | Impact |
|----|:--------:|------|------------------|-----|:------:|:------:|
| OP-01 | **P0** | Home | 0 H1 tags (`h1_count: 0`) | Add one H1: "Low-Risk Insurance Software for MGAs and Insurers" | XS | High |
| OP-02 | P1 | All 4 (template) | H2 layer = repeated nav labels ("By company type"/"By Solution") | Convert nav labels out of `<h2>`; use H2 for real section topics | M | High |
| OP-03 | P1 | Pricing | Title only 13 chars, no keyword | Rewrite: "Insly Pricing: Insurance Software Plans from €5,000/mo" | XS | Med |
| OP-04 | P1 | Pricing | 0 H3s, no descriptive structure on 3.75k-word page | Add H2/H3s for scope, implementation, GWP-based pricing | S | Med |
| OP-05 | P2 | Home | Title 35 chars, brand-led, omits head keyword | Rewrite: "Insurance Software for MGAs & Insurers \| Insly" | XS | Med |
| OP-06 | P2 | All 4 | Meta descriptions 107–137 chars (under 150) | Extend to ~150 chars, add soft CTA, remove repeats | S | Low-Med |
| OP-07 | P3 | P2/P3 | `og:type: article` on product/landing pages | Set `og:type` to `website`/`product` | XS | Low |
| OP-08 | P3 | All | In-body `<img>` alt/filenames not captured | Run rendered crawl to score images (currently N/A) | S | TBD |

P0 = ship today; P1 = this sprint; P2/P3 = backlog.

---

## What is N/A and why

- **Image optimization** — `onpage-*.json` does not expose in-body `<img>` alt text/filenames. Re-run with a rendered crawler to score OP-08.
- **Search volume / keyword difficulty / current rankings / CTR** — no Ahrefs/Semrush/GSC connected. Target keywords above are **Estimated** (inferred from title/H1/meta), not validated demand. Validate before acting on keyword-priority claims.
- **Content quality / E-E-A-T verdict** — out of scope here (structural pass only). Route to content-quality-auditor for CORE-EEAT scoring of the 4,000-word bodies.

---

### Handoff Summary

- **Status**: DONE_WITH_CONCERNS
- **Objective**: On-page structural SEO audit of insly.com homepage + 3 commercial pages from measured `onpage-*.json` captures.
- **Key Findings / Output**: Homepage has **0 H1 tags** (P0, OP-01) — confirmed real. A sitewide template defect puts repeated nav labels ("By company type"/"By Solution") in the H2 layer on every page (OP-02). Pricing title is 13 chars with no keyword (OP-03). MGA and Insurers pages are solid (8.0/B); Home and Pricing are weak (5.6/5.7, D+).
- **Evidence**: `onpage-home.json` (`h1_count: 0`), `onpage-en-mga-insurance-software.json`, `onpage-en-insurance-software.json`, `onpage-en-pricing.json` (`title_length: 13`), `schema-home.json` — all **Measured**. Target keywords **Estimated**. Volume/rankings/images **N/A**.
- **Assumptions**: Target keywords inferred from on-page signals (no keyword tool). Word-count vs heading gap suggests template boilerplate inflation — flagged for manual check.
- **Open Loops**: OP-01 (H1) is the priority item; OP-02 template H2 fix; OP-08 image audit needs a rendered crawl; keyword targets need demand validation.
- **Recommended Next Skill**: technical-seo-checker (the duplicate `/en/` URL and canonical behavior that surround these pages); then internal-linking-optimizer.
- **Priority item IDs**: OP-01 (P0), OP-02, OP-03 (P1).
