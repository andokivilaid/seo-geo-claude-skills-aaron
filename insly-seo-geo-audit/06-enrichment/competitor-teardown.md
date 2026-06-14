# Competitor Teardown — Insly vs SERP Rivals (Measured)

Real off-site analysis of the pages that **outrank or flank Insly** for "mga insurance software platform" (live SERP: #1 OneShield, #2 INSTANDA, **#3 Insly**, #4 Send Technology). On-page signals via `onpage.py` (`00-data/comp-onpage-*.json`); messaging via live fetch (2026-06-14). Upgrades `01-research/competitor-analysis.md` from Estimated → **Measured** for these four.

## 1. Head-to-head on-page table (all Measured)
| Signal | **Insly** (MGA page) | INSTANDA | OneShield | Send Technology |
|--------|----------------------|----------|-----------|-----------------|
| SERP rank (core kw) | **#3** | #2 | #1 | #4 |
| H1 count | **1 ✅** | 1 ✅ | **0 ❌** | 1 ✅ |
| H2 / H3 structure | 5 / 5 ✅ | 5 / 0 (flat) | 5 / 5 | 5 / 5 |
| Word count | 3,973 | 3,215 | **7,516** | 2,288 |
| Meta desc length | 137 | 151 | 120 | 144 |
| JSON-LD schema | **Full: Organization+WebSite+Breadcrumb ✅** | **None ❌** | Full ✅ | Partial (no Organization) |
| Quantified proof on page | Weak | **Strong** | Weak | Weak |
| Security/compliance certs shown | Not on page | No | No | **Yes (ISO 27001, SOC 2, ISO 42001)** |
| Lines-of-business claim | "modular" (vague) | complexity range | **"90+ lines"** | "40+ lines" |

## 2. Positioning map (exact phrases)
| Vendor | Core promise | Hook |
|--------|-------------|------|
| **Insly** | "low-risk insurance software", fast setup (weeks), modular, AI Copilot, fast ROI | Risk reduction |
| **INSTANDA** | "Launch Products Faster. Scale Smarter." — "no-code self-sufficiency" | Speed + autonomy |
| **OneShield** | "Transformative technology empowering MGAs" — enterprise breadth, all-inclusive pricing | Completeness |
| **Send** | "Run a high-growth MGA without operational drag" | Remove overhead |

## 3. Where Insly WINS (defend these)
1. **Schema/structured-data lead.** Insly carries full Organization+WebSite+BreadcrumbList JSON-LD; **INSTANDA has zero schema** and Send has no Organization node. This is a real rich-result + GEO advantage — extend it (add `SoftwareApplication` + `FAQPage`, ref `02-build/schema-markup-generator.md`) before rivals close the gap.
2. **Clean heading structure + balanced depth.** Insly has a proper H1 and full H2/H3 hierarchy at ~4k words — OneShield (the #1) has **no H1**, INSTANDA has **no H3 layer**. Insly's page is technically the best-structured of the four.
3. **Risk-framed positioning is differentiated.** Everyone else sells speed/scale; "low-risk" is a distinct angle for risk-averse insurers/carriers. Lean into it.

## 4. Where Insly LOSES (the gaps to close)
| # | Gap | Evidence | Action | Skill |
|---|-----|----------|--------|-------|
| **CT-1** | **Quantified proof gap — the biggest one.** INSTANDA stacks hard outcomes + named logos: "50+ MGAs", "90% productivity reduction", "209% premium increase", "42 states in 12 months", logos (Moonrock, Savvi, AiA…). Insly's MGA page surfaces few/no comparable numbers — despite Insly *having* case studies (Ridge Canada, Alta Signa, Accelerate Underwriting). | `comp-onpage-instanda` + fetch; ties to CORE-EEAT **Experience 30/100** in `05-cross-cutting/content-quality-audit.md` | Pull 3–5 quantified client outcomes + logos onto the MGA page | `content-quality-auditor` → `seo-content-writer` |
| **CT-2** | **No security/compliance signals on page.** Send leads with ISO 27001 / SOC 2 Type II / ISO 42001 — high-trust buying criteria for insurers handling PII. | `comp-onpage-send` fetch | If Insly holds these certs, display the badges; if not, add a Trust/Security section | `content-quality-auditor` (Trust dimension) |
| **CT-3** | **Vague capability scope.** OneShield "90+ lines", Send "40+ lines" give concrete breadth; Insly says "modular/customisable". | fetches | State a concrete number (products/lines supported, integrations count) | `seo-content-writer` |
| **CT-4** | **No comparison/alternatives asset.** A "best MGA software" listicle (Genasys) ranks page 1; none of these vendors own a neutral comparison page. | live SERP | Build an "Insly vs INSTANDA / OneShield / Send" or "MGA software compared" hub — captures bottom-funnel + AI-citation demand | `content-gap-analysis` → `seo-content-writer` |
| **CT-5** | **Depth ceiling vs #1.** OneShield's ranking page is 7,516 words (2× Insly). Not a mandate to bloat, but the money page can absorb an FAQ + deeper LOB/integration detail. | on-page word counts | Add FAQ + capability depth (also helps GEO citability) | `geo-content-optimizer` |

## 5. Net read
Insly is **already top-3 and technically the best-built page in the set** (schema + headings + balanced depth). It is **not** losing on craft — it's losing on **proof and trust signaling**. The single highest-leverage competitive move is **CT-1: surface quantified client outcomes + logos on the MGA page**, which also directly fixes the lowest CORE-EEAT dimension (Experience 30). Schema lead (win #1) should be pressed, not coasted on.

## Handoff Summary
- **Objective:** Measured competitor teardown of Insly's 3 closest SERP rivals.
- **Key findings:** Insly #3, best-structured page, **only one with full schema** (INSTANDA has none); loses on **quantified proof (CT-1)** and **security/trust signals (CT-2)**; no comparison asset exists to own (CT-4).
- **Status:** DONE (Measured for these 4 competitors; broader field still Estimated without a backlink/traffic tool).
- **Priority items:** CT-1 (proof) > CT-4 (comparison hub) > CT-2 (trust certs).
- **Next skill:** `seo-content-writer` (rebuild MGA page proof section) + `content-gap-analysis` (comparison hub) → `content-quality-auditor` to re-score Experience.
