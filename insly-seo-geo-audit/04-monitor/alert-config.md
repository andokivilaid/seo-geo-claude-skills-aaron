# Alert Configuration — Insly

**Skill:** `monitor/alert-manager` · **Domain:** insly.com · **Date:** 2026-06-14
**Mode:** Tier 1 (no GSC / GA4 / SEO tool connected) · **Baseline:** none yet

> **Critical — Decision Gate.** No baseline or normal-volatility reference exists for ranking/traffic metrics (nothing is connected). Per the skill, thresholds set against a non-existent baseline are **Estimated defaults**, not tuned values. This file pre-configures the alert system so it **arms automatically once each connector is attached and a 2–4 week baseline accrues**. Each alert is tagged with the connector it requires; alerts whose metric is N/A today are **staged (inactive)** until that connector exists.

---

## 1. Alert categories & connector dependency

| Category | Status today | Connector required to activate |
|----------|--------------|--------------------------------|
| Rankings | **Staged** (positions N/A) | Google Search Console (or SEO tool) |
| Organic traffic | **Staged** (traffic N/A) | GA4 |
| Technical / indexing | **Partially active** | Repo crawl/robots/sitemap connectors (re-runnable now); GSC Coverage for full |
| Backlinks | **Staged** (links N/A) | Backlink tool / link database |
| Competitors | **Staged** | SEO tool (SoV) |
| GEO / AI visibility | **Partially active** (manual) | AI-monitor (or manual prompt log) |
| Brand / security | **Partially active** | GSC Security & Manual Actions; brand-mention monitor |

---

## 2. Alert rules by category (thresholds Estimated until baseline accrues)

### Rankings — *needs GSC*
| Alert | Trigger | Threshold | Priority |
|-------|---------|-----------|----------|
| Money-term position drop | Tier A keyword (mga/insurance/broker software) drops | **>3 positions** WoW | High |
| Money-term page-1 exit | Tier A keyword falls off page 1 | crosses pos 10→11+ | **Critical** |
| Brand-term defence | "insly" not ranked #1 | any drop from #1 | **Critical** |
| Position gain | Tier A keyword improves | >3 positions | Low (document/replicate) |

### Organic traffic — *needs GA4*
| Alert | Threshold (Warning / Critical) | Priority |
|-------|-------------------------------|----------|
| Sitewide organic drop | **-15% / -30% WoW** | High / Critical |
| Money-page traffic drop | product page -20% WoW | High |
| Demo/contact conversion drop | -25% WoW (once goals configured) | **Critical** |

### Technical / indexing — *partially active now via repo connectors*
| Alert | Threshold | Priority | Source today |
|-------|-----------|----------|--------------|
| Indexed pages drop | **-5% / -20%** | High / Critical | GSC Coverage (sitemap=523 baseline, Measured) |
| New crawl errors | >10/day warn, >50/day critical | High | crawl connector (re-runnable) |
| robots.txt change | **AI bot or `*` flips to Disallow**, or sitemap line removed | **Critical** | robots.py (Measured: 0 disallow today) |
| Homepage H1 regression | H1 count stays 0 / drops on any money page | High | onpage.py (Measured: home=0 H1 — **already breached**) |
| Canonical/duplication drift | new `/`-vs-`/en/` dupes or canonical change on money pages | High | onpage/crawl |
| New orphan pages | orphan count rises above 4 baseline | Med | linkgraph.py (Measured: 4 + ai.insly.com) |
| Core Web Vitals | "Needs Improvement" warn / "Poor" critical | Med | **N/A today — needs PAGESPEED_API_KEY or GSC/CrUX** |
| Sitemap availability | `/en/sitemap_index.xml` 404/5xx | **Critical** | sitemap.py |

### Backlinks — *needs backlink tool*
| Alert | Threshold | Priority |
|-------|-----------|----------|
| Referring domains lost | -5% warn / -15% critical in 1 week | High |
| Toxic-link spike | toxic ratio crosses 15% | High → trigger domain-authority-auditor |
| Authority signal drop | OpenPageRank score falls ≥1 point | Med (needs OPENPAGERANK_API_KEY) |

### GEO / AI visibility — *manual now, AI-monitor for automation*
| Alert | Threshold | Priority |
|-------|-----------|----------|
| AI citation loss (key query) | Insly drops from a ChatGPT/Perplexity/AIO answer it previously held | High |
| AI citation broad loss | lost on >20% of tracked AI prompts | **Critical** |
| Wikidata/KG entity status | entity created (recognized flips false→true) | Med (positive milestone — `kg.py`, Measured: false today) |
| New AI bot blocked | any AI crawler newly disallowed in robots.txt | High (overlaps technical) |

### Brand / security — *GSC + brand monitor*
| Alert | Threshold | Priority |
|-------|-----------|----------|
| Manual action / security issue | any detected | **Critical** (daily) |
| Negative brand SERP / unlinked mention spike | qualitative | Med |

---

## 3. Response plan (Critical / High / Medium / Low)

| Severity | Response time | Action |
|----------|---------------|--------|
| **Critical** | Same day | Page owner; full diagnostic (technical + content + links); root-cause before fix. E.g. page-1 exit on a money term, robots.txt AI-bot block, security issue, sitemap down. |
| **High** | Within 1 week | Investigate: check recent deploys, competitor moves, algo updates; corroborate observed change before naming a cause. |
| **Medium** | Within 2 weeks | Log, monitor for persistence, batch into next review. |
| **Low** | Next review | Document wins; identify what worked to replicate. |

---

## 4. Alert delivery & routing

| Setting | Value |
|---------|-------|
| Default channel | **Email** (no channel in context; per Decision Gate, default to email and note it) |
| Critical routing | Email **+ Slack** (if Slack MCP connected) to SEO + web-dev owners |
| Cooldown | 24h per alert key (prevent re-fire spam) |
| Maintenance window | Suppress technical alerts during planned deploys |
| Escalation | Critical unacknowledged in 4h → escalate to SEO lead |
| Digest | Weekly Mon AM summary of Medium/Low |

---

## 5. Connector → alert activation map (the unlock list)

| Connect | Activates |
|---------|-----------|
| **Google Search Console** | All Rankings alerts; Indexed-pages; CWV (via CrUX); Security/Manual-action |
| **GA4** | All Traffic + conversion alerts |
| **Backlink tool** | Referring-domain-lost; toxic-link spike |
| **OPENPAGERANK_API_KEY** | Authority-signal-drop alert |
| **PAGESPEED_API_KEY** (or GSC/CrUX) | Core Web Vitals alert |
| **AI-monitor** (or scheduled manual prompt log) | Automated AI-citation-loss alerts |
| **Repo connectors (already available)** | Technical/indexing/robots/orphan/H1/duplication alerts — can run on a schedule today |

> **Already breached at baseline (act now, not future):** homepage H1 = 0, and `/en/` vs `/` duplication on money pages. These are the first two technical alerts that fire the moment monitoring goes live.

---

## Handoff Summary

- **Objective:** Configure threshold alerts for future ranking/traffic/technical/backlink/GEO/brand changes for insly.com, with concrete thresholds, channels, and per-connector activation.
- **Key findings:** Most alerts are **staged** (rankings/traffic/backlinks N/A until GSC/GA4/backlink tool connect); thresholds are Estimated defaults until a 2–4 week baseline accrues. **Technical + GEO-readiness alerts can run today** via repo connectors. Two technical conditions are **already breached** at baseline (homepage 0 H1; URL duplication). robots.txt currently allows all AI bots — a flip to Disallow is a Critical alert.
- **Evidence:** robots.json (0 disallow, 6 AI bots), onpage-home.json (0 H1), linkgraph.json (4 orphans + ai.insly.com), sitemap.json (523 URLs baseline), kg-insly.json (no entity).
- **Open loops → `memory/open-loops.md`:** Connect GSC + GA4 to activate staged alerts; schedule repo connectors for live technical monitoring; fix the two already-breached conditions.
- **Status:** DONE_WITH_CONCERNS (alerts configured; ranking/traffic/backlink categories staged pending connectors).
- **Next skill:** `performance-reporter` (set a monthly reporting cadence so alerts roll up into stakeholder reports) → Terminal.
