# truss-framework

Truss evaluation skill for trade-off analysis in product engineering decisions.

## What this skill does

Truss gives teams a shared, falsifiable language for decision quality:

- **M**aintainability
- **S**trategy
- **C**larity
- **P**erformance

Instead of arguing in adjectives ("clean", "scalable"), the skill pushes evidence-backed trade-offs, explicit constraints, and revisitable decisions.

## Core principle

Quality is a decision problem, not a static property.  
The right profile depends on context, horizon, and constraints.
Scoring is optional: use it when ranking helps; otherwise keep a narrative trade-off memo.

## Required flow (before scoring)

1. Declare context and mode (comparison, single-artifact review, investigation, discussion insight).
2. Lock the optimization statement:
   - "We optimize for X over Y for next N months."
3. Declare pillar weights (`M/S/C/P` totaling `100%`).
4. Declare non-negotiables (security baseline, migration constraints, governance constraints).
5. Run boundary checks (security is transversal and non-negotiable).
6. Evaluate with evidence per pillar (`M/S/C/P`) using either:
   - a `0–5` scorecard (when scoring inputs are complete), or
   - a narrative trade-off memo (no numeric scores).
7. Run contamination test (`S` vs `P` claim hygiene).
8. Run sensitivity pass (strategy-first and runtime-first when ranking is contested).
9. State rank-reversal conditions explicitly for comparison mode.

## Security model boundary

Security is intentionally not a fifth pillar.  
It is a transversal boundary constraint that must hold before trade-off scoring.

## Repository structure

- `SKILL.md`: trigger + workflow entry point
- `agents/openai.yaml`: UI metadata
- `references/OVERVIEW.md`: framework intent and boundaries
- `references/RUBRIC.md`: 0-5 rubric by pillar
- `references/SCORING.md`: scoring process and gates
- `references/TEMPLATES.md`: reusable output templates
- `references/CHECKLISTS.md`: fast execution checklists
- `references/EXAMPLES.md`: worked examples and benchmark cases
- `references/ANTI-PATTERNS.md`: common failure modes and corrections

## Typical outputs

- Truss scorecard with evidence
- Option comparison with explicit trade-offs
- Single-artifact review memo (PR/code/design)
- Investigation insight memo (bug/incident)
- Recommendation with non-negotiables and revisit trigger
- Rank-reversal conditions (for comparison decisions)

## Quick prompt starter

Use one of these before asking for scoring:

```text
Evaluate Option A vs Option B using Truss.
Optimization statement: optimize provider switchability over short-term latency for next 12 months.
Weights: M=25 S=45 C=20 P=10.
Non-negotiables: OWASP baseline, no PII exposure, single provider abstraction.
```

```text
Review this PR using Truss.
Mode: single-artifact review.
Optimization statement: optimize safe migration over feature velocity for next 2 months.
Weights: M=35 S=30 C=20 P=15.
Non-negotiables: no PII exposure, rollback path is explicit.
```

## Changelog

See [`CHANGELOG.md`](./CHANGELOG.md) for release history and framework evolution.
