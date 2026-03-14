# Unified Stack Specification
## Ignorance Must Take Form

**Status:** Draft  
**Authority:** `Book.toml`  
**Layer:** Architecture  
**Depends on:** `Book.toml`, `docs/glossary.md`, `spec/canonical_cell_spec.md`, `spec/ghost_record_spec.md`, `spec/epistemic_state_spec.md`, `spec/continuous_verifier_spec.md`, `spec/closure_fraud_spec.md`

---

## 1. Purpose

This document defines the **Unified Stack** as the four-floor architecture that links semantic canonicalization, deterministic admissibility, protocolized action, and epistemic governance into one coherent system.

The stack is the structure over which the canonical cell, Ghost Records, epistemic state, verifier, and closure guard operate.

---

## 2. Claim

The full system operates across four distinct floors. Each floor has clear responsibility; no floor may be collapsed into another without explicit architectural revision. The same canonical form (the cell) is the semantic core that propagates across floors.

---

## 3. The Four Floors

A conformant description of the stack MUST recognize exactly four floors, in order from bottom (closest to intention) to top (closest to governance):

1. **Semantic Form**
2. **Deterministic Materialization**
3. **Protocol of Action**
4. **Epistemic Governance**

These names and this order are canonical per `Book.toml`.

---

## 4. Floor Definitions

### 4.1 Floor 1 — Semantic Form

**Responsibility:** Where intention is canonicalized into a portable, accountable structure.

**Answers:** *What was asked, and what would count as an answer?*

**Canonical components (per Book.toml):**

- canonical_cell
- tdln (Truth-Determining Language Network)
- semantic_isa

**Key invariants:**

- Intention is captured before backend execution.
- Structure is deterministic, hashable, portable.
- The cell is the minimal unit of governed transition at this floor.

---

### 4.2 Floor 2 — Deterministic Materialization

**Responsibility:** Where policy and admissibility become executable in deterministic, content-addressed form.

**Answers:** *Is this action permitted, and can I prove it?*

**Canonical components (per Book.toml):**

- deterministic_gate
- content_hash
- check_boundary

**Key invariants:**

- Semantic intent is compiled into checks.
- Admissibility is decided by computation, not opinion.
- Meaning meets matter at the gate.

---

### 4.3 Floor 3 — Protocol of Action

**Responsibility:** Where acts are written before they are executed and consequences are declared in advance.

**Answers:** *What will happen, what has happened, and what remains unresolved?*

**Canonical components (per Book.toml):**

- logline
- ledger
- policy
- consent
- ghost_of_action

**Key invariants:**

- Write-before-execute.
- LogLine is the protocolized form of the canonical cell.
- Consequence invariants (`if_ok`, `if_doubt`, `if_not`) are binding.

---

### 4.4 Floor 4 — Epistemic Governance

**Responsibility:** Where the system tracks ghosts, verifies trajectories, routes doubt, and blocks illegitimate closure.

**Answers:** *Does this system have the right to continue, and under what conditions?*

**Canonical components (per Book.toml):**

- manager_plane
- ghost_engine
- continuous_verifier
- closure_guard
- epistemic_router

**Key invariants:**

- Verification is trajectory-level.
- Ghosts are first-class; they affect admissibility and closure.
- The LLM is a proposer, never sovereign.

---

## 5. Cross-Floor Flow

### 5.1 Direction of flow

- **Intention** enters at Semantic Form.
- **Admissibility** is enforced at Deterministic Materialization.
- **Action** is registered at Protocol of Action.
- **Continuation and closure** are governed at Epistemic Governance.

Flow is not strictly sequential: governance may block or route at any floor; protocol may spawn ghosts; materialization may reject before protocol commits.

### 5.2 The cell across floors

The canonical cell is the common semantic object. At:

- **Semantic Form:** the cell is the canonical representation of intended transition.
- **Deterministic Materialization:** the cell (or its compiled form) is what the gate evaluates.
- **Protocol of Action:** the cell appears as LogLine; write-before-execute applies.
- **Epistemic Governance:** the cell’s branches (`if_ok`, `if_doubt`, `if_not`) and status drive routing and closure.

The cell MUST NOT change field set across floors. Aliases or encodings MAY differ; structure MUST NOT.

---

## 6. Component Roles (Summary)

| Component | Floor | Role |
|-----------|--------|------|
| canonical_cell | Semantic (and all) | Minimum accountable form of governed transition |
| tdln / semantic_isa | Semantic | Canonicalization of intent |
| deterministic_gate, content_hash, check_boundary | Materialization | Executable admissibility |
| logline, ledger, policy, consent, ghost_of_action | Protocol | Write-before-execute; consequence invariants |
| manager_plane | Governance | Typed control plane; dispatch; events/receipts/witnesses |
| ghost_engine | Governance | Ghost lifecycle; spawn, resolve, dismiss, escalate |
| continuous_verifier | Governance | Transition admissibility; trajectory-level verification |
| closure_guard | Governance | Closure preconditions; block illegitimate closure |
| epistemic_router | Governance | Route ok / doubt / not at each junction |

---

## 7. Proposer (LLM) Placement

The LLM or other proposer sits as **input to** the stack, not above it.

- Proposer outputs are consumed at Semantic Form (and possibly Protocol) as proposals.
- They are evaluated, verified, and governed by the stack.
- The proposer does not own verification, closure, or ghost resolution.

This placement is non-negotiable per `docs/non_negotiables.md`.

---

## 8. Conformance

A system conforms to this specification only if it:

1. describes the architecture as exactly four floors,
2. assigns the canonical components to the correct floors,
3. preserves the canonical cell as the shared semantic core,
4. does not collapse floors without explicit architectural change,
5. and places the proposer (e.g. LLM) as input to the stack, not sovereign over it.

---

## 9. Non-Goals

This specification does not define:

- the internal design of each component,
- the wire protocol between floors,
- or the exact API of manager plane, ghost engine, or verifier.

Those belong to component-level specs.

---

## 10. Summary

The Unified Stack is the four-floor architecture that carries intention from semantic form to epistemic governance without changing the nature of the canonical form. Same cell, same accountability structure, across floors.
