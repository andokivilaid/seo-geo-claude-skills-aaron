# meta-tags-optimizer — Insly Homepage + 3 Product Pages

> Skill: `build/meta-tags-optimizer` (v9.9.10) · Mode: Tier 1 (no search console / SEO tool connected) · Date: 2026-06-14
> Scope: Homepage, MGA software, Insurance software (insurers), Pricing.
> "Before" values are **Measured** — pulled live and stored in the `onpage-*.json` files. CTR uplift figures are **N/A / Estimated** only — no GSC connected, so no measured impressions or CTR baseline exists. Every "expected lift" below is a qualitative rationale, not a measured number.

Character-length targets: **Title ≤ 60 chars** (avoid truncation), **Meta description 150–160 chars**. Current lengths flagged where under-used.

---

## 1. Homepage — `https://insly.com/en/`

### Before (Measured — `onpage-home.json`)
| Tag | Current value | Len |
|---|---|---|
| Title | `Insly - Low-Risk Insurance Software` | 35 |
| Meta desc | `The low-risk insurance software partner for MGAs and insurers. Fast setup, AI-powered and real results for MGAs and insurers.` | 125 |
| og:title | `Insly - Low-Risk Insurance Software` | — |
| og:description | (same as meta desc) | — |
| og:site_name | `Insly - Design & deliver insurance products` | — |
| twitter:card | `summary_large_image` | — |
| twitter:site | `@insly_com` | — |
| twitter:title / description | **missing** | — |

**Issues:** Title only 35/60 chars — leaves ~25 chars of SERP real estate unused and omits "MGA" and "brokers". Meta desc repeats "for MGAs and insurers" twice and wastes ~35 chars. No Twitter title/description (falls back to OG — acceptable but not optimized).

### After — 3 title variants
1. `Insly — Low-Risk Insurance Software for MGAs & Insurers` (54) — *keyword + audience*
2. `Insurance Software for MGAs, Brokers & Insurers | Insly` (54) — *category-led, adds "brokers"*
3. `Insly: Launch Insurance Products in Weeks, Low-Risk` (50) — *benefit/outcome-led*

**Recommended: #1** — keeps brand-led structure the site already uses, adds the audience keywords, fits in full.

### After — 3 meta description variants (150–160)
1. `Insly is low-risk insurance software for MGAs, brokers, and insurers. Build, distribute, and administer products fast — AI-powered, modular, live in weeks.` (154)
2. `Launch and scale insurance products on one modular platform. Insly gives MGAs and insurers fast setup, built-in AI, and real ROI. Book a demo.` (140) — *adds CTA*
3. `The low-risk insurance software partner for MGAs, brokers, and insurers. Fast setup, built-in AI, and accounting accuracy — go live in weeks.` (139)

**Recommended: #1** — removes the duplicate phrase, adds "brokers", front-loads the keyword.

### Social tags to add
```html
<meta property="og:title" content="Insly — Low-Risk Insurance Software for MGAs & Insurers" />
<meta property="og:description" content="Build, distribute, and administer insurance products on one modular, AI-powered platform — live in weeks." />
<meta name="twitter:title" content="Insly — Low-Risk Insurance Software for MGAs & Insurers" />
<meta name="twitter:description" content="One modular, AI-powered platform for MGAs, brokers, and insurers. Go live in weeks." />
<!-- Keep existing: twitter:card=summary_large_image, twitter:site=@insly_com, og:image -->
```
> Note: `og:image` is currently a 4401×1857 PNG — oversized and not 1.91:1. Recommend a dedicated 1200×630 OG image. `[placeholder — needs a 1200×630 asset]`

---

## 2. MGA Software — `https://insly.com/en/mga-insurance-software/`

### Before (Measured — `onpage-en-mga-insurance-software.json`)
| Tag | Current value | Len |
|---|---|---|
| Title | `MGA Software \| Low-Risk Insurance Software – Insly` | 50 |
| Meta desc | `Insly's MGA software lets you launch fast, scale confidently, and cut complexity all at low-risk. Go live in 7–14 days from €5,000/month.` | 137 |
| og:type | `article` | — |

**Assessment:** This is already the **strongest** of the four — keyword-led title, and a meta desc with two concrete facts (7–14 days, €5,000/month). Light touch only. (Minor: "Low-Risk Insurance Software" partly duplicates the homebrand; the meta desc could use the full 150–160.)

### After — 3 title variants
1. `MGA Insurance Software — Go Live in 7–14 Days | Insly` (53) — *adds the differentiating stat*
2. `MGA Insurance Software \| Low-Risk Platform – Insly` (50) — *closest to current, "insurance" added*
3. `MGA Software for Insurance: Launch Fast, Low-Risk | Insly` (56)

**Recommended: #1** — "MGA insurance software" is the exact target keyword (matches the autocomplete cluster), and the 7–14 day stat is a proven CTR hook.

### After — 3 meta description variants (150–160)
1. `Insly's MGA insurance software lets you build, distribute, and administer products on one platform. Go live in 7–14 days from €5,000/month — low-risk.` (151)
2. `Launch and scale your MGA fast. Insly's modular platform handles products, distribution, accounting, and claims — live in 7–14 days, from €5,000/month.` (152)
3. `MGA insurance software that cuts complexity: product builder, distribution, accounting, and claims in one system. Go live in 7–14 days from €5,000/month.` (153)

**Recommended: #1** — keeps the winning facts, adds the exact keyword "MGA insurance software", fills the length.

---

## 3. Insurance Software (insurers) — `https://insly.com/en/insurance-software/`

### Before (Measured — `onpage-en-insurance-software.json`)
| Tag | Current value | Len |
|---|---|---|
| Title | `Insurance Software for Insurers \| Launch Faster with Insly` | 58 |
| Meta desc | `Low-risk insurance software for insurers who want speed. Launch new products, simplify underwriting, and gain 100% accounting accuracy.` | 135 |

**Assessment:** Good title (keyword + audience + benefit, 58 chars — near the limit, fine). Meta desc has a strong stat (100% accounting accuracy). Light optimization.

### After — 3 title variants
1. `Insurance Software for Insurers — Launch Faster | Insly` (54) — *trims, keeps all signals*
2. `Insurance Software for Insurers: Speed + 100% Accuracy | Insly` (60) — *adds the stat (at limit)*
3. `Low-Risk Insurance Software for Insurers | Insly` (48)

**Recommended: #1** — current title is already strong; #1 just trims to leave snippet margin. Keep current if not re-testing.

### After — 3 meta description variants (150–160)
1. `Low-risk insurance software for insurers who want speed. Launch new products, simplify underwriting, and gain 100% accounting accuracy on one platform.` (151)
2. `Insurers launch faster with Insly: build products, simplify underwriting, and reach 100% accounting accuracy. Modular, AI-powered, low-risk. See a demo.` (152)
3. `Speed-focused insurance software for insurers. New products, simpler underwriting, and 100% accounting accuracy — modular and low-risk. Book a demo.` (146)

**Recommended: #1** — minimal change from current, just extends to full length.

---

## 4. Pricing — `https://insly.com/en/pricing/`

### Before (Measured — `onpage-en-pricing.json`)
| Tag | Current value | Len |
|---|---|---|
| Title | `Insly Pricing` | **13** |
| Meta desc | `Discover Insly's flexible pricing based on system scope, implementation and GWP transacted on the platform.` | 107 |

**Issues (largest opportunity of the four):** Title is only **13/60 chars** — wastes ~47 chars and has zero keyword beyond the brand. Meta desc under-uses length (107/160) and omits the one fact buyers most want — the **from €5,000/month** entry price that appears on the MGA page.

### After — 3 title variants
1. `Insly Pricing — Insurance Software from €5,000/Month` (51) — *adds the anchor price*
2. `Insurance Software Pricing — Scope, GWP & Setup | Insly` (54) — *keyword + model*
3. `Insly Pricing: Flexible Plans for MGAs & Insurers` (49)

**Recommended: #1** — adding the "from €5,000/month" price is the single highest-impact change in this whole document for click-through on a pricing query. (Confirm €5,000 is current before shipping — it is sourced from the MGA page meta, **User-provided**.)

### After — 3 meta description variants (150–160)
1. `Insly's insurance software pricing is based on system scope, implementation, and GWP transacted — from €5,000/month. See how plans scale with your business.` (155)
2. `Flexible insurance software pricing from €5,000/month, based on system scope, implementation, and GWP transacted. Get a tailored quote for your MGA or book.` (155)
3. `Discover Insly's flexible pricing: scope, implementation, and GWP-based plans from €5,000/month. Pay for what you transact — request a custom quote.` (147)

**Recommended: #1** — adds the entry price and a benefit, fills the length, keeps the existing "scope/implementation/GWP" model language.

---

## CORE-EEAT alignment check

| Page | C01 Intent Alignment | C02 Direct Answer | Verdict |
|---|---|---|---|
| Home | Pass — title/desc match "insurance software for MGAs/insurers" intent | Pass — desc answers "what Insly is" | OK |
| MGA | Pass — exact "MGA insurance software" keyword | Pass — facts (7–14 days, €5,000) answer cost/speed intent | OK |
| Insurance software | Pass | Pass — 100% accuracy stat | OK |
| Pricing | Pass after fix (was brand-only) | Pass after fix — price now in title/desc | Fixed |

## CTR notes (qualitative — no measured CTR available)
- **Numbers and prices** in titles/descriptions (7–14 days, €5,000/month, 100% accuracy) are the strongest CTR levers here and Insly already owns the facts — surface them everywhere.
- **Pricing page** is the clearest before/after win: brand-only 13-char title → keyword + price.
- **A/B testing**: real CTR testing requires GSC/Search Console (currently **N/A**). Recommend connecting GSC before declaring any variant a "winner"; until then treat #1 recommendations as best-practice defaults, not measured winners.

---

## Handoff Summary

- **Objective**: Rewrite title + meta description + OG/Twitter for Insly homepage and 3 product pages from their real current values.
- **Output**: This file — before (Measured) vs. after with 3 title + 3 description variants per page, social-tag blocks, CORE-EEAT C01/C02 check, CTR rationale.
- **Evidence**: All "before" values Measured from `onpage-home.json`, `onpage-en-mga-insurance-software.json`, `onpage-en-insurance-software.json`, `onpage-en-pricing.json`. CTR/impression baselines = **N/A** (no GSC).
- **Open loops**: Confirm "from €5,000/month" is current before publishing pricing-page changes; produce a 1200×630 OG image (homepage `og:image` is oversized 4401×1857).
- **Target keyword**: MGA insurance software (page-level: insurance software for insurers, insly pricing).
- **Top win**: Pricing page title `Insly Pricing` (13 chars, brand-only) → `Insly Pricing — Insurance Software from €5,000/Month`.
- **Completion status**: DONE (3+3 variants per page delivered; 2 ship-time confirmations noted).
- **Next skill**: `schema-markup-generator` — complete the SERP package with structured data.
