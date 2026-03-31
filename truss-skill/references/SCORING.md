# Scoring Truss Consistently

Truss works when it replaces adjectives with **evidence** and **falsifiable statements**.

## Scoring is optional (discipline is not)

- Use scoring when ranking or prioritization would benefit from a coarse numeric view.
- If ranking is not needed, use a **narrative trade-off memo** (no numeric scores) with one falsifiable statement per pillar.
- Never force scores by inventing weights or constraints that were not declared.

## Canonical score scale (single source)

In this repository, numeric Truss scoring uses a **0–5 scale**:

- **0:** absent evidence, blocked baseline, or not score-eligible yet
- **1:** weak in-context outcome
- **3:** acceptable/uncertain middle
- **5:** strong in-context outcome

## Evidence standards (what “counts”)

Prefer evidence a teammate can quickly verify:

- Diff shape: “this feature touches 6 files across 3 packages”
- Navigability: “main flow is traceable from routes → loaders → views with consistent naming”
- Constraints: “this adds a critical-path dependency; we need timeouts + fallback”
- Operational reality: “p95 must stay under X; current baseline is Y”
- Investigation evidence: logs, traces, incident timeline, failed assumptions, and reproduced behavior

Avoid:

- “This is cleaner.”
- “This will scale.”
- “This feels enterprise.”

## Calibration rules

- **Score relative to the current context**, not a hypothetical ideal.
- Use **0–5** as a coarse signal; do not pretend precision.
- If you can’t justify a number, write the trade-off first, then infer the score.
- When uncertain, prefer **3** and list what you’d need to learn to move it up/down.

## Define success first (mandatory before scoring)

No Truss scoring is valid until these are explicitly declared:

1. **Optimization statement:** “We optimize for X over Y for next N months.”
2. **Pillar weights:** M/S/C/P percentages summing to 100%.
3. **Non-negotiables:** constraints that must hold (for example, baseline security, platform boundaries, migration requirements).

If any item is missing, stop and request it before producing scores.
If scoring inputs are missing, return a narrative trade-off memo plus the missing-input list.

## Supported application modes

Truss is valid beyond option comparison:

- **Comparison mode:** compare alternatives.
- **Single-artifact review mode:** evaluate a current implementation/PR/design.
- **Investigation mode:** evaluate hypotheses and findings during debugging or incidents.
- **Discussion insight mode:** evaluate claims and tensions in architecture or strategy discussions.

Mode affects inputs, but not pillar definitions.

## Boundary constraints before scoring

Check non-negotiable baselines before any M/S/C/P scoring. Security is a transversal boundary constraint, not a fifth pillar.

- If the option fails the agreed security baseline (for example, OWASP requirements or no PII exposure), it is **not score-eligible** yet.
- Fix baseline compliance first, then score trade-offs across the four pillars.
- In rationale, record where security pressure appears most directly: **Strategy** (risk/regulatory exposure) and **Performance** (runtime cost of protections).

## Pillar contamination test

Before final scoring, review each claim and re-assign if needed:

- If a **Strategy** claim is primarily about latency, throughput, retries, or runtime cost, move it to **Performance**.
- If a **Performance** claim is primarily about future optionality, migration path, or governance, move it to **Strategy**.
- Keep **Clarity** focused on comprehension cost now (speed and accuracy of mental-model construction), not future change cost.

One-line guardrail to include in analyses:

“Strategy is scored against the declared strategic objective, not generic best-practice defaults.”

## Two-perspective sensitivity pass

Run a quick second pass after primary scoring:

1. **Strategy-first perspective** (weights emphasize S)
2. **Runtime-first perspective** (weights emphasize P)

Compare rankings:

- If ranking stays stable, confidence increases.
- If ranking flips, document why and what assumption caused the reversal.
- In either case, record **rank-reversal conditions** explicitly (“Option B beats A when ...; A beats B when ...”).

For non-comparison modes, run a lighter sensitivity pass by varying priorities and checking whether conclusions or next actions change.

## The Truss brief (one-page decision record)

For non-trivial decisions (dependency, refactor, architecture, feature approach), write a short Truss brief near the code (ADR-style).

Minimal template:

1. **Context:** what are we building, for whom, and what is the deadline pressure?
2. **Subject(s):** comparison options, artifact under review, or investigation hypothesis set.
3. **Trade-offs:** one paragraph per pillar (what improves, what worsens).
4. **Risks:** what can fail, and what signal will tell us early?
5. **Decision / insight:** what we pick or conclude, what we intentionally accept, and when we will revisit.

## Decide fast vs invest

- Move fast when the decision is reversible.
- Invest when it is sticky (contracts, data models, platform boundaries).

Heuristic: if the **cost of reversal** is high, slow down and write the brief.
