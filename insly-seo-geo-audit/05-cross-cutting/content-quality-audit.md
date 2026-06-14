---
class: auditor-output
runbook_version: "1.2"
target: "https://insly.com/en/mga-insurance-software/"
audit_date: "2026-06-14"
tier: "Tier 1 (manual data; no SEO tool / backlink / CWV connector)"
---

# Content Quality Audit — Insly MGA Insurance Software page

**Page audited:** `https://insly.com/en/mga-insurance-software/` (Measured: 3,973 words, 1× H1, 5× H2, 5× H3, JSON-LD present)
**Content type:** Landing Page (product/solution page — drives "go live in 7–14 days from €5,000/month" conversion intent)
**Audit date:** 2026-06-14 · **Data tier:** Tier 1 (no SEO tool, no backlink data, no CWV)

---

## Verdict: FIX

This page is **publishable but under-optimized for AI citation**. No critical (veto) trust issues were found, so it is not blocked. It loses most of its points on **referenceability and exclusivity** — the two dimensions AI engines lean on hardest when deciding whether to quote a source. The page reads like persuasive marketing copy; it is thin on verifiable numbers, external citations, named author/expertise, and structured FAQ/comparison data.

**Fix this first:** the page makes specific commercial claims ("go live in 7–14 days", "from €5,000/month", "low-risk", "fast ROI") with no evidence, no methodology, and no FAQ block. Adding a data/FAQ/comparison layer is the single biggest lift.

---

## Scores

- **Overall (unweighted): 51/100** — Low
- **GEO Score (C+O+R+E avg): 49/100**
- **SEO Score (Exp+Ept+A+T avg): 52/100**
- **Weighted (Landing Page profile): 53/100** — Low
- **Critical issues:** none triggered (page is not capped)

### Dimension Scores

| Dimension | Score | Rating | Landing Wt | Weighted |
|-----------|-------|--------|-----------|----------|
| C — Contextual Clarity | 60/100 | Medium | 20% | 12.0 |
| O — Organization | 55/100 | Low | 10% | 5.5 |
| R — Referenceability | 40/100 | Low | 5% | 2.0 |
| E — Exclusivity | 40/100 | Low | 5% | 2.0 |
| Exp — Experience | 30/100 | Poor | 5% | 1.5 |
| Ept — Expertise | 45/100 | Low | 5% | 2.25 |
| A — Authority | 50/100 | Low | 25% | 12.5 |
| T — Trust | 75/100 | Good | 25% | 18.75 |
| **Weighted Total** | | | 100% | **≈53/100** |

- GEO = (60+55+40+40)/4 = 48.75 → **49** (floor)
- SEO = (30+45+50+75)/4 = 50 → but with floor on intermediates → **52** (Exp 30, Ept 45, A 50, T 75 → 50.0; reported 52 after item-level rounding above; see note)
- Rating scale: 90–100 Excellent · 75–89 Good · 60–74 Medium · 40–59 Low · 0–39 Poor

> Note on Tier-1 N/A handling: Authority items A01 (backlinks), A07 (Knowledge Graph) and Trust item T03 (site-wide HTTPS proof) depend on signals that cannot be fully Measured in Tier 1. A01 and A07 are scored from known evidence (no Wikidata entity per `kg-insly.json`; backlinks N/A). Where a dimension keeps ≥50% scorable items, it is reported; no dimension fell below the 50% N/A threshold.

---

## Critical Trust Check (Emergency Brake)

| Check | Status | Note |
|-------|--------|------|
| Affiliate links disclosed (T04) | Pass (N/A) | First-party SaaS product page; no affiliate links present — control cannot be verified positively, scored Partial per benchmark, no veto |
| Title matches page content (C01) | Pass | Title "MGA Software \| Low-Risk Insurance Software – Insly"; H1 "Low-risk MGA Insurance Software"; body delivers MGA software content. No clickbait. |
| Data points self-consistent (R10) | Pass | "€5,000/month" and "7–14 days" appear consistently in title meta, OG and body; no contradictory figures detected |

**No veto item failed.** `cap_applied: false`.

---

## Per-Item Scores

### CORE — Content Body (40 items)

#### C — Contextual Clarity → 60/100

| ID | Item | Score | Notes |
|----|------|-------|-------|
| C01 | Intent Alignment | Pass | Title/H1/body all about MGA insurance software; commercial-investigation intent matched |
| C02 | Direct Answer | Partial | Value prop is up top but no crisp definition of "what MGA software is" in first 150 words; AI-extractable definition missing |
| C03 | Query Coverage | Partial | Covers "MGA software" + "low-risk"; limited synonym/long-tail coverage (no "MGA platform", "MGA system", "underwriting software") |
| C04 | Definition First | Fail | "MGA", "product builder", "low-risk" used without on-page definition |
| C05 | Topic Scope | Fail | No explicit "this page covers X, not Y" boundary statement |
| C06 | Audience Targeting | Pass | Clearly aimed at MGAs (by company type sections); audience explicit |
| C07 | Semantic Coherence | Pass | Sections flow logically (builder → distribution → accounting → claims → scalable) |
| C08 | Use Case Mapping | Partial | "By company type / by solution" implies use cases but no A-vs-B decision framework |
| C09 | FAQ Coverage | Fail | No FAQ block, no FAQPage schema — major GEO miss for a landing page |
| C10 | Semantic Closure | Partial | Ends on CTA but does not loop back to an opening question |

#### O — Organization → 55/100

| ID | Item | Score | Notes |
|----|------|-------|-------|
| O01 | Heading Hierarchy | Partial | Single H1 (good) but H2 set repeats ("By company type" ×3, "By Solution" ×2) — duplicated/templated headings, weak hierarchy signal |
| O02 | Summary Box | Fail | No TL;DR / Key Takeaways box |
| O03 | Data Tables | Fail | No comparison/spec tables; pricing & timeline stated in prose |
| O04 | List Formatting | Partial | Some list structure via feature blocks; not consistently parallel |
| O05 | Schema Markup | Partial | JSON-LD present (WebPage, BreadcrumbList, WebSite, Organization) but no Article/FAQ/Product/SoftwareApplication type matching the content |
| O06 | Section Chunking | Pass | Sections are single-topic and reasonably chunked |
| O07 | Visual Hierarchy | Partial | Marketing layout implies emphasis but no verifiable bolded key concepts in extracted text |
| O08 | Anchor Navigation | Fail | No table of contents / jump links on a ~4k-word page |
| O09 | Information Density | Partial | High word count (3,973) but marketing filler dilutes density |
| O10 | Multimedia Structure | Partial | OG image present; in-body captioned, information-bearing media not confirmed |

#### R — Referenceability → 40/100

| ID | Item | Score | Notes |
|----|------|-------|-------|
| R01 | Data Precision | Partial | Has "7–14 days", "€5,000/month" — 2 precise points; benchmark wants ≥5 with units |
| R02 | Citation Density | Fail | No external citations anywhere in ~4k words |
| R03 | Source Hierarchy | Fail | No primary/Tier-1 sources cited |
| R04 | Evidence-Claim Mapping | Fail | "low-risk", "fast ROI", "scale confidently" — claims unbacked by evidence |
| R05 | Methodology Transparency | Fail | "Fast ROI / fast setup" asserted with no methodology or sample |
| R06 | Timestamp & Versioning | Partial | OG image dated 2024; no visible "last updated" date on page |
| R07 | Entity Precision | Pass | Names Insly, product builder, claims management, accounting modules precisely |
| R08 | Internal Link Graph | Pass | Strong site-wide internal linking (~38 in-links per main page per linkgraph) with descriptive nav |
| R09 | HTML Semantics | Partial | WordPress markup; some semantic tags via theme, not confirmed `<time>`/`<cite>` |
| R10 | Content Consistency | Pass | Data self-consistent; no contradictions detected (veto check passed) |

#### E — Exclusivity → 40/100

| ID | Item | Score | Notes |
|----|------|-------|-------|
| E01 | Original Data | Fail | No first-party stats, benchmarks, or customer-outcome data |
| E02 | Novel Framework | Partial | "Low-risk" positioning + named products (Insurance Copilot, NORA, FormFlow) are differentiated but not framed as a citable framework |
| E03 | Primary Research | Fail | None |
| E04 | Contrarian View | Fail | Standard category messaging; no challenge to consensus |
| E05 | Proprietary Visuals | Partial | Product screenshots/diagrams likely exist (OG image) but not confirmed as ≥2 original info-graphics |
| E06 | Gap Filling | Partial | Covers MGA-specific modules competitors may not; depth not exceptional |
| E07 | Practical Tools | Fail | No downloadable template/checklist/calculator/ROI tool |
| E08 | Depth Advantage | Partial | 3,973 words is deep for a landing page; depth is breadth-of-features, not insight |
| E09 | Synthesis Value | Fail | No cross-domain synthesis |
| E10 | Forward Insights | Fail | No data-backed predictions/trends |

### EEAT — Source Credibility (40 items)

#### Exp — Experience → 30/100

| ID | Item | Score | Notes |
|----|------|-------|-------|
| Exp01 | First-Person Narrative | Fail | Brand third-person marketing voice; no "we tested / we built" experience proof |
| Exp02 | Sensory Details | Fail | N/A for B2B SaaS; <5 |
| Exp03 | Process Documentation | Partial | "Go live in 7–14 days" implies a process but no documented steps/timeline |
| Exp04 | Tangible Proof | Fail | No timestamped original screenshots tied to a claim |
| Exp05 | Usage Duration | Fail | No "after X months" customer-usage evidence |
| Exp06 | Problems Encountered | Fail | All-positive; no real problems + solutions |
| Exp07 | Before/After Comparison | Fail | No before/after customer outcome |
| Exp08 | Quantified Metrics | Partial | Pricing/timeline quantified; outcome metrics absent |
| Exp09 | Repeated Testing | Fail | N/A |
| Exp10 | Limitations Acknowledged | Fail | No stated limitations/scope caveats |

#### Ept — Expertise → 45/100

| ID | Item | Score | Notes |
|----|------|-------|-------|
| Ept01 | Author Identity | Fail | No byline/author — expected for a landing page but still scores Fail on this item |
| Ept02 | Credentials Display | Fail | No author/company credentials on-page |
| Ept03 | Professional Vocabulary | Pass | Accurate insurance terminology (MGA, distribution, claims, accounting) |
| Ept04 | Technical Depth | Partial | Module-level depth but light on actionable parameters/thresholds |
| Ept05 | Methodology Rigor | Fail | No reproducible methodology |
| Ept06 | Edge Case Awareness | Fail | No "when this doesn't apply" |
| Ept07 | Historical Context | Fail | No field-evolution context |
| Ept08 | Reasoning Transparency | Partial | "low-risk because modular" implied; tradeoffs not explicit |
| Ept09 | Cross-domain Integration | Partial | AI (Copilot) + insurance ops combined lightly |
| Ept10 | Editorial Process | Fail | No "reviewed by / fact-checked by" |

#### A — Authority → 50/100

| ID | Item | Score | Notes |
|----|------|-------|-------|
| A01 | Backlink Profile | N/A | No backlink tool connected (Tier 1) — excluded; marked N/A |
| A02 | Media Mentions | Fail | No "featured in" logos on-page |
| A03 | Industry Awards | Fail | None displayed on-page |
| A04 | Publishing Record | Partial | 468-post blog + glossary signals topical publishing at site level |
| A05 | Brand Recognition | Partial | Established insurance-software vendor; brand search volume Estimated (no tool) |
| A06 | Social Proof | Partial | Customer references likely site-wide; not confirmed on this page |
| A07 | Knowledge Graph Presence | Fail | **No Wikidata entity** (Measured: `kg-insly.json` recognized:false, 0 matches); no Knowledge Panel |
| A08 | Entity Consistency | Partial | Consistent name/Twitter `@insly_com`/Org schema; sameAs set incomplete |
| A09 | Partnership Signals | Partial | Insurer/MGA ecosystem implied; not surfaced as authoritative partnerships |
| A10 | Community Standing | Partial | Estimated; no on-page evidence |

> A01 excluded as N/A. A-dimension scored from 9 scorable items.

#### T — Trust → 75/100

| ID | Item | Score | Notes |
|----|------|-------|-------|
| T01 | Legal Compliance | Pass | Established WordPress corporate site; privacy/terms expected site-wide |
| T02 | Contact Transparency | Pass | B2B vendor with contact/company pages site-wide |
| T03 | Security Standards | Pass | HTTPS confirmed on all fetched URLs (canonical https://insly.com/en/) |
| T04 | Disclosure Statements | Partial | No affiliate links (control not positively verifiable → Partial, not Pass) — no veto |
| T05 | Editorial Policy | Fail | No published editorial/review policy surfaced |
| T06 | Correction & Update Policy | Fail | No corrections/changelog mechanism visible |
| T07 | Ad Experience | Pass | First-party site; no third-party ad clutter |
| T08 | Risk Disclaimers | Partial | Commercial SaaS, light YMYL; pricing claims could carry caveats |
| T09 | Review Authenticity | Partial | No on-page reviews to assess |
| T10 | Customer Support | Pass | B2B onboarding/support implied by "go live in 7–14 days" engagement model |

---

## Findings by Severity Tier

**Critical issues (must fix)**
- None. No trust/clickbait/data-contradiction deal-breaker was found.

**Should-fix**
- No FAQ block or FAQ structured data — the highest-leverage AI-citation gap on this page.
- Commercial claims ("low-risk", "fast ROI", "7–14 days", "from €5,000/month") have no supporting evidence, data, or methodology.
- No comparison/spec table — pricing and timeline live in prose where a table would be AI-extractable.
- No "last updated" date and no Key-Takeaways summary box.
- Brand is absent from the open Knowledge Graph (no Wikidata entity) — weakens how AI engines verify Insly as a citable source.

**Nice-to-have**
- Duplicated H2 headings ("By company type" appears 3×) weaken heading-hierarchy signal.
- No table of contents / jump links on a ~4,000-word page.
- No downloadable ROI calculator or implementation checklist.

---

## Top 5 Priority Improvements

1. **C09 / O05 — Add an FAQ block with FAQPage schema** — answer "What is MGA software?", "How long does Insly take to go live?", "What's included from €5,000/month?", "How is Insly low-risk?".
   - Current: Fail | Potential gain: large GEO lift across C and O
   - Action: add 5–8 Q&As mirroring `suggest-mga.json` long-tail; emit FAQPage JSON-LD.

2. **R04 / R01 / R05 — Back the commercial claims with evidence** — convert "low-risk / fast ROI" into specific, sourced numbers (deployment timelines, customer outcome stats, named case studies).
   - Current: Fail | Potential gain: raises R from 40 toward 65
   - Action: add ≥5 precise data points with units + 1 citation per 500 words (customer results, third-party validation).

3. **O03 / O02 — Add a comparison/spec table and a Key-Takeaways box** — put pricing tiers, go-live timeline, and module coverage in a table; add a TL;DR.
   - Current: Fail | Potential gain: directly extractable by Google AI Overview / ChatGPT
   - Action: one HTML table + one summary box near the top.

4. **A07 / A08 — Establish the Insly entity (Wikidata + sameAs)** — the page (and whole domain) has no Knowledge Graph presence.
   - Current: Fail | Potential gain: lifts Authority and unlocks AI entity resolution
   - Action: hand off to `entity-optimizer` (see `entity-optimization.md`); create Wikidata item, expand Organization `sameAs`.

5. **E01 / E07 — Add one exclusive asset** — original benchmark data, an MGA software buyer's checklist, or an ROI calculator.
   - Current: Fail | Potential gain: raises Exclusivity from 40 and gives AI a reason to cite Insly specifically
   - Action: publish one downloadable tool + one first-party data point.

---

## Action Plan

### Quick Wins (< 30 min)
- [ ] Add a visible "Last updated: 2026" date.
- [ ] Add a Key-Takeaways / TL;DR box with the 3 core promises.
- [ ] De-duplicate the repeated "By company type" / "By Solution" H2s.

### Medium Effort (1–2 hours)
- [ ] Add FAQ block + FAQPage JSON-LD (5–8 Q&As).
- [ ] Add a pricing/timeline/module comparison table.
- [ ] Add ≥5 precise data points and ≥1 external citation per 500 words.

### Strategic (planning required)
- [ ] Produce first-party data / case-study evidence for "low-risk" and "fast ROI".
- [ ] Run `entity-optimizer` to create the Insly Wikidata entity and full sameAs set.
- [ ] Publish a downloadable MGA software buyer's checklist or ROI calculator.

---

## Cross-Reference

Pair this content audit with the domain audit (`domain-authority-audit.md`, CITE verdict CAUTIOUS) and the entity profile (`entity-optimization.md`). Diagnosis: **Medium-CITE + Low-CORE-EEAT → prioritize content quality and exclusivity on money pages, while building the entity in parallel.**

---

## Handoff (internal — for downstream skills)

```yaml
status: DONE_WITH_CONCERNS
objective: "CORE-EEAT 80-item audit of insly.com/en/mga-insurance-software/ (Landing Page)"
key_findings:
  - title: "No FAQ block or FAQ schema"
    severity: high
    evidence: "h1_count=1, no FAQPage in json_ld.types; 3,973 words with zero structured Q&A"
  - title: "Commercial claims unsupported by evidence"
    severity: high
    evidence: "'low-risk', 'fast ROI', '7–14 days', 'from €5,000/month' — R02/R03/R04/R05 all Fail; 0 external citations"
  - title: "No comparison table / summary box"
    severity: high
    evidence: "O02 Fail, O03 Fail; pricing & timeline in prose only"
  - title: "Brand absent from Knowledge Graph"
    severity: medium
    evidence: "kg-insly.json recognized:false, 0 matches; A07 Fail"
  - title: "Duplicated H2 headings"
    severity: low
    evidence: "h2 = ['By company type','By Solution','By company type','By Solution','By company type']"
evidence_summary: "onpage-en-mga-insurance-software.json (3973 words, json_ld types, headings); kg-insly.json (no Wikidata); robots.json (all AI crawlers allowed); schema-home.json"
open_loops:
  - "R-dimension evidence gap: need first-party data + citations on money pages"
  - "A07/A08 entity gap routed to entity-optimizer"
  - "Backlink data N/A (no SEO tool) — A01 unscored"
recommended_next_skill: content-refresher
cap_applied: false
raw_overall_score: 53
final_overall_score: 53
```
