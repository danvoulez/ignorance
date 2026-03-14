# Src — Software

This folder is the **reference implementation**: core types (state, claim, evidence, ghost, obligation, transition), engine (proposer, matcher, verifier, ghost engine, epistemic router, closure guard, manager), policies, adapters (LogLine, TDLN, manager plane, deterministic gate), and CLI. Code must satisfy the spec slice it claims to implement.

---

## Structure

| Path | Role |
|------|------|
| [core/](core/) | state, claim, evidence, obligation, ghost, transition |
| [engine/](engine/) | proposer, matcher, verifier, ghost_engine, epistemic_router, closure_guard, manager |
| [policies/](policies/) | ghost_spawn, resolution, escalation, debt, closure |
| [adapters/](adapters/) | logline, tdln, manager_plane, deterministic_gate |
| [cli/](cli/) | run_scenario, inspect_state, spawn_ghost, resolve_ghost, evaluate_closure |

---

## Conventions

- Python for Wave 2 reference impl; each module references the relevant spec.
- Tests and scenario runners live under experiments/ or alongside modules as appropriate.

---

*Ignorance must take form.*
