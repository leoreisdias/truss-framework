# MSCP Anti-patterns

## Turning MSCP into a checklist

**Symptom:** “We checked the boxes” replaces a real trade-off discussion.

**Countermeasure**
- Require at least one falsifiable trade-off statement per pillar for non-trivial decisions.
- Keep the focus on *decisions* and *constraints*, not compliance.

## Scoring theatre

**Symptom:** Numbers are produced without evidence, or treated as objective truth.

**Countermeasure**
- Put evidence next to each score.
- Treat scores as coarse signals (0–5), not precision.
- If the rationale is weak, the score is invalid.

## Purity traps (“ideal architecture” over product reality)

**Symptom:** Solutions optimize for a hypothetical perfect system while ignoring deadlines, existing constraints, and learning loops.

**Countermeasure**
- Explicitly state constraints and revisit triggers.
- Prefer reversible decisions when uncertainty is high.

## False strategy (justifying taste as business need)

**Symptom:** “Strategic” becomes a synonym for preference.

**Countermeasure**
- Ask: what future path does this open (or close)?
- Require an extension/migration story for “strategic” claims.

## Context anchoring error (objective drift)

**Symptom:** Scoring starts before the declared optimization target is explicit, so defaults silently take over.

**Countermeasure**
- Require optimization statement + weights + non-negotiables before scoring.
- Reject score tables that do not include these inputs.

## Pillar leakage (S/P contamination)

**Symptom:** Runtime claims are scored as Strategy, or optionality/governance claims are scored as Performance.

**Countermeasure**
- Run a contamination test before final scores.
- Reclassify claims, then re-score.

## Rank-reversal blindness

**Symptom:** Recommendation is presented as absolute, without stating when it would flip.

**Countermeasure**
- Run strategy-first and runtime-first passes.
- Always document rank-reversal conditions.
