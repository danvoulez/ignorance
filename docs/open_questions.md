# Open Questions
## Ignorance Must Take Form

This document tracks questions that are important, active, and unresolved.

A question belongs here if:

- it matters to the theory or architecture,
- it is not yet canonical,
- and resolving it would materially improve specs, formalization, or implementation.

A question does **not** belong here if it is already settled by:

- `Book.toml`,
- `docs/glossary.md`,
- `docs/non_negotiables.md`,
- or a normative specification.

This file is for unresolved matters, not hidden canon.

---

## 1. Formal Core

### 1.1 What is the minimal formal definition of an epistemic state?

We have a normative container shape, but not yet a mathematically hardened minimal definition.

Open issues:

- Should claims be modeled as propositions, typed records, or graph nodes?
- Should evidence be first-class objects or just references?
- Is provenance part of state or derivable from history?

### 1.2 What is the smallest useful transition algebra?

We know transitions matter, but the exact minimal operator set is still open.

Candidates:

- `spawn_ghost`
- `resolve_ghost`
- `dismiss_ghost`
- `escalate_ghost`
- `propose_claim`
- `attach_evidence`
- `evaluate_closure`

Question:

- which are primitive, and which are syntactic sugar?

### 1.3 What is the right topology for "healthy" trajectories?

We use the language of drift, regions, admissibility, and closure, but the exact formal geometry is still open.

Questions:

- Is semantic drift scalar, vector-valued, or structural?
- Should distance be measured in claim-space, dependency-space, or obligation-space?
- Can we define neighborhoods of admissible continuation cleanly?

---

## 2. Ghosts

### 2.1 When does a Ghost become critical?

We know some Ghosts are closure-critical and others are not.

Open problem:

- what makes a Ghost critical?
- Is criticality intrinsic, contextual, or policy-defined?
- Can criticality be computed or only declared?

### 2.2 Should every Ghost have an expiration or review horizon?

A Ghost should not disappear silently, but indefinite persistence can become clutter.

Open problem:

- Should every Ghost include a review policy?
- Should old Ghosts automatically escalate?
- When is retention itself harmful?

### 2.3 Can Ghosts depend on other Ghosts?

This seems realistic, but dangerous.

Open problem:

- should nested or chained Ghost dependencies be first-class?
- if yes, how do we avoid uncontrolled combinatorial growth?
- should there be a maximum Ghost-depth or debt multiplier?

### 2.4 Should split and merge be automatic or always governed?

Ghost split/merge are important lifecycle moves, but unclear in execution.

Open problem:

- what threshold justifies auto-split or auto-merge?
- when must human or manager-plane intervention be required?

---

## 3. Debt and Budgets

### 3.1 How should Ghost Debt be computed?

We have the conceptual structure:

\[
GD(x_t) = \sum_i w_i \cdot u_i \cdot c_i
\]

But the practical semantics remain open.

Questions:

- what is the right interpretation of `w_i`, `u_i`, and `c_i`?
- should debt be additive, capped, or nonlinear?
- should interacting Ghosts amplify one another?

### 3.2 Are contradiction, drift, and debt independent budgets?

We currently treat them as distinct, but they may interact.

Open problem:

- should a high contradiction budget amplify Ghost Debt?
- should drift reduce confidence in existing evidence?
- should recoverability offset debt?

### 3.3 Are budgets universal or domain-specific?

Some applications may tolerate more doubt than others.

Open problem:

- do we need domain profiles for admissibility?
- can the same closure policy govern legal, medical, and exploratory reasoning?

---

## 4. Closure

### 4.1 What exactly constitutes closure?

We know closure is not just "output emitted."

Open problem:

- is closure a property of state, branch, case, or user-facing answer?
- can closure be partial?
- can a system close one branch while preserving another?

### 4.2 Is Closure Fraud binary or graded?

The current framing treats it as a serious violation.

Open problem:

- should Closure Fraud be boolean?
- or should there be classes:
  - minor,
  - structural,
  - critical,
  - irreversible?

### 4.3 Can closure be legitimate under unresolved Ghosts?

Current theory says yes, sometimes, if they are not critical.

Open problem:

- how exactly is that determined?
- what are the closure-safe classes of unresolved absence?

---

## 5. Continuous Verification

### 5.1 Which invariants are hard constraints and which are tunable?

We currently treat:

- goal preservation
- provenance closure
- contradiction budget
- semantic drift bound
- recoverability

as local invariants, but not all may need equal rigidity.

Open problem:

- which invariants MUST always hold?
- which may be temporarily violated under `doubt`?
- which may degrade gradually?

### 5.2 How expensive can the verifier be?

A very strong verifier may become operationally impractical.

Open problem:

- what is the correct verification cadence?
- every step?
- only before closure?
- only under doubt?
- staged verification?

### 5.3 Can the verifier itself spawn Ghosts?

This seems plausible when the verifier detects unresolved structural absence.

Open problem:

- should the verifier be allowed to create Ghosts directly?
- or only recommend them to the Ghost Engine?

---

## 6. Manager Plane v2

### 6.1 What is the exact relationship between Manager Plane and Epistemic Router?

We know both should exist, but boundary clarity matters.

Open problem:

- is the router part of the manager?
- does the manager consume router decisions?
- or does the manager own routing but delegate verification?

### 6.2 Should `AdvancePointer` be blocked by epistemic state directly?

Current architecture suggests yes, but details remain open.

Open problem:

- does every pointer advance require closure check?
- or only closure-adjacent transitions?

### 6.3 What are the typed outputs of a governed manager plane?

Likely candidates:

- `Delegate`
- `RequestEvidence`
- `SpawnGhost`
- `ResolveGhost`
- `EscalateGhost`
- `AdvancePointer`
- `BlockClosure`
- `Terminate`

Open problem:

- what is the minimal action algebra?

---

## 7. LLM Integration

### 7.1 Can the LLM propose Ghosts?

Probably yes.

Open problem:

- under what constraints?
- does every proposed Ghost require verification?
- can the LLM assign Ghost type, or only suggest one?

### 7.2 Can the LLM resolve Ghosts?

Potentially yes, but only with support.

Open problem:

- what proof threshold is required for a model-proposed resolution?
- how should `confirmed_by` work here?

### 7.3 How much of the epistemic state should be exposed to the proposer?

Too little and the proposer is blind. Too much and prompts become expensive or incoherent.

Open problem:

- what is the minimal promptable state slice?

---

## 8. Formalization Path

### 8.1 What should be formalized first?

Candidates:

- Canonical Cell
- Ghost Record
- Epistemic State
- Closure predicates
- Transition admissibility

Question:

- which ordering gives the best ratio of rigor to progress?

### 8.2 Lean, TLA+, SMT: what belongs where?

We already have a rough split, but exact scope is still open.

Open problem:

- which concepts are best proved?
- which are best model checked?
- which are best explored by satisfiability and counterexample?

---

## 9. Book and Theory Framing

### 9.1 How universal is the Canonical Cell claim?

The current writing is ambitious.

Open problem:

- should the claim remain "smallest known accountable form"?
- or be narrowed to a more domain-bounded claim?

### 9.2 How much should the theory lean into scientific-method language?

The mapping is strong, but can be overclaimed.

Open problem:

- what level of scientific-method analogy is justified?
- what level becomes poetic overreach?

### 9.3 How explicitly should Einstein frame the work?

The epigraph is excellent, but tone matters.

Open problem:

- how much Einstein is enough before it becomes ornamental?

---

## 10. Priority Open Questions

If work must be prioritized, the current top questions are:

1. What is the minimal formal definition of an epistemic state?
2. How is Ghost criticality determined?
3. How should Ghost Debt be computed?
4. What exactly makes closure illegitimate?
5. Which invariants are hard vs tunable?
6. What are the typed outputs of manager plane v2?
7. How should an LLM proposer interact with Ghost creation and resolution?

---

## 11. Working Rule

Until a question here is resolved canonically:

- do not silently assume a final answer,
- do not smuggle a local decision into general terminology,
- and do not rewrite specs as though the matter were already settled.

Unresolved does not mean unusable.

It means the project must stay honest about where theory ends and proposal begins.
