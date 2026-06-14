# Core Web Vitals — Insly (now Measured)

Resolves the N/A from `03-optimize/technical-seo-audit.md`. Pulled **2026-06-14** via `psi.py` with a PageSpeed API key. Two data sources per page: **Field = CrUX real-user data (origin-level, last 28 days) — this is what Google ranks on.** Lab = throttled mobile simulation (diagnostic only).

## Verdict: Insly FAILS Core Web Vitals (mobile)

**Field / CrUX (real users, origin-level — identical across all pages = site-wide):**
| Metric | Value | Threshold | Verdict |
|--------|-------|-----------|---------|
| **LCP** (Largest Contentful Paint) | **3,967 ms** | ≤2,500 good / >4,000 poor | ⚠️ **needs-improvement** (right at the cliff) |
| **TTFB** (Time to First Byte) | **~2,243 ms** | ≤800 good | ❌ **SLOW** (root cause) |
| **FCP** (First Contentful Paint) | **~3,661 ms** | ≤1,800 good | ❌ **SLOW** |
| **INP** (interactivity) | 166 ms | ≤200 good | ✅ good |
| **CLS** (layout shift) | ~0.00 | ≤0.10 good | ✅ good |
| **Overall CrUX** | **SLOW** | — | **`core_web_vitals_pass: false`** |

**Lab perf scores (mobile, diagnostic):** Home **53** · MGA page **49** · Pricing **37**. Lab LCP 15–19s and FCP 9–13s are throttle-inflated, but they confirm the direction: a heavy initial load.

## Diagnosis — it's a loading-speed problem, not interactivity or stability
CLS and INP are already good, so **don't touch interactivity/layout**. Every bad signal is in the *loading* chain, and the same numbers repeat on every page → a **site-wide / server-and-template cause**, not a per-page one. Chain of blame:

1. **TTFB ~2.2s (slow) = the foundation.** This is WordPress server response (hosting, PHP, plugins, no/poor full-page cache). Until TTFB drops, FCP and LCP physically cannot be fast — everything downstream waits on the first byte.
2. **FCP ~3.7s (slow)** = TTFB + render-blocking CSS/JS in the `<head>`.
3. **LCP ~4.0s** = FCP + the largest element rendering. The homepage hero image is a **4401×1857 PNG** (seen in `onpage-home.json` og:image) — almost certainly an oversized, unoptimized LCP element.

## Prioritized fix plan (highest leverage first)
| # | Fix | Targets | Effort |
|---|-----|---------|--------|
| **CWV-1** | **Full-page caching + faster host/PHP** (WP Rocket / Cloudflare APO / server-level cache; PHP 8.x; audit slow plugins) | TTFB → <800ms | M (biggest win) |
| **CWV-2** | **Optimize hero/LCP image** — serve WebP/AVIF, resize to displayed dimensions (not 4401px wide), add `fetchpriority="high"`, preload it | LCP | S |
| **CWV-3** | **Eliminate render-blocking** — inline critical CSS, defer/async non-critical JS, remove unused CSS | FCP, LCP | M |
| **CWV-4** | **CDN for static assets** (likely partially present via Cloudflare; verify images/fonts are edge-cached) | TTFB, FCP | S |
| **CWV-5** | Preconnect to third-party origins; self-host or `font-display: swap` for webfonts | FCP | S |

**Do NOT** spend effort on layout-shift or interactivity fixes — CLS (0.00) and INP (166ms) already pass.

## Re-measure after each change
`python3 scripts/connectors/psi.py https://insly.com/en/ --key <KEY>` (lab updates instantly; **field/CrUX lags ~28 days** — judge real progress on the field LCP/TTFB, not the lab score). Pricing page (lab 37, TBT 820ms) is the worst single page — verify its extra scripts.

## Handoff Summary
- **Objective:** convert Core Web Vitals from N/A → Measured.
- **Key findings:** Site **fails CWV** (`pass:false`); LCP 3,967ms (needs-improvement), **TTFB 2.2s and FCP 3.7s are SLOW**; CLS + INP good. Root cause = WordPress server response + oversized hero image + render-blocking, site-wide.
- **Severity:** HIGH — CWV is a ranking signal and the issue is origin-wide.
- **Status:** DONE (Measured). Field data is origin-level; per-URL field data may differ once each URL has enough traffic.
- **Next skill:** `technical-seo-checker` (fold CWV-1…5 into the technical backlog) → re-run PSI after caching ships.
