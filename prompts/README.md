# Prompts
## Ignorance Must Take Form

This folder holds **prompt templates** for working on the repository with high canon fidelity and clear mode separation.

---

## When to Use Which

### `prompt_strict_mode.md`

Use when the task requires **maximum canon fidelity**, minimal drift, and structurally conservative output.

**Use for:**

- `spec/*.md` — specifications, protocol contracts, normative definitions
- `docs/glossary.md` — glossary work
- `docs/non_negotiables.md` — canonical constraints
- `formal/*` — Lean, TLA+, SMT models and definitions
- state models, protocol contracts, normative architecture descriptions
- any task where accidental ontology drift would be damaging

**Copy the prompt, replace `[INSERT TASK HERE]` with your task, and run.**

---

### `prompt_creative_mode.md`

Use when the goal is **discovery, synthesis, elegance, or architectural exploration** within canon.

**Use for:**

- book chapters (`book/**/*.md`)
- abstracts, preface, introduction
- manifesto (Part XVI)
- architectural maps and diagrams
- new formulations that stay canon-consistent
- scenario generation (`experiments/scenarios/`)
- controlled theoretical discovery
- naming subcomponents, patterns, or helper abstractions

**Copy the prompt, replace `[INSERT TASK HERE]` with your task, and run.**

---

## Rule of Thumb

- **Strict:** preserve canon; be precise and normative; no speculative ontology.
- **Creative:** expand possibility *inside* canon; refine, propose, discover; label proposals and speculation.

Both modes require reading `Book.toml`, glossary, non_negotiables, and relevant specs first. Neither mode permits weakening the canonical cell, `if_doubt`, Ghosts, closure discipline, or the four-floor stack.

---

## Task Template

Use `prompt_task_template.md` to draft a task before inserting it into either prompt. Keeps tasks clear and scoped.
