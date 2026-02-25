# mscp-skill

MSCP evaluation skill for trade-off analysis in product engineering decisions.

## What this skill does

MSCP gives teams a shared, falsifiable language for decision quality:

- **M**aintainability
- **S**trategy
- **C**larity
- **P**erformance

Instead of arguing in adjectives ("clean", "scalable"), the skill pushes evidence-backed trade-offs, explicit constraints, and revisitable decisions.

## Core principle

Quality is a decision problem, not a static property.  
The right profile depends on context, horizon, and constraints.

## Required flow (before scoring)

1. Declare the decision context and options.
2. Lock the optimization statement:
   - "We optimize for X over Y for next N months."
3. Declare pillar weights (`M/S/C/P` totaling `100%`).
4. Declare non-negotiables (security baseline, migration constraints, governance constraints).
5. Run boundary checks (security is transversal and non-negotiable).
6. Score `M/S/C/P` with evidence.
7. Run contamination test (`S` vs `P` claim hygiene).
8. Run two-perspective sensitivity pass (strategy-first and runtime-first).
9. State rank-reversal conditions explicitly.

## Security model boundary

Security is intentionally not a fifth pillar.  
It is a transversal boundary constraint that must hold before trade-off scoring.

## Repository structure

- `SKILL.md`: trigger + workflow entry point
- `agents/openai.yaml`: UI metadata
- `references/OVERVIEW.md`: framework intent and boundaries
- `references/RUBRIC.md`: 1-5 rubric by pillar
- `references/SCORING.md`: scoring process and gates
- `references/TEMPLATES.md`: reusable output templates
- `references/CHECKLISTS.md`: fast execution checklists
- `references/EXAMPLES.md`: worked examples and benchmark cases
- `references/ANTI-PATTERNS.md`: common failure modes and corrections

## Typical outputs

- MSCP scorecard with evidence
- Option comparison with explicit trade-offs
- Recommendation with non-negotiables and revisit trigger
- Rank-reversal conditions (when the recommendation should flip)

## Quick prompt starter

Use this before asking for scoring:

```text
Evaluate Option A vs Option B using MSCP.
Optimization statement: optimize provider switchability over short-term latency for next 12 months.
Weights: M=25 S=45 C=20 P=10.
Non-negotiables: OWASP baseline, no PII exposure, single provider abstraction.
```

## Changelog

See [`CHANGELOG.md`](./CHANGELOG.md) for release history and framework evolution.
