---
name: research-quality-audit
description: Audit evidence-first customer insight for framing contamination, source/elicitation provenance, solution-signal misuse, evidence readiness, independence, context preservation, temporal validity, sampling, over-synthesis, null outcomes, method selection, and decision-ready communication.
inherits: evidence-first-product-researcher
version: 0.11
---

# Research Quality Audit

## Purpose

Evaluate whether the current corpus and analysis can support useful product-research conclusions **without creating false certainty**.

## Research-frame audit

Verify:
- explicit research question;
- corpus/date/channel/population boundaries;
- inclusion/exclusion rules;
- known sampling limitations;
- product/version/event context when available;
- out-of-scope signals did not silently expand the question.

## Team-framing contamination audit

Check whether:
- team hypotheses/solutions were separated from user evidence;
- initial coding was shaped by a team explanation before independent evidence patterns emerged;
- team assumptions were rewritten as user findings;
- alternative explanations were actively considered.

When feasible require a user-evidence-first pass.

## Evidence-readiness audit

Count/estimate where useful:
- `comparison_ready` reported experiences;
- grounded subjective experiences;
- `partial_experience`;
- `follow_up_candidate`;
- opinions/judgments;
- solutions/preferences;
- hearsay/generalizations;
- bugs;
- research leads.

Do **not** label detailed self-reports as “strong evidence.” Evidence readiness means safe enough for comparison, not truth/corroboration/prevalence.

## Independence / incident audit

Verify that recurrence claims distinguish:
- messages;
- authors;
- incidents;
- duplicates/reposts;
- socially linked accounts;
- apparently independent accounts;
- independence unknown.

Flag:
- five retellings of one incident presented as five experiences;
- different authors assumed independent without checking thread/campaign/social linkage;
- repeated language treated as independent confirmation.

## Evidence-episode / context audit

Verify evidence retains:
- focal verbatim message;
- parent/root when relevant;
- materially relevant replies/corrections;
- source/author/date/thread;
- product-state metadata when available.

Flag isolated quotes whose local context changes meaning.

## Source / elicitation provenance audit

Verify that source type and elicitation context are preserved when they materially affect interpretation.

For surveys check:
- exact question wording is retained;
- answer options/scale are retained where relevant;
- open-text responses remain linked to the prompt and preceding context;
- sample/recruitment context is not silently generalized to all customers;
- answers to feature-choice questions are not rewritten as problem prevalence.

For interviews check:
- participant responses remain linked to interviewer prompts;
- prompted agreement with a suggested solution is not treated as spontaneous problem evidence;
- interviewer framing/leading language is visible in interpretation.

## Collection-form bias

Flag prompts that lead directly to solutioning:
- “What should we change?”
- mandatory Solution fields;
- feature-voting prompts;
- “Do you like X?”

Prefer experience reconstruction for problem discovery.


## Input-system quality audit

Check whether low evidence quality is systematic rather than incidental.

Flag when:
- a large share of records are opinions/proposed solutions with no episode context;
- the same goal/sequence/consequence fields are repeatedly absent;
- customer-facing staff must manually reconstruct the same context again and again;
- the analysis returns a null/insufficient outcome but fails to explain what is missing;
- the assistant identifies systematic intake failure but does not offer to inspect/improve the upstream touchpoint.

When the issue appears systematic, the audit should recommend `customer-input-quality` and, if the touchpoint is not available, ask for screenshots or pasted questions/field labels. Do not recommend turning the touchpoint into a long questionnaire.

## Sampling / community-context audit

Inspect:
- active-community/support population only;
- repeat posters;
- leadership/officer/admin dominance when actually evidenced;
- product-stage/device/server/account concentration;
- missing churned/silent users;
- language/time-zone bias;
- moderation/channel-rule effects.

Do not infer `hardcore`, `spender`, `expert`, `high-status`, `novice`, or subgroup identity from tone alone. Require metadata, interaction evidence, or self-description; otherwise mark unknown.

## Social amplification

Look for:
- copied/near-identical framing;
- repeated solutions;
- one thread seeding later language;
- coordinated campaigns;
- reactions/upvotes showing resonance rather than independent experience.

Create research leads/context where appropriate instead of findings.

## Temporal validity audit

Check whether:
- materially different product states were merged;
- the same wording refers to different versions/events/workflows;
- a “persistent” problem actually spans comparable periods;
- before/after evidence should be separated.

## Premature synthesis / compression audit

Check whether analysis:
- grouped by topic/keyword rather than experience structure;
- merged distinct mechanisms into one neat theme;
- failed to retain unclustered/borderline cases;
- skipped candidate/provisional stages;
- failed to document split/merge decisions;
- quantified/ranked **problem patterns** while coding boundaries changed;
- presented overlapping counts as exclusive shares;
- used a broad label that blurs different product decisions;
- could not explain why grouped cases belong together;
- used hypothetical solutions to define the problem boundary.

Default when uncertain: **split, preserve cases, or return a null outcome.**


## Solution/request-signal audit

Verify that repeated proposed solutions are neither discarded nor converted into findings. Check that:
- duplicates, repeated authors, campaigns, and social copying were assessed;
- recurrence is used as signal salience/research priority, not solution validity;
- `solution_request_signal` is kept separate from problem-pattern counts;
- every surfaced solution has a `problem_relationship`;
- high-salience signals with unknown underlying problems have an explicit investigation path when decision-relevant;
- the analysis does not output a feature-request leaderboard as if it were customer insight;
- `request frequency`, `problem prevalence`, `solution desirability`, and `product priority` are not conflated.

## Null-outcome audit

Explicitly ask:

> `Would the evidence be represented more honestly by saying no defensible recurring problem is established?`

Flag analyses that produce a theme simply because the workflow expects one.

Valid outputs include:
- `no_defensible_recurring_problem_established`;
- `insufficient_evidence`;
- `isolated_problem_signal`;
- `research_lead_only`.

## Interpretation-audit check

Every provisional/stabilized finding should document:
- included-because rationale;
- similar exclusions and reasons;
- contradictions/deviant cases;
- alternative interpretations;
- assumptions/risks;
- what evidence would change the interpretation;
- temporal scope.

## Coding-stability audit

Before `stabilized_finding_for_current_frame`, verify inclusion/exclusion rules were reapplied in a fresh pass.

If changed/ambiguous memberships materially alter meaning/scope, return to provisional/null rather than forcing stabilization.

## Evidence-support profile audit

Reject qualitative `low/medium/high confidence` scores.

Require instead:
- readiness/completeness notes;
- independence/linkage notes;
- temporal comparability;
- contradictions;
- sampling limitations;
- triangulation/source diversity;
- remaining unknowns.

## Research-methodology and next-action audit

Check that every material method/source is interpreted according to what it can actually establish. The audit should be able to answer: `What uncertainty does this evidence reduce, and what claim remains unsupported?`

Check the recommendation matches the unknown:
- small missing episode/meaning detail -> targeted follow-up;
- unknown problem space/context/sequence/constraints -> interview or other open qualitative discovery;
- broader open discovery where shorter self-report is adequate -> open-ended survey;
- distribution/segmentation of already-established valid categories -> closed-ended survey with appropriate sampling;
- classification plus explanation -> mixed survey;
- actual behavior/sequence -> observation;
- instrumented frequency/distribution -> analytics;
- concrete proposed solution -> solution evaluation, only after the problem is sufficiently established;
- no decision-relevant gap -> no more research yet.

For surveys, flag:
- closed-ended options used to define an unexplored problem space;
- answer categories that are overlapping, incomplete, or not grounded in prior evidence when category validity matters;
- lack of `Other`/`None`/`Not applicable` where omission would force false classification;
- double-barrelled, leading, hypothetical, vague-timeframe, presupposing, or solution-anchored questions when they threaten the intended inference;
- preference questions reported as behavior/problem prevalence;
- percentages generalized beyond the sampled/recruited population;
- open-ended survey responses treated as interview-depth evidence.

For interviews, flag:
- prevalence claims from qualitative interviews alone;
- interviewer framing treated as participant-originated evidence;
- validation of a suspected solution/problem substituted for episode reconstruction.

Flag method selection when:
- a favored method is recommended by habit rather than because it reduces the stated uncertainty;
- observation is recommended automatically just because messages are incomplete;
- another closed-ended survey is proposed when the remaining unknown is `why/how`;
- more interviews are proposed when the remaining unknown is population distribution of already-established categories;
- solution evaluation is used as problem discovery;
- research is recommended when it cannot change a current decision.

## Solution-evaluation audit

When a solution is being tested, verify:
- the established problem is stated separately from the solution;
- the test question is explicit;
- realistic tasks/context are used rather than feature demos;
- success/failure evidence is defined before exposure;
- preference/opinion is separated from behavior;
- disconfirming outcomes/new problems are actively captured;
- “participants liked it” is not treated as proof the problem was solved.

## Decision-support output audit

Check that provisional/stabilized findings provide enough information for the team to reason about solutions: situation, goal, event/breakdown, consequence, workaround/next action, constraints/dependencies, variations, unknowns, and evidence-supported decision inputs.

If a solution is mentioned, verify the underlying problem remains independently understandable even when that solution tested well.

## Plain-language communication audit

Every team-facing recommendation should say:
- what to do;
- why;
- who/context when supported;
- what to look for/ask;
- what not to say/do;
- what decision this helps;
- what result would change direction when useful.

Flag unexplained researcher jargon.

## Output schema

```yaml
quality_summary: string
research_frame_failures: [string]
team_framing_contamination_risks: [string]
evidence_readiness_mix:
  comparison_ready: number|null
  partial_experience: number|null
  follow_up_candidate: number|null
  opinion_or_preference: number|null
  solution: number|null
  hearsay: number|null
  bug_report: number|null
  research_lead_candidate: number|null
  solution_request_signal_candidate: number|null
independence_risks: [string]
context_preservation_failures: [string]
source_or_elicitation_provenance_failures: [string]
solution_request_signal_failures: [string]
decision_support_output_failures: [string]
temporal_validity_risks: [string]
collection_biases: [string]
input_system_quality_risks: [string]
sampling_caveats: [string]
social_amplification_signals: [string]
null_outcome_risks: [string]
auditability_failures: [string]
interpretation_audit_failures: [string]
coding_stability_failures: [string]
evidence_support_profile_failures: [string]
method_selection_failures: [string]
method_inference_failures: [string]
survey_instrument_failures: [string]
interview_instrument_failures: [string]
solution_evaluation_failures: [string]
plain_language_communication_failures: [string]
premature_synthesis_risks: [string]
recommended_changes: [string]
```
