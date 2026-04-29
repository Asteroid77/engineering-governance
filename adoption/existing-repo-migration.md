Status: active
Owner: engineering-governance
Last verified: 2026-04-20
Source of truth: yes

# Existing Repository Migration

Use this checklist when migrating an existing repository to shared engineering governance.

## Steps

1. Inventory local governance files:
   - root `AGENTS.md`
   - contribution docs
   - document templates
   - active/completed plan directories
   - ad hoc handoff or design documents
2. Classify existing documents:
   - design
   - implementation plan
   - handoff
   - generic document
   - report
   - archive candidate
3. Identify duplicated rules:
   - source-of-truth rules
   - verification rules
   - plan lifecycle rules
   - document boundary rules
   - generated artifact rules
4. Replace duplicated common rules with upstream references.
5. Keep only repository-specific context in root `AGENTS.md`.
6. Move or rewrite local templates to match upstream templates.
7. Review `docs/plans/active/`:
   - move closed plans to `completed/`
   - move related closed designs with their plans
   - keep only unfinished work in `active/`
8. Add or update a documentation check command.
9. Run the repository's relevant verification commands.

## Acceptance Criteria

- Root `AGENTS.md` is a repository adapter.
- Common governance rules point to the shared governance source.
- Local templates either match upstream or are clearly marked as local overrides.
- `active/` contains only active, handed-off, or unfinished work.
- Completed plans and closed single-use designs are in `completed/`.
- Verification evidence is recorded in the migration summary or final response.

