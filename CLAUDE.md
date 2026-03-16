# Product Field — Claude Code Plugin

This repo IS the Product Field plugin for Claude Code. It provides the framework, commands, reference files, and templates that make the Product Field operational in AI-assisted product thinking.

**This is a plugin repo, not a product repo.** No product canvases live here. This repo produces the tooling that product repos consume.

## What We're Building

A Claude Code plugin that ships:
- **Commands** (`commands/`) — slash commands for each PF workflow step (`/pf:new`, `/pf:map`, `/pf:check`, etc.)
- **Reference files** (`reference/`) — domain knowledge loaded by commands on demand (aspect definitions, relational grammar, method library)
- **Templates** (`templates/`) — blank starting files copied into product repos (canvas, check, find, PRD)

Design spec: `docs/specs/2026-03-16-product-field-plugin-design.md`
Architecture decisions: `decisions/`

## The Product Field Framework

The PF treats product innovation as a complex adaptive system with a **geographic model** — a 2D coordinate system where spatial position encodes meaning.

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

**Two axes:** Introduction (Inside→Outside) and Realization (Purpose→Implementation).

**The fundamental movement is diagonal: IDEA (top-left) → MARKET (bottom-right).** The force field analysis reveals what pushes a product along this trajectory and what holds it back.

**Three layers:** Center (product), Core (problem, solution, uniqueness, alternatives), Context (8 outer aspects).

**Four corners:** IDEA (goals, drivers, uniqueness), VALUE (users, motivations, problem), RESOURCES (enablers, production, solution), MARKET (distribution, customers, alternatives).

**Relations:** Context aspects connect in a circular chain: GOALS→DRIVERS→ENABLERS→PRODUCTION→DISTRIBUTION→CUSTOMERS→USERS→MOTIVATIONS→GOALS. Each also connects to the core aspect in its quadrant.

**Four validation qualities:** Desirability (VALUE path), Viability (IDEA path), Feasibility (RESOURCES path), Marketability (MARKET path).

**Meta-method:** The PF doesn't prescribe how to gather insights — it provides the geographic structure that tells you where insights are needed. Established methods (JTBD, Lean Canvas, Design Thinking, etc.) each illuminate specific PF regions. When gaps appear, the position of the gap tells you which method to reach for.

**Workflow:** Frame → Map → Check → Find. Each step has a command. The canvas evolves through these steps and produces outputs (PRDs, backlog items, roadmap entries).

## Key Design Decisions

Read `decisions/` for full ADRs. Summary:

1. **Commands + reference files, not skills** — domain framework, not behavioral modification
2. **Independent plugin** — no dependency on superpowers or other plugins
3. **Full workflow from v1** — 9 commands covering the complete PF process
4. **Original content with CC BY-SA attribution** — PF model structure is open, our content is original
5. **Epistemic status tags** — every fact tagged verified/observed/believed/assumed/aspirational/visionary
6. **Adaptive questioning** — no checklists, user controls depth, inspired by GSD's discuss-phase pattern
7. **Backlog = ordered work items** — not a dashboard (that's `/pf:status`)
8. **No skill in v1** — product repo CLAUDE.md handles session awareness; gap-awareness skill in v1.1

## How to Work on This Repo

### Writing reference files

Reference files go in `reference/`. They contain **original content** — our own descriptions, questions, and method mappings. They are informed by `literature/` (gitignored source books) but never reproduce copyrighted content.

Each reference file is loaded by specific commands:
- `model.md` — loaded by commands needing geographic context
- `aspects.md` — loaded by `/pf:map`, `/pf:audit`, `/pf:find`, `/pf:import`
- `relations.md` — loaded by `/pf:check`
- `methods.md` — loaded by `/pf:find`, available to all commands

### Writing commands

Commands go in `commands/`. Each is a markdown file with YAML frontmatter (name, description, argument-hint). Commands load reference files via `@` references. Follow the patterns in the design spec for each command's behavior.

### Writing templates

Templates go in `templates/`. They're blank starting files that get copied into product repos. The canvas template must include:
- Geographic organization (aspects grouped by quadrant: IDEA, VALUE, RESOURCES, MARKET)
- Epistemic status tag placeholders
- Primary/supporting structure per aspect
- Force Field Assessment section

### Testing

Dogfood on the IDS products repo (`../ids/products/`). Every command should be tested there on real product work.

## Attribution

The Product Field is by Klaus-Peter Frahm, Michael Schieben, and Wolfgang Wopperer-Beholz (CC BY-SA 4.0 for the model). Mark is in discussion with Wolfgang about this integration. See `decisions/004-original-content-attribution.md`.

## Conventions

- Markdown for all files
- kebab-case for filenames
- Commands prefixed `pf-` (become `/pf:` in Claude Code)
- Core aspects lowercase (problem, solution, uniqueness, alternatives)
- Context aspects UPPERCASE (GOALS, DRIVERS, etc.)
- ADRs numbered sequentially in `decisions/`
