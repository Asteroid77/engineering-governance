Status: active
Owner: engineering-governance
Last verified: 2026-04-20
Source of truth: yes

# Source Of Truth

## Rules

- A shared fact must have one owner and one source of truth.
- Other documents and modules may summarize or link to the source of truth, but must not copy large equivalent bodies of rules.
- Shared rules, config, mappings, allowlists, switches, permission names, route policies, generated artifacts, and derivation relationships must converge on one model or generation source.
- Generated artifacts must be marked as generated and must not be hand-edited.
- If a local repository adapts this governance, its local `AGENTS.md` is an adapter, not a fork of the full shared governance text.

## Drift Signals

Treat these as design smells:

- Two files define the same allowlist.
- A runtime config and a generated config are both edited by hand.
- A template is copied into a repository and then modified without tracking upstream.
- A document repeats another source-of-truth document instead of linking to it.
- Different modules encode equivalent permission, routing, or security rules.

## Required Action

When drift is found:

1. Identify the true owner.
2. Move the rule to the owner.
3. Replace duplicates with references, generated output, or a shared API.
4. Add a check command when the invariant can be verified mechanically.

