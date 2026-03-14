# Closure Fraud Specification
## Ignorance Must Take Form

**Status:** Draft  
**Authority:** `Book.toml`  
**Layer:** Epistemic Governance  
**Depends on:** `docs/glossary.md`, `spec/epistemic_state_spec.md`, `spec/continuous_verifier_spec.md`, `spec/ghost_record_spec.md`

---

## 1. Purpose

This document defines **Closure Fraud** as the illegitimate act of concluding while the epistemic state still depends on critical unresolved absence.

Closure Fraud is one of the central violations in this project.

It exists to distinguish:

- mere inaccuracy,

from

- structurally illegitimate conclusion.

---

## 2. Claim

A system commits Closure Fraud when it produces or commits a closure-bearing output while still depending on unresolved conditions that materially invalidate its right to conclude.

Closure Fraud is not reducible to:

- confidence error,
- style error,
- bad phrasing,
- or generic model hallucination.

It is a violation of closure legitimacy.

---

## 3. What Counts as Closure

For this specification, **closure** includes any act by which the system represents a matter as concluded, resolved, finalized, committed, or sufficiently settled for downstream reliance.

Closure MAY include:

- final answer emission,
- branch commitment,
- pointer advance,
- case resolution,
- workflow completion,
- decision finalization,
- state marked complete.

Closure is not limited to user-visible text.

---

## 4. Normative Definition

Closure Fraud occurs if and only if all of the following hold:

1. the system attempts closure,
2. the current epistemic state still contains unresolved absence relevant to closure,
3. that unresolved absence is critical under current policy or structure,
4. the system has not legitimately:
   - resolved,
   - dismissed,
   - or escalated
   the relevant absence,
5. and yet the closure is represented as legitimate.

If these conditions hold, the closure is fraudulent.

---

## 5. Critical Unresolved Absence

This specification uses the notion of **critical unresolved absence**.

A Ghost or unresolved condition is critical if it materially affects whether the closure-bearing claim, answer, or action is justified.

Examples:

- missing evidence directly required by the conclusion,
- unresolved causal gap at the center of the explanation,
- unresolved identity link that changes the target of the answer,
- contradictory provenance on the very claim being closed.

A peripheral Ghost does not necessarily create Closure Fraud.  
A closure-critical Ghost may.

---

## 6. Closure Preconditions

A closure is presumptively legitimate only if:

1. closure-critical Ghosts are resolved, dismissed, or escalated,
2. obligations required for closure are satisfied,
3. provenance closure holds for closure-bearing claims,
4. contradiction remains within admissible bounds,
5. semantic drift has not displaced the answer from the real goal,
6. and the Continuous Verifier does not return `closure_blocked`.

These are not implementation suggestions.  
They are closure conditions.

---

## 7. Fraud Patterns

The following are canonical patterns of Closure Fraud.

### 7.1 Unsupported Completion

The system concludes while relying on a claim with no admissible support.

### 7.2 Ghost Suppression

The system reaches closure by ignoring, dropping, or hiding an active critical Ghost.

### 7.3 Doubt Erasure

The system encounters doubt but represents the final answer as settled rather than suspended, scoped, or escalated.

### 7.4 Causal Fabrication

The system closes by inventing or overcommitting to a causal chain it has not earned.

### 7.5 Linkage Prematurity

The system closes by collapsing unresolved identities or references into one without right.

### 7.6 Evidence Substitution

The system substitutes nearby plausibility for required evidence and closes anyway.

---

## 8. Non-Fraud Cases

Not every imperfect closure is Closure Fraud.

Closure Fraud does **not** automatically occur when:

- there are peripheral unresolved Ghosts that do not affect the closure,
- the system explicitly states the scope and limitations of its conclusion,
- the unresolved condition has been escalated in a way that keeps closure honest,
- or the answer is partial and clearly marked as partial.

The key issue is not imperfection.

It is illegitimate representation of completion.

---

## 9. Relationship to Hallucination

Hallucination and Closure Fraud overlap but are not identical.

### Hallucination

The illegitimate conversion of structured absence into textual presence.

### Closure Fraud

The illegitimate act of concluding despite critical unresolved absence.

A system may hallucinate without formal closure.  
A system may commit Closure Fraud even if every sentence is locally plausible and well-formed.

Closure Fraud is therefore the governance-level name for a class of epistemically invalid endings.

---

## 10. Relationship to Ghost Debt

Closure Fraud is often preceded by Ghost Debt.

Not all Ghost Debt implies fraud.  
But unresolved debt near closure is a major risk signal.

A system SHOULD inspect Ghost Debt before closure attempt.

A system MUST NOT treat low surface uncertainty as sufficient reason to ignore debt.

---

## 11. Relationship to Continuous Verifier

The Continuous Verifier is the primary mechanism that detects or blocks Closure Fraud.

A conformant system SHOULD have a closure evaluation step in which:

- the current epistemic state is inspected,
- closure-critical Ghosts are identified,
- obligations are checked,
- and closure may be blocked independently of output generation.

Closure Fraud is the violation.  
Closure blocking is the prevention mechanism.

---

## 12. Minimal Predicate Sketch

A closure attempt is fraudulent if:

```text
closure_attempted(x_t) AND
exists g in ghosts(x_t) such that critical(g, x_t) AND unresolved(g) AND
not resolved_or_dismissed_or_escalated(g) AND
closure_represented_as_legitimate(x_t)
```

This predicate sketch is illustrative, not final.

---

## 13. Required System Behavior

A conformant system MUST do at least one of the following before closure:

1. resolve the critical absence,
2. dismiss it legitimately,
3. escalate it explicitly,
4. downgrade closure to scoped partial answer,
5. or block closure.

A system MUST NOT simply continue to final presentation as though closure were earned.

---

## 14. Examples

### 14.1 Fraud Example

The system answers:

"The transfer was approved by Director X on March 2."

But:

- the approval record has not been retrieved,
- the identity of Director X is unresolved,
- and the causal chain between request and transfer remains incomplete.

If the answer is presented as settled, this is Closure Fraud.

### 14.2 Non-Fraud Example

The system answers:

"I cannot conclude who approved the transfer. The approval record is still missing, and this blocks a final answer."

This is not fraud.  
It is explicit governed incompletion.

---

## 15. Conformance

A system conforms to this specification only if it:

1. defines what counts as closure,
2. inspects critical unresolved absence before closure,
3. distinguishes partial honest incompletion from fraudulent finality,
4. can block closure even when output generation remains operationally possible,
5. and does not silently suppress closure-relevant Ghosts.

---

## 16. Open Questions

The following remain open:

- Is Closure Fraud binary or should severity classes exist?
- How is criticality best computed?
- Can closure be branch-local while the global case remains open?
- What is the right relationship between Ghost Debt thresholds and closure blocking?
- How should scoped partial closure be represented canonically?

---

## 17. Summary

Closure Fraud names a central violation:

the system closes despite not having the right to close.

It is the governance-level counterpart to hallucination.

If hallucination is how structured absence turns into text,  
Closure Fraud is how unresolved absence turns into illegitimate finality.
