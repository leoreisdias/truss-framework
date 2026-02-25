# Changelog

All notable changes to this repository are documented in this file.

The format follows Keep a Changelog principles, adapted for this skill repository.

## [Unreleased]

### Added

- Mandatory "Define success first" gate before scoring:
  - optimization statement
  - pillar weights (`M/S/C/P` totaling `100%`)
  - non-negotiables
- Pillar contamination test guidance (`S` vs `P`) in process docs.
- Two-perspective sensitivity pass template (strategy-first and runtime-first).
- Rank-reversal condition requirement in recommendations.
- Benchmark-style leakage example showing how rankings flip under different priorities.

### Changed

- `SKILL.md` quick start and workflow now enforce process guards before scoring.
- Templates and checklists now include objective lock, weighting, contamination checks, and stability checks.
- Anti-pattern catalog expanded with objective drift, pillar leakage, and rank-reversal blindness.

### Fixed

- Clarity definition wording normalized to "a competent engineer".

## [0.3.0] - 2026-02-25

### Added

- Security as a transversal boundary constraint (not a fifth pillar).
- Security baseline gate ("not score-eligible" until baseline compliance).
- Security-oriented checklist items and worked example.

## [0.2.0] - 2026-02-25

### Changed

- Framework renamed from MELP to MSCP.
- Pillars updated to:
  - Maintainability (M)
  - Strategy (S)
  - Clarity (C)
  - Performance (P)
- Terminology normalized across skill, templates, rubrics, and examples.

## [0.1.0] - 2026-02-24

### Added

- Initial skill structure:
  - `SKILL.md`
  - `agents/openai.yaml`
  - references (`OVERVIEW`, `RUBRIC`, `SCORING`, `TEMPLATES`, `CHECKLISTS`, `EXAMPLES`, `ANTI-PATTERNS`)

## Historical provenance (before repo split)

The earliest MSCP development happened in `ai-rules-workflows` under `skills/melp-evaluation` before this repository was created.

### 2026-02-25

- `2602d49` — `feat: MELP -> MSCP` (acronym/pillar migration baseline).
- `8fce7a8` — `feat: add security-boundaries` (transversal security model).
- `0b35e38` — `chore: removed melp-evaluation` (cleanup after split/move).

### 2026-02-23

- `89c76f0` — `feat: add melp-evaluation framework` (first packaged framework in skill format).

### 2026-01-22

- `e2c4763` — `fix: update description formatting in melp-evaluation documentation`.

### 2025-11-17

- `6f6e470` — `Create MELP.md` (earliest framework seed in that repository).
