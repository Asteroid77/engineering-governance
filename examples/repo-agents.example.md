Status: example
Owner: engineering-governance
Last verified: 2026-04-29
Source of truth: no

# Agent Guide

## Governance Upstream

- Upstream: `<engineering-governance repository URL>`
- Version: `<tag or commit>`
- Local overrides:
  - `<only repository-specific differences>`

This repository follows upstream engineering governance by default. This file only records repository-specific context and explicit local overrides.

## Repository Goal

<What this repository owns and maintains.>

## Local Working Rules

- Follow upstream governance by default.
- Do not duplicate upstream policies in this file.
- Add only repository-specific rules that cannot live in shared governance.
- If this repository needs a specific worktree setup command, record it here, for example copying ignored `.env*` files or running the repository package manager to restore dependencies.

## Critical Commands

```bash
<command 1>
<command 2>
<command 3>
```

## Verification Standard

- Use the smallest verification that directly proves the change.
- Run broader repository checks when the change affects shared behavior.
- State verification boundaries when checks are partial.

## Directory Map

- `<path>`: `<responsibility>`
- `<path>`: `<responsibility>`

## High-Risk Areas

- `<path>`: `<risk>`
- `<path>`: `<risk>`

## Source Of Truth Docs

- Repository entry: `<path>`
- Documentation index: `<path>`
- Contribution rules: `<path>`
- Active plans: `<path>`
- Completed plans / decisions: `<path>`
