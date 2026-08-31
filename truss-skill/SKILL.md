---
name: truss-evaluation
description: Evaluate consequential software-quality trade-offs through Maintainability, Strategy, Clarity, and Performance. Use for technical planning and architecture, code or PR review and grilling, bug or incident investigation, and decision records when the outcome materially affects those qualities.
---

# Truss Evaluation

Truss is a framework for discussing software-quality trade-offs in real product teams.

## Quick start

1. Ask for the context (deadline pressure, constraints, and what “success” means).
2. Select mode: **comparison**, **single-artifact review**, **investigation**, or **discussion insight**.
3. If in comparison mode, insist on **2–4 real options** (including “do nothing” when valid).
4. Lock the optimization statement: “We optimize for X over Y for next N months.”
5. Declare pillar weights and non-negotiables before scoring.
6. Choose output style: **scorecard** (default when scoring inputs are complete) or **narrative trade-off memo** (no numeric scores).
7. If using scorecard, score **M/S/C/P from 0-5** with evidence (avoid vague claims like “clean” or “scalable”).
8. Write a recommendation or insight summary that states what we’re optimizing for and which trade-offs we are accepting.

## Pillars (canonical names)

- **M — Maintainability (DX):** how safely and cheaply the system can change.
- **S — Strategy (product):** how well today’s choices solve the problem and keep future paths open.
- **C — Clarity (DX):** the speed and accuracy with which a competent engineer can construct a correct mental model of the decision scope (a function, module, PR, or system).
- **P — Performance (UX/runtime):** how well the system runs under real workloads (latency, throughput, cost).

## Workflow

1. **Clarify intent and mode:** comparison, single-artifact review, investigation, or discussion insight.
2. **State constraints:** deadline pressure, team size, runtime/SLO constraints, risk tolerance.
3. **Define success first (mandatory for scored outputs):** write the optimization statement, horizon, pillar weights, and non-negotiables.
4. **Prepare inputs by mode:**
   - comparison: list 2–4 options with concise option notes,
   - single-artifact review: define artifact scope + expected behavior,
   - investigation: define observed evidence + current hypothesis,
   - discussion insight: define claims, assumptions, and unresolved tensions.
5. **Run boundary checks:** enforce non-negotiable constraints (for example, security baseline) before scoring.
6. **Run pillar contamination test:** keep Strategy claims out of runtime concerns, and Performance claims out of strategic optionality.
7. **Evaluate Truss:**
   - scorecard mode: score each pillar 0–5 with evidence bullets,
   - narrative mode: write one falsifiable trade-off statement per pillar without numeric scoring.
8. **Run sensitivity pass (when relevant):** re-score from strategy-first and runtime-first perspectives when ranking or priority is contested.
9. **Recommend / summarize insights:** give next actions, non-negotiables, and rank-reversal conditions when options are being compared.

## References (read only what you need)

- `references/OVERVIEW.md`: what Truss is/isn’t, when to use it, and its naming context.
- `references/RUBRIC.md`: the 0–5 rubric per pillar (signals, alerts, what “good” looks like).
- `references/SCORING.md`: how to score consistently and write falsifiable trade-offs.
- `references/TEMPLATES.md`: ready-to-use templates (evaluation scorecard, option comparison, single-artifact review, investigation insight memo, PR mini-check, ADR).
- `references/EXAMPLES.md`: worked examples with scores + rationale.
- `references/ANTI-PATTERNS.md`: common ways Truss gets misused and how to avoid them.
- `references/CHECKLISTS.md`: fast checklists per pillar.
