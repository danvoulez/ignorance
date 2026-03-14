# Formal — Mathematical Defence

This folder is where the theory **defends itself mathematically**: Lean definitions and propositions, TLA+ protocol and lifecycle specs, SMT constraint models. Formal models are authoritative for the slice they cover; book and spec must not contradict them.

---

## Structure

| Path | Role |
|------|------|
| [lean/](lean/) | Definitions and propositions: state, ghost, operators, predicates, debt, closure |
| [tla/](tla/) | Protocol and lifecycle: protocol.tla, ghost_lifecycle.tla, closure_guard.tla, manager_plane_v2.tla, epistemic_router.tla |
| [smt/](smt/) | Constraint models: closure_allowed, closure_fraud, ghost_debt, admissibility, contradiction_budget |

---

## Conventions

- Lean: one file per conceptual cluster; propositions stated (and proved when feasible).
- TLA+: one spec per system or subsystem; invariants and properties documented in README.
- SMT: used for satisfiability and counterexample exploration; not full verification.

---

*Ignorance must take form.*
