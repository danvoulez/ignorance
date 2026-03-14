# TASKS
## Ignorance Must Take Form — Execution Plan

This file is the **execution plan** for a model or contributor working in this repository. Tasks are ordered by phase and dependency. Check off items as they are completed; add new tasks at the end of the appropriate section.

**Canon:** Follow `PROMPT_ENTRYPOINT.md`, `Book.toml`, `docs/non_negotiables.md`, and the specs. Do not violate the handoff kit.

---

## Phase 0 — Canon (stabilize language and structure)

- [x] Root README, RESEARCH_CHARTER, ROADMAP, INDEX, PHILOSOPHY, CONTRIBUTING
- [x] Book.toml as source of truth; project skill book-toml
- [x] docs/glossary.md, docs/non_negotiables.md, docs/open_questions.md
- [x] PROMPT_ENTRYPOINT.md with read order and guardrails
- [x] spec/canonical_cell_spec.md, ghost_record_spec.md, epistemic_state_spec.md
- [x] spec/continuous_verifier_spec.md, closure_fraud_spec.md
- [x] spec/unified_stack_spec.md, manager_plane_v2_spec.md
- [ ] Harden glossary: ensure every term used in specs has an entry; align with Book.toml core_concepts
- [ ] Resolve or document any conflict between docs/decision_log and current layout

---

## Phase 1 — Formal core (minimum objects and operators)

- [ ] Define minimal formal epistemic state (see docs/open_questions.md §1.1)
- [ ] Define minimal transition algebra: which of spawn_ghost, resolve_ghost, dismiss_ghost, escalate_ghost, propose_claim, attach_evidence, evaluate_closure are primitive (open_questions §1.2)
- [ ] formal/lean: add core.lean or state.lean with epistemic state and cell types (stub or minimal)
- [ ] formal/tla: add protocol.tla or ghost_lifecycle.tla stub
- [ ] formal/smt: add closure_allowed.smt2 or admissibility.smt2 stub
- [ ] Document “healthy trajectory” topology or defer explicitly (open_questions §1.3)

---

## Phase 2 — Protocol physics (transitions, lifecycle, admissibility)

- [ ] Spec: refine logline_mapping_spec.md (map canonical cell to LogLine)
- [ ] Spec: refine proof_carrying_inference_spec.md (what each step must carry)
- [ ] formal/tla: specify ghost lifecycle (spawned → refined | resolved | split | merged | dismissed | escalated)
- [ ] formal/tla or smt: specify closure preconditions and closure_blocked condition
- [ ] Document when a Ghost is critical (open_questions §2.1) in spec or glossary

---

## Phase 3 — Sandbox (simulation-ready software)

- [ ] src/core: implement state.py (epistemic state with state_id, goal, claims, evidence, obligations, ghosts, provenance, branches, status, budgets)
- [ ] src/core: implement ghost.py (Ghost Record with ghost_id, ghost_type, shape, origin, reason, obligations, status)
- [ ] src/core: implement transition.py or cell.py (canonical cell as typed structure)
- [ ] src/engine: implement ghost_engine.py (spawn, resolve, dismiss, escalate; delegate to policies)
- [ ] src/engine: implement closure_guard.py (evaluate closure preconditions; block or allow)
- [ ] src/engine: implement verifier.py (continuous verifier; check local invariants; return admit | admit_with_doubt | repair_required | escalate | reject | closure_blocked)
- [ ] experiments/scenarios: add scenario_01_basic_doubt.md (description + expected behavior)
- [ ] experiments/scenarios: add scenario_02_evidence_ghost.md, scenario_05_premature_closure.md
- [ ] src/cli: run_scenario.py that loads a scenario and runs it through state + ghost_engine + closure_guard (+ verifier if available)

---

## Phase 4 — Constraint and verification (formal tools)

- [ ] formal/lean: definitions for state, ghost, operators; at least one proposition stated
- [ ] formal/tla: manager_plane_v2.tla or epistemic_router.tla stub
- [ ] formal/smt: run closure_fraud.smt2 or admissibility.smt2 with a solver; document results
- [ ] scripts/run_formal_checks.sh: invoke lean/tla/smt as appropriate
- [ ] Document which invariants are hard vs tunable (open_questions §5.1)

---

## Phase 5 — Governed prototype (integration)

- [ ] src/engine: implement epistemic_router.py (ok / doubt / not routing)
- [ ] src/engine: implement manager.py (typed events in, receipts out; dispatch to ghost_engine, verifier, closure_guard)
- [ ] src/policies: ghost_spawn_policy.py, closure_policy.py (stub or minimal)
- [ ] Wire proposer (e.g. stub or simple LLM adapter) → semantic form → verifier → ghost_engine / closure_guard via manager
- [ ] experiments: run 2–3 scenarios end-to-end; record in experiments/results/
- [ ] docs: update ROADMAP.md Wave 2 checkboxes when criteria are met

---

## Phase 6 — Book and presentation

- [ ] book/01_the_search_for_form: draft chapters 1–5 to “draft” level (align with canonical_cell_spec and introduction)
- [ ] book/05_ghost_records: draft chapters 21–27 to “draft” level (align with ghost_record_spec)
- [ ] book/07_debt_fraud_and_the_right_to_continue: draft chapters 35–40 (align with closure_fraud_spec and continuous_verifier_spec)
- [ ] assets/figures: add fig_01_canonical_cell, fig_02_ghost_taxonomy, fig_06_unified_stack (or placeholders)
- [ ] scripts/build_book.sh: aggregate book/ into a single output (e.g. markdown or PDF)
- [ ] scripts/export_release.sh: bundle book + spec + formal + selected experiments for release

---

## Near-term priorities (current focus)

1. **Formal core:** Define minimal epistemic state and transition operators (Phase 1).
2. **Sandbox:** Implement src/core (state, ghost, cell) and src/engine (ghost_engine, closure_guard, verifier) so at least one scenario runs (Phase 3).
3. **Spec alignment:** Harden glossary; ensure open_questions, non_negotiables, and all five core specs are mutually consistent.
4. **Book draft:** First full pass on Part I and Part V (Phase 6 subset).

---

## How to use this file

- **If you are a model:** Start with PROMPT_ENTRYPOINT.md and the spec read order. Then pick a task from Phase 0–1 or Near-term priorities. Mark tasks with `[x]` when done; add new tasks under the right phase.
- **If you are a human:** Use TASKS.md as the single place to see “what’s next” and to assign work. Keep phases in order where dependencies matter.
- **Do not:** Remove or weaken the canon (non_negotiables, Book.toml, specs). If a task conflicts with canon, flag it and propose a canonical change instead of silently violating it.

---

*Ignorance must take form.*
