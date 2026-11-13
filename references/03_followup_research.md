---
name: followup-research
description: Build follow-up queues from incomplete first-hand signals and research leads, and generate non-leading questions that reconstruct experience.
inherits: evidence-first-product-researcher
version: 0.11
---

# Follow-up Research

## Purpose

Select people worth contacting because their message is relevant but does not yet provide sufficient evidence.

Two important candidate types:

1. `partial_experience` — likely first-hand, but missing context/sequence/consequence.
2. `research_lead_participant` — posted a repeated opinion/solution or discourse signal whose underlying experience is unknown.

## Candidate selection

Prioritize people who:
- describe a potentially important first-hand issue but omit context
- report behavioral change without the triggering episode
- offer an unusually detailed or deviant perspective
- contradict an emerging pattern
- represent an under-sampled cohort
- make a hearsay claim and may connect the team to first-hand participants
- are among apparently independent participants behind a recurrent research lead, or represent linked/contradictory cases worth disambiguating

Do not use upvotes or posting frequency to infer solution validity or product priority. However, after deduplication/social-linkage checks, substantial recurrence across apparently independent requesters may increase **research priority** because it signals a situation worth understanding.

## Research-lead example

100 people say:
`"Add file upload."`

Do not ask:
`"Why do you want file upload?"`

Treat this as a high-salience discovery signal, not a feature vote. Select a diverse subset across apparently independent, socially linked, source-type, cohort/context, and unclear-linkage cases when useful and begin with open episode reconstruction:
- “Think back to the situation that led you to post that suggestion. What were you trying to get done?”
- “Walk me through what happened.”
- “What did you do next?”
- “What happened as a result?”

Only after the episode is clear may the interviewer return to the original suggestion: “You suggested file upload afterwards. How did that idea connect to what happened?”

The goal is to discover whether one repeated request contains one problem, several different problems, or no important recurring problem **without anchoring the participant to the proposed solution**.

## Diagnose missing evidence

Explicitly list gaps:
- situation/context
- goal
- concrete event
- sequence
- expectation
- next action
- consequence
- first-hand status
- relevant cohort/context


## Detect repeated missing-context patterns

After diagnosing individual gaps, check whether the **same gaps recur across the corpus**.

If many records repeatedly omit the same information or arrive primarily as proposed solutions/opinions:
- do not create an endless follow-up queue as the only response;
- flag a possible upstream feedback-intake problem;
- summarize which context is systematically absent;
- invoke `customer-input-quality` to improve future input in parallel with following up existing cases.

If the current intake mechanism has not been provided, proactively ask the user for screenshots of the relevant Support/feedback form, Community/Discord template, ticket intake, CS workflow, or other customer input touchpoint. If screenshots are unavailable, ask them to paste the current questions/field labels and describe what happens after submission.

Do not require screenshots to continue analysing the existing evidence. The screenshot request is for improving future input, not a prerequisite for the current corpus analysis.

## Question rules

Prefer episodic reconstruction:
- “Think about the last time...”
- “What were you trying to do?”
- “What happened next?”
- “What did you expect?”
- “What did you do instead?”

Avoid:
- “Why do you think X is bad?”
- “Would feature Y solve this?”
- “Do you agree we need more content?”
- “How would you redesign it?”

Do not introduce the team's hypothesis before reconstructing the event.


## Discovery-first questioning protocol

The participant should reveal the problem in their own terms.

Follow a **broad-to-narrow funnel**:

1. **Episode recall — do not name the suspected problem**
   - “Think about the last time this situation came up. What were you trying to get done?”
   - “Walk me through what happened from the beginning.”

2. **Behavior and sequence**
   - “What did you do first?”
   - “What happened next?”
   - “What did you do after that?”

3. **Expectation / meaning, only after the sequence is clear**
   - “What were you expecting at that point?”
   - “How did you decide what to do next?”

4. **Consequence**
   - “What happened as a result?”
   - “Did that change what you did afterwards?”

5. **Clarify the original request only at the end, if needed**
   - “You mentioned file upload in your message. Where did that idea come into the situation you just described?”

Do not start by asking the participant to explain or defend the feature request.

### Leading-question rejection test

Before outputting a question, reject or rewrite it if it:
- names the suspected problem before the participant does;
- embeds a causal theory (“Was this frustrating because the menu is confusing?”);
- presupposes failure (“Why couldn’t you find it?”);
- suggests a desired answer (“Wouldn’t file upload make this easier?”);
- offers forced alternatives before open recall (“Was it the cost or the grind?”);
- contains evaluative language (“bad”, “annoying”, “unfair”) not introduced by the participant;
- asks the participant to speculate about other users instead of recounting their own episode;
- asks “why” before the concrete sequence is understood, encouraging post-hoc rationalisation.

Prefer neutral prompts such as:
- “What were you trying to do?”
- “Walk me through what happened.”
- “What did you notice?”
- “What did you do next?”
- “What happened after that?”

### Research-lead example: repeated `Add file upload` requests

Do **not** open with:
- “Why do you want file upload?”
- “When was the last time you wanted to upload a file?”

These anchor the interview around the proposed solution.

Prefer:
1. “Think back to the situation that led you to post that suggestion. What were you trying to get done?”
2. “Walk me through what happened.”
3. “What did you do next?”
4. “What happened as a result?”
5. Only after the episode is reconstructed: “You suggested file upload afterwards. How did that idea connect to what happened?”

The goal is to discover the underlying job/problem without teaching the participant what the researcher thinks the problem is.

## Hearsay

If someone says “everyone is quitting because...”:

Ask:
1. What changed in your own play?
2. Which specific people told you why they left?
3. Can we contact them directly?

## Deviant-case follow-up

Prioritize contradictory participants.

If most mature players report repetitive gameplay but one mature player remains highly engaged, investigate what differs in their context rather than discarding them.

## Team-facing communication

Do not present follow-up recommendations as research methodology. Explain them as practical next steps.

Good:
> **Talk to this player because we know they changed what they did, but we do not yet know what happened immediately beforehand. Ask them to walk through the last time it happened. Do not mention our suspected cause. This will help us determine whether this belongs to the emerging problem or is a different issue.**

Avoid unexplained language such as `deviant case`, `episodic reconstruction`, or `qualitative gap`.

## Output schema

```yaml
candidate:
  source_id: string
  author_id: string|null
  candidate_type: partial_experience|solution_request_signal_participant|research_lead_participant|hearsay_connector|deviant_case
  verbatim_quote: string
  why_relevant: string
  why_not_yet_evidence: string
  missing_context:
    - string
  follow_up_questions:
    - string
  research_priority: high|medium|low
  research_priority_rationale: string
  product_priority_inference_allowed: false
  team_facing_recommendation:
    what_to_do: string
    why: string
    what_we_are_trying_to_learn: string
    what_not_to_say: [string]
    what_this_will_help_decide: string
systemic_input_quality:
  status: none|possible|clear
  recurring_missing_context: [string]
  why_this_may_be_an_intake_problem: string|null
  request_touchpoint_screenshots_or_copy: boolean
```
