---
name: customer-input-quality
description: Diagnose systematic customer-input quality problems across feedback/support forms, community flows, surveys, and interview guides; decide whether the collection mechanism is responsible; emit bounded remediation signals and improve prompts while preserving provenance, burden, versioning, and comparability.
inherits: evidence-first-product-researcher
version: 0.11
---

# Customer Input Quality

## Purpose

Improve the **upstream customer evidence system** when the existing corpus repeatedly arrives as opinions, feature requests, proposed solutions, vague complaints, or incomplete first-hand signals.

This skill does not manufacture problem findings from weak input and it is not a generic copywriting assistant. For method-selection and inference questions, use `research-methodology-reasoning`; use this skill when the actual intake/instrument needs diagnosis or redesign. It helps the team:
1. understand what the current intake is producing;
2. identify what context is repeatedly missing;
3. recover useful context from existing cases with non-leading follow-up;
4. determine whether the collection mechanism actually warrants redesign;
5. emit a bounded remediation task when redesign is justified;
6. improve the customer touchpoint so future input is more decision-useful without unnecessary respondent burden.

## Trigger conditions

Invoke when there is a recurring pattern such as:
- many messages say `add X`, `change Y`, `this is bad`, or equivalent without describing a concrete episode;
- the same goal, event, sequence, consequence, expectation, or context fields are repeatedly absent;
- Support/CS/Community repeatedly need manual follow-up just to understand what happened;
- a null/insufficient synthesis is caused primarily by solution/opinion-led or systematically incomplete input;
- the user explicitly asks how to improve a feedback form, support intake, Discord/community template, ticket flow, CS handoff, survey, or interview guide.

Do **not** infer a systemic intake problem from one or two weak messages. State `possible` when evidence is suggestive but limited.

## Step 1 — Diagnose the current input pattern

State plainly:
- what customers are currently providing;
- what useful signal is still present;
- which context is repeatedly missing;
- what downstream work/risk this creates for CS/Community/Product.

Example:

> Customers are repeatedly proposing solutions, but the intake rarely captures the situation that led to the request, what they were trying to accomplish, what happened, or the consequence. That means CS has to reconstruct basic context manually and Product can receive a proposed fix without a defensible problem behind it.

Do not say only `low-quality data` or `insufficient evidence`.

## Step 2 — Recover context from existing records

For current customers/messages, use `followup-research` to generate neutral broad-to-narrow follow-up questions.

Do not ask participants to defend the proposed solution.

Example for `Add file upload`:

> “Think back to the situation that led you to post that suggestion. What were you trying to get done?”

Then reconstruct sequence, expectation, workaround/next action, and consequence before returning to the original request.

## Step 3 — Ask to inspect the current touchpoint

If the team has not already supplied the relevant intake artifact, proactively ask for it.

Ask for one or more of:
- screenshots of the current feedback/support form;
- screenshots of the Discord/community feedback template or bot flow;
- screenshots of the ticket intake or CS workflow;
- pasted field labels/questions when screenshots are unavailable;
- the exact survey questions, options/scales, and recruitment/sample description;
- the interview guide or relevant transcript turns showing interviewer prompts;
- a short description of what happens after submission/research and who follows up.

Suggested wording:

> Your current intake appears to be producing a lot of opinions/solutions without enough problem context. If you upload screenshots of the current form/template/workflow (or paste the questions and field labels), I can show where useful context is being lost and suggest a lighter problem-focused version.

If screenshots may contain personal/customer data, remind the user to redact information they are not authorized to share.

Do not block the current analysis while waiting for screenshots.

## Step 4 — Review the touchpoint

Assess whether the touchpoint, survey, or interview guide:
- invites proposed solutions before concrete experience;
- asks broad opinion questions such as `What should we improve?`;
- asks hypothetical prediction such as `Would you use X?`;
- uses mandatory solution/feature fields;
- lacks space for a recent situation/goal/event/consequence;
- asks too much and creates unnecessary friction;
- makes every customer answer questions that should be conditional follow-ups;
- makes private follow-up difficult where sensitive context is involved;
- loses provenance/context needed by Product later;
- frames survey respondents around a feature/solution before asking about experience;
- asks interview participants to validate a suspected problem or solution instead of reconstructing episodes;
- makes open-text answers uninterpretable by separating them from the exact question/preceding context;
- uses closed-ended options before the answer space is sufficiently understood;
- uses overlapping or materially incomplete answer categories;
- forces classification where `Other`, `None`, `Not applicable`, or an open explanation is needed;
- uses double-barrelled questions, vague timeframes, unbalanced scales, presuppositions, or hypotheticals that weaken the intended inference.

Also consider operational reality: support resolution speed, community norms, user effort, privacy, and who owns follow-up.

## Step 5 — Decide whether redesign is actually needed

When the user asks a methodological question such as `Should this be open-ended or closed-ended?`, answer from the research objective and uncertainty first. Do not rewrite the survey merely because you can.

If the instrument is adequate for the intended inference, say so and avoid gratuitous changes. If it is weak, explain:
1. what the question currently measures/elicits;
2. what inference would be unsafe;
3. why the weakness matters;
4. what type of question/method better fits the uncertainty.

Only then redesign wording when requested or necessary.

## Step 6 — Redesign for minimum useful context

The goal is **not more questions**. The goal is the smallest amount of information that lets the team understand whether there is a concrete problem and what is still missing.

Prefer lightweight prompts such as:
- `What were you trying to do?`
- `What happened?`
- `What did you do next?` or `What did you do instead?` when consequence/workaround matters.

Do not force all of these into every form by default. Use progressive disclosure or conditional follow-up when appropriate.

A good redesign may include:
- one better initial prompt;
- an optional context field;
- a private follow-up path;
- CS/Community coaching for the next neutral question;
- structured metadata already available from the system rather than asking the customer again.

## Step 7 — Preserve opinions and solutions as signals

Do not remove feature-request or opinion channels merely because they are not direct problem evidence.

Keep the original request/opinion verbatim as:
- a research lead;
- a `solution_request_signal` candidate when recurrent;
- a discourse/salience signal;
- a pointer to the customer for follow-up.

The redesign should add problem context **without pretending solution requests are useless**.

## Step 8 — Connect the improved input to AI analysis

Once input quality improves, explain how the evidence-first AI workflow can:
- distinguish reported experience from opinion/solution;
- identify what still lacks context;
- compare cases without grouping by requested solution;
- surface defensible patterns, contradictions, and evidence gaps;
- tell the team when messages have reached their limit and another method is needed.

Do not imply that AI can repair information that was never collected.

## Step 9 — Create a collection-quality remediation signal

When redesign is justified, create a structured handoff rather than a vague instruction to `make the form better`.

```yaml
collection_quality_remediation_signal:
  status: investigate|redesign_candidate|no_redesign_needed
  collection_touchpoint: string
  evidence_window: string|null
  submissions_reviewed: integer|null
  recurring_quality_failures:
    - failure: string
      observed_pattern: string
      estimated_extent: string|null
  mechanism_evidence:
    - string
  alternative_explanations:
    - string
  evidence_missing_because_of_collection:
    - string
  redesign_objective: string|null
  smallest_change_hypothesis: string|null
  burden_constraint: string|null
  comparability_risk: low|medium|high|unknown
  recommended_action: inspect_instrument|propose_redesign|use_other_method|no_change
```

If the corpus shows weak input but does not support a link to the collection mechanism, use `investigate` rather than `redesign_candidate`.

## Step 10 — Preserve instrument versions and evaluate the intervention

For any proposed or deployed redesign, preserve:
- `collection_instrument_version`;
- effective date/time when known;
- exact changed prompts/options/logic;
- rationale tied to the diagnosed evidence-quality failure;
- expected evidence-quality improvement;
- expected respondent-effort/response-rate tradeoff;
- comparability note for historical analysis.

Do not compare pre/post theme or request rates as if the measurement instrument were unchanged when wording, required fields, options, routing, placement, audience, or completion burden changed materially.

After enough post-change input exists, evaluate the targeted outcome. Examples:
- fewer solution-only submissions;
- more submissions with reconstructable situation/goal/consequence;
- less manual follow-up required;
- acceptable completion/response volume;
- no material increase in leading or researcher-imposed categories.

The outcome may be `improved`, `mixed`, `no_material_improvement`, or `harmful_tradeoff`. A failed redesign is evidence to revise or revert, not a reason to keep adding fields.


## Guardrails

- Do not turn Support/Community/CS into researchers.
- Do not turn every feedback form into an interview guide.
- Do not maximize data collection.
- Do not ask leading or solution-anchored questions.
- Do not require every field when conditional follow-up is better.
- Do not claim the intake caused weak evidence unless the corpus/touchpoint supports that interpretation.
- Do not redesign based only on aesthetics; tie every proposed change to an evidence gap or operational need.
- Do not default to open-ended questions. Use them when discovery/explanation is the job.
- Do not default to closed-ended questions. Use them when categories are sufficiently established and measurement/classification is the job.
- Do not produce a full rewritten instrument unless the user asks for one, redesign is the requested task, or a `redesign_candidate` remediation signal has explicitly routed the task to the collection-improvement agent.
- Do not assume weak submissions imply a weak form; consider customer motivation, channel context, issue simplicity, and whether another method is needed.
- Do not silently deploy changes to a production touchpoint by default.
- Do not sacrifice historical comparability without recording the instrument change and its likely effect.
- Do not optimize evidence richness while ignoring completion burden or response volume.

## Team-facing response pattern

Use this order when the corpus is systematically polluted:

**What the current feedback tells us**  
State the useful signal without overclaiming.

**What is repeatedly missing**  
List the specific context preventing problem understanding.

**What to do with the existing feedback**  
Give targeted, non-leading follow-ups or the appropriate next research method.

**What this says about the intake system**  
Explain whether the repeated gaps suggest the touchpoint itself needs improvement.

**Let me inspect the current touchpoint**  
Ask for screenshots or pasted questions/field labels, with a privacy/redaction reminder where relevant.

## Output schema

```yaml
input_quality_diagnosis:
  status: no_systemic_issue|possible_systemic_issue|clear_systemic_issue
  current_input_pattern: string
  useful_signals_preserved: [string]
  recurring_missing_context: [string]
  downstream_cost_or_risk: [string]
  evidence_for_systemic_diagnosis: [string]
existing_feedback_recovery:
  recommended_follow_ups: [string]
  other_next_method_if_needed: targeted_follow_up|interview|survey_open_ended|survey_closed_ended|mixed_survey|observation|analytics|solution_evaluation|no_more_research_yet|null
touchpoint_review:
  artifact_status: not_supplied|screenshots_supplied|text_supplied|workflow_description_supplied|survey_supplied|interview_guide_supplied|transcript_excerpt_supplied
  request_screenshots_or_copy: boolean
  privacy_note_if_relevant: string|null
  issues_found: [string]
redesign:
  objective: string
  proposed_changes:
    - change: string
      evidence_gap_addressed: string
      expected_operational_effect: string
  questions_or_prompts: [string]
  conditional_follow_up_logic: [string]
  avoid: [string]
collection_quality_remediation_signal:
  status: investigate|redesign_candidate|no_redesign_needed
  collection_touchpoint: string|null
  mechanism_evidence: [string]
  alternative_explanations: [string]
  redesign_objective: string|null
  smallest_change_hypothesis: string|null
  comparability_risk: low|medium|high|unknown
  recommended_action: inspect_instrument|propose_redesign|use_other_method|no_change
instrument_change_control:
  current_version: string|null
  proposed_version: string|null
  material_changes: [string]
  historical_comparability_note: string|null
  approval_required_before_deploy: boolean
  post_change_measures: [string]
connection_to_ai_analysis:
  how_better_input_improves_analysis: [string]
```
