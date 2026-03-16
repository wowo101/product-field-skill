# ADR-005: Plugin in Its Own Repo

**Date:** 2026-03-16
**Status:** Accepted

## Context

The framework content was initially developed inside the IDS products repo. We needed to decide where the distributable plugin lives.

## Options Considered

**A. Own repo** — Clean separation. Plugin is a consumer-agnostic package.
**B. Inside products repo** — Build in `products/plugin/`, extract later.
**C. Directly in `~/.claude/`** — Files in place, no repo wrapper.

## Decision

**Option A** — Own repo at `github.com/mark-jaeger/product-field-claude`.

## Rationale

Small extra cost to start clean. Makes the separation between "framework" and "project work" real from day one. It's what you'd share with Wolfgang or distribute to other companies. The IDS products repo becomes a clean consumer of the plugin.

## Consequences

- Plugin repo has no project-specific content
- IDS products repo CLAUDE.md slims down to reference the plugin
- Installation is: clone + symlink commands
