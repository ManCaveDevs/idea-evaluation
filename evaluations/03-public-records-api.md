# Evaluation: Public Records Intelligence API

**Date:** March 28, 2026
**Status:** Evaluated

---

## The Idea

Every county in the US has public records (property assessments, permits, deeds, zoning, liens, code violations, tax delinquency, foreclosures). All technically public, none accessible in consistent machine-readable format. Fragmented across 3,100+ county portals. Build a unified scraping + normalization layer across 500+ counties. Revenue: API pricing $500–5,000/month.

---

## Role 1: Market Researcher

### Problem Validation
**Real, structurally entrenched problem.**

- ~3,143 counties (3,600+ recording jurisdictions), each with different portal tech, data schemas, and access methods
- ~1 in 3 properties has a recorded lien/encumbrance requiring identification before closing
- Manual title searches: abstractors visit individual portals. Express Title Search charges ~$69/search.
- Enterprise vendors: ATTOM (~$28M revenue, 158M+ properties), CoreLogic/Cotality (went private at ~$6B), CoStar ($30B+ market cap) — all enterprise-priced with sales-led processes

**Gap:** Incumbents are enterprise-focused with opaque pricing. Clear gap in **developer-friendly, self-serve API tier** for startups, smaller PropTech, and individual investors.

### Target Customer
| Segment | Count | WTP | Reachability |
|---|---|---|---|
| PropTech companies | ~2,000+ US | High | High (tech communities) |
| Title companies/agents | ~4,500 ALTA members | High | Medium (industry associations) |
| RE investors | 15.5M investor-owned homes | Medium-High (institutional) | Institutional: reachable |
| RE attorneys | ~50,000+ | Medium | Medium |
| Lenders/insurers | $17.1B title insurance market | High but long cycles | Hard |

**Best beachhead:** PropTech startups and mid-market RE platforms — technically sophisticated, underserved by enterprise pricing, reachable via developer marketing.

### Market Size
- **TAM:** US PropTech market $21.5–24.7B (2025–2026), growing 18.5% CAGR. Data-specific: ~$5–8B.
- **SAM:** ~5,000 potential API customers × $24K/year avg = **~$120M/year**
- **SOM (Year 3–5):** 100–300 customers × $2,000/month = **$2.4–7.2M ARR**

### Trends & Timing
- PropTech investment: $16.7B in 2025 (+67.9% YoY). Jan 2026: $1.7B (+176% over Jan 2025).
- AI-driven PropTech growing 42% annualized — amplifies demand for clean structured data
- Investor share of home purchases at 5-year high (32–34% in 2025)
- CoStar's $1.6B Matterport acquisition signals platform data aggregation valued

**Verdict: Real market. Confidence: 7.5/10.** Pain is structural and permanent. But incumbents are well-funded and multiple startups are entering.

---

## Role 2: Business Model Analyst

### Revenue Model
Usage-based API pricing is standard. $500–$5,000/month aligns with market:
| Comparable | Pricing |
|---|---|
| PropMix PubRec | $79–$7,500/mo per endpoint |
| BatchData | ~$95/mo starter to $100K+/yr |
| ATTOM | ~$500/mo starter, scales to six figures |
| CoreLogic | Custom, typically $10K+/mo |

**Recommended:** Hybrid — base subscription + overage per API call. Creates predictable revenue + upside capture.

### Unit Economics
- **Scraping/maintenance cost:** $400K–$620K/year for 200–500 counties (3–4 engineers + infra + proxies)
- **Per-county cost:** ~$1,500–$2,000/county/year (drops at scale — many counties share Tyler/Accela platforms)
- **API serving cost:** Low ($0.001–$0.005/call). **Gross margin on serving: 70–85%**
- **CAC:** $300–$800 (SMB/PLG), $1,000–$3,000 (title companies), $2,000–$5,000 (PropTech enterprise)
- **LTV:** $37,500–$75,000 (at $1,500/mo avg, 2–4% monthly churn)
- **LTV:CAC: 7:1 to 25:1** — healthy

### Pricing Power
**Moderate, constrained at both ends.** Too expensive for hobbyist investors, potentially too cheap for enterprise buyers wanting ATTOM/CoreLogic coverage guarantees. Power exists in **niche depth** incumbents neglect: code violations, zoning details, permit inspection statuses.

### Scalability
Positive up to ~500–800 counties, then diminishing returns. Top 200 counties cover ~70% of US population. Bottom 2,000 are tiny, poorly digitized, expensive per-capita. **Long tail problem is real.**

### Dependency Risks
- County website changes: HIGH (operational certainty, not risk)
- Anti-scraping measures: MODERATE (gov sites weaker than commercial)
- Legal: MODERATE (hiQ v. LinkedIn favorable, but county ToS vary)
- Platform vendor risk: If Tyler Technologies offers own API, could lose hundreds of counties simultaneously

**Verdict: Sound model if narrowly focused. Biggest structural risk: scraper maintenance costs scale linearly with coverage while revenue may scale sub-linearly. The data infrastructure cost is the hidden tax.**

---

## Role 3: Competitive Landscape Analyst

### This Is a Crowded, Well-Funded Market

**Tier 1: Dominant Incumbents**
- **CoreLogic/Cotality** — 99.9% US property coverage. $6B acquisition (2021). Decades of county relationships.
- **ATTOM** — 158M+ properties, 9,000 data attributes, 30TB warehouse. PE-backed. Acquired Estated, Onboard Informatics, Home Junction.
- **First American DataTree** — Fortune 500 subsidiary. Title/escrow industry backbone.

**Tier 2: Well-Funded Verticals**
- **Reonomy** — $130M+ raised, acquired by Altus for ~$201.5M. Direct integrations with all 3,100 county assessors.
- **Cherre** — $105–130M raised (Series C Sept 2024). "Data fabric" connecting 3.3B+ addresses. Launched Agent.STUDIO (AI) in 2025.
- **Regrid** — 150M+ parcels, 99% US coverage. Bootstrapped. Esri partnership.
- **HouseCanary** — $206M raised. 136M+ properties. Strong with SFR REITs.

**Tier 3: Developer-Focused (Your Direct Competitors)**
- **BatchData** — 155M+ properties, $500–5K/mo, developer-friendly SDKs
- **RealEstateAPI (REAPI)** — 159M+ properties, from $599/mo
- **Realie.ai** — **Most similar to your idea.** Directly collects from 3,100+ counties using AI agents. 180M+ parcels.
- **Shovels** — $6.5M raised. 180M permits across 20K+ jurisdictions. Building permits only.

### Key Finding
**At least a dozen companies are already attacking this problem.** The "unified API for county public records" is not an unoccupied space — it's an active battleground with well-funded players at every tier.

### Moat Assessment: WEAK
- Data is public by definition — no proprietary moat in raw information
- County relationships are replicable (public records are public)
- Normalization is engineering work (Cherre raised $105M+ to solve this)
- Coverage breadth massively favors incumbents

### Biggest Competitive Threat
**ATTOM Data Solutions.** PE-backed, acquisition-hungry (4 acquisitions), 158M+ properties, covers exact record types proposed, prices aggressively ($95/mo entry). If you build something valuable, ATTOM either adds the feature or acquires you.

**Verdict: LOW to MODERATE defensibility. The only viable path is going narrower and deeper — specific record types incumbents handle poorly (code violations, zoning overlays, municipal liens), serving a specific vertical, building the fastest update pipeline. A horizontal "all records, normalized" play against ATTOM/CoreLogic is a losing proposition without $50M+ in funding.**

---

## Role 4: Technical Feasibility Assessor

### Core Challenge
The **heterogeneity problem**: 3,100+ counties with different portal tech (Tyler, Accela, custom ASP.NET, scanned PDFs), different schemas ("Assessed Value" vs. "Total Assessment" vs. split fields), different access methods (REST APIs, web portals, bulk files, FOIA-only, in-person-only).

Normalization is harder than scraping. Shovels.ai: "every city or county has its own terminology, standards, and requirements — meaning hundreds or thousands of variations."

### MVP Timeline: 6–9 Months (50 Counties)
| Phase | Timeline |
|---|---|
| Define schema, build framework, first 5 scrapers | Months 1–2 |
| Build remaining 45 scrapers (2–3/week) + normalization | Months 3–6 |
| Harden monitoring, customer pilots | Months 7–9 |

### Scaling to 500 Counties: 18–30 Months
- Counties 1–50: Large metros, modern-ish portals. Painful but doable.
- Counties 50–200: Mid-size. More variation. JS-heavy, legacy HTML, CAPTCHAs.
- Counties 200–500: Smaller. Portal quality degrades. Some have no online portal. Some require FOIA.

### Tech Stack
- **Scraping:** Scrapy + Playwright (industry standard for mixed-content)
- **Proxies:** Bright Data/Oxylabs ($300–$1K/mo)
- **Normalization:** LLM-powered classification for field names, property types, zoning codes
- **Storage:** PostgreSQL + PostGIS + S3
- **API:** FastAPI + Redis + Stripe metered billing
- **Self-healing scrapers:** LLM-powered breakage detection + auto-repair (critical investment)

### The Maintenance Treadmill
- Industry breakage rate: **3–10% per maintenance cycle**
- At 500 counties: **15–50 scrapers breaking at any given time**
- Engineers spend **15–20% of time** on anti-bot countermeasures and repair
- Shovels.ai: 4 years in, $6.5M funding, covers only ONE data type (permits), still relies on third-party data providers, covers <10% of jurisdictions

### Minimum Team: 4–5 People
2 scraping/data engineers, 1 data/ML engineer, 1 backend engineer, 1 CEO/BD. ~$600K–$900K/year + $50K–$100K infra.

**Verdict: Feasibility 6.5/10. Technically feasible but operationally brutal. Biggest build risk: scraper maintenance costs scale linearly (or worse) with county count. At 500 counties × 8 data types = 2,000–4,000 scraping pipelines, each a permanent maintenance liability.**

---

## Role 5: Financial Analyst

### Startup Costs
| Category | Year 1 Estimate |
|---|---|
| Engineering (3–4 engineers) | $450K–$700K |
| Infrastructure (cloud, proxies, storage) | $60K–$180K |
| Legal & compliance | $30K–$75K |
| Data QA & ops (1–2 hires) | $80K–$120K |
| Sales & marketing | $50K–$100K |
| **Total Year 1** | **$670K–$1.175M** |

### Monthly Burn: $60K–$100K
At $1.5M seed: 15–25 months runway.

### Path to Profitability
- Breakeven at $80K/mo burn: ~40 customers at $2,000/mo avg
- **Months 0–12:** Build 100–200 county coverage, first paying customers
- **Months 12–24:** Ramp to 20–40 customers ($40K–$80K MRR)
- **Months 24–36:** Reach 40–60 customers, approach breakeven
- **Cash-flow positive: Month 24–36**

### Funding Strategy
| Phase | Amount | Source |
|---|---|---|
| Bootstrap/pre-seed | $250K–$500K | Build 50–100 county MVP, 5–10 design partners |
| Seed | $1.5M–$3M | Scale to 200–300 counties, full team |
| Series A (if pursuing scale) | $5M–$15M | At $50K+ MRR, 500+ counties |

### Key Financial Risks
1. **Infrastructure cost escalation (HIGH):** 62.5% of scraping professionals reported increased costs in 2025. Costs scale faster than volume.
2. **County blocking / legal exposure (HIGH):** 10–20% of target counties actively blocking degrades the value prop.
3. **Well-funded incumbent competition (MEDIUM-HIGH):** CoreLogic ($6B), ATTOM (PE-backed), Cherre ($130M) already aggregate this data.
4. **Long enterprise sales cycles (MEDIUM):** 6–12 month cycles extend path to revenue.
5. **Data quality consistency (MEDIUM):** 500+ different schemas. Quality issues destroy enterprise trust.

### Return Potential
| Scenario | ARR at Exit | Multiple | Exit Value |
|---|---|---|---|
| Bear case | $2M | 5x | $10M |
| Base case | $5M | 7x | $35M |
| Bull case | $12M | 10x | $120M |
| Reonomy comp | $20M | 11x | $220M |

Most likely path: **strategic acquisition by ATTOM, CoreLogic, CoStar, Cherre, or a title company** for coverage gaps or engineering talent.

**Verdict: Financial picture makes sense conditionally. Biggest financial risk: scraping infrastructure is a living cost center that never stabilizes. The gap between "we cover 500 counties" (the pitch) and "we reliably cover 500 counties with fresh normalized data" (the operational reality) is where the money goes.**

---

## Final Verdict

### Overall Assessment
This is a real market with validated demand and strong exit comps, but the competitive landscape is the most crowded of any idea evaluated so far. At least a dozen well-funded companies (ATTOM, CoreLogic, Cherre, Reonomy, BatchData, Realie.ai, Shovels) are already aggregating this data. The technical moat is weak — public data is public and normalization is engineering work. This could still be a good business, but only if executed as a narrow-and-deep vertical play, not a horizontal competitor to incumbents with decades of head start.

### Top 3 Strengths
1. **Structural, permanent pain point.** County fragmentation will persist for decades. Every county is different. This is genuinely hard infrastructure work that creates real value.
2. **Strong exit comps.** Reonomy acquired for $201.5M on $18.3M revenue (11x). CoreLogic at $6B. Real estate data companies command premium valuations.
3. **Plays directly to founder's backend engineering strengths.** This is a scraping, normalization, and API infrastructure problem — not a UX or marketing challenge. A backend engineer's dream project.

### Top 3 Risks
1. **Extremely crowded competitive landscape.** ATTOM (158M properties), Cherre ($130M raised), Realie.ai (executing exact same strategy), BatchData, Shovels — all attacking this from different angles. No clear lane for a new entrant without differentiation.
2. **Scraper maintenance is a permanent, linearly-scaling cost center.** 500 counties × multiple data types = thousands of fragile pipelines. 3–10% breakage rate per cycle. This never gets easier — it's a treadmill.
3. **Weak moat.** Data is public. Normalization is engineering. County relationships are replicable. The only durable advantages are speed (freshest data) or depth (record types nobody else covers), both of which require ongoing operational investment.

### Critical Questions
1. **What specific data types will you cover that ATTOM, Cherre, and BatchData don't?** "All public records, normalized" is not differentiated. Code violations? Zoning hearing outcomes? Permit inspection statuses?
2. **What's your strategy when Realie.ai (already scraping 3,100+ counties with AI agents) beats you on coverage?** They appear to be executing your exact playbook.
3. **Can you build county data partnerships (FOIA, bulk purchases) as a backup to scraping?** Scraping-only is fragile. Shovels' "Project Storm" (350+ offline jurisdictions in 3 months) is the right model.
4. **What vertical will you serve first?** "All PropTech" is too broad. Fix-and-flip investors? Insurance underwriters? Municipal compliance? Lenders?
5. **Do you have $1.5M+ in runway?** This cannot be bootstrapped on $200K. The infrastructure costs are real and front-loaded.

### Recommendation: CONDITIONAL GO (with strong caveats)

**This is the highest-ceiling but highest-risk idea evaluated.** The exit comps are exceptional. But the competition is fierce, the moat is weak, and the operational burden is relentless.

**Conditions before building:**
1. **Pick ONE data type and ONE vertical.** Don't build "all public records for everyone." Build "building permit data for insurance underwriters" or "code violation data for fix-and-flip investors" or "lien data for title companies." Shovels proved the single-data-type strategy works ($6.5M raised on permits alone).
2. **Talk to 10+ potential API customers.** Confirm which data types are actually underserved. ATTOM covers a lot — find the gaps.
3. **Price out the operational reality.** Build scrapers for 10 counties across your chosen data type. Measure: How long does each take? How often do they break? What's the real cost per county per month? If the math doesn't work at 10, it won't work at 500.
4. **Secure $1.5M+ in funding or committed runway.** This is capital-intensive infrastructure. Underfunding kills data companies.
