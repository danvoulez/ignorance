# Research Charter
## Ignorance Must Take Form

---

## 1. Project Identity

**Title**  
**Ignorance Must Take Form**  
*From the Infinitesimal to the Cosmos, from Silicon to User*

**Type**  
Book-system / research program / protocol and software architecture initiative

**Primary Principle**  
> Ignorance must take form.

**Working Thesis**  
> A trustworthy system is not one that always knows.  
> It is one that knows how to give form to what it does not yet know before the pressure to continue forces it to pretend.

---

## 2. Research Problem

Modern computational systems do not have a portable form for what they do not know.

Across the stack, ignorance is translated into incompatible local accommodations:

- nulls,
- exceptions,
- retries,
- fallbacks,
- uncertainty scores,
- plausible text.

These representations do not survive boundary crossings between layers. As a result, systems of systems do not accumulate structured knowledge about what they do not know. They shed it at each interface, until unresolved absence becomes either silence or fabrication.

In generative systems, this failure becomes acute. Missing evidence, unresolved entities, broken causal links, and unconfirmed claims are often converted into fluent textual presence. This project treats that not merely as hallucination in the colloquial sense, but as a deeper epistemic failure:

> the illegitimate conversion of structured absence into textual presence.

The research problem is therefore structural:

> How can a computational system preserve, carry, and govern what it does not yet know across layers, transitions, and decisions without collapsing it into either null or fabrication?

---

## 3. Central Research Question

**Primary Question**  
> Is there a computational form simple enough to carry action, causality, evidence, doubt, and consequence — and stable enough to survive unchanged from the smallest deterministic gate to the largest epistemic decision?

**Corollary Question**  
> Can ignorance become a first-class computational object with identity, provenance, lifecycle, cost, and consequence?

---

## 4. Core Hypothesis

This project proceeds from the following hypothesis:

> There exists a minimal accountable form of governed transition that can preserve both what a system knows and what it does not yet have the right to erase.

That form is proposed here as the **canonical cell**:

- `who`
- `did`
- `this`
- `when`
- `confirmed_by`
- `if_ok`
- `if_doubt`
- `if_not`
- `status`

The project further hypothesizes that if unresolved but relevant absence is represented as a first-class object within that form, then systems can:

- reduce hallucination,
- reduce premature closure,
- improve auditability,
- preserve epistemic continuity,
- and route uncertainty more honestly and efficiently.

---

## 5. Canonical Commitments

This project is committed to the following design and research commitments:

- **structure before continuation**
- **write before execute**
- **proof before closure**
- **doubt before fabrication**
- **portable ignorance across layers**
- **proper allocation of power**
- **LLMs as proposers, never sovereigns**

These commitments are not rhetorical. They are intended to shape the specifications, the formal models, the architecture, the software, and the written book alike.

---

## 6. Scope

### In Scope

This project includes:

- the formal and conceptual development of the canonical cell,
- the theory of Ghost Records,
- proof-carrying inference,
- continuous verification of reasoning trajectories,
- Ghost Load and Ghost Debt,
- Closure Fraud and admissible closure,
- a unified stack from semantic form to epistemic governance,
- research software to simulate and test these ideas,
- and a book that presents the theory as a coherent system.

### Out of Scope

This project does not currently aim to:

- train a new foundation model,
- replace large language models wholesale,
- solve general intelligence,
- build a polished end-user product,
- or claim complete mathematical closure from the outset.

This is a theory-first, architecture-first, and prototype-oriented research program.

---

## 7. Primary Objects of the Theory

The theory is expected to define and relate at least the following objects:

- **Canonical Cell**
- **Claim**
- **Evidence**
- **Obligation**
- **Ghost Record**
- **Epistemic State**
- **Transition**
- **Proof-Carrying Inference**
- **Continuous Verifier**
- **Ghost Load**
- **Ghost Debt**
- **Closure**
- **Closure Fraud**
- **Epistemic Router**
- **Unified Stack**

These are the minimum semantic objects that must be stabilized across docs, specs, formal models, and software.

---

## 8. Expected Contributions

This project aims to contribute across five layers.

### A. Conceptual Contribution

A new vocabulary for trustworthy computation under uncertainty:

- Ghost Records,
- structured absence,
- Closure Fraud,
- non-monotonic reasoning with receipts.

### B. Formal Contribution

A formal core for:

- epistemic state transitions,
- admissibility,
- debt,
- ghost lifecycle,
- closure legitimacy.

### C. Architectural Contribution

A unified stack linking:

- semantic canonicalization,
- deterministic admissibility,
- protocolized action,
- epistemic governance.

### D. Software Contribution

A research sandbox and governed reasoning prototype that instantiate the theory operationally.

### E. Literary / Scientific Contribution

A book that presents the theory not merely as a technical proposal, but as a new scientific and computational ethic.

---

## 9. Four-Floor Stack

The project understands the full system as operating across four floors:

### 1. Semantic Form

Where intention is canonicalized into a portable accountable structure.

### 2. Deterministic Materialization

Where policy and admissibility become executable in deterministic, content-addressed form.

### 3. Protocol of Action

Where acts are written before they are executed and consequences are declared in advance.

### 4. Epistemic Governance

Where the system tracks ghosts, verifies trajectories, routes doubt, and blocks illegitimate closure.

The research program is not complete unless these four floors can be articulated as one coherent stack.

---

## 10. Research Outputs

The expected outputs of this program are:

### Written Outputs

- book manuscript,
- abstract,
- glossary,
- specifications,
- one-page thesis,
- manifesto,
- possible technical paper(s).

### Formal Outputs

- TLA+ models,
- SMT models,
- Lean definitions and propositions.

### Software Outputs

- epistemic state model,
- ghost engine,
- verifier,
- closure guard,
- manager plane v2 prototype,
- experiment scenarios and metrics.

### Visual Outputs

- canonical cell diagrams,
- ghost lifecycle diagrams,
- stack architecture figures,
- closure fraud flow diagrams.

---

## 11. Research Method

This project proceeds through a layered method:

### 1. Canonicalization

Stabilize vocabulary, principles, and identity via `Book.toml`.

### 2. Literary Formulation

Develop the argument in book form to force conceptual coherence.

### 3. Specification

Translate concepts into canonical contracts and lifecycle documents.

### 4. Formalization

Express the theory in state machines, constraints, and proof-oriented definitions.

### 5. Simulation

Run controlled scenarios to test whether the concepts behave coherently.

### 6. Implementation

Build a prototype that exposes the theory to software reality.

### 7. Evaluation

Measure cost, reliability, closure fraud, dead-branch spend, ghost resolution efficiency, and human recovery cost.

---

## 12. Research Success Criteria

The project will count as successful if it can demonstrate the following:

### Conceptual Success

The theory provides a coherent and reusable account of:

- structured absence,
- epistemic continuity,
- admissible closure,
- and governed reasoning.

### Architectural Success

The four-floor stack can be described without contradictions and assigned clear responsibilities.

### Formal Success

A minimal formal core can be defined and checked for internal consistency.

### Prototyping Success

A software prototype can:

- spawn ghosts,
- preserve uncertainty structurally,
- route doubt,
- and prevent at least some forms of premature closure.

### Empirical Success

The governed system shows meaningful gains over baselines in:

- reduction of illegitimate closure,
- reduction of wasted search on dead branches,
- increased auditability,
- and lower human recovery cost.

---

## 13. Research Risks

The project acknowledges the following risks:

### Conceptual Risks

- overgeneralizing the canonical cell,
- confusing metaphor with formal structure,
- making the theory too broad to harden.

### Architectural Risks

- introducing excessive bureaucracy into reasoning,
- overconstraining exploration,
- or failing to allocate responsibility cleanly across floors.

### Formal Risks

- definitions may be too vague for formalization,
- debt may be difficult to compute well,
- admissibility may resist simple predicates.

### Practical Risks

- the verifier may be too expensive,
- ghost management may explode combinatorially,
- the prototype may become too rigid for useful reasoning.

These are not reasons to stop. They are conditions the research must confront honestly.

---

## 14. Non-Negotiables

The following points are currently non-negotiable unless explicitly revised at the canonical level:

- the canonical cell has nine fields,
- `if_doubt` is a first-class branch,
- Ghost Records are not nulls,
- closure may be blocked for epistemic reasons,
- verification is trajectory-level, not only output-level,
- the LLM is a proposer, not a sovereign authority,
- and `Book.toml` is the source of truth for identity and terminology.

---

## 15. Work Phases

### Phase 0 — Canon

Stabilize language, identity, and structure.

### Phase 1 — Formal Core

Define the minimum theoretical objects and operators.

### Phase 2 — Protocol Physics

Specify transitions, lifecycle, and admissibility.

### Phase 3 — Sandbox

Build simulation-ready software structures.

### Phase 4 — Constraint and Verification

Test rules, constraints, and edge cases via formal tools.

### Phase 5 — Governed Prototype

Integrate proposer, verifier, ghosts, and closure guard.

### Phase 6 — Publication

Deliver the book, specs, visuals, and formal outputs.

---

## 16. Near-Term Priorities

The current immediate priorities are:

1. complete the root documentation (`README.md`, `Research Charter`, glossary),
2. draft the canonical specs:
   - canonical cell,
   - Ghost Record,
   - epistemic state,
   - closure fraud,
3. stabilize chapter sequencing and editorial dependencies,
4. define the first formal objects,
5. create initial simulation scenarios,
6. connect the theory to manager plane v2.

---

## 17. Relationship to Existing Work

This project is not created from nothing. It is in active dialogue with:

- **LogLine** — for write-before-execute, the protocol form of the cell, and consequence invariants,
- **Chip as Code / TDLN** — for semantic canonicalization and policy-level determinism,
- **What Runs Above Software** — for proper allocation of power and the non-chat manager plane,
- **Einstein (1933)** — for the ethical and theoretical standard of simplicity without loss.

These influences are not decorative. They are part of the conceptual ancestry of the work.

---

## 18. Working Definition of Trustworthy Computation

The project adopts the following provisional definition:

> A trustworthy computational system is one that can preserve, govern, and communicate both what it knows and what it still does not have the right to erase.

This is the criterion against which the theory, the software, and the book should all be judged.

---

## 19. Closing Statement

This project begins with a small cell.

It seeks a form simple enough to survive changes of scale without changing nature, and disciplined enough to carry action, evidence, doubt, and consequence without surrendering any of them to silence or fabrication.

It assumes that ignorance is not an edge case.

It is part of the world.

And any system that hopes to be trustworthy must learn to carry it honestly.
