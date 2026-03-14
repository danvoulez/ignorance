# Epistemic State Specification
## Ignorance Must Take Form

**Status:** Draft  
**Authority:** `Book.toml`  
**Layer:** Epistemic Governance  
**Depends on:** `docs/glossary.md`, `spec/canonical_cell_spec.md`, `spec/ghost_record_spec.md`

---

## 1. Purpose

This document defines the **Epistemic State** as the canonical container of what the system currently:

- knows,
- does not yet know,
- owes,
- may still do,
- and may no longer legitimately conclude.

The Epistemic State is the object over which governed reasoning occurs.

Reasoning in this project is not defined as text generation.  
It is defined as **transition between epistemic states**.

---

## 2. Claim

An Epistemic State is the minimum stateful structure required for a system to carry:

- claims,
- evidence,
- obligations,
- ghosts,
- provenance,
- uncertainty,
- branches,
- and closure conditions

across time without erasing unresolved but relevant absence.

---

## 3. Normative Definition

A conformant Epistemic State MUST contain at least the following components:

1. `state_id`
2. `goal`
3. `claims`
4. `evidence`
5. `obligations`
6. `ghosts`
7. `provenance`
8. `branches`
9. `status`
10. `budgets`

These components define the minimum governed state.

Implementations MAY add internal fields, but MUST preserve these canonical components.

---

## 4. Field Definitions

### 4.1 `state_id`

A unique stable identifier for the state snapshot.

### 4.2 `goal`

The current problem, objective, or admissible target of the trajectory.

The goal MUST be explicit enough to evaluate goal preservation.

### 4.3 `claims`

The set of currently active claims, propositions, or asserted state-bearing contents.

Claims MAY be:

- supported,
- unsupported,
- provisional,
- disputed,
- inherited.

### 4.4 `evidence`

The set of evidence-bearing objects currently available to the state.

Evidence MAY include:

- receipts,
- documents,
- witnesses,
- measurements,
- policy results,
- derivations.

### 4.5 `obligations`

The set of pending required actions produced by the current state.

Examples:

- request evidence
- resolve linkage
- escalate witness
- suspend closure
- verify claim

### 4.6 `ghosts`

The set of active Ghost Records carried by the state.

Ghosts are not metadata.  
They are part of the state itself.

### 4.7 `provenance`

The structured trace of how the current state came to contain its claims, evidence, ghosts, and obligations.

### 4.8 `branches`

The currently active, suspended, or terminated branches of continuation available from this state.

### 4.9 `status`

The lifecycle position of the state.

Examples MAY include:

- active
- suspended
- blocked
- ready_for_closure
- closed
- escalated

### 4.10 `budgets`

The current quantitative or bounded governance values relevant to continuation.

At minimum this SHOULD support:

- contradiction budget
- semantic drift bound
- ghost load
- ghost debt

---

## 5. Semantics

The Epistemic State plays three roles simultaneously:

### 5.1 Memory Role

It preserves what the system currently carries.

### 5.2 Governance Role

It determines what the system may legitimately do next.

### 5.3 Closure Role

It determines whether the system has the right to conclude.

---

## 6. Required Structural Properties

A conformant Epistemic State MUST satisfy:

### 6.1 Explicit Goal

A goal MUST exist.

### 6.2 Claim Visibility

Claims MUST be structurally represented, not only implied by text.

### 6.3 Evidence Visibility

Available support MUST be represented explicitly.

### 6.4 Obligation Visibility

Pending duties MUST be represented explicitly.

### 6.5 Ghost Visibility

Relevant unresolved absences MUST remain present as Ghost Records.

### 6.6 Provenance Traceability

The origin of state-bearing contents MUST be recoverable.

### 6.7 Branch Explicitness

Continuation possibilities MUST not remain implicit.

### 6.8 Budget Availability

The state MUST expose the quantities or conditions needed to judge admissibility.

---

## 7. Transition Semantics

A transition from state `x_t` to state `x_(t+1)` is admissible only if:

1. goal preservation is maintained or explicitly revised,
2. provenance is not broken,
3. ghosts are not silently erased,
4. obligations are updated honestly,
5. closure conditions are not violated,
6. budgets remain within admissible range unless routed through doubt or escalation.

A transition MUST NOT merely overwrite the state.  
It MUST preserve the meaning of change.

---

## 8. Relationship to Ghost Records

Ghost Records are members of the Epistemic State.

They are not external annotations.

A state that depends on unresolved relevant absence but does not contain corresponding Ghost Records is structurally incomplete.

---

## 9. Relationship to Closure

Closure is evaluated over the Epistemic State, not over surface output alone.

A state MAY be eligible for closure only if:

- closure-critical ghosts are resolved, dismissed, or explicitly escalated,
- obligations required for closure are satisfied,
- contradiction and drift remain within acceptable bounds,
- and no Closure Fraud condition holds.

---

## 10. Relationship to the Continuous Verifier

The Continuous Verifier evaluates the Epistemic State before, during, and after transitions.

The verifier judges:

- whether the current state may continue,
- whether a proposed next state is admissible,
- and whether closure is legitimate.

---

## 11. Minimal Example

```json
{
  "state_id": "state_0001",
  "goal": "determine whether claim_x may be concluded",
  "claims": ["claim_x"],
  "evidence": ["receipt_17"],
  "obligations": ["resolve_evidence_ghost_42"],
  "ghosts": ["ghost_evidence_42"],
  "provenance": ["cell_12", "transition_14"],
  "branches": ["doubt_branch_a"],
  "status": "active",
  "budgets": {
    "contradiction_budget": 0.1,
    "semantic_drift_bound": 0.2,
    "ghost_load": 1,
    "ghost_debt": 0.7
  }
}
```

---

## 12. Invalid State Example

A state is invalid if:

- it contains claims with no provenance,
- it depends on unresolved absence without ghosts,
- it closes without inspecting budgets,
- or it routes continuation without representing obligations.

---

## 13. Non-Goals

This specification does not yet define:

- exact claim schema,
- exact evidence typing,
- the precise formula for criticality,
- full branch algebra,
- or the complete closure predicate.

These belong to downstream specifications.

---

## 14. Summary

The Epistemic State is the canonical container of governed uncertainty.

It is where:

- knowledge lives,
- ignorance persists,
- obligations accumulate,
- and the right to continue is judged.
