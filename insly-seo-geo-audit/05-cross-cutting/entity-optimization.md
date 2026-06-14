# Entity Optimization — Insly

**Entity:** Insly · **Type:** Organization (B2B insurance-software vendor) · **Primary domain:** insly.com
**Audit date:** 2026-06-14 · **Data tier:** Tier 1 (Wikidata reconciliation Measured; AI-engine resolution tests are user-to-run)

---

## Headline finding

> **Insly has NO entity in the open Knowledge Graph.** Measured: `kg-insly.json` → `recognized: false`, `0 matches`. There is no Wikidata item, no Google Knowledge Panel, and therefore no canonical record for AI engines to anchor a citation to. This is the single highest-leverage GEO fix for the whole project: the homepage already exposes `Organization` schema and robots.txt already welcomes every AI crawler, so the content pipeline is open — but the **entity layer that AI uses to verify "what Insly is" is missing entirely.** Every downstream AI-citation gain is throttled until this is fixed.

---

## Step 1 — Entity Discovery

### Entity Profile

- **Entity Name:** Insly
- **Entity Type:** Organization
- **Primary Domain:** https://insly.com/en/
- **Target Topics:** insurance software, MGA software, insurance broker software, insurer platform, insurance Copilot / AI agents for insurance

### Current Entity Presence

| Platform | Status | Details |
|----------|--------|---------|
| Google Knowledge Panel | ❌ Absent | No KG entity → no panel (inferred from no-Wikidata + no-KG match) |
| Wikidata | ❌ Not listed | **Measured:** reconciliation returns 0 matches, recognized:false |
| Wikipedia | ❌ Absent | No article; notability would need third-party coverage |
| Google Knowledge Graph API | ❌ Not found | No entity ID (consistent with Wikidata absence) |
| Schema.org on site | ⚠️ Partial | **Measured:** `Organization` + `WebSite` + `BreadcrumbList` present (schema-home.json) — but no `sameAs`, no `SoftwareApplication`, thin Organization properties |

### AI Entity Resolution Test (USER TO RUN)

Claude cannot query other AI engines live in Tier 1. Run these and record results, then update the profile below:

- "What is Insly?"
- "Who founded Insly and where is it based?"
- "What does Insly's insurance software do?"
- "Insly vs [competitor]" (e.g. vs Novidea, vs Genius/Applied)

| AI System | Recognizes Entity? | Description Accuracy | Cites Insly's content? |
|-----------|-------------------|----------------------|------------------------|
| ChatGPT | ⚠️ user-to-run | likely generic / may confuse with other "Insly" uses | user-to-run |
| Claude | ⚠️ user-to-run | likely partial — established but no KG anchor | user-to-run |
| Perplexity | ⚠️ user-to-run | may cite blog posts without resolving the brand entity | user-to-run |
| Google AI Overview | ⚠️ user-to-run | no Knowledge Panel to draw from | user-to-run |

**Predicted state (pending tests):** partial-to-unrecognized across engines — content is crawlable but the brand has no canonical entity record, so engines describe Insly inconsistently and under-cite it.

---

## Step 2 — Entity Signal Audit (6 categories)

| # | Category | Status | Key finding |
|---|----------|--------|-------------|
| 1 | Structured Data Signals | ⚠️ Partial | `Organization` schema present but no `sameAs`, no `SoftwareApplication`/`Product`, no `foundingDate`/`founder`/`address` populated |
| 2 | Knowledge Base Signals | ❌ Fail | No Wikidata, no Wikipedia, no Crunchbase/G2 linkage exposed as entity signals |
| 3 | Consistent NAP+E Signals | ⚠️ Partial | Name + Twitter `@insly_com` consistent; logo present; full cross-platform name/description/contact consistency unverified |
| 4 | Content-Based Entity Signals | ⚠️ Partial | Deep topical content (468 blog posts, 25 glossary terms) but no authored author-entities; About/founder signals not surfaced as schema |
| 5 | Third-Party Entity Signals | ❌ Fail (Estimated) | No media-mention / co-citation / press evidence in Tier-1 data; brand monitor N/A |
| 6 | AI-Specific Entity Signals | ⚠️ Partial | Crawlability excellent (all AI bots allowed, sitemap, flat depth-1) — but no disambiguation copy, no canonical "What is Insly" definition, no entity-anchoring same-as set |

**Net:** crawl/access layer is strong; the **identity/knowledge-base layer is the failure**. Insly is easy to read and hard to recognize.

---

## Canonical Entity Profile (draft — to save at `memory/entities/insly.md`)

```yaml
---
name: insly
display_name: "Insly"
type: organization
primary_domain: insly.com
also_known_as:
  - "Insly Ltd"
  - "Insly insurance software"
  - "Insly.com"
founded: null                  # CONFIRM founding year before submitting to Wikidata
founders: []                   # CONFIRM founder(s) — needed for Wikidata + Organization schema
headquarters: null             # CONFIRM HQ (commonly cited as Estonia/UK — verify before publishing)
industry: "insurance software (insurtech SaaS)"
categories:
  - "B2B SaaS"
  - "Insurtech"
  - "Insurance software"
  - "MGA / broker / insurer platform"
wikidata_q: null               # DOES NOT EXIST — create (Measured: kg-insly.json recognized:false)
wikipedia_url: null
knowledge_graph_id: null
same_as:                       # TARGET sameAs set — verify each URL before embedding
  - https://www.linkedin.com/company/insly
  - https://www.crunchbase.com/organization/insly
  - https://twitter.com/insly_com
  - https://www.g2.com/products/insly         # confirm listing exists
  - https://ai.insly.com
schema_type: Organization
schema_sub_type: SoftwareApplication
primary_products:
  - "Insly platform"
  - "Insurance Copilot"
  - "AI agent builder (ai.insly.com)"
  - "Socrates Systems"
  - "NORA"
  - "FormFlow"
logo_url: https://insly.com/wp-content/uploads/2021/08/insly_mainHQ.png   # confirm canonical logo
description_short: "Insly is a low-risk insurance software platform for MGAs, brokers, and insurers, offering fast setup, modular tools, and AI-powered products."   # 158 chars
description_long: |
  Insly is a B2B insurance-software (insurtech) platform serving Managing
  General Agents (MGAs), insurance brokers, and insurers. Its modular, low-risk
  approach lets customers design and deliver insurance products, manage
  distribution, accounting, and claims, and go live quickly (positioned as
  7–14 days for MGA software). Insly's product family includes the Insly
  platform, the AI-powered Insurance Copilot, an AI agent builder at
  ai.insly.com, and Socrates Systems, NORA, and FormFlow.
last_verified: 2026-06-14
ai_resolution_status:
  chatgpt: partial            # user-to-confirm
  perplexity: partial         # user-to-confirm
  claude: partial             # user-to-confirm
  gemini: unrecognized        # no KG entity → likely unrecognized
  last_tested: null           # run the AI resolution test, then set
ai_resolution_notes:
  - "No Wikidata/Google KG entity (Measured) — engines have no canonical anchor"
  - "Generic name risk: disambiguate from unrelated 'Insly' uses in AI copy"
gap_type: knowledge_graph
next_action: "Create Wikidata item; expand Organization schema with sameAs + founder + foundingDate + SoftwareApplication; add disambiguation/About entity copy; run AI resolution test"
---
```

> GDPR note: `founders` will name individuals. Before writing founder names to `memory/entities/`, confirm a lawful basis (legitimate interest for public company-founder facts is typical) per memory-management GDPR guidance. Advisory, not legal advice.

---

## Wikidata Creation Plan (the priority action)

1. **Confirm core facts first** (blocking): founding year, founder(s), headquarters, legal entity name, parent/ownership. These are required Wikidata statements and must be sourced from independent references, not the marketing site alone.
2. **Establish notability / references:** gather ≥2–3 independent sources (insurtech press, funding announcements, Crunchbase, business registries). Wikidata items need verifiable references; this also unblocks a future Wikipedia article.
3. **Create the item** with statements:
   - `instance of (P31)` → business / software company
   - `industry (P452)` → insurance software / insurtech
   - `official website (P856)` → https://insly.com
   - `inception (P571)` → founding year
   - `founded by (P112)` → founder(s)
   - `headquarters location (P159)` → HQ
   - `product or material produced (P1056)` → insurance software
4. **Add external identifiers / sameAs** on the item: LinkedIn company ID, Crunchbase ID, Twitter, Capterra/G2.
5. **Capture the QID** and write it back into `memory/entities/insly.md` (`wikidata_q`) and into the on-site Organization schema (`@id` / `sameAs`).
6. **Let it propagate:** Google KG ingests Wikidata over weeks; monitor for a Knowledge Panel and re-run the AI resolution test.

---

## Organization Schema Upgrade (on insly.com/en/)

Current (Measured) Organization block is thin. Upgrade to:

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "@id": "https://insly.com/#organization",
  "name": "Insly",
  "alternateName": ["Insly Ltd", "Insly insurance software"],
  "url": "https://insly.com/en/",
  "logo": "https://insly.com/wp-content/uploads/2021/08/insly_mainHQ.png",
  "description": "Low-risk insurance software for MGAs, brokers, and insurers — fast setup, modular, AI-powered.",
  "foundingDate": "YYYY",
  "founder": { "@type": "Person", "name": "CONFIRM" },
  "address": { "@type": "PostalAddress", "addressCountry": "CONFIRM" },
  "sameAs": [
    "https://www.linkedin.com/company/insly",
    "https://www.crunchbase.com/organization/insly",
    "https://twitter.com/insly_com",
    "https://www.g2.com/products/insly",
    "https://www.wikidata.org/wiki/QXXXXXXX"
  ]
}
```

Plus a `SoftwareApplication` block on product pages (`applicationCategory: "BusinessApplication"`, `offers` with the €5,000/month price point) so AI engines can resolve Insly as a product entity, not just a webpage.

---

## AI-Recognition Signals (GEO)

1. **Canonical "What is Insly" definition** in first 150 words of the homepage and key pages — give engines an extractable, consistent one-sentence entity definition (fixes content-audit C02/C04 too).
2. **Disambiguation copy** — the name "Insly" is short and generic; add a sentence binding it unambiguously to "insurance software for MGAs, brokers and insurers" wherever the brand is introduced.
3. **sameAs everywhere** — the same external-profile set on schema, footer, and About page so engines see consistent entity edges.
4. **Author entities** — give the 468-post blog real bylines + Person schema + LinkedIn sameAs, so content carries author identity into the entity graph.
5. **Integrate the orphan subdomain** — `ai.insly.com` is orphaned (in:0/out:0 per linkgraph); link it from the main nav and reference it in schema so the AI-product entity connects to the parent brand.
6. **Keep the crawl door open** — robots.txt already allows all AI crawlers with a declared sitemap; no change needed, just maintain it.

---

## Top 5 Priority Actions

| # | Action | Impact | Effort | Category |
|---|--------|--------|--------|----------|
| 1 | Create the Insly Wikidata item (after confirming founding/founder/HQ + ≥2 refs) | Very high | Medium | Knowledge Base |
| 2 | Upgrade Organization schema with `sameAs` + founder + foundingDate + `SoftwareApplication` | High | Low | Structured Data |
| 3 | Add canonical "What is Insly" definition + disambiguation copy on key pages | High | Low | AI-Specific |
| 4 | Add author entities (bylines + Person schema + LinkedIn) across the blog | Medium | Medium | Content-Based |
| 5 | Pursue third-party entity signals (Crunchbase, G2, insurtech press) + link the `ai.insly.com` orphan | Medium | Medium | Third-Party / NAP+E |

## Entity Building Roadmap

- **Week 1–2:** confirm core facts + references; upgrade Organization schema with sameAs; add the "What is Insly" definition.
- **Month 1:** create Wikidata item; capture QID into schema + memory; add `SoftwareApplication` schema; link the orphaned `ai.insly.com`.
- **Month 2–3:** add blog author entities; pursue Crunchbase/G2/press; monitor for Google Knowledge Panel; re-run AI resolution test.
- **Ongoing:** keep cross-platform NAP+E consistent; refresh Wikidata as facts change.

## Cross-Reference (CORE-EEAT ↔ CITE)

- CORE-EEAT **A07 (Knowledge Graph Presence) = Fail** and **A08 (Entity Consistency) = Partial** — exactly the gaps this profile closes.
- CITE **I01 (Knowledge Graph Presence) = Fail**, **I04 (Schema.org) = Pass** — the schema base is there; the entity record is not. This work moves I01 and lifts the whole Identity dimension.

---

## Handoff Summary

```yaml
status: DONE_WITH_CONCERNS
objective: "Entity audit + canonical profile + Wikidata/schema/AI-recognition plan for Insly"
key_findings:
  - title: "No Knowledge Graph entity (no Wikidata, no Panel)"
    severity: high
    evidence: "kg-insly.json recognized:false, 0 matches"
  - title: "Organization schema present but thin (no sameAs/founder/SoftwareApplication)"
    severity: medium
    evidence: "schema-home.json Organization recognized but no external identifiers"
  - title: "ai.insly.com entity orphaned from parent brand"
    severity: medium
    evidence: "linkgraph in:0 out:0"
evidence_summary: "kg-insly.json; schema-home.json; onpage JSON-LD; robots.json; linkgraph.json; sitemap.json (523 URLs)"
open_loops:
  - "CONFIRM founding year, founder(s), HQ before Wikidata submission (blocking)"
  - "Run AI resolution test across ChatGPT/Claude/Perplexity/Gemini; set ai_resolution_status"
  - "gap_type: knowledge_graph"
recommended_next_skill: schema-markup-generator
```
