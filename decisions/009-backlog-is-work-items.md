# ADR-009: Backlog Is Ordered Work Items, Not Dashboard

**Date:** 2026-03-16
**Status:** Accepted

## Context

Early design conflated "portfolio dashboard" (status overview of all products) with "backlog" (ordered list of what to work on). These serve different purposes.

## Decision

- **`/pf:status`** produces the portfolio dashboard (read-only, derived from file existence)
- **`backlog.md`** is the ordered list of product work items — actionable next steps

## Rationale

A backlog in product development is an ordered list of work items: "validate this assumption," "research this competitor," "map this aspect," "write this PRD." Items are generated from canvas gaps, low-confidence facts, failed validation sentences, and workflow progression. The backlog turns PF analysis into action.

The portfolio dashboard is a different view — it shows where every product stands in the PF workflow. It's read-only and derived, not manually maintained.

## Consequences

- Backlog items include: action, target product, aspect/area, epistemic trigger
- Commands can add items to backlog (e.g., `/pf:check` adds "investigate broken relation")
- `/pf:status` and `backlog.md` are complementary, not redundant
