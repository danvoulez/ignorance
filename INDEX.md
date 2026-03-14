# Index — Ignorance Must Take Form

Master index for the monorepo. Use this to jump to the right layer.

---

## By Role

| You want to… | Go to |
|--------------|--------|
| Understand the thesis in one page | [README.md](README.md) (top), [book/ABSTRACT.md](book/ABSTRACT.md) |
| See how the work is rolled out | [ROADMAP.md](ROADMAP.md) |
| Understand research posture and rules | [RESEARCH_CHARTER.md](RESEARCH_CHARTER.md) |
| Read the book by part and chapter | [book/INDEX.md](book/INDEX.md) |
| Check living docs and decisions | [docs/README.md](docs/README.md) |
| Read formal specs (cell, ghost, closure, etc.) | [spec/README.md](spec/README.md) |
| See formal definitions and proofs | [formal/README.md](formal/README.md) |
| Run or read experiments | [experiments/README.md](experiments/README.md) |
| Understand or run the software | [src/README.md](src/README.md) |
| Use figures and tables | [assets/README.md](assets/README.md) |
| Follow references and sources | [refs/README.md](refs/README.md) |
| Build, check, export | [scripts/README.md](scripts/README.md) |

---

## By Concept

| Concept | Book | Spec | Formal | Code |
|--------|------|------|--------|------|
| Canonical cell | Part I, ch. 3–5 | canonical_cell_spec | — | core/ (state, transition) |
| Ghost Record | Part V | ghost_record_spec | lean/ghost.lean, tla/ghost_lifecycle | core/ghost.py, engine/ghost_engine |
| Epistemic state | Part VI, ch. 29 | epistemic_state_spec | lean/state.lean | core/state.py |
| Proof-Carrying Inference | Part VI, ch. 30 | proof_carrying_inference_spec | — | engine/verifier.py |
| Continuous Verifier | Part VI, ch. 31 | continuous_verifier_spec | — | engine/verifier.py |
| Closure / Closure Fraud | Part VII, ch. 38–39 | closure_fraud_spec | lean/closure.lean, smt/ | engine/closure_guard.py |
| LogLine | Part VIII, ch. 42–44 | logline_mapping_spec | — | adapters/logline_adapter |
| Manager plane | Part X, ch. 55–57 | manager_plane_v2_spec | tla/manager_plane_v2 | engine/manager.py, adapters/ |
| TDLN / deterministic gates | Part IX | tdln_mapping_spec, deterministic_gate_spec | — | adapters/tdln_adapter, deterministic_gate_adapter |
| Unified stack | Part XI | unified_stack_spec | — | src/ (full) |

---

## By Part (Book)

| Part | Title | Folder |
|------|--------|--------|
| — | Front matter | book/00_front_matter/ |
| I | The Search for Form | book/01_the_search_for_form/ |
| II | Causality, Collapse, and Doubt | book/02_causality_collapse_and_doubt/ |
| III | The Computational Scientific Method | book/03_the_computational_scientific_method/ |
| IV | The Epistemic Crisis of Generative Systems | book/04_the_epistemic_crisis_of_generative_systems/ |
| V | Ghost Records | book/05_ghost_records/ |
| VI | Governed Reasoning | book/06_governed_reasoning/ |
| VII | Debt, Fraud, and the Right to Continue | book/07_debt_fraud_and_the_right_to_continue/ |
| VIII | The Protocol of Action | book/08_the_protocol_of_action/ |
| IX | From Semantics to Bytes | book/09_from_semantics_to_bytes/ |
| X | What Runs Above Software | book/10_what_runs_above_software/ |
| XI | The Unified Stack | book/11_the_unified_stack/ |
| XII | The Mathematical Core | book/12_the_mathematical_core/ |
| XIII | Building the System | book/13_building_the_system/ |
| XIV | Evaluation | book/14_evaluation/ |
| XV | The Philosophical Consequence | book/15_the_philosophical_consequence/ |
| XVI | The Manifesto | book/16_the_manifesto/ |
| — | Appendices | book/appendices/ |
