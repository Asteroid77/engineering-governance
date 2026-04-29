Status: template
Owner: engineering-governance
Last verified: 2026-04-20
Source of truth: yes

# Implementation Plan Template

Use this template when an accepted design or requirement must be split into executable, verifiable, and handoff-safe implementation steps.

## When To Use

- Use this template after design boundaries are settled and implementation can be planned.
- If the solution is still being debated, write a design first.
- A plan explains how to implement and verify. It must not rewrite the full design rationale.

## Hard Rules

- New implementation plans must copy this template and keep the required top-level structure.
- Required sections, in order:
  - Metadata: `Status`, `Owner`, `Last verified`, `Source of truth`
  - `# <Topic> Implementation Plan`
  - Summary fields: `Goal`, `Architecture`, `Tech Stack`
  - `## Related Design`
  - `## File Structure`
  - At least one `## Task N: ...`
  - `## Self-Review`
- Each `Task` must include:
  - `**Files:**`
  - At least one `- [ ] **Step N:**`
  - `Run:`
  - `Expected:`
- A step without verification is not a complete step. `Run` may be a command, test, build, smoke check, script, or explicit manual inspection action.
- File paths should be absolute in cross-repository or cross-workspace plans.
- Runtime, deployment, proxy, container, network, observability, permission, or security changes require health checks, smoke checks, or equivalent runtime verification.
- If the repository already has a source of truth, the plan must not add a second equivalent config entry, allowlist, or derivation rule.
- If a problem is already solved by design, schema, unified model, boundary validation, or generation pipeline, the plan must not add noisy fallback work.
- Unless the user explicitly requests it, a plan must not include `git commit`, `git push`, branch creation, or history cleanup steps.
- New implementation plans default to `docs/plans/active/`.
- Once the plan's goal, verification, and follow-up actions are closed, the executor must proactively move it to `docs/plans/completed/`.
- If the related design is also closed and no longer serves unfinished active work, move it with the plan. Keep it active only when it remains the source of truth for unfinished active work, and record why.

## Optional Sections

- `## Risks / Assumptions`
- `## Completion Summary`
- `## Implementation Notes`

Optional sections may add context, but must not replace required sections.

## Template

```md
Status: active
Owner: <team-or-repo>
Last verified: YYYY-MM-DD
Source of truth: yes|no

# <Topic> Implementation Plan

**Goal:** <verifiable implementation goal>

**Architecture:** <implementation boundary, source of truth, and key structure; summarize only what is needed from the design>

**Tech Stack:** <framework / services / tools / document format>

## Related Design

- `<related design document path>`

## File Structure

- Modify: `/absolute/path/to/file-a`
- Create: `/absolute/path/to/file-b`
- Delete: `/absolute/path/to/file-c`

## Task 1: <task title>

**Files:**

- Modify: `/absolute/path/to/file-a`
- Create: `/absolute/path/to/file-b`

- [ ] **Step 1: Prove current state**

Run:

```bash
<command>
```

Expected:

```text
<baseline evidence / failure mode / current behavior>
```

- [ ] **Step 2: Implement change**

Run:

```bash
<command or check>
```

Expected:

```text
<direct evidence that the change exists>
```

- [ ] **Step 3: Verify result**

Run:

```bash
<test / build / smoke / curl / script>
```

Expected:

```text
<success criteria>
```

## Task 2: <task title>

**Files:**

- Modify: `/absolute/path/to/another-file`

- [ ] **Step 1: ...**

Run:

```bash
<command>
```

Expected:

```text
<evidence>
```

## Self-Review

### Spec coverage

- Does this plan cover the accepted design scope?
- Is any design requirement missing from the tasks?

### Placeholder scan

- No `TODO`, `TBD`, `later`, `to be filled`, or vague "handle as needed" wording.

### Type consistency

- Terms, variables, service names, script names, and paths match the source of truth.
- No second equivalent naming scheme or config entry was introduced.
```

## Notes

- Split complex work into multiple tasks.
- `Expected` must state evidence, not just "success".
- If useful, add `## Completion Summary` when moving the plan to completed. Do not delete original tasks and verification records.

