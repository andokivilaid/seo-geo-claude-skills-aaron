# Content Gap Analysis — Insly (insly.com)

**Date:** 2026-06-14 · **Mode:** Tier 1 (no SEO tool connected) · **Skill:** content-gap-analysis v9.9.10
**Your domain:** insly.com · **Competitors:** Novidea, INSTANDA, Socotra, Open GI, Applied Epic / Guidewire (ceiling)

> **Labeling rule (repo contract):** Gaps are derived from **Measured** Insly coverage (sitemap.json — 523 URLs, slugs read directly) cross-referenced with **Measured** Autocomplete demand (suggest-*.json) and **Estimated** competitor coverage (no crawl of rival sites this run). Competitor "covers this" claims are **Estimated** from public positioning, not a verified crawl. Volume/traffic per gap = **N/A** (no tool). Each gap still names the competitor(s) likely to cover it and why it matters, per the skill's quality bar — with the Estimated caveat stated.

---

## [Step 1/9: Define Scope]
- **Your site:** insly.com — MGA/broker/insurer SaaS (Measured positioning).
- **Competitors compared:** Novidea, INSTANDA, Socotra (direct), Open GI / Applied Epic / Guidewire (incumbent ceiling).
- **Topic focus:** insurance-software commercial pages + MGA/delegated-authority knowledge + insurance-innovation blog.
- **Decision gate:** competitors named (brief) and Insly's own inventory is fetchable (sitemap) → no stop-and-ask.

## [Step 2/9: Audit Your Existing Content] — Measured (sitemap.json)

| Bucket | Count | Examples (Measured slugs) |
|---|---|---|
| Blog posts | **468** | how-mgas-reduce-underwriting-admin, what-is-straight-through-processing-for-mgas, embedded-insurance, ai, claims-automation |
| Glossary terms | **25** | mga-in-insurance, mga-vs-mgu, coverholder, delegated-authority, bordereaux-management, fnol, acord-form, underwriting, insurtech, no-code-in-insurance |
| Company-type money pages | ~4 | mga-insurance-software, insurance-broker-software, insurance-software (insurers), fleet-insurance-software |
| Function/solution pages | ~6 | insurance-product-builder, insurance-product-distribution, accounting-reporting-insurance-mga, claims-management-software, claims-portal |
| Conversion/assets | several | pricing, roi, quote-and-bind-efficiency-calculator, case-studies, ebooks, videos |

**Winners (Measured):** deep money pages (3,750–4,075 words) + an unusually complete 25-term MGA glossary + an active people-led blog.
**Weaknesses (Measured):** no function-level commercial pages for several high-demand terms; homepage 0 H1; duplicate `/en/` vs `/` URLs; `ai.insly.com` orphaned.

## [Step 3/9: Analyze Competitor Content] — Estimated

| Competitor | Likely content strength (Est.) | Where they likely out-cover Insly |
|---|---|---|
| INSTANDA | No-code/low-code product narrative + glossary | "no-code insurance platform", configurator content |
| Novidea | Broker/MGA data & analytics, funding PR | "insurance data platform", embedded distribution |
| Socotra | Developer docs, API-first core | "insurance API / headless PAS", integration guides |
| Open GI / Applied Epic | Broker-management depth, UK/NA market | geo broker pages, agency-management workflows |
| Guidewire/Duck Creek | Carrier-core, analyst/whitepaper library | claims/underwriting at carrier scale, customer proof |

## [Step 4/9: Identify Keyword Gaps]  ·  [Step 5: Topic Gaps]

Each gap = a query Insly users type (**Measured** autocomplete) OR a topic rivals own (**Estimated**), where Insly has **no dedicated page** (Measured from sitemap).

### High Priority (commercial demand + no Insly page)
| Gap topic | Demand evidence | Likely covered by (Est.) | Vol | Why close it |
|---|---|---|---|---|
| **Insurance policy administration / management software** | Measured: "insurance policy management software", "policyhub insurance management software" | Guidewire, Duck Creek, Socotra | N/A | Core PAS head term; Insly has it as a feature, not a page |
| **Insurance quoting software** | Measured autocomplete (Seeds A+C) | Applied, Open GI, INSTANDA | N/A | Buyer-stage commercial term, no Insly page |
| **Insurance underwriting software** | Measured: "insurance underwriting software" | Guidewire, Sapiens | N/A | Insly's AI/Copilot is a strong angle; no page |
| **Best insurance software for MGAs / brokers (comparison/listicle)** | Measured: "best insurance broker software", "top insurance broker software" | 3rd-party media, all vendors | N/A | List-intent + AI-citation magnet; Insly has 0 |

### Quick Wins (Insly already has adjacent content — extend, don't build from zero)
| Gap topic | Insly has | Action | Why |
|---|---|---|---|
| **Insurance rating engine / rating software** | Glossary `insurance-rating-engine` only | Promote to a solution page | Measured demand "insurance rating software"; convert info→commercial |
| **Cloud-based insurance software** | Glossary `cloud-based-insurance-software` | Add commercial framing + link to money pages | Glossary term + Estimated demand |
| **No-code / low-code insurance** | Glossary `no-code-in-insurance`, `low-code-in-insurance` | Build a pillar page tying to "build your own agent" | Direct competitor (INSTANDA) battleground |
| **Embedded insurance** | Blog posts only | Promote to a solution/landing page | Measured blog interest; rivals have landing pages (Est.) |

### Long-term (strategic builds)
| Gap topic | Demand evidence | Covered by (Est.) | Why |
|---|---|---|---|
| **Geo broker pages — UK / Australia / UAE / South Africa** | Measured: "insurance broker software uk/australia/uae/dubai/south africa" | Open GI/SSP (UK), local players | Strong geo intent, Insly has 0 geo pages; UK is its stated market |
| **Insurance API / headless / integration hub** | Estimated (Socotra territory) | Socotra | Developer-buyer audience Insly under-serves |
| **Carrier/insurer-scale claims & underwriting depth** | Estimated | Guidewire/Duck Creek | Up-market expansion content |

## [Step 6/9: Content Format Gaps]

| Format | Insly today (Measured) | Gap |
|---|---|---|
| Definitions/glossary | **Strong** — 25 terms | none (moat) |
| Blog/thought-leadership | **Strong** — 468 posts | none |
| **Comparison / "X vs Y" / "best of" listicles** | Glossary has "MGA vs MGU"; **no vendor comparison/listicle** | **Big gap** — highest AI-citation value |
| Case studies | Has `case-studies` hub | Thin per-page outcome numbers (Estimated) — add metrics |
| Tools/calculators | Has `quote-and-bind-efficiency-calculator`, `roi` | Good — promote more |
| Function-level landing pages | Partial | Gap: policy admin, quoting, underwriting, rating |

## [Step 7/9: GEO / AI Gaps]

robots.txt allows all AI crawlers (Measured) → content is citation-eligible, but:
- **Missing comparison/"best" content** (the format AI engines cite most for vendor-selection queries) — biggest GEO content gap.
- **Glossary lacks explicit 40–55 word answer blocks + FAQ schema** → leaving Featured-Snippet/AI-Overview wins on the table on definitional queries Insly already ranks the page type for.
- **No Wikidata entity** (Measured, kg-insly.json) → AI engines can't disambiguate the brand even when content is good. Cross-cutting blocker → `entity-optimizer`.

## [Step 8/9: Map to Audience Journey]

| Stage | Insly coverage (Measured) | Gap |
|---|---|---|
| Awareness | **Strong** — glossary + blog | — |
| Consideration | Moderate — money pages exist | Comparison/"best" + function pages missing |
| Decision | Pricing, ROI, calculator, case studies | Customer-proof depth + comparison vs named rivals |
| Retention | Light (some product blog) | Onboarding/help content (lower priority) |

**Pattern:** Insly is **awareness-heavy, consideration-light** — strong top-of-funnel content but missing the mid-funnel comparison and function pages that convert MGA/broker buyers.

## [Step 9/9: Prioritize & Action Plan]

### Executive Summary
Insly's content gap is **not volume — it's shape**. With 468 blog posts and a 25-term glossary (Measured) it over-indexes on awareness/definitional content and under-indexes on **mid-funnel commercial pages** (policy admin, quoting, underwriting, rating) and **comparison/"best-of" content** — exactly the formats that convert buyers and that AI engines cite. Closing 3–4 function pages plus one honest comparison listicle would fill the consideration stage without adding to an already-large blog.

### Prioritized Gap List
**Quick Wins (extend existing assets)**
1. Promote `insurance-rating-engine` glossary → rating-software solution page.
2. Build no-code/low-code insurance pillar from the two existing glossary terms + "build your own agent".
3. Add 40–55 word answer blocks + FAQ schema across the 25 glossary pages (GEO).

**Strategic Builds (new pages, demand-confirmed)**
4. Policy administration software landing page.
5. "Best insurance software for MGAs / brokers 2026" comparison listicle (GEO).
6. Insurance quoting software + underwriting software landing pages.

**Long-term**
7. Geo broker pages (UK first).
8. Insurance API / integration hub (vs Socotra).

### Content Calendar (dated, per Quick Win)
| Date | Asset | Bucket |
|---|---|---|
| 2026-07-07 | Rating-engine → rating-software page | Quick Win |
| 2026-07-21 | No-code/low-code insurance pillar | Quick Win |
| 2026-08-04 | Glossary FAQ-schema + answer blocks (batch 1 of 25) | Quick Win (GEO) |
| 2026-08-18 | Policy administration software page | Strategic |
| 2026-09-01 | "Best MGA software 2026" comparison | Strategic (GEO) |
| 2026-09-15 | Quoting + underwriting software pages | Strategic |

### Success Metrics
- Connect a `~~SEO tool`/GSC to measure ranking + traffic lift per new page (currently N/A).
- Track AI citations on comparison + glossary pages (GEO).
- Mid-funnel page count: from ~6 → 10+ function/comparison pages in 90 days.

---

### Handoff Summary

- **Status:** DONE_WITH_CONCERNS
- **Objective:** Map Insly's content gaps versus direct insurance-software competitors and prioritize a fill plan.
- **Key Findings / Output:** Insly's gap is shape, not volume — awareness-heavy (468 blog + 25 glossary, Measured), consideration-light. Top gaps: function-level commercial pages (policy admin, quoting, underwriting, rating) and comparison/"best-of" listicles (zero today, Measured), which are also the highest-value AI-citation formats.
- **Evidence:** sitemap.json (523 URLs, slugs read directly — Measured); suggest-*.json (policy/quoting/underwriting/geo terms typed — Measured); robots.json (AI crawlers open — Measured); kg-insly.json (no entity — Measured). Competitor coverage = **Estimated** (no rival crawl); per-gap volume/traffic = **N/A** (no tool).
- **Assumptions:** Competitor coverage inferred from public positioning, not a verified crawl; topic scope = full insurance-software + MGA-knowledge overlap.
- **Open Loops:** No Measured volume/traffic per gap; competitor coverage unverified. CWV N/A. No Wikidata entity (GEO blocker → entity-optimizer).
- **Recommended Next Skill:** seo-content-writer (start with the policy-admin page + "Best MGA software 2026" comparison).
- **Target keyword:** `insurance policy administration software` (top high-priority gap) / `mga insurance software` (anchor)
- **CORE-EEAT dimensions:** not scored in this skill.
