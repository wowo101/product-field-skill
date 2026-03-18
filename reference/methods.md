# Product Field — Method Library

The Product Field is a meta-method: it shows you where insights are needed, and established methods are the tools you use to get them. This file maps common product methods to the PF regions they illuminate.

When a gap appears on your canvas — an empty aspect, a broken validation sentence, a weak corner — the position of the gap tells you which method to reach for.

This is a starter library. Teams can extend it with methods they already use.

---

## VALUE Corner Methods

These methods help you understand users, motivations, and problems.

### Jobs to Be Done (JTBD)

**PF territory:** USERS, MOTIVATIONS, problem, alternatives
**When to reach for it:** Thin USERS aspect, unclear MOTIVATIONS, problem feels assumed rather than validated, need to understand what alternatives are really competing with
**What it gives you:** Job statements ("When I..., I want to..., so I can..."), struggling moments, hiring/firing criteria for products
**Key references:** "Competing Against Luck" (Christensen), "Demand-Side Sales" (Moesta)

### Customer Interviews

**PF territory:** USERS, MOTIVATIONS, problem
**When to reach for it:** Any time you need direct evidence for the VALUE corner. Especially when facts are tagged `[assumed]` or `[believed]`
**What it gives you:** Validated (or invalidated) assumptions about users, their motivations, and the problem. Direct quotes that bring aspects to life
**Key references:** "The Mom Test" (Fitzpatrick), "Continuous Discovery Habits" (Torres)

### Design Thinking / Human-Centered Design

**PF territory:** USERS, problem, solution (desirability + feasibility)
**When to reach for it:** Need to deeply understand the user context, prototype solutions, test desirability before committing to build
**What it gives you:** Empathy maps, user journey maps, prototypes, usability findings
**Key references:** "The Design of Everyday Things" (Norman), IDEO Field Guide

### Assumption Testing

**PF territory:** Any aspect with `[assumed]` tags, especially primary facts
**When to reach for it:** Canvas has load-bearing assumptions that haven't been validated. Find reveals high-risk points built on assumed facts
**What it gives you:** Evidence that upgrades (or disproves) your assumptions. Prioritized list of what to test next
**Key references:** "Continuous Discovery Habits" (Torres), "Testing Business Ideas" (Bland & Osterwalder)

---

## IDEA Corner Methods

These methods help you clarify goals, align drivers, and sharpen uniqueness.

### Vision / Mission Workshops

**PF territory:** GOALS, DRIVERS, uniqueness
**When to reach for it:** GOALS are vague or conflicting, DRIVERS aren't aligned, uniqueness doesn't connect to organizational purpose
**What it gives you:** Shared strategic direction, prioritized goals, alignment among drivers

### Value Proposition Canvas

**PF territory:** uniqueness, problem, USERS (bridges IDEA and VALUE)
**When to reach for it:** uniqueness is unclear or doesn't connect to the problem users actually have
**What it gives you:** Explicit mapping between what you offer (value map) and what users need (customer profile). Highlights fit and misfit
**Key references:** "Value Proposition Design" (Osterwalder et al.)

### Blue Ocean Strategy

**PF territory:** uniqueness, alternatives, GOALS
**When to reach for it:** Competing head-to-head on a crowded alternatives landscape, need to find differentiation space
**What it gives you:** Strategy canvas, eliminate-reduce-raise-create grid, new uniqueness angles
**Key references:** "Blue Ocean Strategy" (Kim & Mauborgne)

---

## RESOURCES Corner Methods

These methods help you assess enablers, plan production, and design solutions.

### Lean Startup

**PF territory:** solution, PRODUCTION, ENABLERS (feasibility focus)
**When to reach for it:** High uncertainty about whether the solution can be built or whether it works. Need to validate quickly with minimal investment
**What it gives you:** MVPs, build-measure-learn cycles, pivots
**Key references:** "The Lean Startup" (Ries)

### Technical Spike / Proof of Concept

**PF territory:** solution, ENABLERS, PRODUCTION
**When to reach for it:** Feasibility sentence breaks at "empower production to build solution" — unclear whether the solution is technically achievable
**What it gives you:** Evidence that the technical approach works (or doesn't), identifies missing enablers

### Capability Assessment

**PF territory:** ENABLERS, PRODUCTION
**When to reach for it:** ENABLERS aspect is thin, unclear what's available vs. what's needed, or feasibility sentence breaks early
**What it gives you:** Inventory of available vs. required capabilities, gap analysis, build-vs-buy decisions

---

## MARKET Corner Methods

These methods help you understand distribution, customers, and alternatives.

### Competitive Analysis

**PF territory:** alternatives, uniqueness, CUSTOMERS
**When to reach for it:** alternatives aspect is thin, uniqueness hasn't been tested against real competitors, marketability sentence breaks
**What it gives you:** Competitive landscape map, feature comparison, positioning opportunities, switching cost analysis

### Business Model Canvas

**PF territory:** Spans the full field, emphasis on DISTRIBUTION, CUSTOMERS, ENABLERS, PRODUCTION
**When to reach for it:** Need a holistic business model view, especially when market-side aspects are underdeveloped
**What it gives you:** Revenue model, channel strategy, cost structure, key partnerships
**Key references:** "Business Model Generation" (Osterwalder & Pigneur)

### Customer Development

**PF territory:** CUSTOMERS, DISTRIBUTION, alternatives
**When to reach for it:** CUSTOMERS aspect is thin or assumed, distribution channels untested, unclear if customers will actually pay
**What it gives you:** Validated customer segments, willingness-to-pay data, channel effectiveness evidence
**Key references:** "The Four Steps to the Epiphany" (Blank)

### Go-to-Market Strategy

**PF territory:** DISTRIBUTION, CUSTOMERS, alternatives
**When to reach for it:** Marketability sentence breaks, distribution channels unclear, need a plan to reach customers and displace alternatives
**What it gives you:** Channel strategy, launch plan, customer acquisition approach, competitive positioning

---

## Cross-Corner Methods

These methods span multiple corners of the field.

### Lean Canvas

**PF territory:** problem, solution, uniqueness, CUSTOMERS, DISTRIBUTION, ENABLERS
**When to reach for it:** Early-stage product, need a quick overview across multiple aspects. Good for initial import material
**What it gives you:** One-page product hypothesis covering problem, solution, key metrics, channels, cost/revenue
**Key references:** "Running Lean" (Maurya)

### Wardley Mapping

**PF territory:** alternatives, ENABLERS, PRODUCTION, DISTRIBUTION (strategic landscape)
**When to reach for it:** Need to understand how the competitive landscape and technology stack will evolve, inform build-vs-buy decisions
**What it gives you:** Evolution-aware landscape map, strategic positioning, component analysis
**Key references:** "Wardley Maps" (Wardley)

### OKRs / Strategy Deployment

**PF territory:** GOALS, DRIVERS (bridges to execution)
**When to reach for it:** GOALS exist but aren't translating into action, viability sentence breaks at "goals lead drivers"
**What it gives you:** Measurable objectives with key results, alignment cascade, progress tracking

---

## Using This Library

**During `/pf:find`:** When a weakness is identified, suggest methods from the corresponding region. "Your VALUE corner is thin — Customer Interviews or JTBD would help fill in what's missing about your users and their motivations."

**During `/pf:check`:** When a validation sentence breaks, suggest methods that address the broken link. "The feasibility sentence breaks at 'empower production to build solution' — a Technical Spike would test whether this is actually buildable."

**During `/pf:map`:** When an aspect is hard to fill, suggest methods that generate the right kind of insight. "Having trouble with alternatives? A Competitive Analysis would map what's out there."

This library is extensible. Teams should add their own methods and map them to PF regions.

---

*This reference file contains original content. Method descriptions are our own summaries, not reproductions from the referenced books.*
