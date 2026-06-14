# Memory & Handoffs — Insly SEO/GEO Project

Synthesized project memory for the Insly (insly.com) campaign. Produced by `memory-management` from the project brief (Measured data, 2026-06-14) and the cross-cutting auditor outputs in this folder. Two parts: (1) a HOT-cache block (≤80 lines, ready to drop into `memory/hot-cache.md`); (2) the cross-phase open-loops list.

---

## Part 1 — HOT Cache (`memory/hot-cache.md`, ≤80 lines / 25KB)

```markdown
# HOT CACHE — Insly (insly.com)  ·  updated 2026-06-14  ·  Tier 1 (manual data)

## Project
- Site: insly.com (WordPress, primary locale /en/). Type: B2B insurtech SaaS.
- What: "low-risk insurance software" for MGAs, brokers, insurers. Fast setup, modular, AI-powered.
- Products: Insly platform, Insurance Copilot, AI agent builder (ai.insly.com), Socrates Systems, NORA, FormFlow.
- Goal: rank + get cited by AI engines for MGA/broker/insurer software; convert ("go live 7–14 days, from €5,000/mo").

## Hero keywords (demand = Measured via autocomplete; volume/difficulty = N/A, no SEO tool)
- P1: insurance software · MGA software · insurance broker software · insurer platform software
- Long-tail (suggest-*.json): insurance software for agents/brokers, insurance software companies/systems/tools.
- NOTE: treat all volume/difficulty as Estimated/N/A — never present as Measured.

## Primary competitors (to confirm — no competitor data pulled yet)
- OPEN: competitor set not yet established (research phase pending). Candidates to validate: Novidea, Applied/Genius, Duck Creek, Socotra.

## Active veto / critical status
- Content audit (MGA page): NO veto failed. cap_applied:false. Verdict FIX.
- Domain audit (CITE): NO veto failed (T03/T05/T09 all Pass). cap_applied:false. Verdict CAUTIOUS.
- => No blockers from critical-trust items. Risks are gaps, not penalties.

## Scores (this session)
- CORE-EEAT (MGA page, Landing): weighted 53/100 Low · GEO 49 · SEO 52.
- CITE (insly.com, Product&Service): 60/100 Medium (observable items; link/traffic/AI-citation N/A).
- Diagnosis: Medium CITE + Low CORE-EEAT => fix money-page content quality + build entity in parallel.

## Biggest finding (drives everything)
- NO Knowledge Graph entity. Measured: kg-insly.json recognized:false, 0 matches.
  No Wikidata, no Google Panel => AI engines have no canonical anchor to cite Insly.
  Single highest-leverage GEO fix. Routed to entity-optimizer.

## Other measured site facts
- Homepage has 0 H1 (onpage-home.json); product pages have exactly 1 H1.
- Duplicate URLs: /en/<slug>/ AND /<slug>/ both exist => canonical/duplication risk.
- ai.insly.com orphaned in linkgraph (in:0 out:0). 4 orphan URLs. Max crawl depth 1 (good).
- robots.txt allows ALL AI crawlers (GPTBot/ClaudeBot/Google-Extended/CCBot/PerplexityBot/Bytespider), 0 disallow, sitemap declared => strong GEO baseline.
- Sitemap 523 URLs (468 blog, 25 glossary). Content depth high (~3,700–4,075 words/page).
- Schema present: Organization + WebSite + BreadcrumbList. Missing: sameAs, FAQ, SoftwareApplication.
- Twitter @insly_com. HTTPS site-wide.

## Unavailable (Tier 1 — never fabricate)
- Backlinks / Domain Rating / referring domains: N/A (no link DB).
- Organic traffic / rankings / keyword volume: N/A (no SEO tool/GSC).
- Core Web Vitals: N/A — PSI returned HTTP 429 (psi-home.json). Needs PAGESPEED_API_KEY or GSC/CrUX.
- AI-citation frequency: N/A (no AI monitor).

## Next actions (highest leverage first)
1. entity-optimizer: confirm founding/founder/HQ + refs -> create Wikidata item -> capture QID.
2. content money pages: add FAQ+schema, comparison table, evidence/citations for "low-risk/fast ROI".
3. technical: add homepage H1; resolve /en/ vs / duplication via canonical; link ai.insly.com orphan.
4. schema-markup-generator: upgrade Organization (sameAs+founder+SoftwareApplication) + FAQPage.
5. research phase: establish competitor set + keyword priorities (currently OPEN).
```

---

## Part 2 — Open Loops (cross-phase)

| # | Open loop | Phase / owner skill | Status | Evidence |
|---|-----------|---------------------|--------|----------|
| OL-1 | **Create Insly Knowledge Graph entity** — no Wikidata, no Panel | Cross-cutting / entity-optimizer | OPEN — highest priority | kg-insly.json recognized:false |
| OL-2 | Confirm founding year, founder(s), HQ + ≥2 independent refs (blocks Wikidata) | entity-optimizer | OPEN (blocking OL-1) | entity-optimization.md |
| OL-3 | Run AI resolution test (ChatGPT/Claude/Perplexity/Gemini); set ai_resolution_status | entity-optimizer | OPEN — user-to-run | entity-optimization.md |
| OL-4 | Add FAQ block + FAQPage schema to money pages | Build / schema-markup-generator + content | OPEN | content-quality-audit.md C09/O05 Fail |
| OL-5 | Add evidence/citations/data for "low-risk / fast ROI / 7–14 days" claims | Build / content-refresher | OPEN | content audit R02/R03/R04/R05 Fail |
| OL-6 | Add comparison/spec table + Key-Takeaways box on money pages | Build / content | OPEN | content audit O02/O03 Fail |
| OL-7 | Homepage has 0 H1 — add a single H1 | Optimize / on-page-seo-auditor | OPEN | onpage-home.json h1_count:0 |
| OL-8 | Duplicate URL structure /en/<slug>/ vs /<slug>/ — enforce canonical | Optimize / technical-seo-checker | OPEN | PROJECT-BRIEF #2 |
| OL-9 | ai.insly.com orphaned (in:0/out:0) — integrate into internal links + schema | Optimize / internal-linking-optimizer | OPEN | linkgraph.json |
| OL-10 | Upgrade Organization schema (sameAs + founder + SoftwareApplication) | Build / schema-markup-generator | OPEN | schema-home.json thin Org |
| OL-11 | Add author entities (bylines + Person schema) across 468-post blog | Build / entity + content | OPEN | CITE I05 Fail |
| OL-12 | Connect link database + traffic + AI monitor to replace N/A items | Monitor / setup | OPEN — data gap | CITE C/E dims N/A |
| OL-13 | Core Web Vitals unmeasured (PSI 429) — get PAGESPEED_API_KEY or GSC/CrUX | Optimize / technical-seo-checker | OPEN — data gap | psi-home.json |
| OL-14 | Establish competitor set + keyword priorities | Research / competitor-analysis + keyword-research | OPEN | not yet run |
| OL-15 | Surface third-party reviews (G2/Capterra/Trustpilot) | Cross-cutting / domain-authority | OPEN | CITE T10 Partial |

**No critical (veto) open loops.** Both auditors passed all veto checks; every open loop above is a gap or a data-availability item, not a penalty/blocker.

---

## Notes on memory hygiene
- HOT block above is within the 80-line / 25KB limit.
- Auditor handoffs (content-quality-audit.md, domain-authority-audit.md) carry `class: auditor-output` frontmatter and would archive to `memory/audits/2026-06.md`.
- Canonical entity profile draft belongs at `memory/entities/insly.md` (sole writer: entity-optimizer) — do not duplicate into the dated memory pattern.
- All Tier-1 unavailable metrics are labeled N/A/Estimated and must never be promoted as Measured.
```
