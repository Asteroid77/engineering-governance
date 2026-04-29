Status: active
Owner: engineering-governance
Last verified: 2026-04-20
Source of truth: yes

# Completion Lifecycle

## Active And Completed

- `docs/plans/active/` contains work still being executed, handed off, or not fully closed.
- `docs/plans/completed/` contains completed design and implementation plan records that remain useful as historical evidence.

## Plan Closure Rule

- When an implementation plan's goal, verification, and follow-up actions are closed, the executor must proactively move it from `active/` to `completed/`.
- Do not wait for the user to ask whether the plan is completed.
- Add a completion summary when useful, especially when the verification boundary matters.

## Related Design Rule

- If the implementation plan references a design and that design is also closed, move the design to `completed/` with the plan.
- Keep the design in `active/` only when it still serves unfinished active work, is still evolving, or remains the current source of truth for future implementation.
- When a design stays active while its related plan completes, record the reason in the completed plan or active handoff.

## Handoff Rule

- A handoff remains active while it contains unresolved open items or continuation guidance.
- Move a handoff out of active only after the open items have either been completed, superseded by another active plan, or archived with clear historical status.

