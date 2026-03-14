# Manager Plane v2 Specification
## Ignorance Must Take Form

**Status:** Draft  
**Authority:** `Book.toml`  
**Layer:** Epistemic Governance  
**Depends on:** `docs/glossary.md`, `spec/epistemic_state_spec.md`, `spec/continuous_verifier_spec.md`, `spec/ghost_record_spec.md`, `spec/unified_stack_spec.md`

---

## 1. Purpose

This document defines the **Manager Plane v2** as the typed, non-chat, event-driven control plane responsible for dispatching tasks, routing epistemic outcomes, and coordinating the ghost engine, verifier, and closure guard.

The Manager Plane is not a conversational interface. It is a governed layer that consumes events, produces receipts and witnesses, and issues typed actions.

---

## 2. Claim

A trustworthy system requires a control plane that:

- is typed (structured actions, not freeform text),
- is event-driven (reactive to state and verification outcomes),
- is replayable (events and receipts support audit),
- and allocates power correctly (propose, verify, execute, conclude are distinct roles).

The Manager Plane v2 is that control plane.

---

## 3. Scope

The Manager Plane is responsible for:

- receiving and emitting **events**,
- issuing and tracking **receipts**,
- coordinating **witnesses** where required,
- dispatching typed **actions** to the ghost engine, verifier, closure guard, and workers,
- and ensuring that continuation and closure follow epistemic governance.

The Manager Plane is not:

- a chat interface,
- a natural-language command layer,
- or the LLM proposer itself.

---

## 4. Events, Receipts, Witnesses

### 4.1 Events

**Events** are structured records of something that occurred or was requested in the system.

An event MUST carry at least:

- event identifier,
- type or kind,
- timestamp or sequence,
- source (e.g. proposer, verifier, user),
- payload (reference to cell, state, ghost, or action).

Events are the primary input to the Manager Plane.

### 4.2 Receipts

**Receipts** are structured acknowledgments or outcomes produced by the Manager Plane or its delegates.

A receipt MUST carry at least:

- receipt identifier,
- reference to the event or request it answers,
- outcome (e.g. admitted, blocked, routed_to_doubt),
- reference to any new state, ghost, or obligation.

Receipts support audit and replay.

### 4.3 Witnesses

**Witnesses** are attestations from external or authoritative sources (human, system, document) that support or refute a claim or transition.

The Manager Plane MAY request witnesses and MUST record when a witness is required, provided, or missing.

---

## 5. Typed Action Algebra

The Manager Plane MUST operate over a typed set of actions. The following are canonical candidates (per open_questions and introduction):

- **Delegate** — hand off to a worker or subsystem under constraints
- **RequestEvidence** — request evidence or document; may spawn evidence ghost
- **SpawnGhost** — create a Ghost Record (via ghost engine)
- **ResolveGhost** — attempt or record resolution of a ghost (via ghost engine)
- **EscalateGhost** — escalate a ghost (e.g. to human or policy)
- **AdvancePointer** — advance the current position in a branch or workflow (subject to closure check where applicable)
- **BlockClosure** — block closure for the current case/branch/answer
- **Terminate** — terminate a branch or case without closure

Implementations MAY extend this set but MUST NOT collapse distinct actions (e.g. SpawnGhost vs ResolveGhost) into one.

The **minimal action algebra** is still an open question; this spec fixes the canonical candidates, not the minimal set.

---

## 6. Relationship to Epistemic Router

The **Epistemic Router** decides the regime of continuation at each junction: **ok**, **doubt**, or **not**.

The Manager Plane MAY:

- embed the epistemic router,
- consume the router’s decisions to choose which action to dispatch,
- or own routing and delegate verification to the Continuous Verifier.

The boundary between Manager Plane and Epistemic Router MUST be clearly defined in any implementation. This spec does not fix a single ownership model; it requires that the relationship be explicit.

---

## 7. Relationship to Continuous Verifier

The Manager Plane MUST NOT bypass the Continuous Verifier.

- Before advancing pointer or allowing closure, the Manager Plane (or a dedicated component) MUST consult the verifier where required by policy.
- Verifier outcomes (`admit`, `admit_with_doubt`, `closure_blocked`, etc.) MUST drive Manager Plane behavior.
- The Manager Plane does not replace the verifier; it coordinates with it.

---

## 8. Relationship to Ghost Engine

The Manager Plane dispatches Ghost-related actions to the **Ghost Engine**.

- SpawnGhost, ResolveGhost, EscalateGhost are executed by the Ghost Engine under Manager Plane instruction or policy.
- The Manager Plane does not implement ghost lifecycle itself; it issues typed actions and receives receipts.

---

## 9. Relationship to Closure Guard

The **Closure Guard** determines whether closure is legitimate.

The Manager Plane MUST ensure that:

- closure attempts are evaluated by the closure guard (or equivalent logic),
- closure is blocked when the guard returns block,
- and BlockClosure is issued when the system must not conclude despite operational ability to emit output.

---

## 10. Non-Chat Requirement

The Manager Plane v2 is **non-chat**.

Control decisions MUST be represented as:

- typed events,
- typed actions,
- structured receipts,
- and explicit state transitions,

not as natural-language turns or unstructured prompts.

This does not forbid a chat interface elsewhere in the system; it forbids the Manager Plane from being driven primarily by conversational input.

---

## 11. Conformance

A system conforms to this specification only if it:

1. implements a control plane that is typed and event-driven,
2. uses events, receipts, and witnesses as defined,
3. supports at least the canonical action set (or a documented subset),
4. defines the relationship between Manager Plane, Epistemic Router, Verifier, Ghost Engine, and Closure Guard,
5. does not use chat as the primary control interface for the Manager Plane,
6. and ensures that verification and closure guard are not bypassed.

---

## 12. Non-Goals

This specification does not define:

- the exact wire format of events and receipts,
- the implementation of the Epistemic Router,
- or the policy language for when to escalate or block.

Those belong to downstream specs or implementation.

---

## 13. Summary

The Manager Plane v2 is the typed, event-driven, non-chat control plane that coordinates the governance layer: events in, receipts out, typed actions to ghost engine, verifier, and closure guard. It exists so that the system can be controlled and audited without relying on natural language as the primary control mechanism.
