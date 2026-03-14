# The Book — Ignorance Must Take Form

This folder contains the book as written: **88 chapters** in **16 parts**, plus **front matter** and **appendices**. Each part is a directory; each chapter is a single markdown file.

---

## Structure

- **00_front_matter/** — Epigraph, preface, note to the reader, how to read
- **01–16** — Parts I–XVI as numbered in the outline
- **appendices/** — Glossary, original cell, example traces, ghost taxonomy, protocol state machines, constraint models, Lean, TLA+, implementation notes, Einstein

Navigation by part and chapter: [INDEX.md](INDEX.md).

---

## How It Fits the Organism

- **Book** = narrative and argument. It introduces the canonical cell, Ghost Records, Proof-Carrying Inference, closure, and the unified stack.
- **Spec** = contract. When the book defines a concept (e.g. Ghost Record, closure fraud), the spec fixes the operational definition.
- **Formal** = mathematical defence. Lean, TLA+, and SMT formalize what the book claims.
- **Code** = embodiment. `src/` implements the same concepts.

Read the book for the *why* and the *what*; use spec and formal for the *exactly what*; use code to run it.

---

## Conventions

- Chapter filenames: `NN_short_snake_case_title.md` (e.g. `03_the_canonical_cell.md`).
- Part READMEs summarize the part and list chapters with one-line descriptions.
- Cross-references to spec/formal/src use relative paths from this folder (e.g. `../spec/ghost_record_spec.md`).

---

*Ignorance must take form.*
