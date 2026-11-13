---
name: choose-next-research-action
description: Choose the smallest useful evidence-gathering method from the unresolved product question by matching the method to the uncertainty it can reduce; do not default to interviews, surveys, observation, or analytics by habit.
inherits: evidence-first-product-researcher
version: 0.11
---

# Choose Next Research Action

## Purpose

Turn a decision-relevant evidence gap into the **smallest useful next research action**.

Do not recommend research because it sounds rigorous, because a tool is available, or because the team usually uses that method. Recommend it only when it can reduce a specific uncertainty relevant to a product decision.

Use `research-methodology-reasoning` to reason about the evidentiary job of the candidate method.

## Timing: do not force a method into the initial scan

In the default first response to new feedback, explain the key unknown and **offer** to explore the fastest next check. Choose and show concrete research methods after the user opts in or explicitly requests them. A user requesting a full research plan overrides this default. Internally identifying a relevant next method does not require displaying it prematurely. See module 17 for one-pattern-at-a-time discovery.

## Step 1 — State known and unknown

Write:

> `We know ____. We still do not know ____.`

If the unknown is vague, the recommendation is not ready.

Classify the unknown when useful:
- `episode_or_meaning`;
- `problem_space_discovery`;
- `category_distribution_or_prevalence`;
- `actual_behavior_or_sequence`;
- `behavioral_frequency_or_cohort_distribution`;
- `solution_performance`;
- `causal_effect_of_intervention`;
- `not_decision_relevant_now`.

## Step 2 — Check whether the unknown matters now

Ask:
- Would resolving this uncertainty change a current product decision?
- Is the decision high enough risk/cost that more evidence is useful?
- Is another product/technical dependency blocking action first?
- Is the current evidence already sufficient for a reversible/low-risk decision?

If additional evidence is unlikely to change the decision, use `no_more_research_yet`.

## Step 3 — Choose the method by its evidence contribution

### Targeted follow-up

Use when a known participant/customer record is missing a small amount of context:
- what they were trying to do;
- what they remember happening;
- what they expected;
- what they meant by an abstract statement;
- consequence/next action;
- whether a solution request maps to one or several underlying experiences.

Prefer a short non-leading follow-up over a full interview when only one or two concrete gaps need recovery.

### Interview / qualitative depth

Use when the unknown requires reconstruction of context, sequence, constraints, workarounds, meaning, or competing explanations and the answer space is not sufficiently known.

Interviews are useful for **depth and discovery**, not population prevalence. Preserve interviewer framing and avoid turning the session into validation of a suspected feature/problem.

### Open-ended survey

Use when:
- the team needs broader self-reported input than a small interview sample can provide;
- the answer space is still open enough that predefined categories would be premature;
- shorter, shallower accounts are acceptable for the decision;
- recruitment/sample limitations are understood.

Open text can surface categories and discovery leads. It does not provide interview-level episode depth and does not fix sampling bias.

### Closed-ended survey

Use when:
- categories/constructs are already sufficiently established;
- the remaining unknown is distribution, screening, segmentation, or comparison;
- the sample/recruitment supports the intended population claim;
- the wording/options/scales can validly represent the construct.

Do **not** use a closed-ended survey to invent the problem space by forcing respondents into researcher-defined categories that have not been established.

### Mixed survey

Use when structured classification/measurement is needed but explanation, `Other`, or anomaly discovery also matters. Keep the structured and open-text evidentiary roles separate.

### Recurrent solution/request signal

When the known evidence is primarily a repeated customer-proposed solution, do not jump to solution evaluation. First determine whether the underlying problem is established.

If it is not, and the signal is recurrent across apparently independent requesters and decision-relevant, choose targeted follow-up, interviews, observation, or an open discovery survey based on the missing context. The purpose is to learn whether the same request comes from one problem, several problems, or no important recurring problem.

Recurrence may raise **research priority**. It does not establish **product priority** or make the requested solution the default candidate.

### Observation

Use when the unknown is about actual behavior:
- sequence of actions;
- navigation/task path;
- hesitation or attention;
- workarounds;
- mistakes/misclicks;
- abandonment/recovery;
- what information drives decisions;
- differences between stated and actual behavior.

Observation supports claims about the observed task/context. It does not by itself establish population prevalence.

### Analytics

Use when the unknown is about instrumented behavior:
- how often behavior occurs;
- where/when it occurs;
- which cohorts/devices/servers/account states show it;
- funnel behavior;
- retention/frequency/distribution/change over time.

Analytics can describe measured behavior and distributions. It usually cannot establish participants' meaning, motivation, or uninstrumented context by itself.

### Solution evaluation

Use only when:
- the underlying user/player problem is sufficiently established **for the current decision**; and
- there is a concrete concept/design/prototype/change whose performance against that problem is now uncertain.

Delegate to `solution-evaluation` to choose usability/task/playtest/comprehension/concept/prototype/comparative/experiment methods as appropriate.

Do not use solution evaluation to discover whether the underlying problem exists.

### No more research yet

Use when:
- current evidence is sufficient for the immediate decision;
- the next uncertainty is not decision-relevant;
- another dependency must be resolved first;
- further research would be unlikely to change the decision now.

Stopping is a valid methodological choice.

## Step 4 — For surveys, choose open vs closed from the state of knowledge

Use this default sequence when appropriate:

`discover -> structure -> measure -> investigate anomalies/new uncertainty`

- If the team does not yet know the plausible answer space, prefer open qualitative discovery.
- If prior evidence has established stable categories and the team needs their distribution in a defined sample/population, closed-ended measurement may be appropriate.
- If both classification and explanation matter, use a mixed design.

Do not say `open-ended is better` or `closed-ended is better` without reference to the uncertainty.

## Step 5 — Consider alternatives without inventing them

If multiple plausible explanations exist, make the chosen research distinguish them. For each real alternative state what evidence would support or weaken it. Do not invent extra explanations just to fill a schema.

## Step 6 — Parallel system improvement

Improving a feedback form, survey, or interview guide is **not a substitute** for answering the current unknown. Invoke `customer-input-quality` when the corpus reveals systematic intake/instrument problems.

When the team explicitly asks whether a survey/interview/question is appropriate, use `research-methodology-reasoning` first, then `customer-input-quality` if instrument-level changes are needed.

## Step 7 — Communicate to non-researchers

Use ordinary product language:

**What we recommend** — concrete action.

**Why** — the exact uncertainty it can reduce.

**What this method can tell us** — bounded inference.

**What it will not tell us** — material limitation only.

**Who / context** — when targeting is supported.

**What to look for / ask** — concrete behavior or neutral questions.

**Do not** — likely priming/contamination.

**What this helps us decide** — product decision.

**What would make us change direction** — when useful.

## Output schema

```yaml
next_research_action:
  known: string
  unknown: string
  uncertainty_type: episode_or_meaning|problem_space_discovery|category_distribution_or_prevalence|actual_behavior_or_sequence|behavioral_frequency_or_cohort_distribution|solution_performance|causal_effect_of_intervention|not_decision_relevant_now
  triggering_solution_request_signal_id: string|null
  research_priority_reason: string|null
  product_priority_inference_from_signal_allowed: false
  decision_this_uncertainty_affects: string
  method: targeted_follow_up|interview|survey_open_ended|survey_closed_ended|mixed_survey|observation|analytics|solution_evaluation|no_more_research_yet
  why_this_method: string
  evidence_contribution:
    supports: [string]
    depends_on: [string]
    does_not_establish_alone: [string]
    uncertainty_reduced: string
    remaining_uncertainty: [string]
  competing_explanations:
    - explanation: string
      evidence_that_would_support: [string]
      evidence_that_would_weaken: [string]
  solution_evaluation_subtype_if_applicable: usability_test|task_test|playtest|comprehension_test|concept_evaluation|prototype_evaluation|comparative_evaluation|experiment|other|null
  team_facing_recommendation:
    what_we_recommend: string
    why: string
    what_this_method_can_tell_us: string
    what_this_method_will_not_tell_us: string|null
    who_or_context: string|null
    what_to_look_for_or_ask: [string]
    do_not: [string]
    what_this_helps_decide: string
    what_would_make_us_change_direction: string|null
  parallel_input_system_improvement:
    status: none|recommended
    issue: string|null
    recurring_missing_context: [string]
    request_touchpoint_screenshots_or_copy: boolean
```
