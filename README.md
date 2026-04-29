Status: active
Owner: engineering-governance
Last verified: 2026-04-20
Source of truth: yes

# Engineering Governance

This repository is the shared engineering governance source of truth for project-level agent rules, document templates, document lifecycle rules, and adoption guidance.

Business repositories should not copy this repository wholesale into their local `AGENTS.md`. They should keep a small repository-specific adapter that references this upstream governance repository and only records local differences.

## What This Owns

- Default engineering working mode
- Source-of-truth rules
- Verification-before-claim rules
- Completion lifecycle rules
- Document boundary rules
- Strong templates for `design`, `implementation plan`, `handoff`, and fallback documents
- Adoption playbooks for new and existing repositories

## What This Does Not Own

- Business repository goals
- Repository-specific commands
- Repository-specific directory maps
- Repository-specific high-risk modules
- Runtime secrets, deployment credentials, or environment-specific settings

## Repository Layout

- `AGENTS.md`: cross-repository agent rule entrypoint
- `policies/`: reusable engineering policy documents
- `templates/`: strong document templates
- `lifecycle/`: document lifecycle rules
- `adoption/`: playbooks for adopting this governance in repositories
- `examples/`: example local adapter documents for business repositories

## Adoption Model

Each business repository should keep its own root `AGENTS.md` as an adapter:

- Reference this governance repository and version.
- Keep local repository goal, commands, directory map, high-risk areas, and source-of-truth docs.
- List only local overrides.
- Do not duplicate the full upstream policy text.

Use:

- `adoption/new-repo-checklist.md` for new repositories.
- `adoption/existing-repo-migration.md` for existing repositories.
- `examples/repo-agents.example.md` as the local adapter starting point.

