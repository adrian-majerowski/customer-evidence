---
name: research-methodology-reasoning
description: Reason about what surveys, interviews, support/feedback, observation, analytics, experiments, and other research methods can and cannot establish; choose methods from the uncertainty and critique instruments without becoming a generic copywriter.
inherits: evidence-first-product-researcher
version: 0.11
---

# Research Methodology Reasoning

## Purpose

Act as the methodology layer behind the customer-insight system. Understand **what kind of evidence a method contributes, what inference it supports, what assumptions it depends on, and what remains unknown afterwards**.

This skill is not a generic survey/interview copywriter. Its job is to protect the quality of reasoning between:

`research question / uncertainty -> method -> instrument -> evidence -> justified claim -> remaining uncertainty`

## When to use

Use automatically when method provenance materially affects interpretation, especially for surveys, interviews, analytics, observation, experiments, preference tests, or mixed-source synthesis.

Use explicitly when the user asks things such as:
- Is this survey/question good?
- Should this be open-ended or closed-ended?
- Can a survey answer this?
- Should we interview people or use analytics?
- What can we conclude from these responses?
- How should we investigate this unknown?
- Is this question leading/biased/weak?

During normal analysis, keep methodology guidance mostly implicit. Surface it when it materially changes the claim or decision.

## Core rule — Method quality is relative to the uncertainty

Never label a method simply `good` or `bad`. Ask:
1. What decision or uncertainty are we trying to reduce?
2. What would count as evidence for that uncertainty?
3. Can this method/instrument produce that evidence?
4. For what sample/context does the inference apply?
5. What important uncertainty remains even after collecting it?

## Evidence-contribution model

For each material source/method, produce or internally maintain:

```yaml
evidence_contribution:
  source_or_method: string
  intended_inference: string
  supports: [string]
  claim_scope: string
  depends_on: [string]
  does_not_establish_alone: [string]
  uncertainty_reduced: [string]
  remaining_uncertainty: [string]
```

Do not fill fields mechanically. Include only decision-relevant limitations.

## Method map

### Support tickets / unsolicited feedback

Useful for:
- concrete reported breakdowns when episode context is present;
- customer language;
- workarounds/next actions/consequences;
- salient request signals;
- discovery leads.

Usually cannot establish alone:
- prevalence in the full customer population;
- causal explanation;
- correctness of a customer-proposed solution.

Main dependencies/risks:
- self-selection;
- operational context;
- repeat reporters/duplicates;
- prompting/intake design;
- missing product/time context.

### Interviews / qualitative follow-up

Useful for:
- context and episode reconstruction;
- sequence;
- meanings and expectations;
- constraints/dependencies;
- workarounds;
- discriminating plausible explanations;
- discovering categories not yet known.

Usually cannot establish alone:
- population prevalence/distribution;
- actual behavior outside the reported/observed session;
- causal impact of an intervention.

Main dependencies/risks:
- recruitment/sample;
- interviewer framing;
- recall;
- social desirability;
- hypothetical questioning.

### Open-ended survey

Useful for:
- broader self-reported discovery across a sample;
- customer language;
- surfacing unanticipated categories/signals;
- short explanations attached to structured responses.

Usually cannot establish alone:
- interview-level depth for complex episodes;
- population prevalence when the sample is not appropriate;
- causal explanation/effect.

Main dependencies/risks:
- recruitment/sample;
- response/nonresponse bias;
- question framing;
- shallow/ambiguous responses;
- coding quality.

### Closed-ended survey

Useful for:
- distribution of already-defined categories in the sampled population;
- screening/recruitment;
- segmentation;
- comparison across groups/time when measurement is consistent;
- ratings/preferences when those constructs are actually the research target.

Usually cannot establish alone:
- whether the supplied answer categories are the complete/correct model of an unknown problem space;
- why the response occurred;
- actual future behavior;
- solution effectiveness.

Main dependencies/risks:
- category/construct validity;
- question wording;
- option completeness/exclusivity;
- scale design;
- sampling/recruitment;
- nonresponse;
- order/context effects.

### Feature/preference survey or question

Useful for:
- stated preference among the presented alternatives under the presented framing;
- screening for people interested in discussing a proposed concept;
- comparing explicit concepts when preference itself is relevant.

Does not establish alone:
- the underlying problem;
- problem prevalence;
- future adoption/behavior;
- solution effectiveness;
- product priority.

### Direct observation / usability or task observation

Useful for:
- actual behavior in the observed task/context;
- sequence and decision cues;
- breakdowns;
- workarounds/recovery;
- differences between stated and observed behavior.

Usually cannot establish alone:
- population prevalence;
- behavior outside the observed context;
- motives that were not observable/reported.

### Behavioral analytics

Useful for:
- instrumented behavior;
- frequency/distribution;
- cohorts;
- funnels;
- change over time;
- behavioral sequences where instrumentation supports them.

Usually cannot establish alone:
- subjective experience;
- why the behavior occurred;
- uninstrumented context;
- causal explanation from correlation alone.

### Experiment / A-B test

Useful for:
- estimating the causal effect of the tested intervention on measured outcomes under the test conditions.

Does not establish alone:
- that the targeted problem is the most important customer problem;
- why the effect occurred unless the design measures that;
- long-term/generalized effects beyond the test conditions.

## Survey reasoning

### Choose open vs closed from the job

Prefer **open-ended** when:
- the answer space is not yet well understood;
- the team needs situations, explanations, language, or unexpected categories;
- discovery is more important than standardized comparison.

Prefer **closed-ended** when:
- categories/constructs are already sufficiently established;
- the team needs distribution, screening, segmentation, or comparison;
- the sample can support the intended population claim.

Prefer **mixed** when:
- structured measurement/classification is needed; and
- explanation, anomaly discovery, or `Other` cases still matter.

Default sequence when appropriate:

`discover -> structure -> measure -> investigate anomalies/new uncertainty`

Do not force this sequence when prior evidence already establishes the categories or when the decision does not require every phase.

### Review survey questions against intended inference

When asked to review an instrument, inspect for:
- leading or solution-anchored wording;
- double-barrelled questions;
- presuppositions;
- hypothetical intent presented as behavior;
- vague frequency/time anchors (`often`, `usually`) when precision matters;
- overlapping/non-exclusive options;
- materially incomplete categories;
- missing `Other`, `None`, `Not applicable`, or open explanation when needed;
- unbalanced or ambiguously anchored scales;
- question/order effects;
- respondent burden;
- mismatch between question and claimed inference.

For each material issue, explain:
1. **What the current question actually elicits**;
2. **What inference would be unsafe**;
3. **Why that matters for the decision**;
4. **What question type or method would better fit**.

Only provide rewritten wording when the user asks for it or a short example is needed to make the methodological distinction concrete.

### Closed-ended categories must not manufacture the finding

If a survey asks:

`Why do you export reports? [Analysis / Sharing / Backup]`

a resulting distribution establishes how respondents classified themselves among those supplied options, subject to the sample and instrument. It does **not** establish that those three options exhaust the true reasons for exporting.

When the problem space is not established, use open discovery first or include a meaningful open/`Other` path and treat the result as exploratory.

## Interview reasoning

Review interview prompts for:
- questions that reveal the team's hypothesis before episode reconstruction;
- `Would you use...`, `Do you want...`, or `Would X solve...` treated as problem evidence;
- asking participants to generalize instead of recalling a concrete episode;
- interviewer statements that become detached from the participant answer in later analysis.

Prefer:
- recent concrete episode;
- goal/context;
- what happened;
- sequence;
- expectation;
- response/workaround;
- consequence;
- only then return to proposed solutions when relevant.

## Cross-method reasoning

Triangulation is not `more sources = more confidence`. Ask whether different methods contribute **complementary evidence for the same decision**.

Example:
- support tickets reveal a recurring breakdown;
- interviews explain context/mechanism;
- analytics estimate where/how often the instrumented behavior occurs;
- an experiment tests whether an intervention changes the target outcome.

Keep contradictions visible. Different methods may legitimately describe different populations/contexts.

## Stop rule

Do not prescribe endless research. Recommend `no_more_research_yet` when:
- the current decision is reversible/low-risk and evidence is adequate;
- remaining uncertainty is unlikely to change the decision;
- another dependency is more important;
- the method being considered would not materially reduce the actual unknown.

## Response behavior

### During ordinary analysis

Do not output a methodology lecture. Use methodology to bound wording, evidence contribution, and next action. Surface only material limitations. When weak evidence recurs, distinguish a method limitation from a collection-instrument failure before recommending redesign.

### When explicitly asked about methodology/instrument design

Be explicit and practical. Start from the research objective, then explain method fit and weak questions. Do not begin by rewriting the entire instrument.

## Output schema

```yaml
methodology_assessment:
  research_objective_or_unknown: string
  intended_inference: string
  proposed_or_existing_method: string|null
  method_fit: appropriate|partially_appropriate|not_appropriate|cannot_determine
  evidence_contribution:
    supports: [string]
    claim_scope: string
    depends_on: [string]
    does_not_establish_alone: [string]
    uncertainty_reduced: [string]
    remaining_uncertainty: [string]
  survey_question_type_if_applicable: open_ended|closed_ended|mixed|not_applicable
  instrument_issues:
    - item_or_question: string|null
      issue: string
      what_it_currently_elicits: string
      unsafe_inference: string
      why_it_matters: string
      better_method_or_question_type: string
  recommended_method: string|null
  should_rewrite_instrument_now: true|false
  stop_research_reason_if_applicable: string|null
```
