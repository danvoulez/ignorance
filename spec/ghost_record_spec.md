# Ghost Record Specification
## Ignorance Must Take Form

**Status:** Draft  
**Authority:** `Book.toml`  
**Layer:** Epistemic Governance  
**Depends on:** `docs/glossary.md`, `spec/canonical_cell_spec.md`, `RESEARCH_CHARTER.md`

---

## 1. Purpose

This document defines the **Ghost Record** as the canonical object form of unresolved but relevant absence.

A Ghost Record exists when a system encounters something it cannot yet affirm, but no longer has the right to ignore.

The Ghost Record is intended to:

- preserve unresolved but consequential absence,
- prevent silent collapse of uncertainty into null or fabrication,
- provide a stable target for investigation, routing, and resolution,
- and carry ignorance across transitions, layers, and time without loss of accountability.

This specification treats Ghost Records as **first-class computational objects**, not as placeholders of convenience.

---

## 2. Claim

A Ghost Record is a placeholder with identity for something the system cannot yet affirm but no longer has the right to ignore.

A Ghost Record is not:

- a null,
- a missing field,
- an exception,
- a generic TODO,
- or a freeform note.

A Ghost Record is:

- identity-bearing,
- provenance-bearing,
- lifecycle-bearing,
- obligation-generating,
- and computationally consequential.

Ghost Records are the primary mechanism by which **ignorance takes form**.

---

## 3. Normative Definition

A Ghost Record MUST represent an unresolved absence that satisfies all of the following conditions:

1. **Relevance**  
   The unresolved item materially affects a current or future governed transition.

2. **Non-Erasability**  
   The system cannot honestly proceed as though the absence were irrelevant or nonexistent.

3. **Non-Affirmability**  
   The system does not yet have sufficient basis to assert the missing object, relation, cause, or evidence as present or confirmed.

4. **Preservability**  
   The unresolved absence can and should be carried forward as an explicit object.

If any of these conditions fail, a Ghost Record MUST NOT be created.

---

## 4. Required Properties

A Ghost Record MUST carry at least the following properties:

1. `ghost_id`
2. `ghost_type`
3. `shape`
4. `origin`
5. `reason`
6. `obligations`
7. `status`

Additional properties MAY be included by layer or implementation, but these seven are minimum.

---

## 5. Field Definitions

### 5.1 `ghost_id`

A unique and stable identifier for the Ghost Record.

`ghost_id` MUST:

- be unique within the relevant system scope,
- remain stable across updates to the same ghost,
- and be referenceable by downstream systems, transitions, and logs.

A Ghost without stable identity is not conformant.

---

### 5.2 `ghost_type`

The canonical class of unresolved absence.

Allowed canonical ghost types are:

- `entity_ghost`
- `evidence_ghost`
- `causal_ghost`
- `linkage_ghost`

Implementations MAY define subtypes, but MUST preserve one of the canonical parent classes.

---

### 5.3 `shape`

A structured description of what kind of thing is missing or unresolved.

`shape` answers:

- what kind of object might this be?
- what role would it play if resolved?
- what constraints already apply?

Examples:

- `"invoice document for Q4 2022"`
- `"causal step between approval and transfer"`
- `"identity link between customer_A and account_B"`
- `"unconfirmed actor responsible for state change X"`

`shape` MUST be specific enough to guide investigation.

---

### 5.4 `origin`

A reference to the transition, claim, observation, or cell that caused the Ghost to be created.

`origin` MUST indicate where the unresolved absence became structurally visible.

Examples:

- a Canonical Cell id,
- a LogLine id,
- an inference step id,
- a manager event id,
- a document reference,
- a receipt reference.

Ghosts without origin are invalid.

---

### 5.5 `reason`

A structured explanation of why the Ghost exists.

`reason` MUST state why the system could not proceed with affirmation, including one or more of:

- missing evidence,
- unresolved entity,
- incomplete causal chain,
- conflicting references,
- insufficient confirmation,
- unresolved dependency.

`reason` MUST NOT be empty.

---

### 5.6 `obligations`

The actions, checks, or routes now required because the Ghost exists.

Examples:

- request evidence,
- run entity resolution,
- seek witness,
- query external source,
- defer closure,
- escalate to human review.

A Ghost Record MUST generate at least one obligation.

If a Ghost creates no obligation, it is not operationally meaningful.

---

### 5.7 `status`

The current lifecycle position of the Ghost.

Canonical lifecycle statuses are:

- `spawned`
- `refined`
- `resolved`
- `split`
- `merged`
- `dismissed`
- `escalated`

Implementations MAY add internal statuses, but these canonical statuses MUST remain mappable.

---

## 6. Canonical Ghost Types

### 6.1 Entity Ghost

Represents a missing or unresolved entity required by the epistemic state.

Examples:

- unknown actor,
- unresolved organization,
- unverified referenced identity.

An Entity Ghost is appropriate when the system knows that some entity role must be filled but cannot yet determine the occupant.

---

### 6.2 Evidence Ghost

Represents missing or unavailable evidence required to support a claim, act, or transition.

Examples:

- referenced document not retrieved,
- missing signature,
- absent receipt,
- unavailable measurement.

An Evidence Ghost is appropriate when the system lacks a confirming artifact that materially affects legitimacy.

---

### 6.3 Causal Ghost

Represents a missing or unresolved causal step, dependency, or mechanism.

Examples:

- unexplained transition from A to C,
- unknown intermediate approval,
- missing cause for an observed effect.

A Causal Ghost is appropriate when the current state implies causal structure the system cannot yet account for.

---

### 6.4 Linkage Ghost

Represents unresolved identity or referential linkage between objects, events, claims, or entities.

Examples:

- possible match between two entities,
- uncertain relation between two records,
- suspected co-reference not yet justified.

A Linkage Ghost is appropriate when the system suspects connection but lacks right to collapse the link.

---

## 7. Spawn Conditions

A Ghost Record MUST be spawned when all of the following hold:

1. a governed transition, claim, or closure depends on something unresolved,
2. that unresolved absence is relevant to legitimacy or continuation,
3. the system cannot yet affirm the missing element,
4. and proceeding without preserving it would risk erasure, fabrication, or illegitimate closure.

A Ghost Record MUST NOT be spawned merely because:

- data is absent but irrelevant,
- the system is curious,
- a field is optional,
- a branch is already safely terminated,
- or an implementation wants a generic placeholder.

Ghost spawning is a governance act, not a convenience feature.

---

## 8. Spawn Sources

Ghosts MAY be spawned from:

- Canonical Cells,
- LogLines,
- reasoning steps,
- verification failures,
- failed retrievals,
- contradictory state,
- unresolved branch dependencies,
- manager-plane events,
- human annotations,
- protocol observations.

The source MUST be preserved in `origin`.

---

## 9. Lifecycle

A Ghost Record MUST move through a lifecycle.

### 9.1 `spawned`

The Ghost has been created and registered.

### 9.2 `refined`

The Ghost has gained more structure without yet being resolved.

### 9.3 `resolved`

The absence has been legitimately resolved into confirmed, dismissed, or fully accounted structure.

### 9.4 `split`

One Ghost has been discovered to represent multiple distinct unresolved absences.

### 9.5 `merged`

Multiple Ghosts have been determined to represent the same unresolved absence.

### 9.6 `dismissed`

The Ghost is no longer relevant, necessary, or justified.

Dismissal MUST be justified; a Ghost MUST NOT disappear silently.

### 9.7 `escalated`

The Ghost cannot be resolved within the current automated path and is routed outward.

Examples:

- human witness request,
- policy escalation,
- deeper investigation path.

---

## 10. Structural Requirements

A conformant Ghost Record MUST satisfy:

### 10.1 Identity

It MUST have stable identity.

### 10.2 Provenance

It MUST indicate where it came from.

### 10.3 Type

It MUST belong to a canonical ghost class.

### 10.4 Reason

It MUST state why it exists.

### 10.5 Operationality

It MUST create obligations or routing consequences.

### 10.6 Persistence

It MUST remain present until legitimately resolved, dismissed, merged, split, or escalated.

### 10.7 Non-Silent Death

It MUST NOT vanish without recorded lifecycle transition.

---

## 11. Semantics

A Ghost Record plays three roles at once:

### 11.1 Epistemic Role

It marks something not yet affirmable.

### 11.2 Operational Role

It changes what the system is now obliged or permitted to do.

### 11.3 Structural Role

It occupies persistent space in the epistemic state and deforms future admissibility.

A Ghost is not passive.  
It is active unresolvedness.

---

## 12. Relationship to Null

A null is a passive absence marker.  
A Ghost Record is structured, identity-bearing absence.

Null answers:

- nothing,
- not found,
- no value.

Ghost answers:

- something unresolved matters here,
- it has origin,
- it has consequences,
- it must be carried.

A system MUST NOT substitute null for Ghost when non-erasable absence is present.

---

## 13. Relationship to Doubt

Ghost Records are a primary materialization of `if_doubt`.

Not every doubt requires a Ghost, but every Ghost is a consequence of doubt becoming structurally significant.

Where the Canonical Cell defines the branch:

- `if_doubt`

the Ghost Record often defines the object that the doubt becomes.

---

## 14. Relationship to Proof-Carrying Inference

In reasoning systems, Ghost Records are the lawful alternative to fabrication.

When a transition encounters unresolved but relevant absence, it MUST:

- spawn or inherit a Ghost,
- route via doubt,
- or otherwise preserve the unresolvedness structurally.

A reasoning step that fabricates instead of ghosting is epistemically invalid.

---

## 15. Relationship to Closure

Ghosts directly affect whether closure is legitimate.

A Ghost may be:

- peripheral,
- load-bearing,
- or closure-critical.

Not all Ghosts block closure, but critical unresolved Ghosts MAY render closure inadmissible.

Closure-related policies MUST inspect Ghost state, not only surface confidence.

---

## 16. Relationship to Ghost Load and Ghost Debt

Ghost Records are the units over which Ghost Load and Ghost Debt are computed.

### Ghost Load

The current burden of unresolved absence carried by the system.

### Ghost Debt

The accumulated liability of unresolved absence that has become critical, overdue, or structurally dangerous.

Ghosts therefore serve as:

- epistemic objects,
- operational obligations,
- and accounting units.

---

## 17. Conformance Rules

A system conforms to this specification only if it:

1. creates Ghosts only under justified unresolved relevance,
2. preserves stable identity,
3. records origin and reason,
4. assigns canonical type,
5. generates obligations,
6. maintains explicit lifecycle status,
7. prevents silent disappearance,
8. distinguishes Ghosts from nulls,
9. and allows Ghosts to influence admissibility and closure.

---

## 18. Canonical Example

```json
{
  "ghost_id": "ghost_evidence_0042",
  "ghost_type": "evidence_ghost",
  "shape": "signed invoice document for 2022 Q4",
  "origin": "cell_2026_03_14_1032_request_evidence",
  "reason": "claim requires documentary support that has not yet been retrieved",
  "obligations": [
    "query_document_store",
    "suspend_closure",
    "escalate_if_missing_after_timeout"
  ],
  "status": "spawned"
}
```

---

## 19. Non-Goals

This specification does not yet define:

- the full algebra of Ghost Load and Ghost Debt computation,
- closure-criticality predicates,
- escalation policy,
- or integration with specific manager-plane or verifier APIs.

These belong to downstream specs.
