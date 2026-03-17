# The Product Field — Geographic Model

The Product Field is a map of everything that matters to a product's success. It lays out the people, forces, and decisions around a product in a way that makes gaps and connections visible.

This file describes how the map works. For what goes in each area, see `aspects.md`. For how the areas connect to each other, see `relations.md`.

## The Two Axes

Every product lives at the intersection of two tensions:

**Inside → Outside** (horizontal) — A product starts inside an organization and has to reach users and customers on the outside. This is the journey from creation to introduction.

**Purpose → Implementation** (vertical) — A product exists for a reason (why) and has to be built and delivered (how). This is the journey from intent to execution.

These two axes create four quadrants, and the product sits at the center.

### The Canvas

The canvas is the visual layout of these axes. Each area on the canvas has a fixed position based on whether it's more inside or outside, more purpose or implementation.

```
                          PURPOSE
                             ^
                             |
           IDEA              |              VALUE
        (inside+purpose)     |        (outside+purpose)
                             |
    GOALS ─── uniqueness ─── problem ─── MOTIVATIONS
      |                      |                      |
   DRIVERS                   |                   USERS
      |                      |                      |
  INSIDE ─────────────── [PRODUCT] ─────────────── OUTSIDE
      |                      |                      |
   ENABLERS                  |                 CUSTOMERS
      |                      |                      |
  PRODUCTION ── solution ─── alternatives ── DISTRIBUTION
                             |
        RESOURCES            |            MARKET
      (inside+impl)          |        (outside+impl)
                             |
                             v
                       IMPLEMENTATION
```

## Three Layers

The canvas has three layers, from the center outward.

### Center — The Product

The product itself. One canvas describes one product. Everything else on the canvas exists in relation to it.

### Core — The Value Proposition

The four aspects that define what the product promises:

- **problem** — what's in the way for users that this product addresses
- **solution** — how the product addresses it
- **uniqueness** — what makes this product different from what already exists
- **alternatives** — what people use today instead

These sit in the inner ring, closest to the product. They are the product's promise of value.

### Context — The World Around the Product

The eight aspects that make up the environment the product lives in — who's involved, what they want, and what's available:

- **GOALS** — what the organization wants to achieve with this product
- **DRIVERS** — the people and teams inside the organization pushing the product forward
- **ENABLERS** — the assets, skills, and know-how the organization can draw on
- **PRODUCTION** — the processes and systems that build the product
- **DISTRIBUTION** — the channels that get the product to customers
- **CUSTOMERS** — the people and organizations who pay for the product
- **USERS** — the people who actually use the product
- **MOTIVATIONS** — the needs and desires that drive users and customers

These form the outer ring. The context is what determines whether a product succeeds or fails — a great value proposition in the wrong context still fails.

### How the Layers Relate

Every fact about a product belongs to exactly one aspect. The core defines what the product promises; the context determines whether that promise can be kept. The grammar connecting them is in `relations.md`.

## Four Corners

The canvas groups naturally into four corners. Each corner tells a different part of the product's story.

### IDEA (top-left: inside + purpose)

Why we're doing this. The vision, ambition, and what makes it worth pursuing.

- Includes: GOALS, DRIVERS, uniqueness
- Tests for: **Viability** — is this a practical business idea?

### VALUE (top-right: outside + purpose)

Who needs this and why. The demand side — real people with real problems.

- Includes: USERS, MOTIVATIONS, problem
- Tests for: **Desirability** — does this create real value for users?

### RESOURCES (bottom-left: inside + implementation)

What we can build and how. The capabilities and execution machinery.

- Includes: ENABLERS, PRODUCTION, solution
- Tests for: **Feasibility** — can we actually build this?

### MARKET (bottom-right: outside + implementation)

How we reach people and what we're up against. Distribution, customers, competition.

- Includes: DISTRIBUTION, CUSTOMERS, alternatives
- Tests for: **Marketability** — can we reach enough people who'll switch?

## The Diagonal

The big journey of any product runs diagonally: from **IDEA** (top-left) to **MARKET** (bottom-right). You start with an internal vision driven by purpose, and you need to end up in an external market through implementation.

This is the main trajectory. The force field (below) shows what's pushing your product along this path and what's blocking it.

The other diagonal — **RESOURCES** to **VALUE** — is the supporting axis. Your capabilities enable value; demonstrated value justifies further investment.

## Core/Context Fit

A product works when its context (the people, capabilities, and market around it) supports its core (what it promises). When the organization's goals align with user needs, when enablers match what the solution requires, when distribution reaches the right customers — that's core/context fit.

You test this with four sentences, one per corner, that chain the aspects together. If the sentences make sense and hold up against evidence, you have fit. If they break down, you know exactly where the gap is. The sentences are in `relations.md`.

## Force Field

Once you've identified what's strong and weak about your product's context, you can see how these forces combine along the inside→outside axis:

- **Push** forces propel the product outward (strong drivers, clear goals, solid production)
- **Pull** forces attract the product from outside (user demand, market opportunity, customer willingness)
- **Drag** forces hold the product back (missing enablers, weak distribution, unclear problem)

Where drag forces cluster, that's your highest risk. Where push and pull align, that's your momentum. A healthy product shows a clear flow from inside to outside.

## Character Types

Every product has a character — defined by which corner contributes most to its success. When one corner clearly dominates:

- **Idea Push** — driven by strong internal vision. Clear goals, passionate drivers, distinctive uniqueness. The idea itself creates momentum. Risk: building something nobody asked for.
- **Value Pull** — driven by deep understanding of users. Strong problem-market fit pulls the product toward adoption. Risk: knowing what to build but struggling to build or distribute it.
- **Resources Push** — driven by strong capabilities. Powerful enablers and production push a solution into the world. Risk: a solution looking for a problem.
- **Market Pull** — driven by distribution and customer access. Strong channels and customer relationships pull the product to market. Risk: competing on distribution rather than value.

Most products are blends. The character tells you where your energy comes from and where you might be neglecting.

## Working With Other Methods

The Product Field doesn't replace other product methods — it shows you where they fit. It's a map that tells you which region needs attention, and established methods are the tools you use to explore that region:

- JTBD is great for the VALUE corner (understanding users, motivations, and the problem)
- Lean Canvas touches many areas, especially problem and solution
- Design Thinking focuses on desirability (VALUE) and feasibility (RESOURCES)
- Business Model Canvas spans the whole field with emphasis on MARKET and RESOURCES

When a gap appears on the canvas, its position tells you which method to reach for. See `methods.md` for the full mapping.

## Workflow

Four steps, each building on the last:

1. **Frame** — get oriented. Understand the map and agree on vocabulary.
2. **Map** — fill in what you know. Gather facts about each aspect, tag what's verified vs. assumed.
3. **Check** — test consistency. Do the pieces fit together? Run the validation sentences.
4. **Find** — evaluate. What's strong, what's weak? Where's the force field pushing, where is it dragging?

These build on each other, but you don't just march through them once. Each step can send you back to an earlier one — and when it does, it tells you exactly where to look:

- **Check breaks a validation sentence** → go back to Map for the specific aspects in that sentence. If "enablers empower production to build solution" doesn't hold, you know to dig into ENABLERS, PRODUCTION, or solution — not start over.
- **Check finds a relation with no evidence** → go back to Map to gather facts for that connection. An empty relation means you haven't explored how two aspects interact.
- **Find surfaces a weakness in a corner** → go back to Map to explore that area deeper, or to Check to understand which relations are failing there.
- **Find flags a primary fact tagged `[assumed]`** → that assumption is load-bearing. Go back to Map (or out to research) to validate it before building on it.
- **Audit catches a misplacement** → correct it, then re-run Check, because moving a fact between aspects changes which validation sentences it participates in.

The point: you never "go back and redo everything." The position of the gap on the canvas tells you exactly which aspect to revisit and which step to return to.

---

*The Product Field is by Klaus-Peter Frahm, Michael Schieben, and Wolfgang Wopperer-Beholz. The model structure is licensed CC BY-SA 4.0. This reference file contains original content building on the Product Field framework.*
