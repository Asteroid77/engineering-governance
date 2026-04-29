Status: template
Owner: engineering-governance
Last verified: 2026-04-20
Source of truth: yes

# Design Template

Use this template when a document must explain why a solution is chosen, where boundaries are, where the source of truth lives, and why alternatives were rejected.

## When To Use

- Use this template to converge goals, non-goals, constraints, boundaries, and design decisions.
- Use this template before writing an implementation plan when the solution boundary is not already settled.
- A design defines the solution and boundaries. It does not replace an implementation plan or handoff.

## Hard Rules

- New design documents must copy this template and keep the required top-level structure.
- Required sections, in order:
  - Metadata: `Status`, `Owner`, `Last verified`, `Source of truth`
  - `# <Topic> Design`
  - `## Background`
  - `## Goals`
  - `## Non-Goals`
  - `## Decision Summary`
  - `## Adopted Design`
  - `## Architecture And Responsibility Boundaries`
  - `## Source Of Truth`
  - `## Risks And Controls`
  - `## Acceptance Criteria`
- A design must explicitly state the problem, scope, responsibility boundaries, trust boundaries, source of truth, design-layer constraints, and major rejected alternatives.
- A design must not use `Task / Step / Run / Expected` as its main structure.
- A design must not make branch names, worktree paths, or temporary environment status its main subject; those belong in handoff documents.
- If external standards, official product constraints, or community best practices directly influence the design, record them in `External Evidence` or `References`.
- If something is not decided, mark it as `Open Question` and explain what blocks the decision.

## Optional Sections

- `## External Evidence`
- `## References`
- `## Related Docs`
- `## Migration Strategy`
- `## Open Questions`

Optional sections may add design context, but must not replace required sections.

## Template

```md
Status: active
Owner: <team-or-repo>
Last verified: YYYY-MM-DD
Source of truth: yes|no

# <Topic> Design

## Background

- <Current problem, context, constraints, and trigger>

## Goals

- <Design goals that must be achieved>

## Non-Goals

- <What this design explicitly does not solve>

## Decision Summary

- <One sentence describing the chosen direction>
- <One sentence explaining why main alternatives were not chosen>

## Adopted Design

- <Design overview>
- <Key decisions>
- <Trade-offs and rejected alternatives>

## Architecture And Responsibility Boundaries

- <Module/service/layer responsibilities>
- <Trust boundaries, call relationships, dependencies>
- <Which problems are solved at the design layer>

## Source Of Truth

- <Unique source of truth for rules/config/mapping/derived artifacts>
- <Owner>
- <Places that may reference but must not copy the rule>

## Risks And Controls

### Risk 1: <title>

- Risk:
  - <description>
- Control:
  - <control>

### Risk 2: <title>

- Risk:
  - <description>
- Control:
  - <control>

## Acceptance Criteria

- <How to know the design boundary and decision are settled>
- <Which later plan or implementation evidence will prove this design>

## External Evidence

- <Official docs / standards / community practice and the conclusion drawn>

## References

- <URL 1>
- <URL 2>
```

## Notes

- A design explains why, what, and where the boundaries are.
- If a design solves a constraint, later implementation plans should reference that boundary instead of inventing a second rule.

