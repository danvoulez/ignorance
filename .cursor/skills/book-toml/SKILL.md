---
name: book-toml
description: >-
  Uses Book.toml as the single source of truth when editing or generating content
  for the Ignorance Must Take Form book-system. Applies thesis, principle,
  canonical cell, ghosts, invariants, stack, entrypoints, and build order from
  Book.toml. Use when working in this repo on book/, spec/, docs/, or when the
  user mentions Book.toml, canonical cell, ghost records, closure fraud, or the
  unified stack.
---

# Book.toml — Book-System Authority

When working in this repository, **read `Book.toml` first** (project root). It defines identity, structure, and terminology. All new or edited prose, spec, or code must align with it.

## What to Do

1. **Read Book.toml** at the start of any task touching book, spec, docs, or architecture.
2. **Respect `[identity]`** — Use `thesis`, `principle`, and `tagline` when summarizing or generating claims.
3. **Use `[entrypoints]`** — Link or edit the files listed there (readme, abstract, preface, index, introduction) when updating front matter or navigation.
4. **Follow `[build.order]`** — When adding or reordering content, use the `sequence` order (00_front_matter … 16_the_manifesto, appendices).
5. **Canonical cell** — The nine fields are in `[canonical_cell].fields` (who, did, this, when, confirmed_by, if_ok, if_doubt, if_not, status). Use these names; do not rename or drop fields without updating Book.toml.
6. **Core concepts** — `[core_concepts].required` is the minimal lexicon; use these terms consistently (see also `docs/glossary.md`).
7. **Ghosts** — Types in `[ghosts].types` (entity_ghost, evidence_ghost, causal_ghost, linkage_ghost). Definition in `[ghosts].claim`.
8. **Invariants** — Local and global invariants are in `[invariants.local]` and `[invariants.global]`; reference them in spec and formal layers.
9. **Stack** — Four floors and components are under `[stack]` and `[stack.components]`; use when describing architecture or mapping book ↔ spec ↔ code.
10. **Repository roots** — `[repository]` gives book_root, docs_root, spec_root, formal_root, etc.; use these paths when referring to layers.
11. **Style** — `[style]` sets tone (rigorous-literary), glossary_required, terminology_is_canonical; apply when drafting book or docs.
12. **Open questions** — `[questions].open` lists unresolved items; consider when proposing answers or new sections.

## Entrypoints vs Actual Paths

- `preface` in Book.toml is `book/PREFACE.md`; the repo may have `book/00_front_matter/preface.md`. Prefer the path that exists; if creating a unified build, add or symlink as needed.
- `introduction` points to `book/00_front_matter/introduction.md`; if missing, use or create from `note_to_reader`/`how_to_read_this_book` as appropriate.

## When Not to Override

Do not change Book.toml unless the user explicitly asks to update title, thesis, principle, build order, or schema. When in doubt, keep Book.toml as authority and change the content (book, spec, docs) to match.
