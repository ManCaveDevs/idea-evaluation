# Evaluation: Subcontractor Compliance Tool for Small GCs

**Date:** March 29, 2026
**Status:** Evaluated

---

## The Idea

Small GCs ($2M–$20M revenue, 5–25 person shops) must collect COIs, W-9s, lien waivers, and license verifications from every sub on every project. 60+ documents per 15-sub job. Large GCs use GCPay/Procore. Small GCs use email and spreadsheets. A lightweight $99/month tool for this compliance workflow.

---

## Role 1: Market Researcher

### Problem Validation
**Real, high-stakes, well-documented.**

- A single missed COI cost one GC over **$1 million** — plumber's insurance expired, flood + worker injury, GC absorbed all liability plus $650K project delay.
- Compliance managers spend **15–20 hours/week** on manual certificate tracking = ~$40K/year in wasted labor.
- **Nearly three-quarters** of construction professionals still use physical paper documents.
- Human error in spreadsheets is inevitable — one keystroke corrupted "hundreds of rows" at a commercial GC.

### Target Customer
- ~815,000 employer construction firms in US
- Target: **~80,000–130,000 firms** with 5–99 employees ($2M–$20M revenue)
- Highly reachable: AGC (27,000+ members), state licensing boards, Construction Dive, Procore/Autodesk marketplaces, Google/YouTube search

### Market Size
- **TAM:** ~200,000 GC/GC-like firms × $1,188/year = **~$238M/year**
- **SAM:** ~65,000–110,000 underserved small GCs = **$77M–$131M/year**
- **SOM (Year 3):** 1–3% = 650–3,300 customers = **$770K–$3.9M ARR**

### Trends & Timing
- Florida SB 658 (July 2025): eliminated flexibility in lien waiver forms — must match statutory templates exactly
- 12 states now mandate statutory lien waiver forms, trend toward more regulation
- ConTech VC hit **$3.7B through Q3 2025** (+27% YoY). 90% of investors increasing/maintaining
- **94% of construction firms** report difficulty filling positions — pushes toward automation
- Average construction business now uses 6.2 digital technologies (+20% YoY)

**Verdict: Real market. Confidence: 7.5/10.** Genuine gap between spreadsheets and $10K+/year enterprise tools. Regulatory tailwinds. But crowded adjacent space and price-sensitive buyers.

---

## Role 2: Business Model Analyst

### Pricing: $99/month Is Too Cheap

| Competitor | Annual Cost | Target |
|---|---|---|
| Procore | $10,000–$30,000/yr | Mid-to-large GCs |
| myCOI | $1,500–$3,000/yr | Mid-market |
| SmartCompliance | $2,000–$4,000/yr | Mid-market |
| BCS (self-service) | ~$0.50/vendor/month | All sizes |

**Recommendation: Reprice to $199–$299/month.** The alternative is a $45K/year compliance coordinator. Even $299/month ($3,600/yr) saves 75–85% vs. manual.

### Unit Economics
- **Cost-to-serve:** ~$6–14/month per customer. **Gross margin: 86–94%** at $99, improving to 93–97% at $199.
- **CAC:** $250–$500 (construction industry avg ~$281, SMB SaaS $200–$400)
- **Churn:** 8–12% annual (month-to-month), 5–8% with annual contracts. Construction tools embedded in workflow churn 3.6x slower.
- **LTV at $99/mo:** $7,900–$9,900. **LTV:CAC: 13–16:1** — excellent.
- **LTV at $249/mo:** $19,800–$29,880. **LTV:CAC: 33–50:1** — exceptional.
- **CAC payback:** 2.4–5 months — very fast.

### Scalability
Gets better: state templates amortize, infrastructure sub-linear, mild network effects (subs on-platform for multiple GCs), data moat on insurance patterns.

**Biggest structural risk: Autodesk bundling.** They own GCPay, BuildingConnected, PlanGrid. Could launch a $200/month "small GC starter bundle" that includes compliance.

**Verdict: Structurally sound with excellent unit economics. Reprice to $199–$299/month. Biggest risk is platform players bundling compliance as a feature.**

---

## Role 3: Competitive Landscape Analyst

### Competitive Map

**Enterprise (priced out of target):** Procore ($4,500–$60K/yr), GCPay (custom), Oracle Textura (enterprise), TradeTapp (Autodesk ecosystem)

**Mid-market specialists:** myCOI/illumend (200+ cert minimum), Jones ($15M Series B, full-service), TrustLayer ($23.2M raised, free tier for <50 vendors), BCS (free + self-service tiers)

**Direct threats at your price point:**
- **Contractor Foreman** — $49/month, 50+ features including COIs. Already serves small contractors.
- **Knowify** — $99/month exactly. Has sub compliance tracking with expiration alerts.
- **LienWaiver.pro** — Launched Feb 2026 at $19–$49/month. Same target (small GCs). Lien-waiver-only.
- **FileFlo** — $299/month AI compliance OS. 500+ companies.

### Key Finding
**No dominant player owns the "lightweight, affordable, full-compliance-bundle for small GCs" niche.** Most competitors solve one piece (COIs OR lien waivers OR prequalification). But 5+ players are within striking distance.

### Moat Assessment: WEAK to MODERATE
- Network effects: WEAK (not a marketplace)
- Switching costs: MODERATE (historical audit trails create lock-in)
- Brand/trust: WEAK initially (takes 2–3 years)
- Data advantage: POTENTIAL (shared sub compliance profiles)
- Regulatory complexity: MODERATE (50-state lien waivers genuinely hard)

### Biggest Threat
**Death by a thousand cuts from adjacent tools expanding.** Contractor Foreman ($49), Knowify ($99), BCS (free), TrustLayer (free), LienWaiver.pro ($49) — all within striking distance. **18–24 month window** before convergence closes the gap.

**Verdict: LOW to MODERATE defensibility. Window exists but narrow. Speed to market + depth of state-specific compliance + sub-side network effects are the only defenses.**

---

## Role 4: Technical Feasibility Assessor

### Core Challenge
NOT AI document parsing (solved — Sensible, Nanonets, AZAPI extract ACORD 25 at 99%+). The hard part is **state-specific regulatory data**: 12 states mandate statutory lien waiver forms, 38 are "legal wild west," license verification has no unified API (only MA has an official one).

### MVP: 8–12 Weeks, Solo Engineer Buildable
| Week | Deliverable |
|---|---|
| 1–2 | Auth, multi-tenant model, sub invite portal |
| 3–4 | Document upload + storage, manual COI review |
| 5–6 | COI OCR API integration, expiration tracking |
| 7–8 | Automated email/SMS reminders |
| 9–10 | Lien waiver templates (5–10 high-volume states) |
| 11–12 | Compliance dashboard, polish, deploy |

### Tech Stack (All Buy-Not-Build)
- **App:** Next.js + Supabase + Vercel (~$150/mo at scale)
- **COI parsing:** Sensible.so or Nanonets ($0.10–$0.50/page)
- **E-sign (v2):** DocuSeal (open source, free) or BoldSign ($15/user/mo)
- **PDF gen:** react-pdf or Puppeteer for lien waiver templates
- **Comms:** Resend (email) + Twilio ($0.008/SMS)

### Key Architecture Decision
Keep insurance requirements **configurable per-project** (GC defines thresholds), not hard-coded by state. This sidesteps the impossible task of encoding every jurisdiction's requirements.

**Verdict: 8/10 feasibility. Solo-engineer buildable. Biggest build risk: state-specific compliance data maintenance — a content curation problem disguised as a software problem.**

---

## Role 5: Financial Analyst

### Startup Costs
- **Solo technical founder:** $5,700–$30,600
- **Small team (2–3):** $54,400–$116,000
- **Very bootstrappable.** No exotic tech, no hardware, no regulatory licenses needed.

### Monthly Burn
- Solo (no salary): $2,000–$5,000
- Small team: $8,000–$15,000
- Seed-funded (3–5 people): $25,000–$50,000

### Path to Profitability
- **Solo breakeven:** ~31 customers at $99/mo = **3–6 months post-launch**
- **Small team breakeven:** ~152 customers = **9–15 months**
- **Growth trajectory (bootstrapped):**
  - Month 6: 30–50 customers, $3K–$5K MRR
  - Month 12: 100–200 customers, $10K–$20K MRR
  - Month 24: 300–500 customers, $30K–$50K MRR
  - Year 5: 1,500–2,500 customers, $1.8M–$3M ARR

### Funding Strategy
**Bootstrap strongly recommended.** MVP cost ($30K–$60K) is within savings range. Market rewards grind over blitz-scaling. Profitability reachable in <12 months. Raise only after 50–100 paying customers validate retention.

### Key Financial Risks
1. **SMB churn (BIGGEST):** At 5% monthly, you lose half your base per year. Annual contracts and sticky workflows are essential.
2. **"Feature not product" risk:** Platform players bundling compliance as an add-on.
3. **Seasonality:** Construction drops 10–20% in winter (northern markets).
4. **Project-driven churn:** Contractors may subscribe per-project, not permanently.

### Return Potential
| Scenario | ARR | Multiple | Exit |
|---|---|---|---|
| Acqui-hire | $500K | 3–5x | $1.5M–$2.5M |
| Strategic acquisition | $3M | 6–10x | $18M–$30M |
| Strong growth | $10M | 8–12x | $80M–$120M |
| Levelset-style | $30M+ | 10–15x | $300M–$450M |

Levelset sold to Procore for $500M. PlanGrid sold to Autodesk for $875M. ConTech exits command premium multiples.

**Lifestyle alternative:** $1M–$3M ARR at 80%+ margins = $800K–$2.4M/year pre-tax profit without selling.

**Verdict: Financial picture is excellent for a bootstrap. Lowest startup cost of any idea evaluated. Fastest path to profitability (31 customers). Biggest financial risk: churn treadmill + construction seasonality.**

---

## Final Verdict

### Overall Assessment
The most bootstrappable idea evaluated so far — lowest startup cost, fastest path to profitability, simplest technical build. The market gap between spreadsheets and $10K+/year enterprise tools is real. The competitive landscape is busy but no one owns the specific niche of "lightweight, all-in-one compliance for 5–25 person GC shops." This is a grind-it-out vertical SaaS play, not a moonshot.

### Top 3 Strengths
1. **Fastest path to revenue of any idea evaluated.** Solo founder can reach breakeven at 31 customers in 3–6 months. $30K–$60K total investment. 8–12 week MVP. No exotic tech needed.
2. **Excellent unit economics.** LTV:CAC of 13–50:1 depending on pricing. 86–97% gross margins. 2.4–5 month CAC payback. Strong exit comps ($500M Levelset, $875M PlanGrid).
3. **Real, quantifiable pain with catastrophic downside.** A single missed COI cost one GC $1M+. Compliance managers waste $40K/year on manual tracking. The ROI pitch writes itself.

### Top 3 Risks
1. **Crowded adjacent space with narrow window.** Contractor Foreman ($49), Knowify ($99), TrustLayer (free), BCS (free), LienWaiver.pro ($49) are all within striking distance. 18–24 months before convergence.
2. **SMB churn + construction seasonality.** 5% monthly churn = losing half your base yearly. Project-based buying adds churn pressure. Winter slowdowns compress revenue.
3. **"Feature, not product" risk.** If Procore/Autodesk/Buildertrend bundle compliance into existing affordable plans, standalone value erodes.

### Critical Questions
1. **Can you get 10 small GCs to pay $99–$199/month before building?** Pre-sell or letter-of-intent validates willingness to pay and specific feature priorities.
2. **What's your churn defense?** Annual contracts? Multi-project management? Historical compliance audit trail? The answer determines whether this is a sustainable business or a treadmill.
3. **Will you price at $99 or $199–$299?** The business model analysis strongly suggests repricing upward. $99 leaves money on the table when the alternative is $40K/year in admin labor.
4. **Do you have construction industry connections?** This is a relationship-driven market. Cold outreach to GCs is hard. Trade associations, referral partners, or a co-founder from the industry accelerates GTM dramatically.
5. **How do you build the sub-side network?** A shared compliance profile (sub fills out once, GCs pull from it) is the only path to real network effects and defensibility.

### Recommendation: GO

**This is the strongest GO of any idea evaluated.** Not conditional — just go.

The startup cost is trivial ($30K–$60K), the MVP is buildable in 8–12 weeks by a solo engineer, the path to profitability is 3–6 months, the unit economics are excellent, and the exit comps are outstanding. The competitive risks are real but manageable with speed and depth.

**Suggested execution:**
1. Build MVP in 8–12 weeks covering COIs + lien waivers for 5 high-volume states
2. Price at $199/month (not $99)
3. Get first 10 customers through AGC chapters, contractor forums, Google Ads
4. Validate retention metrics for 3 months
5. Then decide: bootstrap to $3M+ ARR lifestyle business, or raise seed for acceleration
