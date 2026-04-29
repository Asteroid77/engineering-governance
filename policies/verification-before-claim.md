Status: active
Owner: engineering-governance
Last verified: 2026-04-20
Source of truth: yes

# Verification Before Claim

## Rules

- Do not claim success, completion, correctness, or a fix without fresh verification.
- Fresh verification means evidence collected after the current change.
- Prefer the smallest verification that directly proves the changed behavior, then add wider checks when appropriate.
- If verification only covers part of the system, state the boundary explicitly.
- Do not extrapolate local evidence into global success.

## Acceptable Evidence

- Test output
- Build output
- Typecheck output
- Lint or static scan output
- Script output
- Runtime health check
- Smoke test
- `curl` or equivalent protocol check
- Direct file or config inspection when the change is documentation or static configuration

## Reporting

When reporting completion, include:

- What was verified
- The command or inspection used
- The result
- The boundary of the verification
- What was not verified, if material

