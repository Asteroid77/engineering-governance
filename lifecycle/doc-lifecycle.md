Status: active
Owner: engineering-governance
Last verified: 2026-04-20
Source of truth: yes

# Documentation Lifecycle

## Category Rules

- `explanation/`: explains why a design works and emphasizes boundaries, state, request flow, and module relationships.
- `how-to/`: describes execution steps for local development, operations, performance, observability, and troubleshooting.
- `reference/`: provides lookup material such as contracts, token catalogs, script references, and test catalogs.
- `adr/`: records important architecture decisions.
- `plans/active/`: contains work still being executed, handed off, or not closed.
- `plans/completed/`: contains completed design and implementation plan records.
- `reports/`: contains reviews, audits, postmortems, and historical assessments.
- `generated/`: contains generated documentation and must not be hand-edited.
- `archive/`: contains material no longer maintained but still worth preserving.

## Ownership

- The `Owner` field declares who maintains the document.
- The `Last verified` field records the latest date the document was confirmed accurate.
- `Source of truth: yes` must be unique for a fact. Other documents should link or summarize.

## Document Boundary Rules

- `Design` documents answer why, boundary, source of truth, and decision trade-offs.
- `Implementation Plan` documents answer how to implement, how to verify, and each step's success criteria.
- `Handoff` documents answer current state, verified facts, open items, and continuation points.
- Do not mix these document types.

## Governance Templates

- New design documents start from `templates/design-template.md`.
- New implementation plans start from `templates/plan-template.md`.
- New handoff documents start from `templates/handoff-template.md`.
- Generic documents start from `templates/doc-template.md` only when they do not fit the three specialized templates.

## Plan Lifecycle

- New implementation plans default to `plans/active/`.
- When goals, verification, and follow-up actions are closed, move the plan to `plans/completed/`.
- The executor must proactively perform this move after confirming closure.
- If the related design is also closed and no longer serves unfinished active work, move it with the plan.
- Keep a design active only when it is still evolving or remains the source of truth for unfinished active work.

## Archive Rules

- Move fully superseded documents that are no longer current truth to `archive/`.
- Put review, audit, and postmortem records in `reports/`.
- Put generated artifacts in `generated/` and mark them as non-hand-edited.

## Governance References

- Google Documentation Best Practices
  - https://google.github.io/styleguide/docguide/best_practices.html
- Fuchsia RFC Best Practices
  - https://fuchsia.dev/fuchsia-src/contribute/governance/rfcs/best_practices
- AWS Prescriptive Guidance: Cutover runbook
  - https://docs.aws.amazon.com/prescriptive-guidance/latest/cutover-runbook/create-cutover-runbook.html
- Microsoft Cloud Adoption Framework: Document your cloud adoption plan
  - https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/plan/document-cloud-adoption-plan
- Atlassian async handoff guide
  - https://www.atlassian.com/blog/work-management/atlassians-guide-to-out-of-office-for-async-teams
- NIST Capital Facilities Information Handover Guide
  - https://www.nist.gov/publications/capital-facilities-information-handover-guide

