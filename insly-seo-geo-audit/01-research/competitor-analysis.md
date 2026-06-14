# Competitor Analysis — Insly (insly.com)

**Date:** 2026-06-14 · **Mode:** Tier 1 (no SEO tool connected) · **Skill:** competitor-analysis v9.9.10

> **Labeling rule (repo contract):** No backlink/traffic/rankings tool is connected. **Traffic, Domain Rating/Authority, ranking counts, and backlink totals are Estimated** (model/industry inference) or **N/A** — never Measured. The only **Measured** facts here are about Insly itself (from the data files) and the *existence/positioning* of named competitors (well-known public vendors). Every competitor metric below is explicitly tagged **Estimated** or **N/A**. Do not read any number in the comparison table as a real measurement.

---

## [Step 1/8: Identify Competitors]

Insly = "low-risk insurance software" for **MGAs, brokers, and insurers** (Measured: homepage meta). Its rivals split into three tiers by where they compete:

**Direct competitors (MGA / broker / policy-admin platforms — closest fit):**
- **Novidea** — cloud broker/MGA data platform (London/Israel).
- **Open GI** + **SSP** — UK broker software incumbents (Insly's stated UK-broker battleground).
- **INSTANDA** (a.k.a. "Genius"-class no-code) — no-code product builder; overlaps Insly's "build your own product/agent".
- **Socotra** — modern cloud-native core platform / API-first PAS.

**Indirect / enterprise-core competitors (carrier-scale, up-market of Insly):**
- **Guidewire**, **Duck Creek**, **Sapiens**, **Vertafore** (Applied/AMS-adjacent), **Applied Epic** (broker management, North America), **Ebix**.

**Content / SERP competitors (rank for Insly's informational terms even if not product rivals):**
- Industry media & glossaries: **Investopedia / Wikipedia** (definitions like "MGA", "coverholder"), broker-association sites (BIBA, Lloyd's market explainers), and the marketing blogs of the vendors above.

**Decision-gate note:** competitors were inferable from Insly's positioning + the task brief, so no stop-and-ask. Deep-dive set chosen = the **5 closest direct rivals**: Novidea, INSTANDA, Socotra, Open GI, Applied Epic. Enterprise-core players (Guidewire/Duck Creek/Sapiens) are benchmarked at a lighter level as "ceiling" references.

---

## [Step 2/8: Gather Competitor Data]  ·  [Step 3–5: Keywords / Content / Backlinks]

### Comparison table

All competitor figures **Estimated** unless marked. Insly figures **Measured** where cited.

| Vendor | Segment fit vs Insly | Domain age (Est.) | Est. organic traffic | Est. DR/DA | Content footprint | Backlink posture (Est.) |
|---|---|---|---|---|---|---|
| **Insly** | — (self) | est. 2014+ | **N/A** (no tool) | **N/A** | **523 URLs Measured** (468 blog, 25 glossary) | **N/A** |
| **Novidea** | Direct — broker/MGA data platform | Est. older | Est. mid | Est. higher than Insly | Est. blog + resources, funding-PR heavy | Est. strong (VC/press) |
| **INSTANDA** | Direct — no-code product builder | Est. ~2012 | Est. mid | Est. comparable–higher | Est. strong thought-leadership + glossary | Est. strong (awards/PR) |
| **Socotra** | Direct — API-first core PAS | Est. ~2014 | Est. mid–low | Est. comparable | Est. dev-docs + blog | Est. moderate (dev/API links) |
| **Open GI** | Direct — UK broker software | Est. legacy/old | Est. mid (UK) | Est. higher (age) | Est. modest blog | Est. strong (UK age/links) |
| **Applied Epic / Applied Systems** | Direct (NA) — broker mgmt | Est. legacy/old | Est. **high** | Est. **high** | Est. large resource library | Est. very strong |
| **Guidewire** | Indirect ceiling — carrier core | Est. old | Est. high | Est. very high | Est. large (docs, marketplace, blog) | Est. very strong |
| **Duck Creek** | Indirect ceiling — carrier core | Est. old | Est. high | Est. high | Est. large | Est. very strong |
| **Sapiens** | Indirect ceiling — carrier core | Est. old | Est. high | Est. high | Est. large | Est. very strong |
| **Vertafore** | Indirect — agency/broker mgmt (NA) | Est. old | Est. high | Est. high | Est. large | Est. very strong |

> **Why every number is Estimated:** ranking counts, traffic, DR, and backlink totals require Ahrefs/Semrush/SimilarWeb — none connected. The quality bar ("tie each strength to a number and a named competitor") is **only partially satisfiable in Tier 1**; this is logged as a concern. Connect a `~~SEO tool` to replace Estimated cells with Measured ones.

### Keyword posture (Estimated, directional)
- **Enterprise-core players (Guidewire/Duck Creek/Sapiens/Vertafore/Applied)** almost certainly own the broad head terms Insly's Autocomplete data surfaced — "insurance software", "insurance software duck creek", "guidewire", "epic insurance software", "applied insurance software uk" all appear as named queries in `suggest-insurance-software.json` (**Measured** that users type the competitor brand names). Insly does not appear as an autocomplete brand → **lower brand-query demand** than incumbents.
- **Direct players (Novidea/INSTANDA/Socotra)** compete with Insly on "MGA software", "no-code insurance", "embedded insurance", "insurance product builder" — Insly's strongest differentiators.
- **Insly's relative keyword edge:** the 25-term **MGA/delegated-authority glossary** (coverholder, bordereaux, delegated authority, MGA vs MGU) is unusually deep for a vendor of its size — a defensible informational moat most direct rivals under-invest in.

### Content strategy (Measured for Insly; Estimated for rivals)
- **Insly content volume is high for its segment:** 468 blog posts + 25 glossary terms (Measured, sitemap.json), publishing actively (latest posts 2026-06-11; cadence ~weekly). Money pages are deep (3,750–4,075 words, Measured).
- Themes (Measured from slugs): AI in insurance, claims automation, embedded insurance, STP for MGAs, UK brokers/BIBA, "women building Insly" (EEAT/people signals). This is a healthy, people-led, topical blog.
- Rivals (Estimated): enterprise players lean on analyst reports, customer logos, and gated whitepapers; direct players lean on funding PR + product thought-leadership.

### Backlink profile (N/A — no tool)
All backlink totals, referring domains, and anchor distributions are **N/A** in Tier 1. Directional Estimate only: incumbents (Applied, Guidewire, Open GI) have a multi-year age/PR advantage; Insly's linkable assets are its glossary and original blog research. Hand to `backlink-analyzer` once a tool is connected.

---

## [Step 6/8: Technical SEO Assessment] (Insly = Measured)

| Factor | Insly | Source |
|---|---|---|
| Architecture | Flat — all 40 crawled pages reachable at **depth 1**, ~38 internal in-links each | Measured (crawl/linkgraph) |
| Core Web Vitals | **N/A — not measured** (PSI returned HTTP 429; needs PAGESPEED_API_KEY or GSC/CrUX) | Measured limitation (psi-home.json) |
| Crawl/AI access | robots.txt allows ALL AI crawlers, 0 disallow, sitemap declared | Measured (robots.json) |
| Known defects | Homepage **0 H1**; duplicate URLs at `/en/<slug>/` AND `/<slug>/`; `ai.insly.com` orphaned (in:0/out:0); 4 orphan URLs | Measured (onpage-home, brief) |

**Read-across:** Insly's flat architecture and AI-crawler-open robots are a technical *advantage* vs legacy incumbents likely carrying heavier, older stacks (Estimated). The homepage-0-H1 and duplicate-URL issues are self-inflicted gaps to fix before chasing competitive terms.

---

## [Step 7/8: GEO / AI Citation Analysis]

- **Insly baseline is GEO-favorable:** all AI crawlers allowed (Measured) + a deep definitional glossary = good raw material for ChatGPT/Perplexity/AI-Overview citations on MGA/coverholder/bordereaux queries.
- **Critical entity gap:** Insly has **no Wikidata / Knowledge Graph entity** (Measured, kg-insly.json: recognized:false). Larger rivals (Guidewire, Duck Creek, Sapiens, Vertafore) almost certainly *do* have Wikidata/Wikipedia presence (Estimated) → they are easier for AI engines to recognize and cite as entities. **This is Insly's single biggest competitive GEO disadvantage.**
- **Opening to exploit:** on narrow MGA/delegated-authority definitional and "how MGAs reduce admin / STP for MGAs" queries, enterprise rivals publish little buyer-friendly explainer content — Insly's glossary + blog can win these AI citations if entity recognition is fixed.

---

## [Step 8/8: Synthesize]

### Executive Summary
Insly sits **mid-market between legacy incumbents and modern niche platforms**. Against enterprise cores (Guidewire/Duck Creek/Sapiens/Vertafore/Applied) it is out-gunned on Estimated traffic, age, and backlinks, and cannot win broad head terms head-on. Against direct rivals (Novidea/INSTANDA/Socotra/Open GI) it competes on equal footing and has a **content moat**: 468 blog posts + a 25-term MGA glossary (Measured) that most same-size rivals under-build. The two things blocking Insly from converting that content advantage are **self-inflicted technical gaps** (homepage 0 H1, duplicate URLs) and **a missing brand entity** (no Wikidata), both fixable.

### Strengths to learn from (competitors)
- **Applied Epic / Guidewire (Est.):** large, well-organized resource libraries + analyst/customer-proof content. *Lesson:* add customer case studies and outcome numbers to Insly money pages.
- **INSTANDA (Est.):** no-code thought-leadership ties product to a category narrative. *Lesson:* Insly should own "no-code / low-code insurance" (it already has glossary terms for both — `no-code-in-insurance`, `low-code-in-insurance`).
- **Novidea (Est.):** funding/PR-driven authority. *Lesson:* turn Insly milestones (BIBA 2026, claims portal launch) into linkable PR.

### Weaknesses to exploit (competitors)
- **Enterprise rivals publish little MGA buyer-education** (Est.) → Insly's glossary/STP/“how MGAs reduce admin” content can capture informational + AI-citation traffic they ignore.
- **Legacy UK incumbents (Open GI/SSP)** likely run older stacks/sites (Est.) → Insly's flat, fast, AI-open architecture (Measured) is a differentiator to message on broker pages.
- **Geo-modified broker demand is under-served** by everyone in autocomplete (UK/AU/UAE/ZA all typed, Measured) → Insly has 0 geo pages; first-mover room.

### Action plan
**Immediate (0–30 days)**
- Fix homepage H1 + duplicate `/en/` vs `/` canonical issue (removes self-inflicted disadvantage before any competitive push).
- Interlink the 25 glossary pages → MGA/broker/insurer money pages to compound the existing content moat.

**Short-term (1–3 months)**
- Publish "Best insurance software for MGAs / brokers 2026" honest comparison (names rivals; wins list-intent + AI citations).
- Build function-level pages (policy admin, quoting, underwriting) where direct rivals are thin.
- Create entity foundation (Wikidata + sameAs) → hand to `entity-optimizer`.

**Long-term (3–12 months)**
- Geo broker pages (UK first) to claim under-served regional demand.
- Connect a `~~SEO tool` to replace all Estimated competitor metrics with Measured ones and run a true keyword-gap deep-dive.

---

### Handoff Summary

- **Status:** DONE_WITH_CONCERNS
- **Objective:** Benchmark Insly against its closest insurance-software competitors and produce an action plan, in Tier-1 keyless mode.
- **Key Findings / Output:** Insly is mid-market — out-resourced by enterprise cores (Guidewire/Duck Creek/Sapiens/Vertafore/Applied) but on par with direct rivals (Novidea/INSTANDA/Socotra/Open GI), with a real content moat (468 blog + 25 glossary pages, Measured). Biggest competitive disadvantages are the missing Wikidata entity (Measured) and self-inflicted technical gaps (homepage 0 H1, duplicate URLs, Measured).
- **Evidence:** sitemap.json (523 URLs, Measured), onpage-*.json (word counts + 0 H1, Measured), robots.json (AI crawlers open, Measured), kg-insly.json (no entity, Measured), suggest-insurance-software.json (rival brand names typed: duck creek/guidewire/epic/applied/novidea, Measured). All competitor traffic/DR/backlink figures = **Estimated** or **N/A** (no tool).
- **Assumptions:** Competitor set inferred from Insly positioning + brief; domain ages/traffic/DR are model/industry estimates, not measured.
- **Open Loops:** No Measured competitor traffic, DR, ranking counts, or backlinks (Tier-1 limitation) → quality bar only partially met. CWV N/A. No entity.
- **Recommended Next Skill:** content-gap-analysis (then backlink-analyzer once a tool is connected).
- **Target keyword:** `mga insurance software`
- **CITE scores:** not computed here (run domain-authority-auditor for CITE).
