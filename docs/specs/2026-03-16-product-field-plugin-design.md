# Product Field Claude Plugin — Design Spec

**Date:** 2026-03-16
**Status:** Draft
**Authors:** Mark Jaeger, Claude

## Overview

A Claude Code plugin that provides the Product Field framework as a structured product thinking tool. The plugin ships commands, reference files, and templates that guide users through the Product Field workflow: Frame, Map, Check, Find — and derive actionable outputs (PRDs, roadmaps) from validated product canvases.

The Product Field (Frahm, Schieben, Wopperer-Beholz, 2016) treats product innovation as a complex adaptive system. It provides a geographic model — a 2D coordinate system where spatial position encodes meaning — and a workflow for systematically exploring, validating, and evaluating product ideas.

### What this plugin does

- Provides the PF geographic model, aspect definitions, relational grammar, and method library as reference files
- Ships slash commands for each workflow step (new, import, map, check, find, prd, status, audit, consolidate)
- Provides templates for canvases, validation worksheets, evaluation reports, and PRDs
- Generates a CLAUDE.md snippet so any project repo can adopt PF as its product thinking vocabulary

### What this plugin does NOT do

- Prescribe strategy (the PF informs strategy but doesn't formulate it)
- Replace engineering execution (PRDs hand off to engineering repos; implementation is out of scope)
- Depend on other plugins (fully standalone, no superpowers dependency)

## The Product Field Model

### Geography

Two orthogonal axes define a 2D coordinate system:

- **Horizontal: Introduction** (Inside → Outside) — product originates inside, must reach outside
- **Vertical: Realization** (Purpose → Implementation) — product exists for a purpose, realized through implementation

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

**The fundamental movement is diagonal: from IDEA (top-left) to MARKET (bottom-right).** The force field analysis reveals what pushes a product along this trajectory and what holds it back.

### Three Layers

- **Center** — the product itself, at the origin
- **Core** (value proposition) — problem, solution, uniqueness, alternatives
- **Context** — GOALS, DRIVERS, ENABLERS, PRODUCTION, DISTRIBUTION, CUSTOMERS, USERS, MOTIVATIONS

### Four Elements (Corners)

- **IDEA** (inside + purpose) — goals, drivers, uniqueness
- **VALUE** (outside + purpose) — users, motivations, problem
- **RESOURCES** (inside + implementation) — enablers, production, solution
- **MARKET** (outside + implementation) — distribution, customers, alternatives

### Meta-Method Principle

The PF is not a method — it's a meta-method. It provides the geographic structure that tells you where insights are needed and how they connect. Established methods (JTBD, Lean Canvas, Design Thinking, etc.) each illuminate specific regions of the field. When Check or Find reveals a gap, the position of the gap tells you which method to reach for.

## Plugin Architecture

### Packaging Pattern

Commands + reference files (like GSD), not skills. Rationale: the PF is a domain framework, not behavioral modification. Commands explicitly load needed context. The product repo's CLAUDE.md provides session-level PF awareness.

```
product-field-claude/
  commands/                        # Slash commands — workflow entry points
    pf-new.md                      # /pf:new <product-name>
    pf-import.md                   # /pf:import <product-name> [path|text]
    pf-map.md                      # /pf:map <product-name> [aspect]
    pf-audit.md                    # /pf:audit <product-name>
    pf-check.md                    # /pf:check <product-name>
    pf-find.md                     # /pf:find <product-name>
    pf-prd.md                      # /pf:prd <product-name>
    pf-status.md                   # /pf:status
    pf-consolidate.md              # /pf:consolidate <product-name>
  reference/                       # Domain knowledge — loaded by commands on demand
    model.md                       # Geographic model (axes, corners, layers, diagonal)
    aspects.md                     # 12 aspects: definition, position, think-about, questions
    relations.md                   # Circular grammar, context-core links, validation sentences
    methods.md                     # Method library mapped to PF quadrants
  templates/                       # Blank starting files — copied into project repos
    canvas.md                      # Product Field canvas
    check.md                       # Validation worksheet
    find.md                        # Evaluation + force field template
    prd.md                         # Product Requirements Document
    roadmap.md                     # Lean roadmap
    claude-md-snippet.md           # CLAUDE.md section for adopting projects
  decisions/                       # Architecture Decision Records
  literature/                      # .gitignored — source books for reference extraction
  docs/specs/                      # Design specs
  README.md
  LICENSE
  .gitignore
```

### Installation (v1)

Clone the repo, symlink commands into `~/.claude/commands/pf/`:

```bash
git clone git@github.com:mark-jaeger/product-field-claude.git ~/.claude/product-field
ln -s ~/.claude/product-field/commands ~/.claude/commands/pf
```

### Future Distribution

Package for Claude Code plugin marketplace when format stabilizes.

## Project Structure (What the Plugin Creates)

Each company/organization gets one products repo. The plugin operates on this structure:

```
<company>-products/
  CLAUDE.md                        # PF vocabulary + company context
  backlog.md                       # Ordered list of product work items
  roadmap.md                       # OUTPUT: time-sequenced commitments
  products/
    <product-name>/
      canvas.md                    # The 12 aspects mapped by quadrant
      check.md                     # Validation: 4 sentence templates, core/context fit
      find.md                      # Evaluation: strengths/weaknesses, force field, character
      prd.md                       # OUTPUT: product requirements for engineering
      questionnaire.md             # Gap questionnaire (from import)
      import-sources.md            # Provenance log (from import)
      research/                    # Evidence: interviews, market data, analysis
  literature/                      # Optional: project-specific reference material
```

### File Ownership

All files are user-editable. Commands generate content, but the user owns it. No dot-folder separation — PF artifacts are the permanent work product, not scaffolding.

### Lifecycle

Each command produces files. `/pf:status` derives status from file existence:

| Command | Creates / Updates | Status (derived) |
|---|---|---|
| `/pf:new` | `canvas.md` (skeleton) | has canvas |
| `/pf:import` | `canvas.md` + `questionnaire.md` | has canvas + questionnaire |
| `/pf:map` | `canvas.md` (fills in aspects) | has canvas |
| `/pf:audit` | `canvas.md` (corrects placements) | has canvas |
| `/pf:check` | `check.md` | has check |
| `/pf:find` | `find.md` | has find |
| `/pf:prd` | `prd.md` | has prd |

`/pf:status` reports what exists per product (canvas, questionnaire, check, find, prd) and flags inconsistencies (e.g., prd without check). It does not track stages like "mapping" vs. "mapped" — that distinction lives in the canvas content (how many aspects are filled), not in file existence.

`/pf:consolidate` can update the canvas at any point from session insights.

## Command Specifications

### `/pf:new <product-name>`

Create a new product canvas and register it in the backlog.

1. Creates `products/<product-name>/canvas.md` from template
2. Adds a row to `backlog.md`
3. Asks a few framing questions to pre-fill Center + obvious aspects
4. Reports which aspects are filled vs. empty

**Reads:** `templates/canvas.md`
**Writes:** `products/<name>/canvas.md`, `backlog.md`

### `/pf:import <product-name> [path|glob]`

Ingest existing material and map onto a PF canvas. The brownfield onboarding ramp.

**Input flexibility:**
- No path argument: scan entire repo tree for documents
- Folder/file path: scan that specific location
- `@file` references: specific files
- Pasted text in conversation: process directly

**Phase 1 — Ingest:** Read all provided material. No limit on volume.

**Phase 2 — Extract:** Map content to PF aspects. Tag each extracted fact with epistemic status:
- `[verified]` — measured, confirmed, evidenced
- `[observed]` — seen but not systematically measured
- `[believed]` — team consensus, not yet tested
- `[assumed]` — untested, possibly unconscious
- `[aspirational]` — desired near-term state
- `[visionary]` — long-term directional

Flag narrow contradictions: two sources claiming different values for the same variable. Do NOT flag tensions between aspects — those are features, surfaced later in Check/Find.

**Phase 3 — Consolidate:** Directed questions to resolve contradictions and ambiguity. Walk through each conflict, ask user to resolve.

**Phase 4 — Gap Report:** Generate structured questionnaire for missing/thin aspects. Each gap includes:
- Which aspect is missing/thin
- Why it matters (what validation sentences depend on it)
- Specific questions to fill it
- Recommended methods if applicable

**Phase 5 — Write:**
- `products/<name>/canvas.md` — populated with findings
- `products/<name>/questionnaire.md` — gap questionnaire
- `products/<name>/import-sources.md` — provenance (what came from where)
- Add to `backlog.md`

### `/pf:map <product-name> [aspect]`

Guided adaptive questioning to fill in the canvas.

**Without aspect argument** (full session):
1. Read canvas, show current state (filled aspects, thin aspects, empty aspects)
2. Let user choose where to start (not force a sequence)
3. Per aspect: ask a few guiding questions, follow the thread based on answers
4. After a natural pause: "Want to go deeper here, or move to another aspect?"
5. Tag each new fact with epistemic status
6. Rank into primary/supporting within each aspect

**With aspect argument** (`/pf:map showroom users`):
Deep-dive a single aspect. Good for follow-up after check reveals a gap.

**Questioning style:** Adaptive, not checklist. Inspired by GSD's discuss-phase:
- Ask a few questions, see what comes back
- Follow threads based on answers (new questions inspired by what the user reveals)
- Let the user decide depth — "this is enough" is always valid
- No mandatory question count per aspect

**Reads:** `reference/aspects.md`, `reference/model.md`, `products/<name>/canvas.md`
**Writes:** `products/<name>/canvas.md`

### `/pf:audit <product-name>`

Check aspect placement — a teaching tool for PF literacy.

1. Read each aspect's content in the canvas
2. Compare against aspect definitions from `reference/aspects.md`
3. Flag potential misplacements: "You have 'dental trade shows' under PRODUCTION. This sounds like DISTRIBUTION."
4. Suggest moves, ask user to confirm each

**Reads:** `reference/aspects.md`, `products/<name>/canvas.md`
**Writes:** `products/<name>/canvas.md` (with user-confirmed corrections)

### `/pf:check <product-name>`

Validate consistency and core/context fit using the relational grammar.

1. Read canvas
2. Construct the 4 validation sentences using actual canvas content:
   - **Desirability:** "[product] solves [problem] which impedes [motivations] that move [users]"
   - **Viability:** "[goals] lead [drivers] to shape [uniqueness] that differentiates [product]"
   - **Feasibility:** "[enablers] empower [production] to build [solution] realized in [product]"
   - **Marketability:** "[distribution] reaches [customers] who replace [alternatives] with [product]"
3. Test circular relations with actual content
4. Surface tensions between aspects (these are features, not bugs — make them visible)
5. Report: which sentences hold, which break, which have gaps
6. Recommend specific aspects to revisit

**Reads:** `reference/relations.md`, `products/<name>/canvas.md`
**Writes:** `products/<name>/check.md`

### `/pf:find <product-name>`

Evaluate strengths/weaknesses, generate force field, determine character.

1. Read canvas + check results
2. For each mapped fact: evaluate as positive (+) or negative (−) for stakeholder impact, weighted by epistemic status
3. Aggregate per corner (IDEA, VALUE, RESOURCES, MARKET)
4. Generate force field narrative: what pushes toward IDEA→MARKET, what holds back
5. Determine character type (Idea Push, Resources Push, Market Pull, Value Pull)
6. Recommend methods from `reference/methods.md` for weakest corners
7. Identify highest-risk points on the diagonal
8. Generate discovery priorities: primary facts with low epistemic confidence that need validation

**Reads:** `reference/aspects.md`, `reference/methods.md`, `products/<name>/canvas.md`, `products/<name>/check.md`
**Writes:** `products/<name>/find.md`

### `/pf:prd <product-name>`

Derive a Product Requirements Document from a validated canvas.

1. Read canvas + check + find — **refuse if check or find don't exist**
2. Extract: problem statement, solution spec, risk assessment, feasibility notes
3. Generate PRD structured for engineering handoff
4. Flag unresolved weaknesses from find.md as risks/open questions

**Reads:** `templates/prd.md`, `products/<name>/canvas.md`, `products/<name>/check.md`, `products/<name>/find.md`
**Writes:** `products/<name>/prd.md`

### `/pf:status`

Portfolio dashboard — read-only view of all products.

1. Scan `products/*/` — check which files exist per product
2. Derive status from file existence (not metadata)
3. Show coverage per product (which aspects filled, epistemic quality)
4. Flag inconsistencies (e.g., prd.md without check.md)
5. Suggest next action per product

**Reads:** `products/*/`, `backlog.md`
**Writes:** nothing (read-only)

### `/pf:consolidate <product-name>`

Capture insights from free-flowing conversation into the canvas.

1. Review conversation history
2. Extract PF-relevant insights, tag with epistemic status
3. Map to aspects, compare against existing canvas
4. Show diff: new facts, reinforced facts, contradictions
5. User confirms before writing
6. Update canvas + optionally add work items to backlog

**Reads:** `reference/aspects.md`, `products/<name>/canvas.md`
**Writes:** `products/<name>/canvas.md`, optionally `backlog.md`

## Canvas Format

### Epistemic Status Tags

Every fact in the canvas is tagged with its confidence level:

```markdown
### USERS
**Primary:**
- Dental practitioners in private practices researching before purchasing [verified]
- Procurement officers in dental clinic chains comparing systematically [observed]

**Supporting:**
- Dental technicians needing material specs [assumed]
- Dental students researching during education [believed]
```

Tags: `[verified]`, `[observed]`, `[believed]`, `[assumed]`, `[aspirational]`, `[visionary]`

For aspirational/visionary items, optionally include temporal horizon: `[aspirational — Q2 2026]`, `[visionary — 2027+]`

### Primary/Supporting Ranking

No hard limit on facts per aspect. Instead, facts are ranked:

- **Primary:** The load-bearing facts. Used in validation sentences, force field assessment, and PRD requirements. Represent the convergence decision.
- **Supporting:** Additional context, nuance, future optionality. Preserved but not central to evaluation.

The `/pf:map` command guides ranking: "Which of these are the primary ones — the facts that matter most to this product's success?"

### Question-Based Coverage

Completeness is measured by question coverage, not fact count:

- Each aspect has guiding questions in `reference/aspects.md`
- Coverage = which questions have at least a basic answer
- Depth levels: basic (any answer), adequate (observed+, ranked), deep (verified, researched)
- The user decides target depth — "this is enough for me" is always valid

## Backlog

The backlog is an **ordered list of product work items** — actionable next steps generated from PF analysis:

```markdown
# Product Backlog

Ordered by priority. Items generated from canvas gaps, low-confidence
facts, failed validation sentences, and workflow progression.

1. Validate: dental labs would pay for API access [data-api, CUSTOMERS, assumed]
2. Research: competitive landscape for data-api [data-api, alternatives, empty]
3. Interview: showroom user segments [showroom, USERS, believed → verify]
4. Map: data-api canvas RESOURCES corner [data-api, ENABLERS+PRODUCTION, empty]
5. Write PRD: showroom-v2 [showroom, status: evaluated]
```

Items include: action, target product, aspect/area, epistemic trigger.

The backlog is NOT a portfolio dashboard (that's `/pf:status`) and NOT a roadmap (that's a time-sequenced commitment derived from the backlog).

## Reference Files

### `reference/model.md`
The geographic model: axes, corners, layers, diagonal, the meta-method principle. Loaded by commands that need model context.

### `reference/aspects.md`
The 12 aspects organized by quadrant. Each aspect includes:
- Definition (what it is, what it covers)
- Position (which quadrant, which layer)
- Think-about prompts (themes to explore)
- Guiding questions (open-ended, for adaptive questioning)
- Common misplacements (what gets confused with this aspect)

### `reference/relations.md`
- Context-to-context circular chain with bidirectional verbs
- Context-to-core relations
- The 4 validation sentence templates
- How to read a broken validation sentence (what it means, what to do)

### `reference/methods.md`
Starter library of product methods mapped to PF quadrants:

```markdown
## JTBD (Jobs to Be Done)
**PF territory:** VALUE corner (users, motivations, problem, alternatives)
**When to use:** Weak problem→MOTIVATIONS link, thin USERS aspect, need demand-side depth
**Key reference:** "Competing Against Luck" (Christensen)
**What it produces:** Job statements, struggling moments, hiring/firing criteria
```

Extensible — projects can maintain local method notes alongside.

## Version Roadmap

### v1 — Core Framework
All commands, reference files, templates, ADRs. Dogfood on IDS products.

### v1.1 — Gap Awareness + Discovery
- `/pf:discover` — assumption-testing plan from epistemic tags (Torres-inspired)
- Gap-awareness skill — ambient session awareness, nudges toward filling gaps
- Adaptive depth tracking — question coverage metrics

### v2 — Strategy + Portfolio
- `/pf:strategy` — strategy formulation from force field (Rumelt/Lafley-Martin)
- Portfolio-level force field comparison
- `/pf:compare` — side-by-side canvas comparison

## Design Decisions

See `decisions/` directory for full ADR trail. Key decisions:

1. Commands + reference files, not skills (domain framework, not behavioral mod)
2. Independent plugin, no superpowers dependency
3. Full workflow commands from v1
4. Original content with CC BY-SA attribution for PF model
5. Own repo, separate from project repos
6. No skill in v1 (CLAUDE.md handles session awareness; skill in v1.1)
7. Epistemic status tags on every fact
8. Adaptive questioning, no checklists
9. Backlog is ordered work items, not dashboard
10. Strategy out of scope for v1

## Attribution

The Product Field is by Klaus-Peter Frahm, Michael Schieben, and Wolfgang Wopperer-Beholz.
The Product Field model (geographic structure) is licensed CC BY-SA 4.0.
This plugin contains original content inspired by and building on the Product Field framework.
