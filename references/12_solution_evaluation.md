---
name: solution-evaluation
description: Choose and design an appropriate evaluation of a proposed product solution after the underlying user/player problem is sufficiently established for the decision, using realistic tasks and non-leading evidence rather than preference questions.
inherits: evidence-first-product-researcher
version: 0.11
---

# Solution Evaluation

## Purpose

Evaluate a proposed concept, design, prototype, workflow, feature, or game change **without confusing solution preference with evidence that the underlying problem exists or has been solved**.

This skill is vertical-neutral:
- in games, a solution evaluation may be a `playtest`;
- in software/services, it may be a usability/task/prototype/comprehension test;
- at scale, it may be an experiment when the decision requires behavioral comparison.

## Entry gate

Do not run this skill merely because a prototype exists.

Before evaluating a solution, establish:
1. the user/player problem is sufficiently defensible **for the current decision**;
2. the team can state what aspect of the proposed solution is uncertain;
3. showing the solution now will not replace needed problem discovery.

If the problem itself is still materially uncertain, return to `choose-next-research-action` and prefer follow-up, observation, or analytics as appropriate.

## Step 1 — Anchor evaluation to the established problem

Write:

> `Established problem: ____.`
>
> `This solution is intended to change: ____.`
>
> `We need to learn whether: ____.`

Do not redefine the problem around the solution.

## Step 2 — Choose the evaluation type from the question

### Usability test
Use when the question is whether people can understand and operate an interface/workflow.

Typical unknowns:
- can they find it?
- can they complete the flow?
- where do errors/backtracking occur?
- do labels/controls make sense?

### Task test
Use when the key question is whether people can accomplish a realistic goal under representative conditions.

Focus on task success, strategy, errors, effort, and recovery rather than whether they “like” the design.

### Playtest
Use for gameplay systems, mechanics, loops, balance-facing interactions, or experiential game changes.

Focus on what players actually do during play, how decisions/strategies change, where the intended experience appears or fails, and what new problems emerge.

Do not reduce a playtest to post-session preference ratings.

### Comprehension test
Use when the main uncertainty is whether people correctly understand information, rules, states, pricing, rewards, permissions, risks, or system behavior.

Test what they infer **without first explaining the intended meaning**.

### Concept evaluation
Use when the proposed solution is early/abstract and the question is whether people understand the concept, see how it relates to a known problem, or interpret its value proposition.

A concept evaluation does **not** prove demand or establish the original user problem.

### Prototype evaluation
Use when an interactive or semi-interactive representation exists and the question concerns behavior, workflow, comprehension, or problem resolution before full build.

### Comparative evaluation
Use when there are two or more plausible designs and the decision genuinely requires comparison.

Do not force comparative testing when one design can be evaluated against clear behavioral criteria on its own.

### Experiment / A-B test
Use when:
- the change can be deployed safely to comparable populations;
- the decision depends on measurable behavior at scale;
- success/failure metrics and guardrails can be defined before exposure;
- confounds, assignment, and product-state differences can be managed well enough for the decision.

An experiment can estimate behavioral effects; it may still require qualitative work to explain why they occurred.

## Step 3 — Define evidence before testing

Before participants see the solution, define:
- the realistic user/player goal;
- starting context/state;
- what successful problem resolution would look like behaviorally;
- important failure modes;
- what evidence would show the solution did **not** address the problem;
- possible new problems/side effects;
- what remains outside the test's scope.

Do not define success as:
- “participants liked it”;
- “participants said they would use it”;
- “positive sentiment”;
- “high preference score” alone.

## Step 4 — Use realistic tasks, not feature demos

Bad:
> `Try our new rally-location feature and tell us what you think.`

Better:
> `Several rallies are available. Decide which, if any, you would join.`

Bad:
> `Do you understand the new invoice dashboard?`

Better:
> `You have several invoices from this week. Show me which ones still need action.`

Do not tell participants how the design is supposed to work before measuring whether they can use/understand it.

## Step 5 — Separate observed behavior from opinion

Record separately:
- task behavior;
- success/failure;
- errors/misunderstandings;
- time/effort only when meaningful;
- workarounds;
- decision strategy;
- subjective experience;
- preference/opinion;
- participant explanation.

Positive opinion cannot override behavioral failure.
Negative opinion cannot automatically invalidate a solution that successfully resolves the target problem; understand the tradeoff/new issue.

## Step 6 — Avoid leading evaluation questions

Do not ask:
- “Do you like this?” as the primary outcome;
- “Would this solve your problem?”;
- “Is this easier?” before observing behavior;
- “Would you use this feature?” as proof of future behavior;
- “We added this to fix X — did it work?”

After the task, neutral prompts may include:
- “What were you trying to do there?”
- “What did you notice?”
- “What were you expecting?”
- “What made you choose that?”
- “Was there anything you expected to be able to do but couldn't?”

## Step 7 — Look for disconfirmation and side effects

Actively look for:
- the original problem still occurring;
- participants succeeding for an unintended reason;
- new errors/confusion;
- new burden shifted elsewhere;
- subgroup/context differences;
- behavior that contradicts the team's success story.

## Step 8 — Keep the problem visible even when the solution works

A successful solution evaluation must not collapse the insight into the implementation. The final conclusion should still state:
- the established problem;
- relevant situation/context;
- what the solution changed;
- the evidence that the breakdown was reduced/removed in the tested context;
- remaining constraints, trade-offs, or scope limitations.

Prefer: `Teams need to move reporting data into external workflows for recurring reconciliation. In this test context, CSV export removed the manual copy/paste step for the tested workflows.`

Avoid: `Users wanted CSV and CSV tested successfully.`

## Step 9 — Keep the conclusion bounded

Allowed conclusions:
- `In this test context, participants could/could not complete...`
- `The prototype reduced/removed the observed breakdown for these participants...`
- `The concept was interpreted differently than intended...`
- `The test does not tell us how common this behavior is in the full user base.`

Do not conclude population prevalence, long-term retention impact, or causal business outcomes from a small qualitative evaluation unless separate evidence supports them.

## Plain-language team output

Every recommendation/evaluation plan must answer:
- **What we're testing**
- **Why this test**
- **Who/context**
- **What task to give them**
- **What to watch for**
- **Do not tell/ask**
- **What would count as the solution working**
- **What would show it is not solving the problem**
- **What this helps us decide**

Avoid unexplained research jargon.

## Example — game

Established problem:
`Players in the evidence set report opening rally requests one by one because location/distance is not visible before deciding whether to join.`

Prototype:
`Rally cards show star system and estimated travel time.`

Recommended evaluation:
- subtype: `playtest` / `task_test`;
- task: `While playing normally, decide which available rallies you would join.`
- watch: whether players can decide without opening each rally, which information drives the decision, errors, unnecessary navigation, and any new confusion;
- do not say: `We added location to fix rally navigation. Is this better?`;
- disconfirming result: players still open each rally because another missing cue, not location, drives the decision.

## Example — SaaS

Established problem:
`Users report difficulty identifying which invoices still require action.`

Prototype:
`New invoice status dashboard.`

Recommended evaluation:
- subtype: `task_test` / `usability_test`;
- task: `Review these invoices and show which ones need attention today.`
- watch: what statuses they interpret, errors, overlooked invoices, backtracking, and whether they can explain their choice;
- disconfirming result: users still cannot determine action state even though they like the dashboard.

## Output schema

```yaml
solution_evaluation:
  established_problem: string
  problem_status: isolated_problem_signal|provisional_user_problem|stabilized_finding_for_current_frame
  why_problem_is_sufficient_for_current_decision: string
  proposed_solution: string
  problem_remains_independently_stated: true
  evaluation_question: string
  evaluation_type: usability_test|task_test|playtest|comprehension_test|concept_evaluation|prototype_evaluation|comparative_evaluation|experiment|other
  why_this_type: string
  who_or_context: string
  starting_state: string
  realistic_task: string
  evidence_to_capture:
    behavior: [string]
    subjective_experience: [string]
    interpretation_or_opinion: [string]
  success_criteria: [string]
  disconfirming_or_failure_signals: [string]
  new_problem_watchouts: [string]
  do_not_tell_or_ask: [string]
  post_task_questions: [string]
  scope_limitations: [string]
  team_facing_plan:
    what_were_testing: string
    why_this_test: string
    who_or_context: string
    task_to_give: string
    what_to_watch_for: [string]
    do_not_tell_or_ask: [string]
    what_counts_as_working: [string]
    what_shows_it_is_not_solving_the_problem: [string]
    what_this_helps_decide: string
    final_problem_first_conclusion: string
```
