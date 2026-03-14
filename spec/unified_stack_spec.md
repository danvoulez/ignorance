# Unified Stack Specification
## Ignorance Must Take Form

**Status:** Draft  
**Authority:** `Book.toml`  
**Layer:** Cross-Layer / Whole-System  
**Depends on:**

- `docs/glossary.md`
- `docs/non_negotiables.md`
- `spec/canonical_cell_spec.md`
- `spec/ghost_record_spec.md`
- `spec/epistemic_state_spec.md`
- `spec/continuous_verifier_spec.md`
- `spec/closure_fraud_spec.md`

---

## 1. Purpose

This document defines the **Unified Stack** of the project.

The Unified Stack exists to ensure that:

- the same governed form can survive across scales,
- unresolved but relevant absence remains portable across layers,
- action is structured before execution,
- closure remains a governed right,
- and no layer silently converts ignorance into null, omission, or fabrication.

The Unified Stack is the architecture by which the project's theory becomes system design.

---

## 2. Claim

The project requires a four-floor stack in which:

1. intention is canonicalized,
2. admissibility is materialized deterministically,
3. action is protocolized before execution,
4. and continuation is governed epistemically.

These floors are distinct in responsibility but continuous in structure.

The Unified Stack is therefore the canonical architecture linking:

- semantic form,
- deterministic materialization,
- protocol of action,
- epistemic governance.

---

## 3. Canonical Floors

The Unified Stack MUST contain exactly the following four floors:

1. **Semantic Form**
2. **Deterministic Materialization**
3. **Protocol of Action**
4. **Epistemic Governance**

These floors MUST remain distinct.

Implementations MAY refine them internally, but MUST NOT casually collapse them.

---

## 4. Floor Definitions

### 4.1 Semantic Form

The floor at which intention, meaning, or governed transition is canonicalized into portable accountable structure.

This floor answers:

- what is being meant?
- what is the governed transition?
- what would count as confirmation?
- what futures are structurally declared?

Canonical objects at this floor include:

- Canonical Cell
- semantic ISA
- TDLN-like canonical intent structures

The Semantic Form floor MUST preserve:

- accountability,
- causality,
- confirmation structure,
- branch completeness,
- and status explicitness.

---

### 4.2 Deterministic Materialization

The floor at which semantic intent becomes executable admissibility in deterministic, content-addressed, reproducible form.

This floor answers:

- can this be evaluated deterministically?
- what bytes, checks, or content-addressed artifacts encode admissibility?
- what is the gate boundary before real mutation?

Canonical objects at this floor MAY include:

- policy bits
- deterministic gates
- content hashes / CIDs
- CHECK boundary logic
- bytecode or equivalent executable policy form

The Deterministic Materialization floor MUST preserve:

- semantic fidelity to the floor above,
- deterministic evaluation,
- reproducible admissibility decisions,
- and separation between content identity and runtime side effects.

---

### 4.3 Protocol of Action

The floor at which actions are written, evaluated, and registered before execution.

This floor answers:

- what act is being attempted?
- what was declared before effect?
- what follows under ok, doubt, or not?
- what was committed, denied, ghosted, or escalated?

Canonical objects at this floor include:

- LogLine
- receipts
- ledgered action records
- policy and consent checkpoints
- action ghosts

The Protocol of Action floor MUST preserve:

- write-before-execute,
- declared consequences,
- persistent trace,
- and explicit lifecycle of attempted actions.

---

### 4.4 Epistemic Governance

The floor at which the system governs what it may still legitimately do, infer, carry, and conclude.

This floor answers:

- what does the system currently know?
- what remains unresolved?
- what obligations remain active?
- may the system continue?
- may it close?

Canonical objects at this floor include:

- Epistemic State
- Ghost Records
- Continuous Verifier
- Epistemic Router
- Ghost Debt
- Closure Fraud checks
- manager plane v2 components

The Epistemic Governance floor MUST preserve:

- Ghost visibility,
- trajectory-level verification,
- closure discipline,
- doubt routing,
- and explicit representation of unresolved but relevant absence.

---

## 5. Core Responsibilities by Floor

### 5.1 Semantic Form MUST

- canonicalize governed meaning,
- preserve the Canonical Cell,
- define what the transition is about,
- and expose the structure needed downstream.

### 5.2 Deterministic Materialization MUST

- convert admissibility into deterministic evaluable form,
- preserve content identity,
- and decide gate-level permission before real mutation.

### 5.3 Protocol of Action MUST

- record acts before execution,
- expose `if_ok`, `if_doubt`, `if_not`,
- preserve action lifecycle,
- and create persistent action trace.

### 5.4 Epistemic Governance MUST

- maintain epistemic state,
- preserve Ghosts,
- evaluate admissibility of trajectories,
- route doubt,
- and block closure when closure is not yet earned.

---

## 6. Cross-Floor Continuity

The Unified Stack MUST preserve continuity across floors.

This means:

### 6.1 No Semantic Erasure

A lower floor MUST NOT erase meaningful distinctions introduced by an upper floor.

Examples:

- `if_doubt` MUST NOT disappear at materialization or protocol layers.
- `confirmed_by` MUST NOT degrade into decorative metadata.

### 6.2 No Ignorance Flattening

Unresolved but relevant absence MUST remain representable across floors.

Examples:

- a Ghost MUST NOT become null simply because a lower layer lacks a rich local type,
- doubt MUST NOT be flattened into retry or silent omission.

### 6.3 No Unauthorized Collapse

A lower floor MUST NOT conclude, collapse, or finalize what a higher or governance floor has not authorized.

Examples:

- a model output MUST NOT override closure discipline,
- a workflow success MUST NOT imply epistemic legitimacy automatically.

### 6.4 No Responsibility Leakage

Each floor MUST preserve its own role without usurping the role of another.

Examples:

- semantic form MUST NOT pretend to be execution,
- materialization MUST NOT redefine meaning,
- protocol MUST NOT erase epistemic debt,
- LLM proposal MUST NOT become sovereign closure.

---

## 7. Interfaces Between Floors

The Unified Stack depends on explicit interfaces between floors.

### 7.1 Semantic Form → Deterministic Materialization

The semantic floor passes canonicalized intent and admissibility-relevant structure downward.

This interface MUST preserve:

- identity of the governed transition,
- causal skeleton,
- confirmation expectations,
- and branch structure.

The lower floor MUST NOT reinterpret the meaning arbitrarily.

### 7.2 Deterministic Materialization → Protocol of Action

The materialization floor passes admissibility outcomes and executable gate decisions into protocol space.

This interface MUST preserve:

- deterministic decision outcome,
- content identity,
- and the distinction between allowed, doubtful, and denied paths where applicable.

The protocol floor MUST record, not conceal, gate outcome.

### 7.3 Protocol of Action → Epistemic Governance

The protocol floor passes acts, receipts, statuses, and consequence branches into epistemic state.

This interface MUST preserve:

- action trace,
- action Ghosts where relevant,
- obligations implied by `if_ok`, `if_doubt`, `if_not`,
- and state-relevant provenance.

The governance floor MUST interpret protocol artifacts as live inputs to continuation rights.

### 7.4 Epistemic Governance → Protocol / Execution

The governance floor may authorize, suspend, escalate, or block continuation.

This interface MUST preserve:

- closure decisions,
- doubt routing,
- Ghost-sensitive continuation,
- and governance authority over finality.

Lower floors MUST NOT treat governance-level blocking as optional.

---

## 8. Canonical Flow

A conformant system SHOULD follow a flow structurally equivalent to:

1. meaning or request enters Semantic Form,
2. governed transition is canonicalized,
3. admissibility is compiled or evaluated at Deterministic Materialization,
4. action is written and registered at Protocol of Action,
5. Epistemic Governance updates state, Ghosts, obligations, and budgets,
6. the Continuous Verifier judges continuation,
7. the Epistemic Router classifies:
   - `ok`
   - `doubt`
   - `not`
8. the system either:
   - continues,
   - repairs,
   - escalates,
   - suspends,
   - or blocks closure.

This flow is illustrative of architecture, not a single required runtime implementation.

---

## 9. Canonical Components

A Unified Stack implementation SHOULD include, in some form, the following components:

### At Semantic Form

- Canonical Cell engine
- semantic canonicalizer
- intent normalizer

### At Deterministic Materialization

- deterministic gate
- content-addressed policy artifacts
- CHECK boundary evaluator

### At Protocol of Action

- LogLine registration
- receipt handling
- policy/consent handling
- action ghost persistence

### At Epistemic Governance

- Epistemic State container
- Ghost Engine
- Continuous Verifier
- Epistemic Router
- Closure Guard
- manager plane v2 or equivalent control structure

These components MAY be distributed, but their functions MUST remain represented.

---

## 10. LLM Placement

Large language models MAY participate in the Unified Stack only in limited roles.

A model MAY:

- propose candidates,
- interpret ambiguous requests,
- summarize,
- suggest Ghosts,
- suggest resolutions,
- translate between user language and canonical form.

A model MUST NOT:

- become the sole authority on admissibility,
- erase Ghosts,
- override closure discipline,
- or unilaterally convert doubt into conclusion.

The Unified Stack treats LLMs as **proposers**, not sovereigns.

---

## 11. Failure Modes the Stack Exists to Prevent

The Unified Stack exists in part to prevent the following cross-layer failures:

### 11.1 Silent Ignorance Loss

Absence disappears at layer boundaries.

### 11.2 Null Substitution

Structured absence is flattened into empty fields or generic failures.

### 11.3 Fabricated Continuation

A system continues with plausible output where it should have preserved doubt.

### 11.4 Premature Closure

The system concludes because workflow ended, not because epistemic legitimacy was achieved.

### 11.5 Responsibility Collapse

One layer takes authority that belongs to another.

### 11.6 Managerial Improvisation

Control is performed by free-form chat or untyped improvisation instead of structured governance.

---

## 12. Conformance

A system conforms to this specification only if:

1. it preserves the four canonical floors,
2. it assigns distinct responsibilities to each floor,
3. it preserves the Canonical Cell across the stack,
4. it does not silently erase unresolved but relevant absence,
5. it preserves `if_doubt` as meaningful through the stack,
6. it prevents lower layers from overriding closure discipline,
7. and it keeps LLMs in proposer-level roles rather than sovereign ones.

---

## 13. Non-Goals

This specification does not yet define:

- exact serialization format across all floors,
- exact manager plane message schema,
- exact deterministic gate instruction model,
- exact policy bit language,
- or full runtime orchestration semantics.

Those belong to more specific downstream specs.

---

## 14. Open Questions

The following remain open:

- What is the strongest canonical interface between Semantic Form and Deterministic Materialization?
- How much of `if_doubt` should be executable directly at lower floors versus routed upward?
- Which cross-floor mappings should be lossless by requirement?
- Should action Ghosts and epistemic Ghosts remain distinct classes forever or unify later?
- What is the minimal viable manager plane v2 that preserves governance without overengineering?

---

## 15. Summary

The Unified Stack is the canonical architecture of the project.

It exists so that:

- meaning can be preserved,
- admissibility can be decided deterministically,
- action can be written before execution,
- and ignorance can be carried honestly until closure becomes legitimate.

It is the structure by which one form survives multiple scales without changing nature.
