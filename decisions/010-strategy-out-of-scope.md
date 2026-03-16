# ADR-010: Strategy Formulation Out of Scope for v1

**Date:** 2026-03-16
**Status:** Accepted

## Context

The Product Field informs strategy (force field reveals where energy and risk are) but doesn't formulate strategy. The question was whether the plugin should include strategy guidance.

## Decision

Strategy formulation is out of scope for v1. The plugin focuses on the PF workflow (Frame, Map, Check, Find) and its outputs (PRD, backlog items). Strategy frameworks (Rumelt, Lafley/Martin) are candidates for v2's `/pf:strategy` command.

## Rationale

The PF reference guide does not cover strategy formulation. Adding strategy methods would require sourcing from other frameworks (Good Strategy Bad Strategy, Playing to Win) and designing how they integrate with the PF canvas output. This is significant work that should build on proven v1 usage.

## Consequences

- v1 `reference/methods.md` can reference strategy frameworks as "further reading"
- Force field output in `find.md` naturally feeds into strategy work
- v2 `/pf:strategy` command is on the plugin backlog
