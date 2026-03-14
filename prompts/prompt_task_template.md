# Task Template
## Ignorance Must Take Form

Use this template to draft a task before inserting it into `prompt_strict_mode.md` or `prompt_creative_mode.md`. Copy the section below, fill it in, then paste the **Task description** into the `[INSERT TASK HERE]` slot of the chosen prompt.

---

## Task draft

**Mode:** [ ] Strict  [ ] Creative

**Scope (file or area):**
- 

**Goal (one sentence):**
- 

**Task description (paste this into the prompt):**
```
[Describe what you want the model to produce. Include:
 - exact deliverable (e.g. "Add section 4.3 to spec/ghost_record_spec.md defining obligation lifecycle")
 - any constraints (e.g. "Do not add new ghost types")
 - format if relevant (e.g. "Normative spec style with MUST/MAY")
]
```

**Canon files to emphasize (if any):**
- 

**Open questions to leave open (if any):**
- 

---

## Example (Strict)

**Mode:** Strict

**Scope:** `spec/ghost_record_spec.md`

**Goal:** Add a short section defining when a Ghost may be dismissed without resolution.

**Task description:**
```
Add a new subsection to spec/ghost_record_spec.md (after the lifecycle section) titled "Dismissal conditions". Define under what conditions a Ghost may transition to status `dismissed` without being resolved. Use normative language (MUST, MAY, MUST NOT). Do not introduce new ghost types or alter the canonical lifecycle statuses. Reference docs/open_questions.md §2.2 if relevant; leave expiration/review horizon as open if not yet canonical.
```

---

## Example (Creative)

**Mode:** Creative

**Scope:** `book/05_ghost_records/25_the_life_of_a_ghost.md`

**Goal:** Draft the chapter so it illustrates ghost lifecycle without inventing new ontology.

**Task description:**
```
Draft book/05_ghost_records/25_the_life_of_a_ghost.md. The chapter should explain the lifecycle of a Ghost (spawned, refined, resolved, split, merged, dismissed, escalated) with one concrete running example (e.g. an evidence ghost for a missing document). Preserve the canonical statuses and the distinction between Ghost and null. Use clear, compressive prose. Label any formulation that is not yet in the spec as "proposal" or "illustrative". Do not add new lifecycle states.
```
