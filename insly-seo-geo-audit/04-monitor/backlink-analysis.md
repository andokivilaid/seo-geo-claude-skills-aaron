# Backlink Analysis — Framework & Domain-Authority Signal

**Skill:** `monitor/backlink-analyzer` · **Domain:** insly.com · **Date:** 2026-06-14
**Mode:** Tier 1 (no backlink tool / link database connected)

> **Critical — Decision Gate triggered:** No backlink data is provided and no ~~link database (Ahrefs / Semrush / Majestic) is connected. Per the skill contract, **referring-domain and backlink counts cannot be measured and are marked N/A. They are NOT estimated from the domain alone.** This file delivers the *analysis framework, criteria, and method* so the moment a link export or tool is connected, the analysis runs immediately. The one authority signal available in-repo — Open PageRank — also needs a free key that is **not present in this environment**, so even that is N/A today (see §5).

---

## 1. Profile overview (framework — values pending data)

| Metric | Value | Source | CITE item |
|--------|-------|--------|-----------|
| Referring domains | **N/A** | needs ~~link database | C01 |
| Total backlinks | **N/A** | needs ~~link database | — |
| Dofollow / nofollow ratio | **N/A** | needs ~~link database | T02 |
| Authority distribution (DA buckets) | **N/A** | needs ~~link database | C02 |
| Link velocity (new RDs / month) | **N/A** | needs time-series export | C04 |
| Geographic distribution | **N/A** | needs ~~link database | C10 |
| Toxic-link ratio | **N/A** (compute once data lands) | derived | T01, T03 |
| Profile health score | **N/A** | derived | — |

**Internal-link context (Measured, for contrast — NOT backlinks):** the 40-page crawl shows a flat, well-linked *internal* graph (every main page ~38 internal in-links, max depth 1; `linkgraph.json`). This is internal architecture only and says nothing about external authority. `ai.insly.com` is orphaned (in:0/out:0) — a separate subdomain that, if it earns external links, would not pass equity into the main domain.

---

## 2. What to pull (the moment a tool/export is connected)

1. **Referring domains export** — domain, first-seen, last-seen, DR/DA, dofollow flag, anchor, target URL.
2. **Backlinks export** — full URL-level list for anchor and target-page analysis.
3. **Lost/new links time-series** — for link velocity (C04) and the "Track Link Changes" step.
4. **Competitor referring-domain exports** — for the link-gap intersection (§4).
5. **Anchor-text distribution** — branded vs exact-match vs naked-URL vs generic.

Respect `robots.txt`/TOS on any direct fetching. insly.com robots.txt has 0 disallow rules (Measured), so crawl-permission is not a constraint.

---

## 3. Toxic-link criteria (apply when data arrives)

Flag a referring domain as **toxic / review** if it shows any of:

| Signal | Threshold / rule |
|--------|------------------|
| Exact-match commercial anchor over-rep | >20% of anchors are exact "insurance software / mga software" type → unnatural (T01) |
| Link-traffic incoherence | Referring domain has high link count but ~0 organic traffic (PBN signal, T03) |
| Spam TLD / language mismatch | Links from unrelated-language or known-spam TLD farms to an EN B2B SaaS |
| Sitewide footer/template links | Single domain contributing hundreds of sitewide links |
| Low-quality directories / link schemes | Paid-link footprints, "add your link" farms |
| Dofollow ratio anomaly | Near-100% dofollow exact-match from low-DA sources (T02) |

**Toxic ratio = (toxic referring domains ÷ total referring domains).** Action rule from the skill: if toxic ratio **>15%**, escalate to `domain-authority-auditor` for formal CITE veto scoring (T01/T03/T05) and prepare a disavow file. Disavow cautiously — domain-level, only clearly manipulative sources.

---

## 4. Competitor link-gap method

Goal: find referring domains linking to competitors but **not** to Insly = warmest prospects.

1. Pull RD exports for Insly + top 3 category competitors (suggested: **Applied Systems, Vertafore, Novidea**; add Duck Creek / Guidewire for enterprise).
2. Build the intersection matrix: domains linking to ≥2 competitors but **0** links to insly.com.
3. Rank prospects by: links-to-N-competitors (3 > 2), referring-domain authority, topical relevance (insurtech / MGA / broker media, insurance trade press, review sites like G2/Capterra/SoftwareAdvice).
4. Map each prospect to an outreach angle: review-site listing, broken-link reclaim, unlinked brand mention, guest post, resource-page inclusion.
5. **Priority pre-targets even before tool data** (clear category fits to claim): **G2, Capterra, GetApp, SoftwareAdvice** (B2B SaaS review directories), **insurance trade press** (Insurance Business, Insurance Times, Reinsurance News), and **insurtech ecosystem lists**. These are deterministic wins regardless of competitor export.

---

## 5. Available authority signal: Open PageRank

Open PageRank (`scripts/connectors/openpagerank.py`) is the one keyless-ish domain-authority proxy in the repo (0–10 score + global rank). **Status today: N/A** — the connector ran but requires a free `OPENPAGERANK_API_KEY` that is not set in this environment:

```
$ python3 openpagerank.py insly.com applied.com vertafore.com duckcreek.com guidewire.com novidea.com
→ error: missing_api_key  (register free at https://www.domcop.com/openpagerank/)
```

**To activate (free, no payment):** register a key, then:
```bash
export OPENPAGERANK_API_KEY=YOUR_KEY
python3 scripts/connectors/openpagerank.py insly.com applied.com vertafore.com novidea.com duckcreek.com guidewire.com
```
This returns a relative 0–10 authority score + global rank for Insly vs competitors — a directional benchmark (feeds CITE C02 context) until a full backlink tool is connected. It does **not** return referring-domain counts; those remain N/A.

---

## 6. Link-building opportunities (framework, not yet data-validated)

| Opportunity | Effort | Impact | Notes |
|-------------|--------|--------|-------|
| B2B review directories (G2/Capterra/GetApp/SoftwareAdvice) | Low | High | High-authority, category-relevant, drive demos |
| Unlinked brand mentions ("Insly", "Socrates Systems") | Low | Med | Reclaim once tool surfaces mentions |
| Competitor link intersection (§4) | Med | High | Needs competitor RD export |
| Insurtech / MGA trade-press features & PR | Med | High | Insly already has `/en/press-releases/` + `/en/insly-in-the-media/` to seed |
| Broken-link reclaim on resource pages | Med | Med | Needs broken-link export |
| Customer case-study co-marketing links | Low | Med | Existing customer stories (Accelerate, Ridge Canada, Alta Signa) → request partner backlinks |

---

## Handoff Summary

- **Objective:** Build the backlink-analysis framework for insly.com (what to pull, toxic criteria, competitor link-gap method, authority signal) with no link tool connected.
- **Key findings:** All referring-domain/backlink/anchor/toxic metrics are **N/A** (Tier 1 gate); not estimated. Open PageRank — the one available authority proxy — is also N/A pending a free key. Deterministic link wins exist now regardless of tooling: B2B review directories + insurtech trade press + customer co-marketing. `ai.insly.com` is an orphaned subdomain whose external links would not flow to the main domain.
- **Evidence:** linkgraph.json (internal-only graph + orphan), robots.json (0 disallow), openpagerank.py run output (missing_api_key), PROJECT-BRIEF.
- **Open loops → `memory/open-loops.md`:** Connect a backlink tool (or paste an RD export) to convert all N/A to Measured; set `OPENPAGERANK_API_KEY` for the directional authority benchmark; claim G2/Capterra/GetApp listings.
- **Status:** DONE_WITH_CONCERNS (framework complete; no backlink data measurable in Tier 1).
- **Next skill:** `domain-authority-auditor` — run CITE scoring once a referring-domain export exists (and immediately if toxic ratio later computes >15%).
