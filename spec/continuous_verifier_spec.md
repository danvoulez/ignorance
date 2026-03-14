# Continuous Verifier Specification
## Ignorance Must Take Form

**Status:** Draft  
**Authority:** `Book.toml`  
**Layer:** Epistemic Governance  
**Depends on:** `docs/glossary.md`, `spec/epistemic_state_spec.md`, `spec/ghost_record_spec.md`

---

## 1. Purpose

This document defines the **Continuous Verifier** as the component responsible for judging whether a trajectory may continue, branch, suspend, escalate, or close.

The Continuous Verifier does not evaluate only final outputs.  
It evaluates the admissibility of state transitions over time.

The verifier exists to prevent a system from continuing illegitimately under pressure.

---

## 2. Claim

A trustworthy system must verify the legitimacy of its trajectory continuously, not merely inspect the plausibility of its outputs after the fact.

The Continuous Verifier is therefore the mechanism that determines:

- whether a proposed transition is admissible,
- whether doubt must be routed,
- whether obligations must be updated,
- and whether closure remains legitimate.

---

## 3. Scope

The Continuous Verifier is responsible for:

- local transition admissibility,
- trajectory-level governance,
- budget monitoring,
- ghost-sensitive continuation,
- and closure preconditions.

The Continuous Verifier is not:

- a generic linter,
- a style checker,
- a confidence estimator,
- or a final-output-only evaluator.

---

## 4. Inputs

A conformant Continuous Verifier MUST be able to inspect at least:

1. current epistemic state `x_t`
2. proposed next state `x_(t+1)` or proposed transition `T`
3. active ghosts
4. active obligations
5. active branches
6. current budgets
7. current goal
8. provenance of newly introduced claims or transitions

---

## 5. Outputs

A conformant Continuous Verifier MUST return a decision in one of the following classes:

1. `admit`
2. `admit_with_doubt`
3. `repair_required`
4. `escalate`
5. `reject`
6. `closure_blocked`

Implementations MAY define subcodes, but these canonical decision classes MUST remain mappable.

---

## 6. Core Responsibilities

The Continuous Verifier MUST determine:

### 6.1 Whether the proposed transition preserves the goal

A transition MUST NOT silently drift into solving a different problem without explicit reframe.

### 6.2 Whether provenance remains closed

New claims MUST be attributable to:

- evidence,
- derivation,
- or explicitly marked hypothesis.

### 6.3 Whether contradictions remain admissible

The state MUST NOT exceed tolerated contradiction without routing through doubt, repair, or escalation.

### 6.4 Whether semantic drift remains bounded

The system MUST NOT move too far from the original problem or meaning without explicit re-grounding.

### 6.5 Whether recoverability remains acceptable

The system MUST NOT enter states from which error correction becomes disproportionately difficult without explicit justification.

### 6.6 Whether ghost conditions alter continuation rights

Active Ghosts MUST affect admissibility, not merely be observed passively.

### 6.7 Whether closure remains legitimate

The verifier MUST inspect closure preconditions continuously, not only at final output time.

---

## 7. Canonical Local Invariants

The Continuous Verifier MUST inspect at least the following local invariants.

### 7.1 Goal Preservation

A proposed transition preserves goal if it remains directed toward the currently active objective or explicitly performs a valid goal revision.

Violation examples:

- silent task switching
- drift into proxy objective
- conclusion about a different claim than the one under question

### 7.2 Provenance Closure

A proposed transition satisfies provenance closure if each newly introduced claim is traceable to:

- evidence,
- derivation,
- or explicit hypothesis status.

Violation examples:

- unsupported assertion
- surface paraphrase presented as support
- fabricated detail without grounding

### 7.3 Contradiction Budget

A proposed transition satisfies contradiction budget if it does not increase unresolved internal incompatibility beyond admissible bounds.

Contradiction MAY include:

- logical incompatibility
- state inconsistency
- mutually incompatible commitments
- unresolved conflicting support

### 7.4 Semantic Drift Bound

A proposed transition satisfies semantic drift bound if it does not move too far from the operative semantics of the current goal, branch, and claim structure.

Drift MAY include:

- concept substitution
- redefinition without declaration
- moving from evidence request to conclusion
- shifting object identity silently

### 7.5 Recoverability

A proposed transition satisfies recoverability if an error in the transition remains corrigible without disproportionate downstream damage.

Transitions that make recovery very difficult SHOULD be treated with suspicion, especially under doubt.

---

## 8. Global Conditions

Beyond local invariants, the verifier MUST be able to inspect broader trajectory conditions, including:

- accumulation of ghost debt,
- repeated unresolved branching,
- progressive erosion of provenance quality,
- branch divergence without consolidation,
- attempts to conclude under critical unresolved absence.

These are not tied to one step only.  
They are properties of the evolving path.

---

## 9. Ghost-Aware Verification

The Continuous Verifier MUST be Ghost-aware.

This means:

### 9.1 Active Ghosts influence admissibility

Ghosts are not comments.  
They change what may be done next.

### 9.2 Critical Ghosts may block continuation

A proposed transition MAY be rejected or downgraded to doubt if it proceeds as though a critical Ghost did not exist.

### 9.3 Ghost inheritance must be explicit

A branch or transition that continues under unresolved Ghosts MUST carry them forward explicitly unless they are resolved, dismissed, merged, split, or escalated.

### 9.4 Ghost erasure is forbidden

A transition MUST NOT silently remove a Ghost from state.

---

## 10. Doubt Routing

The Continuous Verifier MUST distinguish between:

- inadmissible continuation,
- and continuation that remains possible only under doubt.

A system MUST NOT map every failed local invariant directly to rejection.

Some violations require:

- repair,
- suspension,
- or routing through `doubt`.

Examples:

- missing evidence with preserved structure,
- unresolved linkage that does not yet poison the whole branch,
- causal incompleteness that permits investigation but not closure.

---

## 11. Closure Sensitivity

The Continuous Verifier MUST inspect closure continuously.

This means:

- closure is never judged solely by output fluency,
- closure eligibility is a function of the state,
- and closure preconditions MAY fail even when intermediate continuation remains allowed.

The verifier MUST be able to distinguish:

- continuation-admissible

from

- closure-admissible

These are not the same thing.

---

## 12. Decision Semantics

### 12.1 `admit`

The proposed transition is admissible as-is.

### 12.2 `admit_with_doubt`

The transition may proceed, but only under explicit doubt routing and preserved unresolvedness.

### 12.3 `repair_required`

The system may not proceed until certain structural issues are corrected.

Examples:

- missing provenance
- unresolved state inconsistency
- malformed obligation update

### 12.4 `escalate`

The system should route the matter outward:

- human witness,
- stronger verification,
- policy decision,
- external evidence retrieval.

### 12.5 `reject`

The proposed transition is inadmissible and must not occur.

### 12.6 `closure_blocked`

The system may continue investigating, but may not close the case, branch, or answer.

---

## 13. Non-Goals

The Continuous Verifier does not decide:

- final truth in the philosophical sense,
- user interface phrasing,
- model decoding strategy,
- or semantic canonicalization itself.

It governs legitimacy of movement through epistemic state.

---

## 14. Minimal Pseudocode

```text
evaluate(x_t, T, x_t1):
  check goal_preservation
  check provenance_closure
  check contradiction_budget
  check semantic_drift_bound
  check recoverability
  inspect ghosts
  inspect obligations
  inspect closure conditions

  if closure illegitimate:
      return closure_blocked

  if unrecoverable structural violation:
      return reject

  if repairable structural violation:
      return repair_required

  if continuation possible only with unresolvedness preserved:
      return admit_with_doubt

  if external resolution is required:
      return escalate

  return admit
```

This pseudocode is illustrative, not normative.

---

## 15. Conformance

A system conforms to this specification only if it:

1. verifies transitions continuously,
2. checks at least the canonical local invariants,
3. is Ghost-aware,
4. distinguishes continuation from closure,
5. can route through doubt,
6. can block closure independently of output generation,
7. and does not reduce verification to confidence scoring alone.

---

## 16. Open Questions

The following remain open:

- Which invariants are absolute versus tunable?
- Should contradiction, drift, and debt be inspected independently or jointly?
- Can the verifier directly spawn Ghosts?
- What is the correct verification cadence in expensive systems?
- How should the verifier interact with the manager plane?

---

## 17. Summary

The Continuous Verifier is the component that judges whether a system still has the right to continue.

It protects the architecture from:

- unsupported transitions,
- silent drift,
- erased uncertainty,
- and illegitimate closure.

It verifies not just where the system ends, but how it gets there.
