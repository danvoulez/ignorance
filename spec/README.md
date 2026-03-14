# Spec — Protocol and Architecture Contract

This folder is where **theory becomes contract**. The specs fix the operational definitions that the book argues for and the code must satisfy. When book and spec conflict, spec wins for implementation; the book is then updated for consistency.

---

## Specs (Stubs)

| Spec | Purpose |
|------|----------|
| [canonical_cell_spec.md](canonical_cell_spec.md) | The nine fields, types, and invariants of the canonical cell |
| [ghost_record_spec.md](ghost_record_spec.md) | Ghost Record: identity, taxonomy, lifecycle, resolution conditions |
| [epistemic_state_spec.md](epistemic_state_spec.md) | Epistemic state: components, transitions, invariants |
| [proof_carrying_inference_spec.md](proof_carrying_inference_spec.md) | What each step must carry to justify continuity |
| [continuous_verifier_spec.md](continuous_verifier_spec.md) | Role and interface of the continuous verifier |
| [closure_fraud_spec.md](closure_fraud_spec.md) | When closure is allowed vs closure fraud |
| [logline_mapping_spec.md](logline_mapping_spec.md) | Mapping from canonical cell to LogLine protocol |
| [manager_plane_v2_spec.md](manager_plane_v2_spec.md) | Manager plane v2: events, receipts, witnesses, non-chat |
| [tdln_mapping_spec.md](tdln_mapping_spec.md) | Mapping from intention to TDLN / semantic form |
| [deterministic_gate_spec.md](deterministic_gate_spec.md) | Deterministic gates, CHECK boundary, content determinism |
| [unified_stack_spec.md](unified_stack_spec.md) | Four floors, components, and data flow |

---

## Conventions

- Each spec states: **scope**, **definitions**, **invariants**, **operations** (if any), and **references** to book chapters and formal models.
- Code in `src/` that implements a spec must reference it (e.g. in module docstring or README).

---

*Ignorance must take form.*
