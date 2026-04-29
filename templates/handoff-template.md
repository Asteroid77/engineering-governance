Status: template
Owner: engineering-governance
Last verified: 2026-04-20
Source of truth: yes

# Handoff Template

Use this template when work has useful current state and verified findings but is not fully closed.

## When To Use

- Use this template to record current state, verified facts, open items, and continuation points.
- A handoff helps the next person continue without repeating discovery.
- A handoff does not replace a design or implementation plan.

## Hard Rules

- New handoff documents must copy this template and keep the required top-level structure.
- Required sections, in order:
  - Metadata: `Status`, `Owner`, `Last verified`, `Source of truth`
  - `# <Topic> Handoff`
  - `## Current Context`
  - `## What Is Already Done`
  - `## Conclusions Already Reached`
  - `## Verified Findings`
  - `## Open Items`
  - `## Recommended Next Steps`
  - `## Risks / Caveats`
- A handoff must distinguish verified facts, unfinished items, and next-step recommendations.
- A handoff may record branch, worktree, environment status, entrypoints, and blockers, but only to help continuation.
- A handoff must not rewrite full design trade-offs or become a task checklist.
- If a conclusion is a guess, inference, or pending confirmation, label it explicitly.
- A handoff must link relevant documents so the next person does not repeat scavenger-hunt discovery.

## Optional Sections

- `## Environment`
- `## Branch / Worktree`
- `## Related Docs`
- `## Contacts`

Optional sections may help transfer context, but must not replace required sections.

## Template

```md
Status: active
Owner: <team-or-repo>
Last verified: YYYY-MM-DD
Source of truth: yes|no

# <Topic> Handoff

## Current Context

- <current phase>
- <environment / entrypoint / workspace status>

## What Is Already Done

- <completed work>
- <landed changes>
- <updated docs / config / environment>

## Conclusions Already Reached

- <decisions and conclusions that can be reused>
- <boundaries that should not be re-litigated>

## Verified Findings

- <checks performed>
- <facts observed>
- <proven or disproven hypotheses>

## Open Items

- <unfinished items>
- <facts still pending>
- <current blockers>

## Recommended Next Steps

1. <first thing the next person should do>
2. <second action>
3. <third action>

## Risks / Caveats

- <likely pitfalls or misreadings>
- <environment, permission, or dependency limitations>

## Related Docs

- `<related design>`
- `<related implementation plan>`
- `<related how-to / reference>`
```

## Notes

- The most important handoff content is verified facts and the next valid entrypoint.
- Do not make the next person rediscover what is already known.

