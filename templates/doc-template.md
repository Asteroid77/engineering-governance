Status: template
Owner: engineering-governance
Last verified: 2026-04-20
Source of truth: yes

# Document Template

Use this fallback template only for formal documents that are not design, implementation plan, or handoff documents.

## When To Use

- Use this template only when the document is not:
  - `Design`
  - `Implementation Plan`
  - `Handoff`
- If the document explains design and boundaries, use `templates/design-template.md`.
- If the document splits implementation steps and verification, use `templates/plan-template.md`.
- If the document transfers current state and continuation points, use `templates/handoff-template.md`.

## Hard Rules

- New generic documents must copy this template.
- Do not use the generic template as a loophole for half-design, half-plan, or half-handoff documents.
- Required sections, in order:
  - Metadata: `Status`, `Owner`, `Last verified`, `Source of truth`
  - `# <Title>`
  - `## Purpose`
  - `## Scope`
  - `## Details`
  - `## Related Docs`
- Generic documents must not introduce a second source of truth. If another document owns the fact, link to it instead of copying large equivalent text.
- Generic documents should not contain full execution plans, full design rationale, or full handoff state.

## Template

```md
Status: active
Owner: <team-or-repo>
Last verified: YYYY-MM-DD
Source of truth: yes|no

# <Title>

## Purpose

- <why this document exists>

## Scope

- <what this covers>
- <what this does not cover>

## Details

- <core content>
- <constraints / notes>

## Related Docs

- `<related design / plan / handoff / how-to / reference>`
```

## Notes

- Suggested `Status` values: `active`, `completed`, `historical`, `generated`, `archived`.
- `Owner` names the team, repository, or module responsible for correctness.
- Update `Last verified` when the document is confirmed accurate.
- Only one document should have `Source of truth: yes` for a fact.

