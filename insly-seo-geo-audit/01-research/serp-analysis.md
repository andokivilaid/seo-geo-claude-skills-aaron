# SERP Analysis — Insly (insly.com)

**Date:** 2026-06-14 · **Mode:** Tier 1 (no SEO tool, no live SERP fetch this run) · **Skill:** serp-analysis v9.9.10
**Primary query analyzed:** `mga insurance software` (Insly's primary commercial target) · secondary: `insurance broker software`, `what is an MGA`

> **Method honesty (repo contract + skill quality bar):** This skill's `Done when` requires a **verified live/provided SERP**. In this run **no live SERP was fetched** (no `~~SEO tool`, no provided screenshots/top-10 URLs, and no live WebFetch executed). Therefore the **SERP composition, exact top-10 holders, and True Difficulty score are NOT verified — they are Estimated from query intent and the Insly site data**, and are labeled **Estimated** or **N/A** throughout. This is a **DONE_WITH_CONCERNS** output. To complete it properly, provide a SERP screenshot / top-10 URLs for each query, or connect a SERP tool, and the Estimated cells convert to Measured.

---

## [Phase 1/8: Understand the Query]

| Query | Locale (assumed) | Device | Dominant intent (Estimated) | Insly fit |
|---|---|---|---|---|
| `mga insurance software` | UK/global EN, desktop | desktop | **Commercial investigation** (buyer comparing vendors) | Has page `/en/mga-insurance-software/` |
| `insurance broker software` | UK/global EN | desktop | **Commercial investigation** | Has page `/en/insurance-broker-software/` |
| `what is an mga` (insurance) | global EN | desktop+mobile | **Informational / definitional** | Has glossary `mga-in-insurance` |

Autocomplete evidence (**Measured**, suggest-*.json) confirms all three are real, frequently-typed queries; their *intent* below is Estimated.

---

## [Phase 2/8: Map SERP Composition] — Estimated (no live SERP)

Expected modules per query, inferred from intent + query class. **None verified this run.**

**Query A — `mga insurance software` (commercial):**
- Likely: 2–4 paid ads (vendor PPC is heavy in B2B insurtech) — Estimated
- Likely: organic top-10 = vendor product pages (Guidewire, Duck Creek, Novidea, INSTANDA, Socotra, Insly) + a "best MGA software" listicle or two — Estimated
- Possible: AI Overview summarizing "what MGA software does + top vendors" — Estimated (robots open, so Insly *could* be cited)
- Likely thin: PAA present ("What is MGA software?", "What is an MGA in insurance?") — Estimated
- Unlikely: shopping/local/news packs

**Query B — `insurance broker software` (commercial):** same shape as A, with heavier geo-modification (UK/AU buyers) and stronger incumbent presence (Applied, Open GI, SSP) — Estimated.

**Query C — `what is an mga` (informational):**
- Likely: **AI Overview + Featured Snippet + PAA** dominate (classic definition SERP) — Estimated
- Likely top organic: Investopedia / Wikipedia / association explainers + vendor glossaries (Insly's `mga-in-insurance` competes here) — Estimated

---

## [Phase 3/8: Analyze Top Ranking Pages]  ·  [Phase 4: Patterns]

**Not verified** — no live top-10 captured. Estimated ranking patterns by query class:

- **Commercial (A,B):** winners are deep product pages with clear segment H1, feature blocks, pricing signals, and customer proof, backed by high domain authority. Insly's pages are **deep (3,973 words on the MGA page, Measured)** and have a correct single H1 ("Low-risk MGA Insurance Software", Measured) — content depth is competitive; the gap is Estimated domain authority and customer-proof density.
- **Informational (C):** winners are concise, well-structured definition pages with a 40–55 word answer up top, FAQ/PAA coverage, and schema. Insly's glossary pages are candidates but need explicit definition blocks + FAQ schema (see GEO below).

**Common trait across all three (Estimated):** the top results carry recognizable brand entities. Insly's **missing Wikidata entity (Measured, kg-insly.json)** is a structural disadvantage in entity-led SERPs and AI Overviews.

---

## [Phase 5/8: Analyze SERP Features]

| Feature | Query A (commercial) | Query C (definitional) | Insly opportunity |
|---|---|---|---|
| AI Overview | Likely (Est.) | Very likely (Est.) | Open robots = eligible; needs quotable answer blocks |
| Featured Snippet | Possible (Est.) | Likely (Est.) | Add 40–55 word definition at top of glossary/MGA page |
| People Also Ask | Likely (Est.) | Likely (Est.) | Map PAA → FAQ schema on the page |
| Shopping/Local/News | Unlikely (Est.) | Unlikely (Est.) | n/a |
| Site links (brand) | Only on brand query | n/a | Strengthen with clean architecture (already flat, depth 1 — Measured) |

> All feature presence is **Estimated** — confirm against a live SERP before acting.

---

## [Phase 6/8: Determine Search Intent]

- `mga insurance software` → **Commercial investigation** (Estimated; high confidence from query structure: software + buyer segment). Build/optimize a vendor product page, not a blog post. ✅ Insly already has the right page type.
- `insurance broker software` → **Commercial investigation** (Estimated). ✅ Right page type exists.
- `what is an mga` → **Informational/definitional** (Estimated, high confidence). ✅ Glossary page is the right type; optimize for snippet + AI Overview.

Intent–page-type alignment is **correct** for all three Insly targets — a genuine strength (the common failure mode of pointing a blog post at a commercial query does not apply here).

---

## [Phase 7/8: Calculate True Difficulty] — N/A (cannot verify inputs)

The template weights: Top-10 authority 25% · page authority/links 20% · content-quality bar 20% · backlinks required 20% · SERP stability 15%. **Four of five inputs (top-10 authority, links, backlinks, stability) require a live SERP or backlink tool — none available.** Therefore:

| Query | True Difficulty | Status |
|---|---|---|
| `mga insurance software` | **N/A** (Est. directional: High — incumbent-heavy commercial SERP) | inputs unverifiable in Tier 1 |
| `insurance broker software` | **N/A** (Est. directional: High — incumbents + geo competition) | inputs unverifiable |
| `what is an mga` | **N/A** (Est. directional: Medium — definitional, beatable with structure) | inputs unverifiable |

**Per-site-stage advice (Estimated):**
- *New site:* skip the head commercial terms; start with the long-tail definitional + "how MGAs reduce admin" cluster.
- *Growing site (Insly's likely stage):* attack definitional/comparison terms and function-level pages while building entity + authority; defend the MGA page.
- *Established site:* contest head commercial terms directly with customer-proof-heavy pages.

---

## [Phase 8/8: Recommendations]

### Key Findings
1. All three target queries have **correct intent-to-page-type alignment** on Insly's side (Measured page types) — a real strength.
2. The commercial SERPs (A, B) are **Estimated incumbent-heavy**; Insly competes on content depth (Measured 3,900+ words) but is disadvantaged on Estimated authority and the **Measured missing entity**.
3. The definitional SERP (C) is the **most winnable** and most AI-Overview-exposed — Insly's glossary is the right asset, under-optimized for snippets.

### Minimum Content Requirements to Rank (Estimated, by query)
- **Commercial (A/B):** segment-specific H1 ✅, feature/benefit blocks ✅, **pricing signal** (Insly has "from €5,000/mo, 7–14 days" — surface it), **named customer proof + outcome numbers** (add), comparison/alternatives section (add).
- **Definitional (C):** 40–55 word answer block up top, FAQ schema, internal links to the commercial page, cited sources.

### SERP Feature Strategy
- Win **Featured Snippet + AI Overview** on definitional terms: add concise answer blocks + FAQ/HowTo schema to the 25 glossary pages and the MGA page (hand to `schema-markup-generator` + `geo-content-optimizer`).
- Fix homepage **0-H1** (Measured) before chasing brand/sitelink features.

### Recommended Content Outline — "MGA insurance software" page upgrade
1. H1: Low-risk MGA Insurance Software (exists ✅)
2. 40–55 word "what is MGA software / what Insly does" answer block (for snippet + AI)
3. Core modules (product builder, distribution, accounting, claims — exists ✅)
4. Pricing + speed signal ("from €5,000/mo, live in 7–14 days")
5. Customer proof + outcome metric (ADD)
6. "Insly vs alternatives" comparison block (ADD — also seeds the GEO listicle)
7. FAQ block with schema (ADD)

### Next Steps
- **Provide a live SERP (screenshot or top-10 URLs) or connect a SERP tool** for each target query → converts every Estimated cell here to Measured and unlocks a real True Difficulty score. This is the gating action.
- Then hand to `seo-content-writer` / `geo-content-optimizer` to build against the verified SERP.

---

### Handoff Summary

- **Status:** DONE_WITH_CONCERNS
- **Objective:** Map SERP composition, intent, and difficulty for Insly's primary commercial and definitional target queries.
- **Key Findings / Output:** Insly's target queries are correctly aligned to the right page types (Measured page inventory). Commercial SERPs are Estimated incumbent-heavy (True Difficulty directional High, **not verified**); the definitional `what is an MGA` SERP is the most winnable and AI-Overview-exposed, and Insly's glossary is the right asset but under-optimized for snippets/schema.
- **Evidence:** Autocomplete confirms all 3 queries are real (suggest-*.json, Measured); onpage-en-mga-insurance-software.json (1 H1, 3,973 words, Measured); onpage-home.json (0 H1, Measured); robots.json (AI crawlers open, Measured); kg-insly.json (no entity, Measured). **SERP composition, top-10, and True Difficulty = Estimated/N/A — no live SERP fetched this run.**
- **Assumptions:** Locale = UK/global EN desktop; intents inferred from query structure; SERP feature presence inferred from query class.
- **Open Loops:** No verified live SERP → True Difficulty is N/A and feature presence is unconfirmed. Provide SERP evidence or connect a tool to finish.
- **Recommended Next Skill:** seo-content-writer (for the MGA/broker page upgrades) — but first supply a live SERP to verify difficulty.
- **Target keyword:** `mga insurance software`
- **CORE-EEAT dimensions:** not scored in this skill.
