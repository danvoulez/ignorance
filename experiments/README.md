# Experiments — Laboratory

This folder is the **laboratory**: scenarios, notebooks, baselines, and result summaries. Scenarios are small, reproducible situations that stress the theory; notebooks explore metrics and behaviour; baselines define what we compare against; results hold reported outcomes.

---

## Structure

| Path | Role |
|------|------|
| [scenarios/](scenarios/) | Scenario descriptions and runnable setups (e.g. basic doubt, evidence ghost, premature closure) |
| [notebooks/](notebooks/) | Jupyter notebooks for ghost debt, closure fraud cases, epistemic router, cost vs reliability |
| [baselines/](baselines/) | RAG-only, workflow-only, proposer-only, unguided agent — what we compare to |
| [results/](results/) | Reported metrics: closure_fraud_rate, cost_per_reliable_decision, ghost_resolution_efficiency, etc. |

---

## Conventions

- Each scenario has a README and a markdown description; runnable scenarios wire to `src/cli/` or scripts.
- Results are dated and reference the scenario/baseline and config used.

---

*Ignorance must take form.*
