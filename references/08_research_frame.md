---
name: establish-research-frame
description: Establish the question, corpus, represented population, boundaries, product context, team context, and known limitations before evidence extraction or synthesis begins.
inherits: evidence-first-product-researcher
version: 0.11
---

# Establish Research Frame

## Purpose

Prevent the AI from discovering whatever is easiest to summarize or cluster.

Before broad analysis of a corpus, explicitly define what the analysis is trying to establish and what data it is allowed to speak for.

## Default research question

When the team has not supplied a narrower question, use:

> **What user/player problems are evidenced in these customer/research sources?**

Do not silently replace this with:
- What features do users/players want?
- What topics are most common?
- What are users/players unhappy about?
- What should the team build?

Those are different research questions.

## Required frame

```yaml
research_frame:
  question: string
  decision_or_uncertainty_to_reduce: string|unknown
  intended_inference: string|unknown
  corpus:
    sources: [string]
    channels_or_spaces: [string]
    date_range: string|unknown
  population_represented: string
  inclusion_rules: [string]
  exclusion_rules: [string]
  known_product_context:
    versions_releases_or_patches: [string]
    events_workflows_or_product_states: [string]
  source_types: [support_ticket|feedback_submission|community_post|review|survey_open_text|survey_structured|interview_transcript|research_session|direct_observation|behavioral_data|other]
  elicitation_modes_present: [unsolicited|prompted_open|prompted_problem|prompted_solution|prompted_rating|interviewer_led|unknown]
  survey_or_interview_prompt_context: [string]
  sample_or_recruitment_context: string|unknown
  known_limitations: [string]
  team_context:
    hypotheses: [string]
    assumptions: [string]
    concerns: [string]
    proposed_solutions: [string]
    roadmap_or_business_constraints: [string]
  analysis_order: user_evidence_first_then_team_comparison
  out_of_scope_signals_policy: research_lead
```


## Source and elicitation frame

For mixed-source customer insight, record which source types are present and how responses were elicited. Do not treat support, feature-choice surveys, open-text surveys, interviews, analytics, observation, and experiments as interchangeable. Also record the decision-relevant uncertainty when known, because method quality is relative to the inference the team is trying to make.

Capture when available:
- source type(s);
- exact survey/interview prompts relevant to the evidence;
- answer options/scales for structured surveys;
- recruitment/sample context;
- unsolicited vs prompted input;
- whether prompts name a problem, cause, or solution;
- interview/researcher identity/role only when relevant to framing;
- time/product-state differences across sources.

## Rules

1. Do not claim the corpus represents populations it does not sample.
2. Record unknown boundaries rather than inventing them.
3. If the product changed materially during the corpus period, create temporal strata where possible.
4. If an interesting signal falls outside the research question, retain it as a `research_lead` instead of expanding scope silently.
5. If the research frame changes, log the change and re-evaluate prior inclusion/exclusion decisions.
6. Team hypotheses and proposed solutions are **context, not user evidence**. Record them separately.
7. When feasible, perform user-evidence coding before comparing findings to team beliefs. Do not create initial categories from the team's proposed cause/solution.
8. Before treating a source as sufficient, state what inference the team wants and whether this source/method can support it. Use `research-methodology-reasoning` when method fit is material.

## Output

Return the frame before synthesis when the analysis is broad enough that scope could materially affect interpretation.
