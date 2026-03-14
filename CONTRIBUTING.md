# Contributing — Ignorance Must Take Form

This repository treats the **book**, **theory**, **spec**, and **software** as one organism. Contributions should keep them aligned.

---

## Before You Start

- Read [README.md](README.md) and [RESEARCH_CHARTER.md](RESEARCH_CHARTER.md).
- Check [docs/open_questions.md](docs/open_questions.md) for open threads.
- Use [docs/glossary.md](docs/glossary.md) and [docs/language_decisions.md](docs/language_decisions.md) for terminology.

---

## How to Contribute

- **Book (book/):** Prose follows the outline in [book/INDEX.md](book/INDEX.md). One file per chapter; part READMEs introduce each section.
- **Docs (docs/):** Proposals, decisions, and rejected paths go in the appropriate doc; update `decision_log.md` for material choices.
- **Spec (spec/):** Specs are contracts. Changes must be reflected in the book and, where applicable, in formal/ and src/.
- **Formal (formal/):** Lean, TLA+, and SMT must stay consistent with spec and glossary. Document assumptions in READMEs.
- **Code (src/):** Implementations must satisfy the spec slice they claim to cover. Tests and scenarios live under experiments/.
- **Experiments (experiments/):** New scenarios or baselines should be described in markdown and, if runnable, wired to the CLI or scripts.

---

## Consistency

- **Spec wins over code** in case of conflict.
- **Formal models** are authoritative for the slice they cover; book and spec must not contradict them.
- **Glossary** is the source of truth for definitions; new terms are proposed in docs before use in book/spec/code.

---

## Pull Requests

- Reference the part of the organism you are changing (book, docs, spec, formal, src, experiments).
- If you change a spec, note whether book or code needs a follow-up.
- For new concepts, add a glossary entry or open_questions item and link it.

---

*Ignorance must take form.*
