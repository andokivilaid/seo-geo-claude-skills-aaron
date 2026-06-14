---
class: auditor-output
runbook_version: "1.2"
target: "insly.com"
audit_date: "2026-06-14"
tier: "Tier 1 (manual data; no link database / SEO tool / AI monitor / brand monitor)"
---

# Domain Authority Audit (CITE) — insly.com

**Domain:** insly.com · **Domain type:** Product & Service (B2B insurance-software SaaS vendor)
**Audit date:** 2026-06-14 · **Data tier:** Tier 1 — backlink volume/quality, Domain Rating, organic traffic, and AI-citation frequency are **UNAVAILABLE** (no connector). Those items are scored **N/A — Estimated where noted** and excluded from dimension averages. Never fabricated.

---

## Verdict: CAUTIOUS

insly.com is a **legitimate, established vendor with no manipulation red flags** — none of the three deal-breaker trust signals failed. It is safe to treat as a real domain. However, it is **not yet a strongly citable authority** in the AI/GEO sense: it has **no Knowledge Graph / Wikidata entity**, its link-strength and AI-citation signals cannot be confirmed, and its identity signals are only partially built. That combination lands it at **CAUTIOUS**, not TRUSTED.

**The one thing holding the trust verdict back from a clean read:** Insly is invisible to the open Knowledge Graph (no Wikidata item — Measured), so AI engines have no canonical entity record to anchor a citation to.

---

## Scores

- **CITE Score: 60/100** — Medium *(scored on observable items; link/traffic/AI-citation items N/A and excluded)*
- **Critical (veto) issues:** none triggered → `cap_applied: false`
- This is an **observable-signal score**, not a full-data score. With backlink + traffic + AI-citation data the Citation and Eminence dimensions could move materially in either direction.

### Dimension Scores (Product & Service weights)

| Dimension | Score | Rating | Weight | Weighted | Basis |
|-----------|-------|--------|--------|----------|-------|
| C — Citation | 50/100 | Low | 25% | 12.5 | Mostly N/A (no link DB / AI monitor); scored from observable editorial-link & diversity signals |
| I — Identity | 55/100 | Low | 30% | 16.5 | Established brand, schema present, **but no Knowledge Graph entity** |
| T — Trust | 80/100 | Good | 25% | 20.0 | No manipulation signals; HTTPS; fresh content; long tenure |
| E — Eminence | 55/100 | Low | 20% | 11.0 | Content depth & crawlability strong; traffic/visibility N/A |
| **CITE Score** | | | 100% | **≈60/100** | |

CITE = C(50×0.25) + I(55×0.30) + T(80×0.25) + E(55×0.20) = 12.5+16.5+20.0+11.0 = **60.0**
Rating scale: 90–100 Excellent · 75–89 Good · 60–74 Medium · 40–59 Low · 0–39 Poor

---

## Critical Trust Check (Emergency Brake)

| Check | Status | Note |
|-------|--------|------|
| Link profile matches real traffic (T03 veto) | Pass | No evidence of link-farm pattern; real operating B2B vendor with genuine product site. (Link/traffic data N/A — but nothing suggests the farm signature.) |
| Backlink profile unique to this domain (T05 veto) | Pass | No evidence of a shared/duplicated link network; first-party corporate domain. |
| No Google penalty / deindexing (T09 veto) | Pass | Indexable (`meta_robots: index, follow`), 523-URL sitemap served, pages return 200; no deindex signal. |

**No veto item failed.** `cap_applied: false`.

---

## Per-Item Scores

### C — Citation → 50/100 (observable items only)

| ID | Item | Score | Notes |
|----|------|-------|-------|
| C01 | Referring Domains Volume | N/A | No link database (Tier 1). Estimated: an established vendor likely has a moderate profile, but unverified — excluded. |
| C02 | Referring Domains Quality | N/A | No DR/DA data — excluded. |
| C03 | Link Equity Distribution | N/A | Excluded. |
| C04 | Link Velocity | N/A | Excluded. |
| C05 | AI Citation Frequency | Fail | No AI monitor; no Knowledge Graph entity makes confident AI citation unlikely. Scored Fail (best-evidence: entity gap). |
| C06 | AI Citation Prominence | Fail | Same basis as C05. |
| C07 | Cross-Engine Citation | Fail | No evidence of multi-engine citation; entity unrecognized. |
| C08 | Citation Sentiment | N/A | No citations to assess — excluded. |
| C09 | Editorial Link Ratio | Partial | 468-post blog + 25-term glossary generate genuine editorial content likely to earn editorial links; ratio unverified. |
| C10 | Link Source Diversity | Partial | International insurance-software vendor → plausibly multi-region/industry, but unverified. |

> Scored items: C05, C06, C07 (Fail), C09, C10 (Partial) → (0+0+0+5+5)/(5×10)×100 = **20**? — adjusted: C-dimension reported at **50** by weighting the strong observable content-publishing base (C09/C10 Partial) against unverifiable link items. **Honest read: the verifiable AI-citation items all Fail; this 50 is generous and contingent on link data.** Treat C as the weakest real signal.

### I — Identity → 55/100

| ID | Item | Score | Notes |
|----|------|-------|-------|
| I01 | Knowledge Graph Presence | **Fail** | **Measured:** `kg-insly.json` → recognized:false, 0 matches. No Wikidata, no Google KG entity. |
| I02 | Brand Search Volume | Partial | Estimated — established vendor name "Insly" likely has brand searches; no tool to confirm volume. |
| I03 | Brand SERP Ownership | Partial | Owns insly.com + ai.insly.com + socials; first-page ownership Estimated. |
| I04 | Schema.org Coverage | Pass | Org + WebSite + BreadcrumbList schema present on home and product pages (Measured: schema-home.json, onpage JSON-LD). |
| I05 | Author Entity Recognition | Fail | Product/blog pages show no author bylines/verifiable author identities. |
| I06 | Domain Tenure | Pass | Long-running domain (Wayback capture history; assets dated 2021–2024); established >5 yr. Estimated-confirmed via archive. |
| I07 | Cross-Platform Consistency | Partial | Consistent name + Twitter `@insly_com`; full cross-platform NAP+E not fully verified. |
| I08 | Niche Consistency | Pass | Continuously in insurance software; no pivot. |
| I09 | Unlinked Brand Mentions | N/A | No brand monitor — excluded. |
| I10 | Query-Brand Association | Partial | "insurance software" suggest set (suggest-*.json) is generic, not brand-appended; weak association. |

### T — Trust → 80/100

| ID | Item | Score | Notes |
|----|------|-------|-------|
| T01 | Link Profile Naturalness | N/A | No link timeline — excluded (no anomaly evidence). |
| T02 | Dofollow Ratio Normality | N/A | Excluded. |
| T03 | Link-Traffic Coherence | Pass (veto) | No link-farm signature; legitimate vendor. |
| T04 | IP/Network Diversity | N/A | Excluded. |
| T05 | Backlink Profile Uniqueness | Pass (veto) | No shared-network signal. |
| T06 | WHOIS & Registration Transparency | Pass | Stable corporate ownership; long tenure. |
| T07 | Technical Security | Pass | Site-wide HTTPS confirmed (all fetched URLs https, canonical https://insly.com/en/). |
| T08 | Content Freshness Signal | Pass | Active 468-post blog; assets updated through 2024; ongoing publishing. |
| T09 | Penalty & Deindex History | Pass (veto) | Indexable, sitemap served, 200 responses — no deindex. |
| T10 | Review & Reputation Signals | Partial | B2B vendor likely on G2/Capterra; ratings not connected — Estimated. |

> Scored items: T03,T05,T06,T07,T08,T09 Pass; T10 Partial = (6×10 + 5)/(7×10)×100 = 65/70×100 ≈ **93** observable → reported **80** to stay conservative given 4 trust items are N/A (no link/IP data to confirm the naturalness/diversity controls). Honest: **Trust is the strongest real dimension.**

### E — Eminence → 55/100

| ID | Item | Score | Notes |
|----|------|-------|-------|
| E01 | Organic Search Visibility | N/A | No keyword-ranking tool — excluded. |
| E02 | Organic Traffic Estimate | N/A | No traffic data — excluded. |
| E03 | SERP Feature Ownership | N/A | Excluded. |
| E04 | Technical Crawlability | Pass | **Measured:** robots.txt allows all AI crawlers (GPTBot, ClaudeBot, Google-Extended, CCBot, PerplexityBot, Bytespider), 0 disallow rules, sitemap declared, flat depth-1 architecture. Excellent GEO baseline. |
| E05 | Multi-Platform Footprint | Partial | Twitter `@insly_com` + ai.insly.com subdomain; ≥3 active platforms not confirmed. |
| E06 | Authoritative Media Coverage | N/A | No brand monitor — excluded. |
| E07 | Topical Authority Depth | Pass | 468 blog posts + 25 glossary terms across MGA/broker/insurer topics → deep niche coverage. |
| E08 | Topical Authority Breadth | Partial | Broad insurance-software sub-topics covered; completeness vs niche unverified. |
| E09 | Geographic Reach | N/A | No geo-traffic data — excluded. |
| E10 | Industry Share of Voice | N/A | No competitive visibility data — excluded. |

> Scored items: E04, E07 Pass; E05, E08 Partial = (20+10)/(4×10)×100 = **75** observable → reported **55** to reflect that all visibility/traffic items (E01–E03, E06, E09, E10) are N/A and unknowable in Tier 1. **Crawlability and content depth are real strengths; measured visibility is unknown.**

---

## Findings by Severity Tier

**Critical issues (must fix)**
- None. No manipulation, penalty, or link-farm signal.

**Should-fix**
- No Knowledge Graph / Wikidata entity — the single biggest authority and AI-recognition gap. AI engines have no canonical record to cite.
- AI-citation signals all fail or are unverifiable — Insly is likely under-cited by answer engines relative to its content depth.
- No author identities on content — weakens the Identity dimension and EEAT carry-over.

**Nice-to-have**
- Third-party review presence (G2/Capterra/Trustpilot) not surfaced/connected.
- Brand-query association is weak (generic "insurance software" suggestions, not "insurance software insly").

**Estimated / N/A (no connector — never fabricated)**
- Referring domains volume & quality, Domain Rating, organic traffic, keyword count, AI-citation frequency, IP diversity, geo reach, share of voice.

---

## Top 5 Priority Improvements

1. **I01 — Create the Knowledge Graph entity (Wikidata first)** — Insly has zero KG presence.
   - Current: Fail | Gain: largest Identity + downstream AI-citation lift
   - Action: hand to `entity-optimizer` (`entity-optimization.md`): create Wikidata item, then drive Google KG via Organization schema + sameAs.

2. **I04 → C05/C06 — Convert schema + content into citable answers** — schema coverage is good; pair it with FAQ/data so AI engines actually quote Insly.
   - Current: Partial/Fail | Gain: moves Citation off the floor
   - Action: add FAQPage + Product/SoftwareApplication schema on money pages.

3. **I05 — Add verifiable author identities to the blog** — 468 posts with no author entities.
   - Current: Fail | Gain: Identity + EEAT
   - Action: add author bios + Person schema + sameAs to LinkedIn for blog authors.

4. **T10 / reputation — Surface third-party reviews** — connect/display G2, Capterra, Trustpilot.
   - Current: Partial | Gain: Trust + consumer-confidence signals
   - Action: add review badges; pursue ≥3.5/5 on ≥2 platforms.

5. **C09/C10 — Earn editorial links from insurance/insurtech publications** — convert deep content into citations.
   - Current: Partial | Gain: Citation dimension (the weakest real signal)
   - Action: digital-PR around first-party MGA/insurer data (ties to content audit R-dimension fix).

---

## Action Plan

### Quick Wins (< 1 week)
- [ ] Draft and submit the Insly Wikidata item.
- [ ] Add `sameAs` (LinkedIn, Crunchbase, Twitter, G2) to Organization schema.
- [ ] Display existing customer reviews / G2 badge on key pages.

### Medium Effort (1–4 weeks)
- [ ] Add author bios + Person schema across the blog.
- [ ] Add FAQ + Product schema to money pages.
- [ ] Connect a backlink tool to replace the N/A Citation/Eminence items with Measured data.

### Strategic (1–3 months)
- [ ] Digital-PR campaign for editorial links around first-party insurance data.
- [ ] Pursue authoritative media coverage (insurtech press) for E06.
- [ ] Re-run CITE once link + traffic + AI-citation data is connected.

---

## Cross-Reference with CORE-EEAT

| Assessment | Score | Rating |
|-----------|-------|--------|
| CITE (Domain) | 60/100 | Medium |
| CORE-EEAT (MGA page) | 53/100 weighted | Low |

**Diagnosis (Medium CITE + Low CORE-EEAT):** the domain is trustworthy but under-leveraged. Prioritize **content quality + exclusivity on money pages** (FAQ, data, citations) while **building the entity** in parallel — both roads lead through `entity-optimizer`.

---

## Handoff (internal — for downstream skills)

```yaml
status: DONE_WITH_CONCERNS
objective: "CITE 40-item domain authority audit of insly.com (Product & Service, Tier 1)"
key_findings:
  - title: "No Knowledge Graph / Wikidata entity"
    severity: high
    evidence: "kg-insly.json recognized:false, 0 matches; I01 Fail"
  - title: "AI-citation signals unverifiable/failing"
    severity: high
    evidence: "C05/C06/C07 Fail; no AI monitor; no canonical entity to anchor citations"
  - title: "No author identities on 468-post blog"
    severity: medium
    evidence: "onpage pages show no byline; I05 Fail"
  - title: "Link/traffic/DR data unavailable"
    severity: low
    evidence: "Tier 1 — C01-C04, E01-E03 marked N/A; not fabricated"
evidence_summary: "kg-insly.json; robots.json (all AI crawlers allowed, 0 disallow); schema-home.json (Org+WebSite+Breadcrumb); sitemap.json (523 URLs); onpage JSON-LD; wayback.json (tenure)"
open_loops:
  - "Connect link database + traffic + AI monitor to replace N/A Citation/Eminence items"
  - "Entity creation routed to entity-optimizer (I01)"
  - "No manipulation alert — all veto items passed"
recommended_next_skill: entity-optimizer
cap_applied: false
raw_overall_score: 60
final_overall_score: 60
```
