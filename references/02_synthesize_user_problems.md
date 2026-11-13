---
name: synthesize-user-problems
description: Build cautious decision-ready user problems from qualified experiences while separately aggregating solution/request signals for discovery priority, never as proof of solution validity.
inherits: evidence-first-product-researcher
version: 0.11
---

# Synthesize User Problems

## Purpose

Turn qualified case-level evidence into defensible, decision-ready user/player problems **without compressing too early**, while keeping repeated customer-proposed solutions in a separate signal lane.

A successful synthesis may end with **no defensible recurring problem established**. Do not force themes.

## Eligible evidence

Primary problem synthesis may use:
- `comparison_ready` first-hand reported experiences;
- grounded `reported_subjective_experience` attached to a concrete episode;
- supplied `direct_observation`;
- supplied `behavioral_data` when provenance and interpretation boundaries are clear.

`partial_experience` may provide context but should not anchor a pattern when the missing information could change the interpretation.

Opinions, preferences, solutions, hearsay, and community discourse cannot independently support a user-problem finding.

## Anti-summary / anti-compression constraints

Do not:
- summarize the corpus before case extraction is complete;
- group by shared keyword, feature, screen, event, sentiment, or requested solution alone;
- force every experience into a theme;
- merge different mechanisms because they sound related;
- create polished themes after seeing only a few superficially similar messages;
- use frequency to justify grouping before boundaries are stable;
- produce taxonomy buckets such as `UI`, `PvP`, `economy`, `billing`, `navigation`, `progression`, or `onboarding` as findings.

Prefer **under-grouping over over-grouping**.

## Required analysis states

Use these states internally and expose them when useful:
- `unclustered_experience`
- `candidate_pattern`
- `provisional_pattern`
- `provisional_theme`
- `isolated_problem_signal`
- `research_lead_only`
- `insufficient_evidence`
- `no_defensible_recurring_problem_established`
- `stabilized_finding_for_current_frame`

A provisional theme is not a final finding.

# Procedure

## Stage 0 — Protect synthesis from team framing

Keep `team_hypothesis`, `team_assumption`, `team_concern`, `team_proposed_solution`, `roadmap_context`, and `business_constraint` separate from user evidence.

When feasible:
1. synthesize user evidence without using the team's explanation/solution to create categories;
2. only after provisional findings/null outcomes exist, compare them with the team's beliefs.

## Stage 1 — Preserve cases individually

Before grouping, keep each relevant experience intact with:
- source/provenance;
- verbatim quote;
- context;
- user goal;
- what happened;
- next action;
- consequence;
- subjective state when reported;
- missing context;
- product/time context;
- `incident_id` and `independence_status`.

Do not normalize away participant wording and then cluster only the normalized text.

## Stage 2 — Check evidence independence before recurrence claims

Before saying a pattern recurs, inspect whether supporting cases are:
- the same incident;
- duplicates/reposts;
- socially linked through one thread/campaign/narrative;
- apparently independent;
- independence unknown.

Do not treat five retellings of one incident as five independent experiences.

Do not assume different authors are independent if the corpus shows shared framing or coordination.

## Stage 3 — Constant comparison

Compare cases based on **experience structure**, not surface wording.

Compare:
- user goal;
- situation/context;
- product state;
- breakdown/event;
- consequence;
- response/next action;
- relevant cohort/device/server/account state;
- evidence independence/linkage;
- unknowns preventing safe comparison.

Two cases mentioning the same feature can be different problems.
Two cases mentioning different features can sometimes share a higher-order problem.

## Stage 4 — Create candidate patterns, not themes

A `candidate_pattern` is a tentative recurring manifestation.

Define:
- label;
- inclusion criteria;
- exclusion criteria;
- evidence IDs;
- apparently independent incident IDs when available;
- borderline cases;
- contradictory/deviant cases;
- unresolved differences.

## Stage 5 — Try to break each pattern

Before promotion:
1. search for similar-context cases with different outcomes;
2. search for cases that almost fit but differ in goal, mechanism, or consequence;
3. ask whether one pattern hides two mechanisms;
4. ask whether shared wording/social copying created the apparent pattern;
5. retain deviant cases.

If meaningful differences would imply different product decisions, **split**.

## Stage 6 — Promote only coherent provisional patterns

A `provisional_pattern` should have:
- coherent case structure;
- explicit boundaries;
- no major unresolved internal contradiction;
- independence/linkage understood enough not to misstate recurrence;
- an abstraction that preserves important differences.

There is no magic minimum N.

A single important case remains an `isolated_problem_signal` unless other evidence justifies recurrence.

## Stage 7 — Consider a higher-order provisional user problem

Only after lower-level patterns are coherent should the AI consider a theme/problem.

A good problem label:
- describes a recognizable user/player problem;
- does not embed a proposed solution;
- does not embed an untested cause;
- stays at the right level of abstraction;
- does not erase materially different manifestations.

A theme may contain several patterns only when their shared experience structure is defensible and the lower-level distinctions remain visible.

## Stage 8 — Explicitly consider the null outcome

Before keeping a provisional theme ask:

> **Would a careful researcher be better served by saying “we do not yet have a defensible recurring problem” than by keeping this grouping?**

Use a null/non-theme outcome when:
- evidence is sparse;
- cases are too heterogeneous;
- recurrence is mostly duplicate/socially linked;
- product states are not comparable;
- cases are mostly solutions/opinions;
- pattern boundaries remain unstable;
- the only commonality is a broad product topic.

Possible outputs:
- `no_defensible_recurring_problem_established`;
- `insufficient_evidence`;
- `isolated_problem_signal`;
- `research_lead_only`.

### Null-outcome recovery is mandatory

A null outcome must not be presented as a dead end. For every null/non-theme outcome, also state:
- `what_current_material_supports` — e.g. repeated solution signal, isolated experience, or discourse signal;
- `missing_evidence` — the specific episode/context fields preventing a defensible problem interpretation;
- `immediate_recovery_action` — follow-up, observation, analytics, or other smallest useful next evidence;
- `systemic_input_quality_signal` — whether the same missing-context pattern recurs widely enough to suspect the intake process itself.

When `systemic_input_quality_signal` is present, invoke `customer-input-quality`. Explain that the current intake appears to be producing opinions/solutions or incomplete reports without enough problem context, and offer to review the actual intake touchpoint. If it has not been supplied, ask for screenshots or pasted field labels/questions from the Support form, feedback form, Community/Discord template, CS workflow, or equivalent.

## Stage 9 — Challenge the theme boundary

Ask:
- Which patterns genuinely belong together?
- Could any pattern stand alone as a different product problem?
- Are different cohorts/states experiencing materially different problems?
- Are we smuggling an assumed cause into the label?
- Are we grouping because the team wants a neat story?
- Is the shared mechanism supported by the evidence rather than imagined from likely solutions?

Do **not** use “would one solution solve all of these?” as a merge criterion. Solution thinking must not define the problem boundary.

## Stage 10 — Attach ALL qualifying evidence

Every evidence record used must remain available with:
- source ID;
- participant;
- date;
- verbatim quote/excerpt;
- pattern(s) supported;
- evidence readiness;
- independence status;
- incident ID when known;
- source reference.

Do not replace participant wording with AI interpretation when presenting evidence.

## Stage 11 — Keep borderline and deviant cases visible

Maintain:
- `borderline_evidence`;
- `contradictory_or_deviant_evidence`;
- `unclustered_relevant_experiences`.

These protect against premature closure.

## Stage 12 — Quantify signals and problems in separate lanes

**Solution/request signals** may be counted before problem boundaries stabilize when the signal object is explicit and duplicate/linkage review has been performed. These counts describe recurrence/salience only.

**Problem-pattern counts** may be added only after:
- deduplication;
- incident/linkage review;
- stable-enough inclusion/exclusion criteria;
- borderline review;
- split/merge decisions are stable or clearly marked provisional.

Rules:
- counts describe the coded dataset, not population prevalence;
- distinguish messages, authors, and apparently independent incidents;
- upvotes indicate salience, not evidence strength;
- overlapping pattern counts are not exclusive shares;
- do not rank “top problems” from qualitative counts alone unless the ranking question and denominator are justified.

## Stage 13 — Aggregate recurrent solution/request signals outside findings

Repeated requests/opinions should be shown separately when they are decision-relevant. Create a `solution_request_signal` after checking duplicates, repeated authors, social linkage/campaigns, source mix, elicitation mode, product state, and time.

Example:
`"Add file upload"` repeated many times may be a salient discovery signal. It does not establish the underlying user problem or validate file upload as the intervention.

For every signal record a `problem_relationship`:
- `established_problem`;
- `possible_problem`;
- `multiple_possible_problems`;
- `underlying_problem_unknown`.

If recurrence is substantial and the decision matters, set an investigation status such as `investigate_now` rather than merely parking the request as non-evidence. The investigation must sample requesters and reconstruct the underlying episodes without grouping them by solution.

## Stage 13A — Produce a decision-ready problem brief

For each provisional/stabilized problem, provide a problem brief that helps the team design solutions without choosing one for them. Include:
- who/context, when supported;
- user goal;
- triggering situation;
- what happens;
- consequence;
- workarounds/next actions;
- constraints/dependencies;
- important variations;
- linked solution/request signals;
- what is known;
- what remains unknown;
- `decision_inputs`: evidence-supported facts any eventual solution should account for.

Do not turn `decision_inputs` into a recommended implementation unless the user explicitly asks for solution generation.

## Stage 14 — Run coding-stability check before stabilization

Before `stabilized_finding_for_current_frame`:
- freeze inclusion/exclusion criteria;
- reapply them to relevant raw cases in a fresh pass;
- inspect changed/ambiguous memberships;
- revise, split, narrow, return to provisional, or return to a null outcome if meaning changes materially.

## Stage 15 — Use an evidence-support profile, not a confidence score

Do not output `low/medium/high confidence`.

Report:
- evidence readiness/completeness;
- number of apparently independent incidents/authors when meaningful;
- duplicate/social-linkage caveats;
- temporal comparability;
- contradictory/deviant evidence;
- sampling limitations;
- triangulation/source diversity;
- remaining unknowns.

# Merge / split decision rule

Default: **split before merge**.

Merge only when all are true:
1. cases share a meaningful experience structure;
2. the abstraction improves product understanding;
3. the merged label does not imply an untested cause;
4. important subgroup/context differences remain visible;
5. the shared boundary is supported by evidence, not by a hypothesized solution.

If uncertain, keep separate provisional patterns or return a null outcome.

# Output schema

```yaml
synthesis:
  outcome: no_defensible_recurring_problem_established|insufficient_evidence|isolated_problem_signal|research_lead_only|provisional_user_problem|stabilized_finding_for_current_frame
  title: string|null
  summary: string|null
  scope_notes: string|null
  inclusion_logic: string|null
  exclusion_logic: string|null
  alternative_explanations: [string]
  null_recovery:
    what_current_material_supports: [string]
    missing_evidence: [string]
    immediate_recovery_action: string|null
    systemic_input_quality_signal: none|possible|clear
    input_quality_reason: string|null
    request_current_touchpoint_artifacts: boolean
patterns:
  - id: string
    label: string
    status: candidate_pattern|provisional_pattern
    inclusion_criteria: [string]
    exclusion_criteria: [string]
    evidence_ids: [string]
    apparently_independent_incident_ids: [string]
    borderline_evidence_ids: [string]
    deviant_evidence_ids: [string]
all_evidence: [evidence_record]
borderline_evidence: [evidence_record]
contradictory_or_deviant_evidence: [evidence_record]
unclustered_relevant_experiences: [evidence_record]
research_leads: [research_lead]
solution_request_signals:
  - signal_id: string
    requested_solution: string
    verbatim_variants: [string]
    occurrence_count: number|null
    unique_participant_count: number|null
    apparently_independent_participant_count: number|null
    duplicate_or_socially_linked_count: number|null
    source_mix: object
    elicitation_mix: object
    temporal_pattern: string|null
    problem_relationship:
      status: established_problem|possible_problem|multiple_possible_problems|underlying_problem_unknown
      problem_ids: [string]
      explanation: string
    investigation_status: investigate_now|investigate_later|already_investigated|not_currently_decision_relevant
    investigation_rationale: string
problem_briefs:
  - problem_id: string
    problem_statement: string
    who_and_when: string
    user_goal: string
    triggering_situation: string
    what_happens: string
    consequence: string
    workarounds_or_next_actions: [string]
    constraints_and_dependencies: [string]
    important_variations: [string]
    linked_solution_request_signal_ids: [string]
    what_we_know: [string]
    what_we_do_not_know: [string]
    decision_inputs: [string]
sample_caveats: [string]
synthesis_decisions:
  - action: split|merge|rename|exclude|retain_unclustered|return_null_outcome
    rationale: string
coding_stability:
  status: not_run|unstable|stable_enough_for_current_frame
  changed_or_ambiguous_case_ids: [string]
  effect_on_finding: string
evidence_support_profile:
  readiness_notes: [string]
  independence_notes: [string]
  temporal_comparability: string
  contradictions: [string]
  sampling_limitations: [string]
  triangulation_notes: [string]
  remaining_unknowns: [string]
quantification:
  signal_quantification_status: not_run|descriptive_signal_only
  problem_quantification_status: not_ready|descriptive_only
  notes: string
```

# Summary rule

A summary is a **late-stage interpretation**, not an early compression step and never a replacement for evidence.

Keep it at the same abstraction as the problem label. If no defensible recurring problem exists, say that plainly instead of writing a pseudo-theme — **then immediately explain what is missing and how to recover it**. If the missing context is systematic, also surface the upstream intake-quality problem and offer to review the current touchpoint.
