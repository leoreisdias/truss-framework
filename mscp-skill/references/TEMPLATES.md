# MSCP Templates

## Template: MSCP scorecard + recommendation (default)

**Decision:** <what are we deciding?>
**Context:** <deadline pressure + constraints + definition of success>
**Optimization statement (mandatory):** <we optimize for X over Y for next N months>
**Weights (mandatory):** <M=% S=% C=% P=%; total=100%>
**Boundary constraints (must hold before scoring):**
- Security baseline: <OWASP/compliance/PII constraints that are non-negotiable>
- Other non-negotiables: <platform/governance/migration constraints>

**Options**
- A: <…>
- B: <…>
- (C / Do nothing): <…>

**Scores (1–5)**
- **M Maintainability:** <1–5>
  - Evidence:
  - Trade-off:
- **S Strategy:** <1-5>
  - Evidence:
  - Trade-off:
- **C Clarity:** <1-5>
  - Evidence:
  - Trade-off:
- **P Performance:** <1–5>
  - Evidence:
  - Trade-off:

**Recommendation**
- Pick: <Option A/B/...>
- Why: <2–5 bullets>
- Non-negotiables: <tests/guardrails/rollout/measurement>
- Rank-reversal conditions: <B beats A when ... ; A beats B when ...>
- Revisit: <date or trigger>

## Template: Option A vs B comparison (short)

| Pillar | Option A | Option B | Notes |
|---|---:|---:|---|
| M |  |  |  |
| S |  |  |  |
| C |  |  |  |
| P |  |  |  |

**Call:** <A/B> because <…>. **Risk:** <…>. **Next step:** <…>.
**Rank-reversal condition:** <when would this call flip?>

## Template: PR mini-check (fast)

- **Maintainability:** is the change localized? are critical risks covered by tests?
- **Strategy:** is the path justified? do we have an extension/migration story?
- **Clarity:** can a reviewer construct a correct mental model quickly and accurately without opening 5 files?
- **Performance:** are timeouts/retries/limits explicit? do we know the likely bottleneck?
- **Contamination test:** are any Strategy claims actually runtime concerns (or vice versa)?

## Template: Ultra-short ADR (6 lines)

Context: <real problem>
Alternatives: <A, B, C>
Decision: <what and why>
Risks: <known>
Mitigation: <plan B / rollback>
Review: <when to revisit>

## Template: Comment-ready PR feedback (no code anchoring)

Write as if the reader can see the diff already (do not include file paths, line numbers, or code blocks):

- **Maintainability:** <one concrete improvement request>
- **Strategy:** <risk + extension/migration story>
- **Clarity:** <improve speed and accuracy of understanding the decision scope (naming, structure, flow, and reduced indirection)>
- **Performance:** <measurement/guardrail request>
- **Boundary constraints:** <confirm security baseline is met; if not, request remediation before trade-off scoring>
- **Contamination test:** <reclassify any S claim that is really P, or P claim that is really S>

## Template: Two-perspective sensitivity pass

**Primary perspective:** <weights and objective used in final recommendation>
**Strategy-first pass:** <updated weights + resulting ranking>
**Runtime-first pass:** <updated weights + resulting ranking>
**Stability result:** <stable / rank reversal>
**Rank-reversal conditions:** <explicitly state what changes the winner>
