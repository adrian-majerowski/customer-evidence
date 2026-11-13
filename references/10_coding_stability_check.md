---
name: coding-stability-check
description: Reapply frozen pattern and theme boundaries to raw evidence in a fresh pass before a provisional finding can be called stabilized.
inherits: evidence-first-product-researcher
version: 0.11
---

# Coding Stability Check

## Purpose

Prevent a plausible-sounding synthesis from becoming self-confirming.

The AI that created a pattern may unconsciously bend later cases to fit it. Before stabilization, test whether the pattern's written rules can be applied consistently to the raw evidence.

## Trigger

Run after:
- candidate/provisional patterns have survived contradiction and split checks;
- inclusion/exclusion rules have stopped changing rapidly;
- a provisional theme is being considered for `stabilized_finding`.

Do not use this step to force stability early.

## Procedure

### 1. Freeze the boundary

Record the exact:
- pattern/theme definition;
- inclusion criteria;
- exclusion criteria;
- temporal/product-state scope.

Do not edit these during the recoding pass.

### 2. Re-read the relevant raw evidence

Prefer a fresh context/model pass that does not expose the original case assignments.

Apply only the frozen rules plus the parent evidence rules.

Classify each relevant case as:
- `include`;
- `exclude`;
- `ambiguous`.

### 3. Compare with the original grouping

Inspect:
- cases whose membership changed;
- ambiguous cases;
- exclusions that now appear inconsistent;
- cases that reveal the boundary is actually two patterns.

### 4. Decide based on meaning, not a magic score

Do not invent an agreement percentage threshold.

Ask:
> If these changed/ambiguous cases are handled correctly, does the finding keep essentially the same product meaning and scope?

If **no**:
- return to provisional;
- revise/split/narrow the pattern;
- rerun comparison later.

If **yes**:
- record `stable_enough_for_current_frame`;
- retain disagreements as audit evidence.

## Important boundary

`stable_enough_for_current_frame` does not mean:
- true for all users/players;
- prevalent;
- causal;
- worth prioritizing;
- impossible to change with new evidence.

It means the current interpretation has a sufficiently repeatable boundary for the current evidence and research question.

## Output schema

```yaml
coding_stability_check:
  finding_id: string
  frozen_definition: string
  frozen_inclusion_criteria: [string]
  frozen_exclusion_criteria: [string]
  original_included_ids: [string]
  second_pass:
    included_ids: [string]
    excluded_ids: [string]
    ambiguous_ids: [string]
  changed_membership_ids: [string]
  material_boundary_issues: [string]
  status: unstable|stable_enough_for_current_frame
  action: revise|split|narrow|return_to_provisional|allow_stabilization
  rationale: string
```
