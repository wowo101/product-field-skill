# ADR-003: Full Workflow Commands From v1

**Date:** 2026-03-16
**Status:** Accepted

## Context

We could ship a minimal command set (just canvas creation + mapping) or the full workflow (new, import, map, audit, check, find, prd, status, consolidate).

## Options Considered

**A. Full workflow** — All 9 commands from v1.
**B. Canvas-centric** — 3 commands (new, map, status). Check and Find as canvas sections.
**C. Single entry point** — One `/pf:canvas` command that adapts to context.

## Decision

**Option A** — Full workflow. Each PF step gets its own command.

## Rationale

Each workflow step has a distinct purpose and loads different reference material. Discrete commands make the process legible ("I'm checking now, not mapping") and allow users to enter at any point. The full set also demonstrates the framework's depth from day one.

## Consequences

- 9 commands to build and test for v1
- Clear command-to-workflow-step mapping
- Users can skip steps or enter at any point
