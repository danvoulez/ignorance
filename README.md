# Ignorance Must Take Form

**From the Infinitesimal to the Cosmos, from Silicon to User**

> "The supreme goal of all theory is to make the irreducible basic elements as simple and as few as possible without having to surrender the adequate representation of a single datum of experience."  
> — Albert Einstein, 1933
>
> *We owe it to Einstein to keep looking for the simplest form that does not break when reality changes scale.*

---

## What this is

**Ignorance Must Take Form** is a book-system: a unified project that treats a book, a theory, a protocol stack, and a software architecture as parts of the same object.

At its center is a single claim:

> A trustworthy system is not one that always knows.  
> It is one that knows how to give form to what it does not yet know before the pressure to continue forces it to pretend.

This repository develops that claim across four layers:

1. **Book** — the full theory, argument, and narrative.
2. **Spec** — the canonical definitions and protocol contracts.
3. **Formal** — the mathematical core, model checking, and proof path.
4. **Software** — the research sandbox and governed reasoning prototype.

---

## The principle

The project is organized around one principle:

> **Ignorance must take form.**

Anything a system cannot yet affirm, but no longer has the right to ignore, must become a first-class computational object.

That principle leads to a new architecture for reasoning and action built around:

- the **canonical cell**
- **Ghost Records**
- **Proof-Carrying Inference**
- the **Continuous Verifier**
- **Ghost Debt**
- **Closure Fraud**
- a **unified stack** that runs from semantics to governance

---

## The canonical cell

The core form proposed in this project is a nine-field canonical cell:

- `who`
- `did`
- `this`
- `when`
- `confirmed_by`
- `if_ok`
- `if_doubt`
- `if_not`
- `status`

The claim is that this is the minimum accountable form of a governed transition.

It is used as the common structure across scales:

- from semantic intent
- to deterministic admissibility checks
- to protocolized action
- to epistemic reasoning and closure

---

## Why this project exists

Modern systems do not have a portable form for what they do not know.

At each layer, ignorance is handled locally:

- nulls
- exceptions
- retries
- fallbacks
- uncertainty scores
- plausible text

But none of these survive the crossing between layers.

As a result, systems of systems do not accumulate structured knowledge about what they do not know. They shed it at every interface until absence becomes either silence or fabrication.

This project starts from the idea that the problem is not just model quality. It is **missing form**.

---

## The stack

The architecture developed here spans four floors:

### 1. Semantic form

Where intention is canonicalized into a portable and accountable structure.

### 2. Deterministic materialization

Where policy becomes executable at the gate, in deterministic, content-addressed form.

### 3. Protocol of action

Where acts are written before they are executed, with consequences declared in advance.

### 4. Epistemic governance

Where the system tracks ghosts, verifies trajectories, measures debt, and prevents illegitimate closure.

---

## Repository structure

This repository is organized as a monorepo with multiple layers:

```text
book/         # the book itself
docs/         # research notes, glossary, charter, decisions
spec/         # canonical definitions and protocol specifications
formal/       # Lean, TLA+, SMT models
experiments/  # scenarios, baselines, notebooks, results
src/          # research software and governed reasoning prototype
assets/       # figures, tables, diagrams
refs/         # bibliography and source works
```

---

## Source of truth

The canonical authority for the project is **Book.toml**.

It defines:

- project identity
- thesis and principle
- canonical cell
- core concepts
- ghost types
- invariants
- stack structure
- build order
- repository roots
- project status
- open questions

**If you are working on this repository, read Book.toml first.**

---

## Entry points

Recommended starting points:

- **PROMPT_ENTRYPOINT.md** — bootloader for high-capability model sessions (read this first if you are a model)
- **README.md** — project overview
- **Book.toml** — canonical identity and structure
- **book/ABSTRACT.md** — short statement of the whole work
- **book/PREFACE.md** — why this exists
- **book/00_front_matter/introduction.md** — formal opening of the book
- **book/INDEX.md** — full book structure
- **docs/north_star.md** — research direction
- **spec/canonical_cell_spec.md** — first formal atom
- **spec/ghost_record_spec.md** — structured absence as object

---

## Current status

The project currently has:

- a defined identity and canonical configuration (Book.toml)
- a project-scoped skill that uses Book.toml as authority
- book entrypoints in place
- a developed conceptual introduction
- a full book index
- a monorepo layout

Still ahead:

- glossary hardening
- first protocol specs
- formal core definitions
- TLA+ lifecycle modeling
- SMT constraint checks
- manager plane v2 design
- software prototype
- evaluation framework

---

## Working model

This project treats reasoning as state transition, not text generation.

It treats doubt as a first-class epistemic regime, not as a weak version of failure.

It treats absence as something that must be:

- preserved,
- named,
- routed,
- and governed.

The system does not ask only:

- *What is the next plausible output?*

It asks:

- Does this system still have the right to continue?
- What remains unresolved?
- What has been confirmed?
- What must be carried forward?
- Is closure legitimate yet?

---

## Design commitments

This repository is committed to the following:

- structure before continuation
- write before execute
- proof before closure
- doubt before fabrication
- portable ignorance across layers
- proper allocation of power
- LLMs as proposers, never sovereigns

---

## For readers

You may approach this repository in different ways.

**If you want the theory** — Start with:

- book/ABSTRACT.md
- book/PREFACE.md
- book/00_front_matter/introduction.md

**If you want the architecture** — Start with:

- spec/unified_stack_spec.md
- spec/manager_plane_v2_spec.md
- book/11_the_unified_stack/

**If you want the formal path** — Start with:

- formal/README.md
- formal/tla/
- formal/smt/
- formal/lean/

**If you want the software** — Start with:

- src/README.md
- experiments/README.md

---

## What success would look like

A successful outcome for this project would be a system in which:

- unresolved absence is never silently discarded,
- plausible text cannot substitute for missing support,
- closure can be formally blocked when critical uncertainty remains,
- reasoning leaves receipts,
- and the same underlying form can survive across scales without changing nature.

---

## Status of the claim

This repository does not claim that the work is finished.

It claims something narrower and more serious:

- the form has been identified,
- the architecture has been sketched,
- the stack has been aligned,
- and the path from theory to implementation is now explicit.

The rest is the work.

---

## License

See LICENSE.md.

---

## Closing line

This project begins with a small cell.

It aims at a different idea of what a trustworthy system is.
