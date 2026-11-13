---
name: observation-recommendations
description: Plan direct observation when the unresolved question is about current behavior, sequence, attention, errors, workarounds, or competing explanations, without priming participants.
inherits: evidence-first-product-researcher
version: 0.11
---

# Observation Recommendations

## Purpose

Turn a specific behavioral uncertainty into a focused observation plan.

Observation is for learning **what happens in the current experience**. Evaluating a proposed solution is handled by `solution-evaluation`.

Do not recommend observation merely because message evidence is incomplete. First run `choose-next-research-action` and confirm the unknown is behavioral.

## Recommend observation when the unknown concerns

- actual action sequence;
- navigation/task path;
- hesitation or attention;
- errors/misclicks;
- workarounds;
- abandonment/recovery;
- differences between stated and actual behavior;
- what information drives a decision;
- which of several plausible explanations best matches behavior;
- behavior that messages/recall cannot establish reliably.

## Observation plan

### 1. State the unknown

Use one plain-language sentence:

> `We know ____. We still cannot tell ____ from messages alone.`

Do not design generic “watch users use feature X” research.

### 2. Choose who/context only from evidence

Target a cohort only when the corpus/metadata supports that distinction.

Do not invent labels such as `hardcore`, `novice`, `spender`, `high-status`, or `expert` from tone or posting behavior alone.

### 3. Observe a realistic current task

Prefer natural or realistic use before explanation.

Capture:
- starting state;
- participant goal;
- first action;
- path/sequence;
- information inspected;
- pauses/hesitation;
- backtracking;
- errors/misclicks;
- external tools/information;
- workarounds;
- abandonment/recovery;
- immediate consequence/next action.

### 4. Consider competing explanations without inventing them

List **all plausible explanations currently supported enough to matter**.

If there are two or more plausible explanations, design the observation to distinguish them.

For each real alternative state:
- what behavior would make it more plausible;
- what behavior would make it less plausible.

If only one plausible explanation is currently visible, do **not** invent a fake alternative to satisfy a template. Instead specify what observation would challenge or weaken the current interpretation.

### 5. Avoid leading/priming

Before behavior occurs, do not reveal:
- the suspected problem;
- the team's hypothesis;
- expected behavior;
- the proposed solution.

After behavior occurs, use neutral recall prompts such as:
- “What were you trying to do there?”
- “What did you notice?”
- “What were you expecting when you did that?”
- “What made you change direction?”

### 6. Define what would change the team's direction

The plan should state what observed result would:
- strengthen the current interpretation;
- weaken it;
- suggest a different problem;
- show the issue is not observable in this context.

## Example

Evidence:
`Several players report skipping Arena opponents shown as much stronger.`

Unknown:
`We cannot tell which information actually drives the skip or whether viable alternatives are available.`

Observe participants choosing an opponent in the current game.

Watch:
- which numbers/details they inspect first;
- what makes them reject a matchup;
- whether they inspect other cues;
- what they do when every option appears poor.

Do not say:
`"We are testing whether matchmaking is unfair."`

This helps decide whether the next investigation should focus on matchmaking quality, how matchup strength is communicated, or player strategy.

## Plain-language team recommendation

Use:
- **What to do**
- **Why**
- **Who/context** when supported
- **What to watch for**
- **Do not tell participants**
- **What this helps decide**
- **What would make us change direction**

Avoid unexplained methodology jargon.

## Output schema

```yaml
observation_plan:
  unresolved_question: string
  why_observation: string
  who_or_context: string
  task_or_situation: string
  capture: [string]
  competing_explanations:
    - explanation: string
      more_plausible_if: [string]
      less_plausible_if: [string]
  challenge_to_current_interpretation: [string]
  post_observation_questions: [string]
  avoid_before_observation: [string]
  direction_change_signals: [string]
  team_facing_recommendation:
    what_to_do: string
    why: string
    who_or_context: string
    what_to_watch_for: [string]
    do_not_tell_participants: [string]
    what_this_helps_decide: string
    what_would_make_us_change_direction: string
```
