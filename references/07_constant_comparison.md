---
name: constant-comparison-and-slow-synthesis
description: Compare qualitative user/player-experience cases iteratively, preserve differences, form provisional patterns, and prevent premature problem grouping or problem quantification while keeping signal counts separate.
inherits: evidence-first-product-researcher
version: 0.11
---

# Constant Comparison and Slow Synthesis

## Purpose

Prevent the AI's natural tendency to compress many messages into neat themes too early.

Use after experience extraction and before final user-problem synthesis.

## Principle

**Do not ask “How can these messages be summarized?”**

Ask:

`What is similar about these experiences, what is different, and which distinctions still matter?`

The desired output is not maximal compression. It is a defensible structure that preserves product-relevant differences.

## Workflow

### 1. Keep every case independent initially

Each qualified experience begins as `unclustered_experience`.

Never pre-assign it to a theme based on keywords or product taxonomy.

### 2. Compare dimensions

For each new case compare:
- goal
- context
- breakdown/event
- consequence
- response/next action
- cohort/context when explicitly supported
- missing information

### 3. Form candidate patterns

Create a candidate pattern only when the cases share enough experience structure to justify comparison.

Document:
- why they appear similar
- what still differs
- inclusion/exclusion criteria
- borderline cases

### 4. Search for disconfirming cases

Actively find:
- same context, different outcome
- same complaint, different cause
- different complaint, same underlying breakdown
- subgroup differences
- cases that challenge the proposed boundary

### 5. Split aggressively

Split when cases differ in ways that could lead to different product decisions.

Example:
- `nothing left to upgrade`
- `weekly events repeat`
- `friends left so I log in less`

Do not combine these merely because all include “boredom”.

### 6. Merge cautiously

Merge only after a shared higher-order problem survives comparison and contradiction checks.

Retain the lower-level patterns under the merged theme so distinctions remain visible.

### 7. Leave cases unclustered

It is acceptable for relevant evidence not to fit a stable pattern yet.

Do not force exhaustiveness.

### 8. Hand stable-looking patterns to an independent coding-stability check

When pattern boundaries appear mature, freeze the criteria and reapply them to relevant raw cases in a fresh pass before any theme can be called stabilized.

The second pass should focus on whether the same rules produce the same *meaningful boundary*, not on hitting a numeric agreement target.

### 9. Delay problem counts, not explicit signal counts

Do not calculate or present prevalence-like **problem** percentages while pattern boundaries are changing.

A clearly defined solution/request signal may be counted earlier after duplicate/linkage checks, but that count is recurrence/salience only and must remain outside problem synthesis.

After problem coding stabilizes, problem counts can be descriptive with explicit denominator and overlap caveats.

## Output

```yaml
case_comparisons:
  - case_a: string
    case_b: string
    similarities: [string]
    differences: [string]
    same_candidate_pattern: true|false|unclear
candidate_patterns:
  - label: string
    evidence_ids: [string]
    inclusion_criteria: [string]
    exclusion_criteria: [string]
    unresolved_differences: [string]
    status: candidate_pattern|provisional_pattern
borderline_cases:
  - evidence_id: string
    reason: string
deviant_cases:
  - evidence_id: string
    challenge: string
split_merge_log:
  - action: split|merge|retain_separate|leave_unclustered
    items: [string]
    rationale: string
quantification_status: not_ready|descriptive_only
```

## Failure modes

Reject:
- grouping by shared feature name only;
- grouping by sentiment only;
- grouping because the same solution is requested;
- creating one broad theme to “cover” several different problems;
- ranking themes before coding boundaries stabilize;
- interpreting repeated language as independent confirmation without checking social copying.
