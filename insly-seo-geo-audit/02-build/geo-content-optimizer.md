# geo-content-optimizer — Insly AI-Citation Readiness

> Skill: `build/geo-content-optimizer` (v9.9.10) · Mode: Tier 1 (no AI-monitor / SEO tool connected) · Date: 2026-06-14
> Scope: Insly's homepage + 3 product pages (mga / insurance-software / pricing) and what it takes for ChatGPT, Perplexity, Gemini, Claude, and Google AI Overviews to cite them.
> Metric labeling: AI citation share / impressions = **N/A** (no `~~AI monitor` connected — cannot measure how often Insly is already quoted). All GEO scores below are **Estimated** (model inference from page structure in the `onpage-*.json` files), not Measured.

---

## 1. Technical GEO baseline (Measured — strong)

| Signal | State | Source | GEO impact |
|---|---|---|---|
| AI crawler access | **All AI bots allowed**, 0 disallow rules (GPTBot, ClaudeBot, Google-Extended, CCBot, PerplexityBot, Bytespider) | `robots.json` | Best-case baseline — nothing is blocking AI ingestion. |
| Sitemap declared | Yes, 523 URLs | `robots.json` / `sitemap.json` | AI crawlers can discover the full corpus. |
| Content depth | Home 4,004 words; product pages 3,750–4,075 | `onpage-*.json` | High raw material — but depth ≠ quotability (see §3). |
| Schema present | Organization + WebSite + BreadcrumbList | `schema-home.json` | Entity scaffolding exists, but **no `sameAs`, no SoftwareApplication, no FAQPage** (gap — see schema file). |
| **Wikidata entity** | **recognized:false, 0 matches** | `kg-insly.json` | **Critical GEO gap.** No Knowledge-Graph node = AI engines have no canonical entity to anchor "Insly" to. |

**Verdict:** Insly has done the *access* half of GEO (bots welcome, sitemap, deep content) but almost none of the *citability* half (quotable blocks, statistics, standalone definitions, entity grounding). The site is readable by AI but not *quotable* by AI.

---

## 2. Why Insly is currently hard to cite (diagnosis)

AI answer engines preferentially quote content that is: (a) a self-contained 25–60 word answer, (b) attached to a recognized entity, (c) backed by a specific dated statistic or source, and (d) structured as Q&A / definition / list. Insly's pages fail mostly on (a), (b), and (c):

1. **Homepage has 0 H1 and no definitional block** (`onpage-home.json`, `h1_count: 0`). The H2s are navigation labels ("By company type", "By Solution") — *not* answerable statements. An AI engine scanning the homepage finds no sentence it can lift to answer "What is Insly?"
2. **No canonical entity** (`kg-insly.json`). When a user asks ChatGPT/Perplexity "what is Insly", the model has no Knowledge Graph / Wikidata node to ground the answer, so it may hedge, conflate Insly with other "Insly"/insurance tools, or decline to cite.
3. **Claims are marketing-shaped, not quote-shaped.** "Fast setup, AI-powered and real results" (home meta) and "launch fast, scale confidently, cut complexity" (MGA meta) are unquotable — no AI engine cites an adjective. The genuinely citable facts (go-live **7–14 days**, **from €5,000/month**, **100% accounting accuracy**) are buried in body copy, not surfaced as standalone statements.
4. **No FAQ blocks / no FAQPage schema** anywhere in the four pages — the single highest-leverage GEO format for B2B SaaS is absent.

> **GEO score (Estimated, current):** Home **22/100**, MGA page **41/100**, Insurance-software page **42/100**, Pricing **38/100**. Scores are model-inferred from structure, not measured citation rates (which are **N/A**).

---

## 3. Concrete rewrites (quotable blocks)

These are drop-in blocks. Each is engineered as a standalone 25–55 word answer that an AI engine can lift verbatim. Numbers used are Insly's own on-site claims (User-provided); nothing is invented.

### Rewrite A — Homepage "What is Insly?" block (NEW — currently missing)
Place directly under a new H1 (`Low-Risk Insurance Software for MGAs, Brokers and Insurers`). This simultaneously fixes the missing-H1 on-page bug and the missing-definition GEO bug.

> **Insly is a low-risk insurance software platform for MGAs, insurance brokers, and insurers.** It provides a product builder, distribution, policy administration, accounting, and claims management in one modular system, with AI tools (Insurance Copilot) built in — so insurance providers can launch new products in weeks rather than months.

*Why it works:* names the entity in the first three words, states the category ("insurance software platform"), lists capabilities, and ends with the differentiator. ~50 words. Quotable by every engine.

### Rewrite B — MGA page lead definition
Current page opens with marketing ("launch fast, scale confidently, cut complexity"). Add this above it:

> **Insly's MGA insurance software lets a Managing General Agent build and rate products, distribute through brokers, administer policies, and manage claims in one platform.** New programs can go live in **7–14 days**, with pricing **from €5,000/month** based on system scope and GWP transacted.

*Why it works:* definition + two specific, dated-style facts in one block. This is the exact shape Perplexity and AI Overviews lift for "MGA insurance software" / "MGA platform cost".

### Rewrite C — Convert one marketing H3 into a statistic block
On the insurer page, the claim "gain 100% accounting accuracy" exists in the meta but not as a quotable on-page statement. Surface it:

> **Insly delivers 100% accounting accuracy for insurers** by reconciling premium, commission, and bordereaux automatically inside the policy system, removing the manual reconciliation that causes most capacity-provider disputes. *(Insly platform claim.)*

*Why it works:* leads with a number, explains the mechanism, and is honestly attributed as a vendor claim — AI engines reward attributed specifics over bare adjectives.

---

## 4. Statistics & sourcing upgrades

AI engines cite *specific, attributable* numbers. Insly currently has a few good ones (7–14 days, €5,000/month, 100% accounting, 523 content URLs, 4,000-word depth) but presents them as marketing rather than evidence.

**Do:**
- Surface every concrete number as a standalone sentence with the unit and a light source tag ("Insly platform data", "based on customer implementations").
- Add **dated** proof points where they exist: "As of 2026, …", customer counts, GWP processed, number of live products. `[needs source — supply from Insly's own metrics; do not invent]`
- Where Insly cites an industry stat, attribute it to a named, dated source. Unattributed stats are the #1 reason AI engines skip a block.

**Don't:**
- Don't convert marketing adjectives into fake precision. If the real number isn't available, leave the claim qualitative rather than fabricating a statistic. (Tier 1 rule.)

---

## 5. Structure rewrites (format = citability)

1. **Add a 4–6 item FAQ block to each money page** (home, mga, insurance-software, pricing) using real questions from the autocomplete clusters ("what is MGA software", "how much does insurance software cost", "insurance software for brokers"). Pair with **FAQPage schema** (see `schema-markup-generator.md`). This is the single highest-ROI GEO change — it creates 4–6 standalone quotable answers per page.
2. **Fix the homepage H1** — no H1 means no anchor heading for AI extraction. Rewrite A doubles as the fix.
3. **Replace navigation-only H2s** ("By company type", "By Solution") with answerable H2s on at least the editorial/blog layer ("How fast can an MGA launch?", "What does MGA software cost?").
4. **Add a comparison table** (MGA-specific vs. generic insurance software) — tables are disproportionately lifted into AI Overviews.

---

## 6. Entity grounding (hands off to entity-optimizer)

The Wikidata/Knowledge-Graph gap (`kg-insly.json` recognized:false) is outside this skill's body-content scope but is the largest single ceiling on Insly's AI citation rate. Per the entity-geo handoff schema, `memory/entities/insly.md` is **missing** — so this run is declared **DONE_WITH_CONCERNS** and `entity-optimizer` is logged as an open loop. Minimum entity actions to unblock GEO:
- Create a Wikidata item for Insly (company, insurance software, HQ, founded, products).
- Add `sameAs` (LinkedIn, Crunchbase, Twitter/X `@insly_com`, Wikidata) to Organization schema — see schema file.
- Establish one consistent `description_short` reused across schema, OG, and the homepage definition block (Rewrite A).

---

## CORE-EEAT GEO self-check

| Item | Check | Result |
|---|---|---|
| C02 | Standalone direct-answer block per target query | **Fail → addressed** by Rewrites A/B/C + per-page FAQ. |
| C04 | Clear definitions | Fail (no definition on home) → fixed by Rewrite A. |
| C09 | Specific, attributed data | Warn — facts exist but unsurfaced/under-attributed (§4). |
| O02/O03 | Scannable Q&A / list / table structure | Fail (nav-only H2s) → §5. |
| O05 | Schema matching visible content (FAQPage) | Fail — no FAQ schema → hand to schema-markup-generator. |
| O06 | Freshness signals (dated facts) | Warn — no visible dates; add "as of 2026". |
| R01/R02/R04/R07 | Source attribution / reliability | Warn — vendor claims must stay labeled as claims. |
| E01 | Entity recognized by AI / Knowledge Graph | **Fail** — no Wikidata node → entity-optimizer (open loop). |
| Exp10 / Ept08 | First-hand experience / expertise signals | Warn — add customer/implementation specifics `[needs source]`. |

**AI Query Coverage (Estimated):** Of the target queries (`what is Insly`, `MGA insurance software`, `insurance software for insurers`, `MGA platform cost`), **0/4 currently have a quotable standalone answer on-page**; after Rewrites A–C + FAQ blocks, **4/4** would. Actual citation lift is **N/A** until an AI monitor is connected.

---

## Handoff Summary

- **Objective**: Assess Insly's AI-citation (GEO) readiness and produce concrete quotable-block / statistic / structure rewrites.
- **Output**: This file — technical GEO baseline, 4-point diagnosis, 3 drop-in quotable rewrites (A/B/C), statistics & structure upgrades, entity-grounding plan, GEO self-check.
- **Evidence**: robots all-allow + sitemap (`robots.json`); no Wikidata node (`kg-insly.json`); homepage 0 H1 / nav-only H2s (`onpage-home.json`); on-site facts (7–14 days, €5,000/mo, 100% accounting) from product `onpage-*.json`. Citation-rate metrics = **N/A** (no AI monitor).
- **Open loops**: `memory/entities/insly.md` missing → Wikidata entity + `sameAs` (entity-optimizer); FAQPage schema (schema-markup-generator); fill `[needs source]` proof points from Insly's own data.
- **Target keyword**: MGA insurance software / "what is Insly" (entity query).
- **GEO score (Estimated)**: Home 22 → ~70 projected; MGA 41 → ~78 projected after rewrites. AI Query Coverage 0/4 → 4/4 projected.
- **CORE-EEAT (Estimated)**: C:55 O:48 R:50 E:35 (E capped by missing entity node).
- **Completion status**: DONE_WITH_CONCERNS (entity profile missing + several `[needs source]` proof points).
- **Next skill**: `entity-optimizer` (unblock the Wikidata/`sameAs` ceiling) → `schema-markup-generator` (FAQPage) → `content-quality-auditor` (gate).
