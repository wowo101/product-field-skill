# Product Field — Relations and Validation

The Product Field's grammar describes how aspects interact. These relations let you test whether a product's description is consistent and whether the innovation itself is coherent.

For what each aspect means, see `aspects.md`. For the overall model, see `model.md`.

## Context-to-Context Relations (The Circular Chain)

The eight context aspects form a circular chain. Each adjacent pair has a directional relationship — one leads to the next. The chain runs clockwise on the canvas:

| From | → verb | To | ← verb |
|------|--------|----|---------|
| GOALS | lead | DRIVERS | pursue |
| DRIVERS | rely on | ENABLERS | support |
| ENABLERS | empower | PRODUCTION | leverages |
| PRODUCTION | supplies | DISTRIBUTION | takes over from |
| DISTRIBUTION | reaches | CUSTOMERS | receive |
| CUSTOMERS | authorize | USERS | become |
| USERS | pursue | MOTIVATIONS | move |
| MOTIVATIONS | match | GOALS | match |

**How to read these:** "GOALS lead DRIVERS" means the organization's objectives direct the people driving the product. Going the other way, "DRIVERS pursue GOALS" means the drivers are working toward those objectives. Both directions should hold.

**Boundary blurriness is normal.** The guide notes that neighboring aspects can be somewhat blurry — goals and motivations, users and customers, production and distribution, drivers and enablers. Things can belong to either side or transition between them. This adds to the system's dynamics rather than being a problem.

### What a broken context chain link means

When a link in the chain doesn't hold, it reveals a disconnect:

- **GOALS don't lead DRIVERS** → the team isn't aligned with the strategic objectives, or the goals aren't clear enough to guide action
- **DRIVERS can't rely on ENABLERS** → the team lacks the capabilities or resources they need
- **ENABLERS don't empower PRODUCTION** → capabilities exist but aren't translating into productive output
- **PRODUCTION doesn't supply DISTRIBUTION** → what's being built isn't reaching the channels
- **DISTRIBUTION doesn't reach CUSTOMERS** → the channels aren't connecting with buyers
- **CUSTOMERS don't authorize USERS** → buyers aren't enabling actual usage (common in B2B)
- **USERS don't pursue MOTIVATIONS** → the product isn't actually helping users achieve what they want
- **MOTIVATIONS don't match GOALS** → what users need and what the organization wants to achieve are misaligned

## Context-to-Core Relations

Each context aspect also connects to a core aspect in its quadrant. These are direct or indirect interactions — the context shapes the core, and the core demands things of the context.

### IDEA corner → uniqueness

| From | → verb | Core | ← verb |
|------|--------|------|---------|
| GOALS | inform | uniqueness | suits |
| DRIVERS | shape | uniqueness | guides |

### VALUE corner → problem

| From | → verb | Core | ← verb |
|------|--------|------|---------|
| USERS | overcome | problem | hinders |
| MOTIVATIONS | confront | problem | impedes |

### RESOURCES corner → solution

| From | → verb | Core | ← verb |
|------|--------|------|---------|
| ENABLERS | make possible | solution | demands |
| PRODUCTION | builds | solution | requires |

### MARKET corner → alternatives

| From | → verb | Core | ← verb |
|------|--------|------|---------|
| DISTRIBUTION | tackles | alternatives | challenge |
| CUSTOMERS | replace | alternatives | influence |

### What a broken context-core link means

- **GOALS don't inform uniqueness** → the product's differentiation isn't connected to what the organization is trying to achieve
- **DRIVERS can't shape uniqueness** → the team doesn't have the vision or authority to make the product distinctive
- **USERS can't overcome the problem** → the problem exists but users can't get past it with this product
- **MOTIVATIONS confront a problem that doesn't impede them** → the problem may not be painful enough to drive adoption
- **ENABLERS don't make the solution possible** → you're trying to build something your capabilities don't support
- **PRODUCTION can't build the solution** → the solution design exceeds production capacity
- **DISTRIBUTION can't tackle alternatives** → your channels can't compete with how alternatives reach customers
- **CUSTOMERS won't replace alternatives** → buyers don't see enough reason to switch

## Core-to-Center Relations (Product)

The core aspects connect directly to the product at the center:

| Product | → verb | Core | ← verb |
|---------|--------|------|---------|
| PRODUCT | solves | problem | prompts |
| PRODUCT | realizes | solution | defines |
| PRODUCT | exhibits | uniqueness | differentiates |
| PRODUCT | surpasses | alternatives | is replaced by |

## The Four Validation Sentences

These are the key tool for testing core/context fit. Each sentence chains aspects through one corner, from context through core to the product. Fill them in with actual facts from the canvas and test whether they hold.

### Desirability (VALUE corner)

> **[product] solves [problem] which impedes [motivations] that move [users]**

Tests whether the product creates real user value. If this sentence holds, users have a genuine motivation, there's a real problem blocking them, and the product actually solves it.

**When it breaks:**
- "solves [problem]" breaks → the product doesn't actually address the problem, or the problem is poorly defined
- "impedes [motivations]" breaks → the problem exists but it's not really blocking what users care about — the problem may not be painful enough
- "that move [users]" breaks → the motivations described don't actually drive user behavior

### Viability (IDEA corner)

> **[goals] lead [drivers] to shape [uniqueness] that differentiates [product]**

Tests whether the product expresses a practical business idea. If this holds, the organization has clear goals, capable drivers pursuing them, and the result is a product with genuine differentiation.

**When it breaks:**
- "lead [drivers]" breaks → goals exist but the team isn't aligned with or directed by them
- "to shape [uniqueness]" breaks → the drivers are working hard but the product isn't becoming distinctive
- "that differentiates [product]" breaks → there's a claimed uniqueness but it doesn't actually set the product apart in practice

### Feasibility (RESOURCES corner)

> **[enablers] empower [production] to build [solution] realized in [product]**

Tests whether the product can be built with available resources. If this holds, the organization has the right capabilities, a production system that can use them, and together they can actually build the solution.

**When it breaks:**
- "empower [production]" breaks → capabilities exist but they're not translating into productive capacity
- "to build [solution]" breaks → the production system is running but it can't build what the solution requires
- "realized in [product]" breaks → the solution is being built but it's not coming together as a coherent product

### Marketability (MARKET corner)

> **[distribution] reaches [customers] who replace [alternatives] with [product]**

Tests whether there's a viable market. If this holds, the channels can reach enough buyers, those buyers are willing to switch from what they use today, and they'll switch to this product.

**When it breaks:**
- "reaches [customers]" breaks → the distribution channels can't actually connect with the target buyers
- "who replace [alternatives]" breaks → customers are reachable but they're not willing to switch from what they have
- "with [product]" breaks → customers are ready to switch but they're not choosing this product specifically

## How to Use These in Practice

### Running a check (`/pf:check`)

1. Read the canvas and pull out the primary facts for each aspect
2. Fill in each validation sentence with the actual content
3. Read each sentence out loud — does it make sense? Does it flow?
4. For each sentence: does evidence support the claim, or is it wishful thinking?
5. Where a sentence breaks, identify exactly which link fails
6. The broken link points you to the aspects that need work — go back to Map

### Reading the results

- **All four sentences hold and have evidence** → strong core/context fit. The product description is consistent and the innovation is coherent.
- **Sentences hold but lack evidence** → the description is consistent but unvalidated. You have a plausible story, not a proven one. Discovery priorities: gather evidence for the weakest links.
- **Sentences break** → inconsistency or incompleteness. Either the description has gaps (go Map), or the innovation itself has a real problem to solve.
- **Sentences produce unrelated statements** → possible product convolution. You might be describing two different products that have been merged. Consider whether to split.
- **Orphan facts** (facts that don't participate in any sentence) → either the fact is misplaced, or there's a missing counterpart elsewhere on the canvas.

### Tensions vs. contradictions

**Contradictions** are errors — two facts in the same aspect that directly conflict. ("Our primary users are dental practitioners" and "Our primary users are procurement officers" when both can't be true.) Flag these during import, resolve during Map.

**Tensions** are features — aspects pulling in different directions. ("GOALS want rapid growth but ENABLERS are limited" or "USERS want simplicity but the solution is technically complex.") These are the interesting findings. Surface them, don't try to eliminate them. Tensions reveal where strategic choices need to be made.

---

*The Product Field is by Klaus-Peter Frahm, Michael Schieben, and Wolfgang Wopperer-Beholz. The model structure is licensed CC BY-SA 4.0. This reference file contains original content building on the Product Field framework.*
