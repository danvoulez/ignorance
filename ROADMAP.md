# Roadmap — Ignorance Must Take Form

This document tracks the rollout of the monorepo and the work it contains. The structure is built in waves; the content co-evolves.

---

## Wave 1 — Skeleton

**Goal:** Repo exists, navigable, with clear identity.

- [x] Root README, ROADMAP, RESEARCH_CHARTER, INDEX
- [x] `book/` with README and INDEX; part folders and chapter stubs
- [x] `docs/` with README and placeholder files (north_star, glossary, decision_log, etc.)
- [x] `spec/` with README and spec file stubs
- [x] `refs/` with README and bibliography placeholder

**Outcome:** Anyone can land and understand what the project is and where things live.

---

## Wave 2 — Living Core

**Goal:** Theory, spec, and software can be exercised and tested.

- [ ] **book:** First pass on Part I (The Search for Form) and Part V (Ghost Records) — enough to anchor the vocabulary
- [ ] **spec:** Canonical cell, ghost record, epistemic state, closure fraud — one coherent slice
- [ ] **formal:** TLA+ for protocol and ghost lifecycle; SMT stubs for closure and admissibility
- [ ] **src:** Core types (state, claim, evidence, ghost, transition) and ghost engine + closure guard
- [ ] **experiments:** 2–3 scenarios (e.g. basic doubt, evidence ghost, premature closure) runnable via CLI

**Outcome:** A minimal but runnable “honest ignorance” pipeline: propose → verify → carry ghosts → block or allow closure.

---

## Wave 3 — Hardening

**Goal:** Formality and presentation match the ambition of the thesis.

- [ ] **formal/lean:** Definitions for state, ghost, operators, predicates; initial propositions
- [ ] **book:** Parts II–IV, VI–VIII drafted to the same standard as Wave 2 chapters
- [ ] **assets:** Figures for canonical cell, ghost taxonomy, epistemic state, unified stack, closure flow
- [ ] **scripts:** `build_book.sh`, `run_formal_checks.sh`, `run_experiments.sh`, `export_release.sh`
- [ ] **evaluation:** Metrics (closure fraud rate, cost per reliable decision, ghost resolution efficiency) and baselines documented in experiments/

**Outcome:** The book is buildable; formal checks and experiments are scriptable; figures support the narrative.

---

## Wave 4 — Full Organism

**Goal:** All 16 parts and appendices present; stack and evaluation coherent.

- [ ] **book:** All 88 chapters and appendices at draft-or-better
- [ ] **spec:** Full coverage (manager plane v2, TDLN mapping, deterministic gate, unified stack)
- [ ] **formal:** Lean propositions proved or clearly stated; TLA+ specs for manager plane and epistemic router
- [ ] **src:** Manager plane adapter, TDLN adapter, policy layer wired; CLI complete
- [ ] **experiments:** Baselines run and reported; failure modes and success criteria written

**Outcome:** Book, spec, formalization, and software tell one story and can be released as a single artefact.

---

## Current Focus

**Wave 1** is complete. The next step is Wave 2: choose one slice (e.g. canonical cell → ghost → closure) and implement it end-to-end in spec, formal, src, and experiments, then reflect it in the corresponding book chapters.

---

## Notes

- **Book first vs code first:** Either is valid; the repo is designed so that `book/` and `spec/` can lead and `src/` can follow, or the other way around. Consistency is maintained via `docs/` (decision log, glossary).
- **Formal:** Lean and TLA+ can progress in parallel; SMT is used for constraint and counterexample exploration rather than full verification.
- **Experiments:** Scenarios should be small and reproducible; results live under `experiments/results/` and are cited from the book and spec where relevant.
