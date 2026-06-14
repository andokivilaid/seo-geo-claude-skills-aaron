# Project Brief — Insly (insly.com)

Shared context for all SEO/GEO skill runs. Date of data capture: 2026-06-14.
All metrics below are **Measured** (pulled live via repo connectors) unless tagged otherwise.

## What Insly is
- **Insly** = B2B SaaS, "low-risk insurance software" platform for **MGAs (Managing General Agents), insurance brokers, and insurers**.
- Positioning: fast setup, modular, AI-powered ("Insurance Copilot", build-your-own-agent), fast ROI.
- WordPress site. Primary locale path `/en/`. Twitter `@insly_com`. Org + WebSite + BreadcrumbList schema present.
- Sub-brands/products seen: Socrates Systems, NORA, FormFlow, Insurance Copilot, AI agent builder (ai.insly.com).

## Site shape (Measured)
- Sitemap: **523 URLs** at `/en/sitemap_index.xml`. Breakdown: **468 blog posts**, **25 glossary terms**, ~20 product/solution/company pages, case studies, ebooks, videos.
- 40-page crawl: all reachable at depth 1 (flat architecture, strong header/footer linking — every main page ~38 internal in-links).

## Key MEASURED findings (evidence for skills)
1. **Homepage has 0 H1 tags** (`onpage-home.json`). Product pages (mga, insurance-software, pricing) each have exactly 1 H1 — only the homepage is missing one.
2. **Duplicate URL structure**: same pages exist at `/en/<slug>/` AND `/<slug>/` (e.g. `/en/mga-insurance-software/` and `/mga-insurance-software/`). Canonical/duplication risk. Homepage canonical = `https://insly.com/en/`.
3. **`ai.insly.com` is orphaned** in the link graph (in:0, out:0) — separate subdomain not integrated into main internal linking.
4. **4 orphan URLs** flagged by linkgraph; max crawl depth = 1 (good).
5. **robots.txt allows ALL AI crawlers** (GPTBot, ClaudeBot, Google-Extended, CCBot, PerplexityBot, Bytespider). 0 disallow rules. Sitemap declared. → GEO-friendly baseline.
6. **No Wikidata entity** — `kg.py reconcile "Insly"` returns recognized:false, 0 matches. No Knowledge Graph entity = entity/GEO gap.
7. Content depth is high: homepage 4004 words, product pages ~3700–4075 words.
8. Titles: Home "Insly - Low-Risk Insurance Software" (35 chars). Meta desc 107–137 chars (in range).
9. **PageSpeed = N/A** — PSI returned HTTP 429 (keyless shared-IP quota). Mark Core Web Vitals as "not measured; needs PAGESPEED_API_KEY or GSC/CrUX". Do NOT invent CWV numbers.

## Keyword demand (Measured — Google Autocomplete via suggest.py; volume/difficulty NOT available, no SEO tool connected)
- `suggest-insurance-software.json`: 219 expanded suggestions (e.g. insurance software companies, for agents, systems, tools, development, for brokers).
- `suggest-mga.json`, `suggest-broker.json`: MGA and broker software variants.
- These are **demand signals / ideas only** — search volume & difficulty are UNAVAILABLE (no Ahrefs/Semrush/GSC). Label any volume/difficulty as Estimated or N/A; never present as Measured.

## Data files in this folder
- `onpage-home.json`, `onpage-en-mga-insurance-software.json`, `onpage-en-pricing.json`, `onpage-en-insurance-software.json`
- `robots.json`, `sitemap.json`, `schema-home.json`, `kg-insly.json`
- `crawl.json` (40 pages), `linkgraph.json` (orphans/depth/pagerank), `wayback.json` (capture history)
- `suggest-*.json` (keyword ideas), `psi-home.json` (429 error — no CWV data)

## Tier / labeling rules (from repo contract)
- Tier 1 manual-data mode (no MCP SEO tool connected). Label every metric **Measured / User-provided / Estimated**; mark unavailable metrics **N/A**; never fabricate volume, difficulty, traffic, rankings, or CWV.
