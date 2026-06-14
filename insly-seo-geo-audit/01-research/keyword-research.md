# Keyword Research — Insly (insly.com)

**Date:** 2026-06-14 · **Mode:** Tier 1 (no SEO tool connected) · **Skill:** keyword-research v9.9.10
**Locale focus:** English `/en/`, primary markets UK + EU + ANZ (per blog signals)

> **Labeling rule (repo contract):** Search **volume** and **keyword difficulty** are **N/A** in this run — no Ahrefs/Semrush/GSC connected. Every keyword idea below is a **Measured demand signal** harvested from Google Autocomplete (`suggest-*.json`, status 200, 258 total suggestions across 3 seeds). Autocomplete proves the query is typed often enough for Google to surface it; it does **not** give a number. Difficulty, volume, and Opportunity score are therefore **N/A — needs ~~SEO tool**. Intent and GEO flags are **Estimated** (model inference). Nothing here is presented as a measured volume.

---

## [Phase 1/8: Scope]

| Field | Value | Source |
|---|---|---|
| Product | B2B SaaS — "low-risk insurance software" / policy admin platform | Measured (homepage title + meta) |
| Audience | MGAs, insurance brokers, insurers/carriers | Measured (homepage meta: "for MGAs and insurers") |
| Differentiators | Go live 7–14 days, from €5,000/mo, modular, AI ("Insurance Copilot", build-your-own-agent), fast ROI | Measured (mga-insurance-software meta + homepage H3s) |
| Site DR | **N/A** — no backlink tool connected | N/A |
| Existing money pages | `/en/insurance-software/`, `/en/mga-insurance-software/`, `/en/insurance-broker-software/`, `/en/fleet-insurance-software/`, `/en/pricing/` | Measured (sitemap.json) |
| Content footprint | 468 blog posts + 25 glossary terms + ~20 product/company pages = 523 URLs | Measured (sitemap.json) |
| Business goal (assumed) | Demo bookings from MGAs/brokers/insurers evaluating policy-admin / MGA platforms | Estimated (no user-stated goal) |

---

## [Phase 2/8: Discover] — Seed harvest (Measured demand signals)

Three Autocomplete pulls. Insly-relevant subset extracted; consumer/jobs/geo-noise removed.

**Seed A — "insurance software"** (219 suggestions). Relevant B2B-vendor subset:
- insurance software for agents / for brokers / **for carriers and mgas**
- insurance software solutions / systems / tools / platforms / providers / vendors
- insurance software **uk** / usa / australia / canada / south africa
- insurance **broker** software / **agency** software / **mga** software
- insurance **underwriting** software / **claims management** software / **quoting** software / **rating** software / **policy** (management) software
- insurance software **ai** / automation software / workflow software / distribution software
- named competitors users type: duck creek, guidewire, epic, sapiens, novidea, origami, zywave, hawksoft, applied, keylane

**Seed B — "MGA software"** (14 suggestions, mostly Tagalog noise). Relevant: `mga software insurance`, `mga software solutions`. → Thin English MGA-software autocomplete; demand for "MGA" is expressed inside the broader "insurance software for carriers and mgas" string, not as a standalone head term.

**Seed C — "insurance broker software"** (25 suggestions). Relevant subset:
- insurance broker software **uk** / india / australia / south africa / **uae** / **dubai**
- insurance broker **crm** software / **accounting** software / **erp** software / **portal** software / **quoting** software
- **best** insurance broker software / **best insurance broker software uk** / **top** insurance broker software
- car insurance broker software / commercial insurance broker software / health / life insurance broker software

---

## [Phase 3/8: Variations & long-tail]

Patterns observed in the Measured data, expanded into Insly's ICP:
- **Modifier: market** — `<term> uk | usa | australia | south africa | uae` (broker autocomplete is heavily geo-modified → buyers search by region).
- **Modifier: role** — `for brokers | for agents | for carriers and mgas | for insurers`.
- **Modifier: function** — `underwriting | claims | quoting | rating | bordereaux | accounting | policy admin | distribution`.
- **Modifier: commercial intent** — `best | top | solutions | providers | vendors | platforms`.
- **Glossary/definitional long-tail** — `what is an MGA | MGA vs MGU | coverholder | delegated authority | bordereau | FNOL | ACORD form` (Insly already publishes 25 of these — see Phase 7).

---

## [Phase 4/8: Classify by intent]  ·  [Phase 5/8: Score]

Intent = **Estimated**. Volume/Difficulty/Opportunity = **N/A** (no tool). Autocomplete presence = **Measured (Yes)**.

| # | Keyword | Intent (Est.) | Autocomplete (Measured) | Vol | KD | Opp | Insly page status |
|---|---|---|---|---|---|---|---|
| 1 | insurance software for carriers and mgas | Commercial | Yes (Seed A) | N/A | N/A | N/A | Partial — split across 2 pages |
| 2 | mga insurance software / mga software | Commercial | Yes (A,B) | N/A | N/A | N/A | **Has page** `/en/mga-insurance-software/` |
| 3 | insurance broker software | Commercial | Yes (A,C) | N/A | N/A | N/A | **Has page** `/en/insurance-broker-software/` |
| 4 | insurance broker software uk | Commercial | Yes (C) | N/A | N/A | N/A | **Missing** (geo page) |
| 5 | best insurance broker software (uk) | Transactional | Yes (C) | N/A | N/A | N/A | **Missing** (comparison) |
| 6 | insurance underwriting software | Commercial | Yes (A) | N/A | N/A | N/A | Weak — sub-feature only |
| 7 | insurance claims management software | Commercial | Yes (A) | N/A | N/A | N/A | **Has page** `/en/claims-management-software/` |
| 8 | insurance quoting software | Commercial | Yes (A) | N/A | N/A | N/A | Weak — no dedicated page |
| 9 | insurance rating engine / rating software | Commercial | Yes (A) + glossary | N/A | N/A | N/A | Glossary only |
| 10 | insurance policy management / admin software | Commercial | Yes (A: "policyhub… management software") | N/A | N/A | N/A | **Missing** as head landing page |
| 11 | insurance automation software | Commercial | Yes (A) + glossary | N/A | N/A | N/A | Glossary + blog |
| 12 | insurance software solutions / providers / vendors | Commercial | Yes (A) | N/A | N/A | N/A | Implicit |
| 13 | cloud based insurance software | Commercial | Yes (glossary term exists) | N/A | N/A | N/A | Glossary only |
| 14 | what is an MGA / coverholder / delegated authority | Informational | Yes (glossary) | N/A | N/A | N/A | **Has glossary pages** |
| 15 | mga vs mgu / managing general agents vs brokers | Informational | Yes (glossary) | N/A | N/A | N/A | **Has glossary pages** |
| 16 | bordereaux management / bordereau | Informational | Yes (glossary) | N/A | N/A | N/A | **Has glossary pages** |
| 17 | embedded insurance software | Commercial/Info | Inferred (blog covers it) | N/A | N/A | N/A | Blog only — no landing page |
| 18 | usage-based / fleet insurance software | Commercial | Yes (A) + has page | N/A | N/A | N/A | **Has page** `/en/fleet-insurance-software/` |

> Opportunity score `(Volume × IntentValue) / Difficulty` **cannot be computed** in Tier 1 — both Volume and Difficulty are N/A. Priority below is ranked by **business-fit + ICP-match + existing-coverage gap** (Estimated), not by an Opportunity number. This is a known limitation; connect a `~~SEO tool` to convert these into scored opportunities.

---

## [Phase 6/8: GEO-Check] — AI-answer-friendly queries (Estimated)

robots.txt allows **all** AI crawlers (GPTBot, ClaudeBot, Google-Extended, CCBot, PerplexityBot, Bytespider) with **0 disallow rules** (Measured, robots.json) → Insly content is eligible for AI answers. These query shapes get cited in ChatGPT/Perplexity/AI Overviews:

| GEO query pattern | Insly asset today | GEO action |
|---|---|---|
| "what is an MGA / MGU / coverholder" (definition) | Glossary pages exist | Add concise 40–55 word definition block + FAQ schema |
| "MGA vs MGU" / "managing general agents vs brokers" (comparison) | Glossary pages exist | Strong GEO candidate — keep tables, add sources |
| "best insurance software for MGAs / brokers" (list) | **No listicle** | Build an honest comparison/listicle — high AI-citation value |
| "how do MGAs reduce underwriting admin" (how-to) | Blog post exists (2026-06-02) | Strong — add Q&A schema |
| "what is straight-through processing for MGAs" (definition) | Blog post exists (2026-05-19) | Strong GEO candidate |
| "insurance software pricing / cost" | Pricing page (from €5,000/mo, 7–14 days) | Surface the number in a quotable sentence for AI |

**GEO gap:** Insly has **no Wikidata / Knowledge Graph entity** (`kg-insly.json` → recognized:false, 0 matches, Measured). Definition/comparison content can rank, but the brand itself is not yet a recognized entity AI engines disambiguate — flag to `entity-optimizer`.

---

## [Phase 7/8: Cluster] — Pillar + cluster hubs

**Pillar 1 — Insurance software by company type** (commercial money pages)
- Clusters: MGA insurance software ✅ · insurance broker software ✅ · insurance software for insurers ✅ · *coverholder software* (missing) · *carrier/insurer platform* (thin)

**Pillar 2 — Insurance software by function** (commercial, mostly thin/missing)
- Clusters: underwriting software (thin) · claims management software ✅ · quoting software (missing) · rating engine (glossary only) · **policy admin software** (missing head page) · accounting & reporting ✅ · distribution/embedded (blog only)

**Pillar 3 — MGA / delegated-authority knowledge hub** (informational + GEO — Insly's strongest existing cluster)
- Clusters: what is an MGA ✅ · MGA vs MGU ✅ · coverholder ✅ · delegated authority ✅ · bordereaux ✅ · FNOL ✅ · ACORD ✅ — **25 glossary terms already live.** This is a defensible GEO moat; interlink it to Pillar-1 money pages.

**Pillar 4 — Insurance innovation / AI** (informational, brand + GEO)
- Clusters: AI in insurance · straight-through processing · embedded insurance · Amazon effect on claims · future of insurance — 468 blog posts, actively published (latest 2026-06-11).

**Geo-modified cluster (untapped):** UK / Australia / UAE / South Africa broker-software pages — Autocomplete shows strong geo intent, Insly has **0** geo landing pages.

---

## [Phase 8/8: Deliver]

### Executive Summary
Insly's keyword footprint is **strong on definitional/MGA-knowledge terms** (25 glossary pages map almost 1:1 to "what is…" autocomplete queries) and **adequate on company-type money pages** (MGA, broker, insurer pages exist with 3,700–4,075 words each). The biggest opportunities are **function-level commercial pages** (policy admin, quoting, underwriting, rating) that buyers clearly search for but Insly only covers in glossary/blog form, and **geo-modified broker queries** (UK/AU/UAE) with zero landing pages. Volume/difficulty are unmeasurable in Tier 1 — priorities are fit-ranked, not score-ranked.

### Quick Wins (existing page + clear Measured demand — optimize, don't build)
1. **`insurance broker software` page** — autocomplete-confirmed head term, page already exists. Optimize meta/H1 and interlink from the 25 glossary pages. *Why:* demand confirmed (Seeds A+C), asset exists, near-zero build cost.
2. **MGA glossary cluster → money page links** — "what is an MGA", "MGA vs MGU", "coverholder", "delegated authority" all live and all autocomplete-confirmed. Add CTAs/links into `/en/mga-insurance-software/`. *Why:* converts existing GEO traffic to commercial intent.
3. **Pricing quotability** — pricing page (13-char title "Insly Pricing") is weak for the "insurance software cost/pricing" pattern. Expand title + surface "from €5,000/mo, live in 7–14 days" as a quotable sentence.

### Growth (new commercial pages — demand confirmed, no Insly page)
4. **Policy administration software** landing page — autocomplete: "insurance policy management software", "policyhub insurance management software". No dedicated Insly page.
5. **Insurance quoting software** landing page — autocomplete-confirmed, broker-relevant, currently a sub-feature only.
6. **Insurance underwriting software** landing page — autocomplete-confirmed; Insly's AI/Copilot story is a strong angle.
7. **Geo broker page(s): "insurance broker software UK"** — autocomplete shows UK/AU/UAE/ZA all typed; UK is Insly's stated market (BIBA 2026 blog, "uk-brokers" tag).

### GEO Opportunities (AI-citation plays)
8. **"Best insurance software for MGAs / brokers" comparison listicle** — list-intent query, no Insly asset, high AI-citation value (AI engines love honest comparison tables).
9. **Definition + FAQ schema on glossary pages** — convert 25 existing pages into AI-answer blocks (40–55 word definitions).
10. **Entity foundation** — no Wikidata entity today; without it AI engines can't disambiguate "Insly". Hand to `entity-optimizer`.

### Content Calendar (next 90 days, indicative)
| When | Asset | Type | Cluster |
|---|---|---|---|
| Jul 2026 | Optimize `insurance broker software` + glossary interlinks | Optimize | P1 |
| Jul 2026 | Policy administration software landing page | New page | P2 |
| Aug 2026 | "Best MGA software 2026" comparison listicle | New (GEO) | P1/GEO |
| Aug 2026 | Insurance quoting software landing page | New page | P2 |
| Sep 2026 | Insurance broker software UK (geo page) | New page | P1 geo |
| Sep 2026 | FAQ schema rollout across 25 glossary pages | Optimize (GEO) | P3 |

### Next Steps
- Connect a `~~SEO tool` (Ahrefs/Semrush) or GSC to attach Measured volume + difficulty and compute real Opportunity scores — this is the single biggest unlock.
- Hand the competitor-relative view to `competitor-analysis`, then `content-gap-analysis`.

---

### Handoff Summary

- **Status:** DONE_WITH_CONCERNS
- **Objective:** Build a prioritized keyword/topic map for insly.com from Tier-1 (keyless) Autocomplete demand signals and the live site inventory.
- **Key Findings / Output:** 18 prioritized keywords across 4 pillars. Strong existing coverage on MGA-knowledge/glossary terms (25 live pages) and company-type money pages; clear gaps on function-level commercial pages (policy admin, quoting, underwriting, rating) and geo-modified broker queries (UK/AU/UAE) where Insly has zero landing pages.
- **Evidence:** suggest-insurance-software.json (219, Measured), suggest-broker.json (25, Measured), suggest-mga.json (14, Measured); sitemap.json (523 URLs: 468 blog, 25 glossary — Measured); onpage-*.json (word counts 3,750–4,075 — Measured); robots.json (all AI crawlers allowed — Measured); kg-insly.json (no Wikidata entity — Measured). Volume/difficulty/Opportunity = **N/A** (no tool).
- **Assumptions:** Business goal = demo bookings from MGA/broker/insurer buyers (no user-stated goal). Intent and GEO flags are Estimated.
- **Open Loops:** No Measured volume or difficulty → cannot compute Opportunity scores or rank by traffic. No DR. No Wikidata entity (GEO blocker).
- **Recommended Next Skill:** competitor-analysis (then content-gap-analysis).
- **Target keyword:** `mga insurance software` (primary commercial pillar)
- **CORE-EEAT dimensions:** not scored in this skill.
