Status: active
Owner: engineering-governance
Last verified: 2026-04-29
Source of truth: yes

# Default Working Mode

## Rules

- Treat all requirements as engineering work by default, not as one-off patching.
- Start by reading the current code, active plans, and repository documentation.
- Confirm responsibility boundaries, trust boundaries, and the source of truth before implementation.
- Do not introduce scattered fixes, side channels, duplicate configs, duplicate allowlists, or equivalent local rules.
- If the proposed implementation increases fragmentation, parallel truth sources, shared mutable state, rule drift, or manual synchronization, stop and redesign.
- Keep the solution no larger than the current requirement. Do not add speculative extension points or future-only abstractions.

## Exploration And Delivery Branches

- Do not use a worktree as the default response to every change. If the change is narrow, low-risk, already understood, and the current working tree is clean, implement it directly on the active delivery branch.
- When work is uncertain, broad, likely to involve trial and error, risky, parallel to other work, or blocked by a dirty working tree, start from the current integration baseline in an isolated worktree or branch named `spike/<topic>` or `wip/<topic>`.
- Exploration branches may contain frequent `wip(<scope>): ...` commits. These commits record investigation direction and intermediate findings, but they are not delivery history by default.
- Once the direction is stable, create clean delivery branches from the integration baseline: `feat/<topic>`, `fix/<topic>`, `docs/<topic>`, or `chore/<topic>`.
- A delivery branch should carry one coherent change set. Migrate only the relevant result from the exploration branch, and leave discarded experiments, temporary outputs, and scratch files behind.
- Delivery commits must be semantic, scoped, and verifiable. Do not preserve noisy exploration history unless each commit remains useful, reviewable, and independently defensible.
- Preserve traceability from delivery work back to exploration through one of:
  - commit body references to the source `spike/<topic>` branch and relevant WIP commit IDs
  - PR description references to the source spike and discarded alternatives
  - active plan, completed plan, or handoff references that record the exploration path
- If a WIP commit is directly reused, prefer `git cherry-pick -x <commit>` so the resulting delivery commit records the original commit hash.
- When integrating multiple delivery branches into a shared baseline, merge them one branch at a time with explicit merge commits, preferably `git merge --no-ff <branch>`, and run the smallest relevant verification after each merge. Avoid batching unrelated delivery branches into one multi-parent merge unless the user explicitly accepts the reduced bisect and review granularity.
- Do not commit local artifacts, temporary samples, scratch files, or generated side effects to delivery branches unless they are deliberately promoted to owned fixtures, documentation, or generated artifacts with a verification command.

## Worktree Setup

- A new worktree usually omits ignored local files. Copy required local-only environment files and machine-local config from the source workspace when they are needed for local verification, especially ignored `.env*` files.
- Only copy files that are intentionally local and ignored by git, or files the repository documentation explicitly says are safe to reuse. Never turn copied secrets, tokens, or ignored environment files into tracked changes.
- A new worktree may also miss dependency directories and generated local tool state. Restore them with the repository-declared setup command when one exists.
- If no setup command exists, infer conservatively from lockfiles and standard project files, then use the project package manager for the narrowest dependency restore needed for verification. Examples include `pnpm install --frozen-lockfile` for a `pnpm-lock.yaml` Node project, wrapper-based Maven or Gradle commands for Java projects, and `go mod download` or test-driven module download for Go projects.
- If the inferred command would update lockfiles, perform global installs, change system configuration, or fetch unusually broad toolchains, stop and ask for confirmation.

## Boundary Principle

Protection belongs at the boundary that owns the responsibility:

- Validate external input at ingress boundaries.
- Check permissions at authorization boundaries.
- Validate protocols at protocol boundaries.
- Control resource access at resource boundaries.
- Keep internal code simple once upstream design and boundary validation already guarantee the invariant.

## Responsibility Boundary Rule

Every implementation must preserve the responsibility boundaries already established by the target repository:

- Before changing code, identify which component, module, layer, package, service, adapter, public contract, or owner is responsible for the behavior.
- Place new behavior in the owner that already owns that responsibility, or explicitly create a new owner when the existing boundaries do not fit.
- Public contracts must expose the responsibility they own, not incidental implementation details or unrelated framework capabilities.
- Callers must not bypass the owner of a responsibility by depending directly on internal implementation details.
- Cross-boundary access must go through the repository's established public contracts, ports, adapters, APIs, or documented integration points.
- When a change introduces or changes dependency direction, public contracts, ownership, or responsibility boundaries, add or update structure tests or boundary tests where the repository has a testable boundary mechanism.
- Structure rules should describe responsibilities, package or layer patterns, dependency direction, or ownership rules. Avoid one-off restrictions for a single concrete class unless the repository intentionally defines that class as a boundary.

## Noise Rule

When a constraint is already solved by design, schema, type system, generated artifacts, or boundary validation, do not repeat the same constraint downstream through fallback branches, compatibility paths, duplicate config, duplicate allowlists, or noisy logs.

This does not remove required protections. It concentrates them where they are owned and verifiable.
