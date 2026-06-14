# External Enrichment & Corrections — Insly

Second pass (2026-06-14): real **off-site** data via live web search + connector verification, which the Tier-1 own-site run could not see. This upgrades several findings from **Estimated → Measured** and corrects two.

---

## A. Corrections to the first-run audit

### Correction 1 — Duplicate URLs are canonically consolidated (severity downgraded P0 → P2)
**Verified (Measured, `onpage` on non-`/en/` variants):** `/<slug>/` pages return **200** but each carries a **self-correcting canonical to the `/en/` version**:
| URL fetched | status | canonical | meta robots |
|---|---|---|---|
| `/mga-insurance-software/` | 200 | `…/en/mga-insurance-software/` | index, follow |
| `/insurance-software/` | 200 | `…/en/insurance-software/` | index, follow |
| `/claims-management-software/` | 200 | `…/en/claims-management-software/` | index, follow |

→ Not "split equity with no canonical." Google should consolidate to `/en/`. **Residual risk only:** both URLs are crawlable + `index,follow`, so it still wastes crawl budget and depends on Google honoring the canonical. Cleaner fix remains a 301, but this is no longer a P0 emergency.

### Correction 2 — Schema is consistent sitewide (not homepage-only)
**Verified (Measured, `schema_lint` on 3 product pages):** every product page carries the same 5 JSON-LD types as the homepage — `WebPage, ImageObject, BreadcrumbList, WebSite, Organization`. The "schema is half-built" finding stands (no `SoftwareApplication`/`FAQPage`/`sameAs`), but the base is applied **template-wide**, so one template change propagates everywhere. Good leverage.

### Still N/A — Core Web Vitals
PSI returned **HTTP 429 again** (keyless shared-IP quota). CWV remains genuinely unmeasured. Needs a free `PAGESPEED_API_KEY` or Google Search Console / CrUX.

---

## B. Real SERP & competitive position (Measured — live search)

**Query "mga insurance software platform" — live organic results:**
| Rank | Result |
|---|---|
| 1 | OneShield |
| 2 | INSTANDA |
| **3** | **Insly** — `…/en/mga-insurance-software/` (the page we audited) |
| 4 | Send Technology |
| 5 | Insurity Pro Suite |
| 6 | Dyad (ALIS DX) |
| — | also: Genasys "best MGA software" listicle, BindHQ, Vertafore |

**Implications (upgrade `01-research/competitor-analysis.md` + `serp-analysis.md`):**
- Insly is **already top-3** for its core money keyword — the on-page work is paying off; the priority is **defending/widening**, not breaking in.
- **Confirmed real competitor set** (was Estimated): OneShield, INSTANDA, Send Technology, Insurity, Dyad, BindHQ, Vertafore — plus enterprise Guidewire, Duck Creek, Majesco, Sapiens.
- A **"best MGA software" listicle (Genasys) ranks on page 1** — Insly has no comparable comparison/listicle asset. Confirms the content-gap finding: build a comparison/alternatives hub.

---

## C. Real entity footprint — `sameAs` set (Measured — feeds the #1 finding)

The biggest first-run finding was **no Knowledge Graph entity**. Here is Insly's **actual verified off-site presence** to declare in `sameAs` and use as Wikidata references:

```json
"sameAs": [
  "https://www.linkedin.com/company/inslytech",
  "https://www.crunchbase.com/organization/insly",
  "https://www.capterra.com/p/131631/Insly/",
  "https://www.g2.com/products/insly/reviews",
  "https://www.softwareadvice.com/accounting/insly-profile/",
  "https://www.selecthub.com/p/insurance-software/insly/",
  "https://twitter.com/insly_com"
]
```
> Verify each resolves before publishing (LinkedIn slug is `inslytech`, not `insly`). G2 URL is inferred — confirm the exact product slug. Add Wikidata + Wikipedia URLs once created.

**Entity facts gathered (for the Organization schema + Wikidata draft):**
| Property | Value | Confidence |
|---|---|---|
| Founded | **2014** | High (multiple sources agree) |
| HQ | **Tallinn, Estonia** | High |
| Category | Insurance software / MGA & broker platform (insurtech) | High |
| Third-party rank | "#21 in Insurance Software" (SelectHub) | Measured (one source) |
| Review presence | Capterra, G2, SoftwareAdvice, SelectHub, SoftwareWorld, ITQlick | Measured |

### ⚠️ Two data conflicts to resolve before publishing entity data
1. **Founding/HQ conflict:** most sources say **2014, Tallinn**; one aggregator says "launched 2000 in London." Wikidata/`foundingDate` must be correct — confirm against Insly's own `/en/history/` page and incorporation records before submitting.
2. **Pricing conflict:** third-party listings show **$49–$89/user/mo** (up to ~$6,999/100 users); the on-site figure used in the meta/Offer drafts was **"from €5,000/month."** These describe different plans/eras. **Confirm the current canonical price** before shipping the `Offer` schema or pricing-led meta — a wrong price in schema is a factual/trust risk.

---

## D. Trust signal (upgrades CITE domain-authority read)
Insly has **broad third-party review-site coverage** (Capterra, G2, SoftwareAdvice, SelectHub, SoftwareWorld, ITQlick, TechnologyCounter, Software Finder). This is a genuine **off-site citation/trust signal** that was N/A in the Tier-1 CITE run — it supports the "Established/recognized vendor" items and is consistent with the CAUTIOUS→ lean-TRUSTED direction once backlink data is connected.

---

## Handoff Summary
- **Objective:** enrich the Tier-1 audit with real off-site data; verify high-stakes findings.
- **Key findings:** Insly ranks **#3** for its core keyword (Measured); real competitor set + real `sameAs` footprint captured; duplicate-URL severity downgraded (canonical present); CWV still N/A.
- **Open loops (must resolve before publishing):** (1) confirm founding year/HQ (2014 Tallinn vs 2000 London); (2) confirm current canonical pricing (€5,000/mo vs $49–89/user); (3) get a PSI key for CWV.
- **Status:** DONE_WITH_CONCERNS (2 factual conflicts flagged).
- **Next skill:** `entity-optimizer` (use the real `sameAs` set + facts to draft the Wikidata entity) → `schema-markup-generator` (real Organization+sameAs block).
