Status: active
Owner: engineering-governance
Last verified: 2026-04-20
Source of truth: yes

# New Repository Adoption Checklist

Use this checklist when creating a new repository that should follow shared engineering governance.

## Steps

1. Create a root `AGENTS.md` from `examples/repo-agents.example.md`.
2. Fill in `Governance Upstream`:
   - upstream repository URL
   - version, tag, or commit
   - local overrides
3. Fill in repository-specific context:
   - repository goal
   - critical commands
   - directory map
   - high-risk areas
   - source-of-truth docs
4. Create local documentation directories:
   - `docs/governance/`
   - `docs/plans/active/`
   - `docs/plans/completed/`
   - `docs/reports/`
   - `docs/archive/`
5. Decide whether templates are referenced from upstream or projected locally.
6. If templates are projected locally, mark them as upstream-derived and avoid local divergence.
7. Add a documentation check command if the repository has scripts.
8. Run the repository's initial verification commands.

## Acceptance Criteria

- Root `AGENTS.md` is an adapter, not a copy of all upstream governance.
- Local rules only describe repository-specific differences.
- New design, plan, and handoff documents have clear template sources.
- `active` and `completed` plan directories exist.
- The repository has at least one documented verification path.

