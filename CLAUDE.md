# Idea Exploration & Validation

## What This Repo Is

This is the working directory for evaluating and building things that make money. The founder is a 27-year-old backend software engineer who can vibe code full-stack. Ideas range from small passive-income side projects to serious startup ventures.

## Key Files & Folders

- `startup-evaluation-prompt.md` — Full 5-role evaluation for serious ventures (startups, SaaS with growth ambitions). Deep analysis: market sizing, moats, competitive landscape, financials.
- `side-project-evaluation-prompt.md` — Lighter 3-role evaluation for income-generating side projects (tools, APIs, extensions, templates). Focused on: build speed, maintenance burden, effort-to-reward ratio, passive income potential.
- `past-ideas.md` — Rejected ideas with reasons and dates. **Always check before evaluating a new idea** — don't revisit dead ends.
- `evaluations/` — Completed evaluation reports. Naming convention: `s##-idea-name.md` for startup evals, `sp##-idea-name.md` for side project evals (zero-padded, sequential within each track). This prevents numbering conflicts between tracks.

## Which Evaluation to Use

- **Startup eval** → The idea has real growth potential, you'd go full-time on it, and you care about moats, market size, and scaling. Use `startup-evaluation-prompt.md`.
- **Side project eval** → You want passive income or a small revenue stream. You'd build it in a few weekends and it should mostly run itself. Use `side-project-evaluation-prompt.md`.
- **Not sure?** Ask: "Would I quit my job for this?" If yes → startup eval. If no → side project eval.
- If the user doesn't specify, ask which track before running the evaluation.

## How We Work

- **Be brutally honest.** No sugarcoating ideas. If something is too competitive or won't make money, say so immediately.
- **Do real research.** Use WebSearch and WebFetch to find competitors, funding data, and market sizes. Don't speculate — cite what you find. Name specific companies, their funding rounds, pricing, and traction.
- **No cliche ideas.** No to-do apps, AI agencies, generic SaaS, or overdone indie hacker retreads. The bar is high.
- **Validate before building.** Market research and competitive analysis come before any code.
- **When evaluating ideas**, use the appropriate framework — startup eval (5 roles) or side project eval (3 roles). See "Which Evaluation to Use" above.
- **When passing on ideas**, add them to `past-ideas.md` with the concept, specific reasons, date, and **type tag** (`[Startup]` or `[Side Project]`) so they can be filtered later.
- **Before evaluating any idea**, check `past-ideas.md` for duplicates or close variants. If it overlaps with a past idea, say so and stop unless the founder explicitly wants to revisit it.
- **Keep both trackers in sync.** After every evaluation, update the tracking table in the appropriate file — `startup-evaluation-prompt.md` for startup evals, `side-project-evaluation-prompt.md` for side project evals — with the verdict and link.

## Preferences

- Terse responses, no trailing summaries
- Show actual data (market sizes, competitor names, funding amounts) not vague claims
- Complex is fine if the moat is real
- B2B or B2C — open to anything
- Solo-buildable MVP is a must

## Comparing Ideas

When multiple ideas have Go/Build verdicts, or the founder asks to compare ideas, produce a side-by-side table. Use these **universal dimensions** that work across both evaluation tracks:

1. **Speed to revenue** — how fast can it charge money? (maps to "Speed to first dollar" in startup, "Build speed" + pricing in side project)
2. **Solo-buildability** — can the founder ship the MVP alone in a reasonable timeframe?
3. **Revenue ceiling** — what's the realistic monthly revenue at maturity?
4. **Maintenance / effort burden** — how much ongoing work after launch?
5. **Risk level** — regulatory, competitive, or platform dependency risk?

Pull from each evaluation's scorecard where dimensions align. For dimensions that don't map directly, make a judgment call and note it. Give a clear recommendation on which to pursue first.

**Cross-track comparisons** (startup idea vs. side project idea) are valid — sometimes a "worse" startup idea is a better side project, or vice versa. Note the tradeoff explicitly.

## After a Go / Build Verdict

Once an idea passes evaluation and the founder decides to build:

- Create `builds/<idea-name>/` with a 1-page README: MVP scope, target user, pricing, first customer channel
- Track build progress in `builds/<idea-name>/TODO.md`
- **Startup (Go):** No code until the "First 7 days" validation plan is complete. MVP goal: deployable in 2-4 weeks after validation.
- **Side project (Build):** Start building immediately per the launch plan. MVP goal: shippable in 1-2 focused weeks.
- Both: cut scope aggressively — the first version should do one thing well
- Both: honor the **kill criteria** defined in the evaluation. If the signal hits, stop — don't chase sunk costs.

## Common Requests

- **"Gut check [idea]"** — Give a 2-3 sentence honest take without running either framework. Flag obvious killers (saturated market, no monetization path, can't solo-build, regulatory nightmare).
- **"Evaluate [idea]"** — Ask which track (startup or side project) if not specified, then run the appropriate framework.
- **"Compare [idea A] vs [idea B]"** — Side-by-side table using scorecard dimensions. Clear winner recommendation. Works across both tracks.
- **"Research competitors for [X]"** — Use WebSearch. Return a table: company name, funding, pricing, traction, and what gap they leave open.
- **"What should I build?"** — Review all Go/Build evaluations across both trackers, compare using the universal dimensions above, and make a single recommendation with reasoning.
