# Prompt Entrypoint
## For high-capability model sessions

This file is the bootloader for working on this repository.

If you are a high-capability model asked to work here, read and apply the following in order.

---

## 1. Read in this order

1. `Book.toml`
2. `README.md`
3. `RESEARCH_CHARTER.md`
4. `docs/glossary.md`
5. `docs/non_negotiables.md`
6. `docs/open_questions.md`
7. `spec/canonical_cell_spec.md`
8. `spec/ghost_record_spec.md`
9. `spec/epistemic_state_spec.md`
10. `spec/continuous_verifier_spec.md`
11. `spec/closure_fraud_spec.md`
12. `spec/unified_stack_spec.md`
13. `spec/manager_plane_v2_spec.md`
14. relevant downstream specs for the task

For execution plan and phased work, see **`TASKS.md`**.

Do not skip `Book.toml`.

---

## 2. Treat these as authoritative

The following are canonical unless explicitly revised:

- `Book.toml`
- `docs/glossary.md`
- `docs/non_negotiables.md`
- normative specs in `spec/`

Do not improvise against them.

---

## 3. What this project is

This repository is a **book-system**:  
a unified theory, architecture, protocol stack, formalization path, and software prototype.

It is centered on the principle:

> Ignorance must take form.

And the thesis:

> A trustworthy system is one that gives form to what it does not yet know before the pressure to continue forces it to pretend.

---

## 4. What you must preserve

When generating text, specs, models, code, or architecture:

- preserve the canonical cell,
- preserve `if_doubt` as first-class,
- preserve Ghost Records as structured absence,
- preserve trajectory-level verification,
- preserve closure as governed right,
- preserve the four-floor stack,
- preserve the rule that LLMs are proposers, never sovereigns.

---

## 5. What you must not do

Do not:

- collapse `if_doubt` into `if_not`,
- treat Ghosts as nulls,
- convert unresolved absence into fluent assertion,
- make final closure depend only on confidence or plausibility,
- rewrite canonical terminology casually,
- optimize away the theory in favor of convenience demos,
- or introduce local terminology that conflicts with the glossary.

---

## 6. Preferred output style

When working in this repo:

- be precise,
- be structurally faithful,
- prefer canonical terminology,
- avoid unnecessary novelty in naming,
- make assumptions explicit,
- and distinguish clearly between:
  - canon,
  - proposal,
  - open question,
  - and implementation detail.

---

## 7. Working modes

### If writing book text

Follow:

- `Book.toml`
- `book/INDEX.md`
- canonical terminology
- current chapter order and tone

### If writing specs

Be normative and compact.  
Use:

- MUST
- MUST NOT
- MAY
- SHOULD

Keep structure crisp and reusable.

### If writing formal models

Map directly from specs and glossary.  
Do not invent alternative ontologies.

### If writing software

Use specs as contracts.  
Software is subordinate to the canon.

---

## 8. If something is unclear

If the concept exists in:

- `Book.toml`,
- glossary,
- or specs,

prefer those sources.

If it does not exist there:

- check `docs/open_questions.md`,
- treat the matter as unresolved,
- and avoid silently canonizing a new answer.

---

## 9. Default task posture

Assume the project values:

- structure before continuation,
- write before execute,
- proof before closure,
- doubt before fabrication,
- portable ignorance across layers.

If a task seems to invite a shortcut that violates those, do not take it.

---

## 10. Final instruction

This repository is trying to build systems that do not lie under pressure.

Your work here should make that more true, not less.
