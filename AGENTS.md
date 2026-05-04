Status: active
Owner: engineering-governance
Last verified: 2026-04-29
Source of truth: yes

# Shared Agent Guide

## Default Working Mode

- All requirements default to engineering-mode implementation. Unless the user explicitly accepts a temporary patch, do not proceed through scattered fixes, side channels, or multi-point manual synchronization.
- Before implementation, identify responsibility boundaries, trust boundaries, and the single source of truth. Shared rules, policies, config, mappings, allowlists, switches, and derivation logic must converge on one owner or generation source.
- Generated artifacts may only be derived from the unique source of truth. They must have a generation script or verification command, and generated files must not be hand-edited.
- When a problem is reliably solved by upstream design, a unified model, schema, type system, boundary validation, or generation pipeline, do not add duplicate downstream fallbacks, compatibility branches, duplicate allowlists, duplicate config, or noisy logs expressing the same constraint.
- Required input validation, permission checks, protocol checks, resource access controls, and high-risk failure protections must remain, but they must live at the boundary that owns the responsibility. Do not replace boundary defenses with repeated internal noise.
- If an implementation would increase fragmentation, parallel sources of truth, shared mutable state, rule drift, or manual synchronization cost, stop and converge the design first.
- Without fresh verification, do not claim completion, correctness, or a fix. Conclusions must be based on current command, test, build, runtime, or inspection evidence.

## Exploration And Delivery Branches

- Do not make worktrees the default for every change. When the requested change is narrow, low-risk, and the current working tree is clean, work directly on the active delivery branch.
- Use an isolated `spike/<topic>` or `wip/<topic>` branch/worktree for uncertain, broad, exploratory, risky, parallel, or dirty-workspace work.
- `wip(<scope>): ...` commits are acceptable inside exploration branches and may record intermediate reasoning, but exploration branches are not delivery branches by default.
- Once the result is clear, create clean delivery branches from the integration baseline: `feat/<topic>`, `fix/<topic>`, `docs/<topic>`, or `chore/<topic>`.
- Delivery branches must contain one coherent, verifiable change set. Migrate the result, not the entire noisy exploration history.
- Preserve traceability through commit bodies, PR descriptions, plan/handoff references, or `git cherry-pick -x` when reusing a WIP commit directly.
- When integrating multiple delivery branches into a shared baseline, merge them one branch at a time with explicit merge commits, preferably `git merge --no-ff <branch>`, and run the smallest relevant verification after each merge. Avoid batching unrelated delivery branches into one multi-parent merge unless the user explicitly accepts the reduced bisect and review granularity.
- Keep temporary artifacts, scratch files, and incidental generated side effects out of delivery branches unless they are explicitly promoted to owned project assets with verification.
- When creating a worktree, bring over required local-only environment files and machine-local config needed for verification, such as ignored `.env*` files. Never add copied secrets or ignored environment files to delivery commits.
- After creating a worktree, restore missing dependencies or tooling with the repository-declared setup command first. If no setup command exists, infer conservatively from lockfiles and standard project files, use the project package manager, and avoid global installs or broad environment changes unless explicitly requested.

## Document Workflow

- Use `templates/design-template.md` when the work needs a design decision, boundary definition, or source-of-truth decision.
- Use `templates/plan-template.md` when the design is accepted and the work must be split into executable and verifiable implementation tasks.
- Use `templates/handoff-template.md` when work is not fully closed and the next person needs current state, verified findings, and continuation points.
- Use `templates/doc-template.md` only for formal documents that are not design, implementation plan, or handoff.
- Keep `design`, `implementation plan`, and `handoff` responsibilities separate. Do not mix them into one document.

## Completion Lifecycle

- New implementation plans default to `docs/plans/active/`.
- When an implementation plan's goal, verification, and follow-up actions are closed, the executor must proactively move it from `docs/plans/active/` to `docs/plans/completed/` without waiting for a separate reminder.
- If the related design is also closed and no longer serves other unfinished active work, move it to `docs/plans/completed/` with the plan.
- Keep a design in `active/` only when it is still evolving or remains the source of truth for other unfinished active work. Record the reason in the related plan or handoff.

## Local Repository Adapter Rule

Each business repository keeps a local root `AGENTS.md` for repository-specific context only:

- Repository goal
- Critical commands
- Directory map
- High-risk areas
- Local source-of-truth documents
- Governance upstream version
- Local overrides

Do not copy this full shared guide into every repository. The shared governance repository remains the source of truth for common rules.
