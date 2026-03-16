# Product Field — Claude Code Plugin

A Claude Code plugin that brings the [Product Field](https://productfield.com) framework to AI-assisted product thinking.

The Product Field (Frahm, Schieben, Wopperer-Beholz) treats product innovation as a complex adaptive system. It provides a geographic model — a 2D coordinate system where spatial position encodes meaning — and a structured workflow for exploring, validating, and evaluating product ideas.

This plugin makes the Product Field operational in Claude Code: structured commands for each workflow step, reference files for the domain model, and templates for product canvases and deliverables.

## Installation

```bash
git clone git@github.com:mark-jaeger/product-field-claude.git ~/.claude/product-field
ln -s ~/.claude/product-field/commands ~/.claude/commands/pf
```

## Commands

| Command | Purpose |
|---|---|
| `/pf:new <product>` | Create a new product canvas |
| `/pf:import <product> [path]` | Ingest existing material into a PF canvas |
| `/pf:map <product> [aspect]` | Guided questioning to fill the canvas |
| `/pf:audit <product>` | Check aspect placement, suggest corrections |
| `/pf:check <product>` | Validate relations, test core/context fit |
| `/pf:find <product>` | Evaluate strengths/weaknesses, force field, character |
| `/pf:prd <product>` | Derive PRD from validated canvas |
| `/pf:status` | Portfolio dashboard |
| `/pf:consolidate <product>` | Capture session insights into canvas |

## How It Works

Each product idea gets a **canvas** — the 12 aspects of the Product Field mapped by quadrant. The canvas evolves through four steps:

1. **Frame** → establish shared understanding
2. **Map** → gather facts, tag with epistemic confidence, rank by importance
3. **Check** → validate consistency using the relational grammar
4. **Find** → evaluate strengths/weaknesses, visualize the force field

The fundamental movement is diagonal: from **IDEA** (inside + purpose) to **MARKET** (outside + implementation). The force field analysis reveals what pushes a product along this trajectory and what holds it back.

## Project Structure

The plugin operates on a products repo — one per company/organization:

```
<company>-products/
  CLAUDE.md              # PF vocabulary + company context
  backlog.md             # Ordered product work items
  roadmap.md             # Time-sequenced commitments
  products/
    <product>/
      canvas.md          # The 12 PF aspects mapped
      check.md           # Validation results
      find.md            # Force field assessment
      prd.md             # Product requirements (output)
```

## Attribution

The Product Field is by Klaus-Peter Frahm, Michael Schieben, and Wolfgang Wopperer-Beholz. The Product Field model is licensed CC BY-SA 4.0. This plugin contains original content building on the Product Field framework.

## Status

Early development. See `docs/specs/` for design documentation and `decisions/` for architecture decision records.
