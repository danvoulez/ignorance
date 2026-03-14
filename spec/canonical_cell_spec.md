# Canonical Cell Specification
## Ignorance Must Take Form

**Status:** Draft  
**Authority:** `Book.toml`  
**Layer:** Semantic Form / Protocol Foundation  
**Depends on:** `docs/glossary.md`, `RESEARCH_CHARTER.md`

---

## 1. Purpose

This document defines the **Canonical Cell** as the minimum accountable form of a governed transition.

The Canonical Cell is intended to be:

- semantically stable across layers,
- compact enough to remain invariant under scale change,
- expressive enough to carry action, causality, evidence, branching, and state,
- and strict enough to prevent silent loss of accountability.

This specification treats the Canonical Cell as a **normative structure**, not a convenience schema.

---

## 2. Claim

The Canonical Cell is the smallest known structure capable of carrying, in one object:

- responsible agency,
- transformation,
- target,
- temporal registration,
- epistemic grounding,
- future branching under confirmation, doubt, or rejection,
- and lifecycle state.

The Canonical Cell is therefore the proposed **minimal accountable form of a governed transition**.

---

## 3. Canonical Fields

A Canonical Cell MUST contain exactly the following nine fields:

1. `who`
2. `did`
3. `this`
4. `when`
5. `confirmed_by`
6. `if_ok`
7. `if_doubt`
8. `if_not`
9. `status`

No field is optional at the structural level.

Implementations MAY allow temporary drafting states, but any committed or authoritative cell MUST contain all nine fields.

---

## 4. Field Definitions

### 4.1 `who`

The responsible agent of the governed transition.

This field identifies the locus of responsibility for the act, claim, or transition being registered.

`who` MUST be resolvable to an accountable actor class, such as:

- human,
- service,
- system component,
- institution,
- protocol actor.

`who` MUST NOT be omitted.

---

### 4.2 `did`

The action, transformation, or claim-bearing operation performed.

`did` defines what kind of transition is being attempted, asserted, or recorded.

Examples:

- created
- approved
- denied
- queried
- linked
- inferred
- requested
- escalated

`did` MUST describe the operative transformation, not merely a narrative paraphrase.

---

### 4.3 `this`

The object, content, claim, target, or evidence to which the action applies.

`this` identifies what the transition is about.

Depending on layer, `this` MAY denote:

- an entity,
- a document,
- a claim,
- a state object,
- a policy target,
- an epistemic dependency,
- a piece of evidence.

`this` MUST be specific enough for the transition to be interpretable and replayable.

---

### 4.4 `when`

The temporal registration point of the transition.

`when` records when the cell enters governed space.

It MAY represent:

- wall-clock time,
- logical time,
- event time,
- ledger time,
- monotonic sequence position.

`when` MUST establish orderability relative to other cells.

---

### 4.5 `confirmed_by`

The authority, evidence, witness, derivation, or condition that grants epistemic legitimacy to the transition.

This field defines what would count as confirmation, support, or admissible grounding.

`confirmed_by` MAY reference:

- a document,
- a witness,
- a signature,
- a receipt,
- a measurement,
- a derivation,
- a verification routine,
- a policy decision.

`confirmed_by` MUST NOT be treated as decorative metadata.  
It is the field that anchors epistemic weight.

---

### 4.6 `if_ok`

The declared continuation if the transition is confirmed and accepted.

This field specifies what becomes permitted or expected under successful confirmation.

Examples:

- advance pointer
- commit state
- release funds
- mark claim as supported
- continue workflow
- authorize next step

`if_ok` MUST be structurally explicit.

---

### 4.7 `if_doubt`

The declared continuation if the transition cannot yet be confirmed or denied.

This field is the formal home of unresolved but relevant absence.

Examples:

- spawn ghost
- request evidence
- escalate witness
- suspend closure
- branch investigation
- retry under constraint
- defer and preserve state

`if_doubt` MUST exist even when the author expects certainty.

`if_doubt` is not a fallback afterthought.  
It is a required branch of accountable transition.

---

### 4.8 `if_not`

The declared continuation if the transition is rejected, denied, or fails.

Examples:

- deny action
- abort transition
- persist action ghost
- rollback
- escalate denial
- notify actor
- terminate branch

`if_not` MUST specify what follows from non-acceptance.

---

### 4.9 `status`

The current lifecycle position of the cell.

`status` expresses where the governed transition currently stands.

Examples MAY include:

- draft
- pending
- committed
- ghost
- denied
- resolved
- escalated
- closed

Allowed status vocabularies MAY differ by layer, but every implementation MUST define them explicitly.

---

## 5. Structural Properties

A Canonical Cell MUST satisfy the following structural properties:

### 5.1 Completeness

All nine fields MUST be present.

### 5.2 Accountability

The cell MUST identify who is responsible for the transition.

### 5.3 Actionability

The cell MUST identify what transition is being attempted or claimed.

### 5.4 Object Binding

The cell MUST bind the transition to a target or content-bearing object.

### 5.5 Temporal Orderability

The cell MUST be placeable in an ordered trajectory.

### 5.6 Epistemic Grounding

The cell MUST declare what grants or would grant confirmation.

### 5.7 Branch Completeness

The cell MUST explicitly represent continuations for:

- acceptance,
- doubt,
- rejection.

### 5.8 Lifecycle Explicitness

The cell MUST indicate current state.

---

## 6. Semantics

The Canonical Cell is not merely descriptive.

It has three semantic roles simultaneously:

### 6.1 Descriptive Role

It records a governed transition.

### 6.2 Normative Role

It declares what counts as legitimate continuation under multiple epistemic regimes.

### 6.3 Operational Role

It can be compiled, interpreted, routed, or enforced by downstream systems.

The Canonical Cell therefore acts as both:

- a record of what is at stake,
- and a commitment structure for what may happen next.

---

## 7. Causality

The tuple `who / did / this / when` constitutes the cell's minimum causal skeleton.

Together, these fields define:

- source,
- intervention,
- object,
- order.

This specification treats that quartet as the minimum intrinsic causal structure of a governed transition.

If any of the four is missing, the transition becomes causally underdetermined.

---

## 8. Epistemic Regimes

The Canonical Cell explicitly recognizes three epistemic regimes:

### 8.1 Confirmation

The transition is supported or accepted.

### 8.2 Doubt

The transition is not yet confirmed, but cannot be erased or ignored.

### 8.3 Rejection

The transition is denied, fails, or is ruled inadmissible.

These regimes are represented structurally through:

- `if_ok`
- `if_doubt`
- `if_not`

A system implementing the Canonical Cell MUST preserve the distinction between doubt and rejection.

---

## 9. Why `if_doubt` is Mandatory

A system without `if_doubt` can only:

- confirm,
- reject,
- or silently improvise.

That is insufficient for trustworthy computation.

`if_doubt` is mandatory because many meaningful transitions enter an epistemic regime where:

- evidence is incomplete,
- dependencies remain unresolved,
- relevant absences must persist,
- and continuation must remain honest without premature closure.

This specification therefore treats `if_doubt` as non-negotiable.

---

## 10. Relationship to Ghost Records

The Canonical Cell does not require that every `if_doubt` branch spawn a Ghost Record.

However:

- Ghost Records are a canonical downstream realization of unresolved relevant absence,
- and `if_doubt` is the branch through which Ghost creation is typically authorized.

In that sense:

- the Canonical Cell provides the structural place for doubt,
- Ghost Records provide the object form of unresolved doubt.

---

## 11. Relationship to LogLine

The LogLine is the protocolized form of the Canonical Cell.

This specification does not require ledger semantics by itself.  
However, it is compatible with write-before-execute systems in which the cell is registered before mutation occurs.

Where LogLine exists, the Canonical Cell is its semantic core.

---

## 12. Relationship to Proof-Carrying Inference

In inference contexts, the Canonical Cell may represent not only acts but reasoning steps.

In that setting:

- `who` identifies the responsible reasoning actor,
- `did` identifies the inference operation,
- `this` identifies the claim or object under transition,
- `confirmed_by` identifies support,
- `if_doubt` identifies how unresolved reasoning must continue,
- `status` identifies current epistemic position.

The Canonical Cell is therefore admissible as a unit of proof-carrying transition.

---

## 13. Serialization Guidance

Implementations MAY serialize Canonical Cells as:

- JSON objects,
- TOML records,
- database rows,
- ledger entries,
- protobuf messages,
- typed structs.

However, serialization MUST preserve:

- field names or canonical aliases,
- branch distinction,
- status explicitness,
- and referential integrity for `confirmed_by` and `this`.

A serializer MUST NOT collapse:

- `if_doubt` into `if_not`,
- `confirmed_by` into freeform comments,
- or `status` into implicit state.

---

## 14. Canonical Example

```json
{
  "who": "manager.default",
  "did": "request_evidence",
  "this": "invoice_2022_q4",
  "when": "2026-03-14T10:32:00Z",
  "confirmed_by": "document_receipt(invoice_2022_q4)",
  "if_ok": "attach_evidence_and_continue",
  "if_doubt": "spawn_evidence_ghost_and_suspend_closure",
  "if_not": "deny_claim_and_escalate",
  "status": "pending"
}
```

This example is illustrative, not normative.

---

## 15. Invalid Example

```json
{
  "who": "assistant",
  "did": "answer",
  "this": "claim_x",
  "when": "2026-03-14T10:32:00Z",
  "if_ok": "return_response",
  "if_not": "retry",
  "status": "done"
}
```

This cell is invalid because it omits:

- `confirmed_by`
- `if_doubt`

It therefore lacks both epistemic grounding and a formal regime for unresolved uncertainty.

---

## 16. Conformance

A system conforms to this specification only if:

1. it preserves all nine fields,
2. it treats `if_doubt` as a first-class branch,
3. it does not collapse epistemic grounding into optional metadata,
4. it does not treat status as implicit,
5. and it maintains the cell as a stable accountable object across transitions.

---

## 17. Non-Goals

This specification does not yet define:

- the full Ghost Record schema,
- the complete epistemic state model,
- closure fraud predicates,
- debt computation,
- lifecycle algebra across all floors.

These belong to downstream specs.

---

## 18. Open Questions

The following remain open for future refinement:

- Should `confirmed_by` allow composite authorities directly or only references?
- Should `status` be globally canonical or floor-specific?
- What is the strongest possible type discipline for `did` and `this` across layers?
- How much normalization is required for cross-floor portability?
- Should the cell admit nested cells as values inside `this` or `confirmed_by`?

---

## 19. Summary

The Canonical Cell is the proposed minimum accountable form of a governed transition.

It is small by design.  
Its rigidity is part of the claim.

It exists to preserve:

- agency,
- action,
- target,
- time,
- confirmation,
- doubt,
- consequence,
- and state

within one portable structure that does not need to change nature when it changes scale.
