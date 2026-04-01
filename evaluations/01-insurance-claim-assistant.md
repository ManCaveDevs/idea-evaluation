# Evaluation: Insurance Claim Documentation Assistant

**Date:** March 28, 2026
**Status:** Evaluated

---

## The Idea

When your roof gets damaged or your basement floods, the insurance adjuster minimizes what you get paid. Public adjusters charge 10–15% of settlement. The product: film a walkthrough of damage, AI categorizes everything, generates a structured claim report with proper insurance language, flags what else to document (code upgrades, concealed damage, depreciation disputes), drafts your claim narrative. Revenue: $99–299 per claim.

---

## Role 1: Market Researcher

### Problem Validation
**This is a real, painful, high-stakes problem.**

- Underpayment is the norm. Insurance adjusters work for the carrier. In Florida, 46.7% of home insurance claims were closed without any payment in 2024 — up 17% since 2022.
- Documentation is the #1 lever — and homeowners blow it. Insufficient evidence is one of the most common reasons claims are denied or underpaid.
- Average claims cycle time hit 32.4 days in 2024 (worst since J.D. Power began tracking).
- After the January 2025 LA wildfires, 33,717 claims were filed. Six months later, 51% of total-loss survivors still had not settled. 62% reported being underinsured.

**Current alternatives:**
1. DIY (most common): Accept the first offer. Leave money on the table.
2. Public adjuster: 10–20% of settlement. On a $50K claim = $5,000–$7,500.
3. Attorney: 33–40% contingency. Only for large claims.
4. Contractor estimates: Helpful but limited insurance expertise.

### Target Customer
Middle-class homeowner filing a $5K–$100K property damage claim. Not wealthy enough to have "a person for this," not poor enough to be uninsured. They're stressed, displaced, and googling "what to do after roof damage."

**Reachability is good:** High-intent search at moment of need, geo-targeted ads to disaster ZIP codes, contractor/roofer referral partnerships, Nextdoor/Facebook groups.

**Challenge:** Low-frequency purchase. Most homeowners file a claim once every 10+ years. Crisis capture, not habit product.

### Market Size
- **TAM:** ~5.2M homeowner claims/year × $199 avg = **~$1.03B/year**
- **SAM:** ~60% are in the $2K–$100K sweet spot = ~3.1M claims × $199 = **~$620M/year**
- **SOM (Year 3–5):** 1–3% penetration = 31K–93K customers = **$6M–$18.5M ARR**

### Trends & Timing
- Billion-dollar weather disasters: averaged 9/year historically, **23/year from 2020–2024**
- Insured catastrophe losses growing 5–7% annually. Roof claims totaled $31B in 2024 (+30% from 2022)
- Insurers pulling out of high-risk states. Coverage gaps widening.
- AI technology for this use case only recently became viable at consumer price points
- 74% of insurers deploying AI — but almost entirely carrier-side. Consumer side dramatically underserved.
- Post-LA-fires regulatory environment increasingly sympathetic to policyholders

### Demand Signals
- The public adjuster industry ($10.8B claims adjusting market) exists specifically because homeowners can't navigate claims alone
- United Policyholders (nonprofit) surveyed 1,100+ LA wildfire survivors — massive unmet need
- The "adjuster-side" AI market is booming (Sprout.ai, EvolutionIQ, Guidewire), but almost nothing on consumer side
- CompanyCam found PMF in adjacent territory (structured photo documentation for insurance)
- Xactimate used by 80% of top insurers but no consumer version exists — classic asymmetry

**Verdict: There is a real market here. Confidence: HIGH (8/10).** The problem is painful, affects 5M+ households/year (growing due to climate), and the consumer side is dramatically underserved.

---

## Role 2: Business Model Analyst

### Revenue Model
Per-claim flat fee is the right structure. Subscription is absurd for something used once a decade.

**Recommended tiering:**
- $99: Basic documentation report (photo categorization, structured damage list)
- $199: Full claim narrative with insurance-standard language, supplemental checklist, contractor estimate cross-reference
- $299: Everything above plus claim review with second-pass analysis

**Important:** The "% of settlement delta" model is structurally dangerous — creates regulatory exposure (many states regulate who can take a percentage), potential unauthorized practice of adjusting. **Stick to flat-fee.**

### Unit Economics

**Cost-to-serve per customer:** ~$5–$15
- AI inference: $0.50–$3.00 (200 frames × multimodal LLM)
- Storage/processing: $0.10–$0.50
- Payment processing (Stripe): $3–$9
- Customer support: ~$1.25 average
- **Gross margin at $199: ~92–97%**

**CAC (the hard part):**
- SEO/content: $30–$60
- Google Ads (high-intent): $80–$150
- Contractor referral partnerships: $20–$50
- Geo-targeted post-disaster ads: $40–$80
- **Blended estimate: $50–$120**

**LTV = ~$175–$200** (one-time transaction, virtually no repeat in 5 years)

**LTV:CAC = ~2.1:1** (below the 3:1 healthy threshold)

### Pricing Power
- **For:** Extreme emotional urgency. Clear ROI framing ($199 vs. $5K+ for public adjuster). No competitor at this price.
- **Against:** Free content is abundant. ChatGPT could get a "decent" result for $20/mo. No switching costs. Hard to prove counterfactual value.
- **$99 is easy. $299 requires proof. Above $299, you compete with actual adjusters.**

### Scalability
- **Gets better:** AI quality improves with more claims, template library grows, SEO compounds, cost-to-serve drops
- **Doesn't improve:** Every customer acquired fresh (no habit loop, no network effect). Revenue is lumpy/seasonal (spikes after disasters).

### Dependency Risks
1. **Regulatory risk (HIGH):** If classified as unlicensed public adjusting, model collapses
2. **AI API dependency (MEDIUM-HIGH):** Third-party API pricing or policy changes
3. **Insurer countermove (MEDIUM):** Carriers could build self-service tools
4. **Channel concentration (MEDIUM):** Google Ads dependency

**Verdict: Strong gross margins but structurally challenged by one-time-purchase LTV and high CAC. Biggest structural risk: the LTV:CAC ratio is below healthy at 2.1:1. Needs breakthrough organic/referral channel or B2B expansion.**

### B2B Pivot Signal
Nearly every competitor (Tractable, Yembo, Sprout.ai) sells to carriers, not consumers. This is not a coincidence — B2B solves distribution, LTV, and regulatory problems simultaneously. The consumer model is contrarian. Could be a strength or a warning.

---

## Role 3: Competitive Landscape Analyst

### Direct Competitors

**Brelly** — The closest direct competitor.
- AI "Claims Copilot" for policyholders. Organizes documents, analyzes policies, drafts communications, flags issues.
- Currently in beta. Primary users: contractors, attorneys, public adjusters (not mainstream homeowners yet).
- **Gap:** Does NOT do video walkthrough + AI damage categorization. Text/document-centric, not vision-AI.

**Claim Navigator AI** — Second-closest.
- AI document generation and denial analysis for policyholders.
- Small/early-stage. Some packages delivered within 48 hours (suggesting manual involvement).
- **Gap:** No video/vision AI. Purely text-based.

### Insurer-Side Tech (Wrong Side of Table)

**Yembo (ScanMyHome)** — $13.9M raised, $10–25M revenue, ~56–69 employees
- Smartphone video → 3D models, floor plans, content inventories. Integrates with Xactimate.
- **Sells to insurers, not policyholders.** But has the core vision-AI tech. Could pivot.
- **Threat level: HIGH** (tech capability), **LOW** (incentive conflict with carrier customers)

**Tractable** — $185M raised, $1B valuation (SoftBank, Insight Partners)
- AI damage assessment processing $7B+ in annualized repairs. Expanding from auto to property.
- Insurer-facing. Not a policyholder tool.
- **Threat level: MODERATE** (channel conflict prevents near-term pivot)

**Avallon AI** (YC X25) — $4.6M seed. Insurer-facing claims automation.
**Verdex AI** (YC) — Satellite imagery for claim verification. Insurer-facing.

### Indirect Competitors
| Alternative | Cost | Weakness |
|---|---|---|
| Public adjusters | 10–15% of settlement | Expensive, workforce shrinking (400K projected attrition by 2026) |
| Attorneys | 33–40% contingency | Only for large claims |
| Contractors | Free (bundled with repair) | Conflict of interest, limited insurance expertise |
| DIY | Free | Consistently lower settlements |
| Xactimate | ~$200–300/month | Built for adjusters, not consumers |

### Key Finding
**The specific combination of video walkthrough + AI damage categorization + insurance-language report + proactive flagging does NOT exist as a consumer product today.**

### Moat Assessment: SHALLOW to MODERATE
- No deep tech moat (underlying AI is commodity)
- Domain expertise moat is real but narrow (claims terminology, carrier-specific knowledge)
- Data moat is aspirational (years of claims outcome data needed)
- Trust/brand moat is possible (being the "policyholder's advocate")

### Incumbent Risk
Verisk (Xactimate owner), Yembo, and Tractable have the pieces but face **incentive misalignment**: building a tool that helps policyholders maximize claims against their own carrier customers creates channel conflict.

**Verdict: Moderately defensible short-term (2–3 years). The window is ~18–24 months before serious competition arrives. Biggest threat: Brelly adding video/vision AI, or a well-funded new entrant (e.g., Avallon pivoting policyholder-side).**

---

## Role 4: Technical Feasibility Assessor

### Core Technical Challenge
The hard problem is NOT detecting damage — it's the semantic gap between "I see damage" and "wind-driven impact damage to laminated architectural shingles, 3 test squares showing 8+ hits per square, exceeding carrier threshold for full replacement at RCV with matching endorsement for undamaged slopes."

This is a **solved problem applied in a new way**, not a breakthrough. Components exist:
- Multimodal LLMs (Claude 4, GPT-4o) for image analysis + domain text generation
- Object detection (YOLOv8) for damage localization
- LLMs for insurance-grade narratives with domain prompting

### MVP Timeline: 10–14 Weeks
| Weeks | Milestone |
|---|---|
| 1–3 | Mobile video capture, keyframe extraction, upload pipeline |
| 4–6 | Multimodal LLM pipeline for damage categorization |
| 7–9 | Structured report generation with insurance terminology |
| 10–12 | "What else to document" flagging, UI polish |
| 13–14 | Testing with real adjusters, iteration |

### Tech Stack — What Exists
| Component | Solution |
|---|---|
| Video frame extraction | FFmpeg, OpenCV |
| Damage detection | Claude Vision, GPT-4o, Gemini 2.5 Pro |
| Report generation | Claude/GPT-4o structured outputs |
| Mobile capture | React Native / Swift / Kotlin |
| Cloud inference | AWS Bedrock, Anthropic API |

### What Needs Building from Scratch
1. Domain-specific prompt engineering pipeline (visual observations → insurance terminology) — **this is the core IP**
2. "What else to document" rules engine
3. Carrier-specific claim narrative templates
4. Confidence scoring / human-in-the-loop for uncertainty

### Data Requirements
- Property damage training datasets are scarce (unlike auto damage). MVP can use general VLMs with domain prompting — no custom training needed initially.
- Building codes by jurisdiction: publicly available but complex to systematize
- Historical claim outcomes: extremely hard to obtain without carrier partnerships

### Critical Hire
**Insurance domain expert** (former public adjuster or catastrophe adjuster) as co-founder or key early hire. This person bridges adjusting knowledge with AI system design.

### Scaling Risks
- LLM API costs at volume: 100 frames × $0.01–$0.05/image = $0.50–$5.00/claim. At 10K claims/day = $5K–$50K/day.
- Accuracy variance: water damage and structural issues harder to classify than roof damage
- Carrier-specific formatting scales linearly (maintenance burden)
- Liability if AI-generated narrative omits damage or uses incorrect terminology

**Verdict: Highly feasible (8/10). No fundamental research needed. Biggest build risk: domain accuracy at the terminology layer — the gap between "roof damage detected" and a report that survives carrier scrutiny.**

---

## Role 5: Financial Analyst

### Startup Costs to MVP
| Category | Estimate |
|---|---|
| Engineering (3–4 devs, 9–12 months) | $400K–$600K |
| AI/ML costs (APIs, fine-tuning) | $30K–$60K |
| Legal & compliance | $50K–$100K |
| Insurance domain expertise | $30K–$50K |
| Design & UX | $30K–$50K |
| Cloud infrastructure | $15K–$30K |
| Marketing launch | $25K–$50K |
| **Total** | **$630K–$1.0M** |

### Monthly Burn (Post-MVP, 6–8 person team)
~$90K–$130K/month

### Path to Profitability
- Breakeven: ~550 claims/month at $199 avg and $110K burn
- **Months 1–12:** Build, beta test. Revenue: ~$0.
- **Months 12–24:** Launch, grow to 100–300 claims/month. Revenue: $20K–$60K/mo.
- **Months 24–36:** Hit 500–800 claims/month with PMF. Revenue: $100K–$160K/mo.
- **Cash-flow positive: Month 28–36**

### Funding Strategy
| Stage | Amount | Source |
|---|---|---|
| Pre-seed | $300K–$500K | Angels |
| Seed | $1.5M–$3M | Insurtech VCs, YC |
| Series A (if needed) | $5M–$10M | VC |

**VC-backable? Conditionally.** $400M+ SAM, 85%+ gross margins, AI-native. But the consumer transactional model is harder to scale than B2B SaaS. VCs will want platform expansion path.

### Key Financial Risks
1. **Regulatory reclassification (CRITICAL):** States classifying this as unlicensed public adjusting
2. **Low frequency + high CAC:** LTV = one transaction. Every customer acquired fresh.
3. **Insurer pushback:** Rejecting or scrutinizing AI-generated documentation
4. **Liability exposure:** E&O risk if AI-generated reports cause claim denial
5. **Revenue lumpiness:** Spikes after disasters, near-zero in calm months

### Return Potential
| Scenario | Likelihood | Outcome |
|---|---|---|
| Failure | 30–40% | Lose capital |
| Lifestyle business ($2M–$5M ARR) | 20–25% | $5M–$15M valuation |
| Acquisition ($5M–$20M ARR) | 20–25% | $30M–$100M (5–8x revenue) |
| Venture-scale ($50M+ ARR) | 5–10% | $250M–$500M+ |

**Most realistic good outcome:** Build to $5M–$15M ARR, get acquired by a Snapsheet, Guidewire, or insurer for $30M–$80M.

**Verdict: Financial picture makes sense with caveats. 85%+ gross margins are excellent. Biggest financial risk: regulatory — spend $15K–$25K on insurance regulatory attorney opinions BEFORE writing any code.**

---

## Final Verdict

### Overall Assessment
This is a compelling product idea targeting a real, growing, high-stakes problem with excellent gross margins and a genuinely underserved consumer side. The technology is feasible and the competitive window is open. However, the business model has structural challenges — primarily the one-time-purchase LTV problem, regulatory ambiguity, and the question of whether the consumer-facing approach can achieve healthy unit economics at scale.

### Top 3 Strengths
1. **Massive, growing pain point with clear willingness to pay.** $50K claim + $199 tool vs. $5K public adjuster = obvious value. Climate change guarantees the market grows every year.
2. **The consumer side is genuinely wide open.** Every AI claims tool is built for insurers. The information asymmetry is stark and nobody has flipped it yet.
3. **Technology is ready and feasible.** Multimodal LLMs + domain prompting can deliver an MVP in 3 months. No breakthrough needed, 85%+ gross margins.

### Top 3 Risks
1. **Regulatory: Could be classified as unlicensed public adjusting.** This is existential. State-by-state insurance law, blurry line between "documentation tool" and "claims advocacy." Must get legal opinions before building.
2. **LTV:CAC economics are thin.** One-time purchase, no repeat behavior, high CAC for crisis-moment acquisition. ~2.1:1 ratio needs channel partnerships or B2B expansion to fix.
3. **18–24 month competitive window.** Brelly is already in beta on the policyholder side. Yembo has the vision-AI tech. Once it's proven, well-funded entrants will follow.

### Critical Questions
1. **Have you gotten a regulatory opinion?** In your target launch states, is an AI claim documentation tool legally distinct from public adjusting? This is question #1 and everything depends on the answer.
2. **Can you get a claims domain expert as co-founder?** The entire product quality hinges on insurance-specific knowledge that can't be faked with prompts alone.
3. **What's your distribution channel?** Direct-to-consumer Google Ads will bleed you dry. Contractor/restoration company partnerships are the likely answer — have you validated willingness to refer?
4. **Can you prove settlement uplift?** The product lives or dies on whether AI-generated documentation actually gets people more money. How do you measure and prove this?
5. **What's the B2B expansion story?** VCs and acquirers will want to know: does this stay consumer-only, or does it become a platform for contractors, public adjusters, and restoration companies?

### Recommendation: CONDITIONAL GO

**Conditions before building:**
1. Get written legal opinions from insurance regulatory attorneys in 3 target states (start with Florida, Texas, California). Budget $15K–$25K. If the answer is "this requires a public adjuster license," the idea is dead — pivot to B2B.
2. Secure a domain expert (former public adjuster or catastrophe adjuster) as co-founder or committed advisor. Non-negotiable.
3. Validate contractor referral channel — talk to 10 restoration companies and ask if they'd refer homeowners to this tool. If the channel exists, the CAC problem is solvable.

If all three conditions clear: **build it.** The market is real, the timing is right, and the window is open.
