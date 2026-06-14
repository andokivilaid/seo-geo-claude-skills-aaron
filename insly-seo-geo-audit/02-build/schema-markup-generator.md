# schema-markup-generator — Insly JSON-LD Package

> Skill: `build/schema-markup-generator` (v9.9.10) · Mode: Tier 1 · Date: 2026-06-14
> Current state (Measured — `schema-home.json`): 5 schema blocks present — **Organization + WebSite + BreadcrumbList** recognized; WebPage/ImageObject generic. **Missing: SoftwareApplication/Product, FAQPage, and `sameAs` on Organization.**
> Placeholder rule: any value not confirmed in the provided data is wrapped in `PLACEHOLDER_…` and listed in the placeholder table. Do **not** publish placeholders unverified — replace with real Insly values first.

---

## 1. What to add and why

| Schema | Status | Rich result (2026) | Recommend |
|---|---|---|---|
| Organization (+ `sameAs`) | Present, **no `sameAs`** | Knowledge panel / entity grounding | **P0** — add `sameAs`, `logo`, `description`. Directly addresses the Wikidata/entity gap (`kg-insly.json` recognized:false). |
| SoftwareApplication | **Missing** | No rich snippet without `aggregateRating`, but strong entity/AEO signal | **P0** — Insly is SaaS; this is the correct product type. |
| Product / Offer | Optional | Price-in-SERP only with valid Offer | **P1** — use on `/en/pricing/` and `/en/mga-insurance-software/` (has €5,000/month). |
| FAQPage | **Missing** | Google **retired FAQ rich results 2026-05-07** for non-gov/health — **no SERP accordion**. Still high value for **AI/answer engines (AEO)** + entity understanding. | **P1** — add for GEO, not for a rich-result promise. |
| BreadcrumbList | Present, recognized | Breadcrumb trail | Keep as-is. |

> Pre-flight before publishing: `python3 scripts/connectors/schema_lint.py <url>` then Google Rich Results Test UI (no public API).

---

## 2. Organization + `sameAs` (P0) — site-wide

Replace/extend the current Organization block. `sameAs` is the highest-leverage addition: it tells search engines and AI which external profiles are *the same Insly*, partially compensating for the missing Wikidata node until one is created.

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "@id": "https://insly.com/#organization",
  "name": "Insly",
  "url": "https://insly.com/en/",
  "logo": {
    "@type": "ImageObject",
    "url": "PLACEHOLDER_LOGO_URL_512x512.png",
    "width": 512,
    "height": 512
  },
  "description": "Insly is a low-risk insurance software platform for MGAs, insurance brokers, and insurers, providing product building, distribution, policy administration, accounting, and claims management in one modular, AI-powered system.",
  "foundingDate": "PLACEHOLDER_YYYY",
  "sameAs": [
    "https://twitter.com/insly_com",
    "https://www.linkedin.com/company/PLACEHOLDER_INSLY_LINKEDIN",
    "https://www.crunchbase.com/organization/PLACEHOLDER_INSLY_CRUNCHBASE",
    "https://www.wikidata.org/wiki/PLACEHOLDER_QID_AFTER_ENTITY_CREATION"
  ],
  "contactPoint": {
    "@type": "ContactPoint",
    "contactType": "sales",
    "url": "https://insly.com/en/"
  }
}
```
- `twitter:site` `@insly_com` is **Measured** (from every `onpage-*.json`) → the X/Twitter `sameAs` is safe.
- LinkedIn, Crunchbase, Wikidata are placeholders — fill from Insly's real profiles. Wikidata QID only exists *after* `entity-optimizer` creates the node.

---

## 3. SoftwareApplication (P0) — homepage / product pages

Insly is B2B SaaS, so `SoftwareApplication` (subtype of the broader software product) is the correct entity type.

```json
{
  "@context": "https://schema.org",
  "@type": "SoftwareApplication",
  "@id": "https://insly.com/#software",
  "name": "Insly",
  "applicationCategory": "BusinessApplication",
  "applicationSubCategory": "Insurance Software",
  "operatingSystem": "Web-based (SaaS)",
  "url": "https://insly.com/en/",
  "description": "Low-risk insurance software for MGAs, brokers, and insurers: product builder, distribution, policy administration, insurance accounting and reporting, and claims management, with built-in AI (Insurance Copilot).",
  "publisher": { "@id": "https://insly.com/#organization" },
  "offers": {
    "@type": "Offer",
    "price": "5000",
    "priceCurrency": "EUR",
    "priceSpecification": {
      "@type": "UnitPriceSpecification",
      "price": "5000",
      "priceCurrency": "EUR",
      "unitText": "MONTH",
      "description": "Entry pricing from €5,000/month, based on system scope, implementation, and GWP transacted. Verify current price before publishing."
    },
    "url": "https://insly.com/en/pricing/"
  }
}
```
- `price: "5000"` / EUR / month is **User-provided** (from `onpage-en-mga-insurance-software.json` meta "from €5,000/month"). It is a *from* price — confirm it is current and acceptable to expose as structured `Offer` before shipping.
- **No `aggregateRating`** is included — Insly has no review data in the provided files. Do **not** add a fabricated rating; without genuine reviews this block earns no star snippet, which is correct.

---

## 4. FAQPage (P1) — pair with the FAQ blocks from the article / GEO rewrites

Add to pages where the Q&A is **visibly on the page** (required — schema must match visible content). Questions reuse the autocomplete clusters and the article FAQ.

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "@id": "https://insly.com/en/mga-insurance-software/#faq",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "What is MGA insurance software?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "MGA insurance software is a platform that lets a Managing General Agent build and rate products, distribute through brokers, administer policies, manage claims, and report to capacity providers in one system instead of separate tools."
      }
    },
    {
      "@type": "Question",
      "name": "How much does MGA insurance software cost?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Pricing is typically based on system scope, implementation, and the gross written premium (GWP) transacted on the platform rather than a flat per-seat fee. Insly publishes entry pricing from €5,000/month."
      }
    },
    {
      "@type": "Question",
      "name": "How long does it take to launch on an MGA platform?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Software configuration can be fast — Insly advertises go-live in 7–14 days — but full commercial launch also depends on capacity agreements, compliance, and data migration outside the platform."
      }
    },
    {
      "@type": "Question",
      "name": "What is the difference between an MGA and a broker?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "A broker arranges cover for clients, while an MGA holds delegated authority from an insurer to underwrite and bind on the insurer's behalf, so an MGA needs underwriting and bordereaux capabilities a broker platform may not have."
      }
    }
  ]
}
```
> **Rich-result note:** Google retired FAQ rich results (2026-05-07) for non-government/health sites — this will **not** render a SERP accordion. Ship it for AI/answer-engine citation and entity understanding only. Each `Answer.text` must match an answer visible on the page.

---

## 5. Placeholder register (replace before publishing)

| Placeholder | Where | Source needed |
|---|---|---|
| `PLACEHOLDER_LOGO_URL_512x512.png` | Organization.logo | Insly brand logo URL (square ≥112px, ideally 512). |
| `PLACEHOLDER_YYYY` | Organization.foundingDate | Insly founding year. |
| `PLACEHOLDER_INSLY_LINKEDIN` | sameAs | Insly LinkedIn company slug. |
| `PLACEHOLDER_INSLY_CRUNCHBASE` | sameAs | Insly Crunchbase slug. |
| `PLACEHOLDER_QID_AFTER_ENTITY_CREATION` | sameAs | Wikidata QID — exists only after `entity-optimizer` creates the node. |
| `price: "5000"` EUR/MONTH | SoftwareApplication.offers / Product | Confirm "from €5,000/month" is current and OK to expose as structured Offer. |

**Confirmed-real values (no placeholder):** `name: "Insly"`, `url`, Twitter `@insly_com` (Measured), the 7–14 days and €5,000/month claims (User-provided from on-site meta), `applicationCategory: BusinessApplication`.

---

## 6. Implementation & validation

1. **Placement:** add as separate `<script type="application/ld+json">` blocks in `<head>` (WordPress: theme header or an SEO plugin's JSON-LD slot). Keep the existing Organization/WebSite/BreadcrumbList; merge the new `sameAs`/`logo`/`description` into the *existing* Organization rather than creating a duplicate `@id`.
2. **De-dupe:** ensure only one `Organization` with `@id` `#organization` across the page; reference it from SoftwareApplication via `publisher`.
3. **Validate:** `python3 scripts/connectors/schema_lint.py https://insly.com/en/mga-insurance-software/` → then Google Rich Results Test + Schema.org Validator.
4. **Match visible content:** publish the FAQ blocks (from `seo-content-writer-sample-article.md` / `geo-content-optimizer.md`) on the page *before* shipping FAQPage schema.
5. **Monitor:** Search Console > Enhancements after deploy.

**Validation self-check:** All four blocks are syntactically valid JSON-LD, use a single `@context`, cross-reference via `@id`, and contain no fabricated ratings/dates. Every non-confirmed value is a flagged placeholder. ✔

---

## Handoff Summary

- **Objective**: Generate ready-to-paste JSON-LD for Insly — SoftwareApplication, FAQPage, and Organization with `sameAs` — beyond the current Organization+WebSite+BreadcrumbList.
- **Output**: This file — 4 copy-pasteable JSON-LD blocks (Organization+sameAs, SoftwareApplication+Offer, FAQPage), placeholder register, implementation + validation steps.
- **Evidence**: Current schema state Measured from `schema-home.json` (Org/WebSite/Breadcrumb recognized; no sameAs/SoftwareApplication/FAQ); Twitter handle Measured; €5,000/month + 7–14 days User-provided from product `onpage-*.json`; no review data → no `aggregateRating`.
- **Open loops**: 6 placeholders to fill (logo, founding year, LinkedIn, Crunchbase, Wikidata QID, confirm price); Wikidata QID depends on `entity-optimizer`.
- **Target keyword**: MGA insurance software (entity: Insly).
- **Completion status**: DONE_WITH_CONCERNS (valid blocks delivered; 6 placeholders + FAQ-must-be-visible dependency before publish).
- **Next skill**: `technical-seo-checker` — verify deployment, then `entity-optimizer` to mint the Wikidata node that fills the `sameAs` QID.
