# Truss Framework

Truss is a working framework for evaluating engineering trade-offs in product systems.

It treats software quality as a decision problem, not a static property. The goal is to help teams replace vague adjectives like "clean", "scalable", or "enterprise-ready" with falsifiable trade-off statements, explicit constraints, and decisions that can be revisited later.

## Status

Truss is currently a research beta.

The framework core is intended to stay stable while the surrounding artifacts evolve:

- the paper explains the theory and research direction,
- the skill helps LLM agents apply the framework in real work,
- the examples and field notes will grow as the framework is tested.

The skill may change more often than the framework. Agent prompts need to adapt as models and workflows change; that does not necessarily mean the Truss model itself changed.

## The Core Idea

Quality is not something code simply has. Quality is the outcome of repeated decisions made under constraints.

Truss organizes those decisions around four pressures:

- **Maintainability (DX):** how safely and cheaply the system can change.
- **Strategy (product):** how well today's choice solves the problem and keeps future paths open.
- **Clarity (DX):** how quickly and accurately an engineer can build the right mental model.
- **Performance (UX/runtime):** how well the system behaves under real workloads.

The point is not to score everything perfectly. The point is to name the tension, choose a coherent profile for the context, and write down what the team is intentionally accepting.

## What Truss Is For

Use Truss when a decision has enough weight that vague preference is not good enough:

- comparing implementation options,
- reviewing a PR or design,
- writing an RFC or ADR,
- investigating an incident or recurring bug,
- deciding whether to optimize for speed, flexibility, clarity, cost, or future change.

Truss is especially useful when multiple answers are plausible and the real question is: **what are we optimizing for, for how long, and what are we willing to give up?**

## What Truss Is Not

Truss is not:

- a checklist that proves quality,
- a scoring game that replaces judgment,
- a purity test for architecture,
- or a way to justify personal taste as strategy.

Scores are optional. Evidence is not.

## The Skill

This repository includes an agent skill at [`truss-skill/`](./truss-skill/).

The skill is an operational adapter for applying Truss with LLM agents. It supports:

- option comparison,
- single-artifact review,
- bug or incident investigation,
- discussion insight,
- ADR-style decision records.

Before scoring, the skill asks for:

1. context and mode,
2. an optimization statement,
3. pillar weights,
4. non-negotiables,
5. boundary checks,
6. evidence per pillar.

Example prompt:

```text
Evaluate Option A vs Option B using Truss.
Optimization statement: optimize provider switchability over short-term latency for the next 12 months.
Weights: M=25 S=45 C=20 P=10.
Non-negotiables: OWASP baseline, no PII exposure, single provider abstraction.
```

## Paper

The paper should live in this repository. The scaffold is in [`paper/`](./paper/), but no draft PDF or source file is committed yet.

Recommended shape:

```text
paper/
  truss-framework.tex
  truss-framework.pdf
  references.bib
```

Keeping the paper next to the skill makes the relationship explicit:

- the paper is the canonical research layer,
- the skill is the applied LLM/agent layer,
- field examples can point back to both.

If the paper is still changing quickly, commit a clearly dated or versioned PDF snapshot only once the structure is comfortable enough to review publicly.

## Citation

If you use Truss in research, engineering documentation, or agent workflows, cite the repository using [`CITATION.cff`](./CITATION.cff).

Current public-beta citation target:

```text
Truss: A Framework for Engineering Trade-offs in Product Systems
Leonardo Reis Dias
Version: 0.3.0-research-beta
Repository: https://github.com/leoreisdias/truss-framework
```

## License

Truss uses a dual-license structure:

- Apache-2.0 for reusable code-like and agent-skill materials.
- CC BY 4.0 for research and documentation materials.

See [`LICENSE.md`](./LICENSE.md) for the license map.

## Repository Structure

```text
paper/
  README.md
truss-skill/
  SKILL.md
  agents/openai.yaml
  references/
    OVERVIEW.md
    RUBRIC.md
    SCORING.md
    TEMPLATES.md
    CHECKLISTS.md
    EXAMPLES.md
    ANTI-PATTERNS.md
```

Key files:

- [`paper/README.md`](./paper/README.md): paper location and snapshot guidance.
- [`truss-skill/SKILL.md`](./truss-skill/SKILL.md): skill entry point and workflow.
- [`truss-skill/references/OVERVIEW.md`](./truss-skill/references/OVERVIEW.md): framework summary and boundaries.
- [`truss-skill/references/RUBRIC.md`](./truss-skill/references/RUBRIC.md): 0-5 scoring guide by pillar.
- [`truss-skill/references/SCORING.md`](./truss-skill/references/SCORING.md): scoring process and evidence requirements.
- [`truss-skill/references/TEMPLATES.md`](./truss-skill/references/TEMPLATES.md): reusable output formats.
- [`truss-skill/references/ANTI-PATTERNS.md`](./truss-skill/references/ANTI-PATTERNS.md): common failure modes and corrections.

## Field Feedback Wanted

Truss needs real usage more than polished agreement.

Useful feedback includes:

- examples where Truss clarified a decision,
- examples where it felt too heavy,
- cases where pillars overlapped or leaked into each other,
- decisions where the recommendation changed after weights were declared,
- before/after PR, RFC, ADR, or incident-review notes.

The most useful reports are concrete: context, options, declared optimization, trade-offs, decision, and what happened afterward.

## Changelog

See [`CHANGELOG.md`](./CHANGELOG.md) for release history and framework evolution.
