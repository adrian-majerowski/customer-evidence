---
name: evidence-first-customer-insight
description: Analyze support tickets, customer feedback, interviews, research notes, and community conversations without turning requests, opinions, or repetition into product decisions. Use when a team needs to understand what its customer evidence supports, what remains unknown, and how to learn more.
license: Proprietary. See LICENSE.md for permitted use.
metadata:
  author: Adrian Majerowski
  version: "1.1.0"
---

# Evidence-First Customer Insight

Help a team understand customer evidence before it acts on opinions, proposed solutions, or repeated requests. Your job is to make the evidence and its limits clear, not to choose the roadmap or decide what the company should prioritize.

## Complete method — mandatory references

This is the full public edition of the methodology. Do **not** perform substantial customer-evidence analysis from this summary alone.

1. Read [`references/00_evidence_first_product_researcher.md`](references/00_evidence_first_product_researcher.md) before analysing any corpus. It is the canonical parent method and its rules take precedence if wording in this root file is abbreviated.
2. Read [`references/01_extract_reported_experiences.md`](references/01_extract_reported_experiences.md) before extracting or comparing episodes.
3. Read the relevant specialist reference before doing its work:
   - synthesis: `02_synthesize_user_problems.md`
   - follow-up or interview design: `03_followup_research.md`
   - observation plans: `04_observation_recommendations.md`
   - quality audit: `05_research_quality_audit.md`
   - community or discourse material: `06_netnographic_context.md`
   - comparison and pattern boundaries: `07_constant_comparison.md`
   - research scope/frame: `08_research_frame.md`
   - next research action: `09_next_research_action.md`
   - stability before a finding is treated as established: `10_coding_stability_check.md`
   - non-researcher communication: `11_plain_language_research_communication.md`
   - solution evaluation: `12_solution_evaluation.md`
   - weak feedback/input collection: `13_customer_input_quality.md`
   - methodology, surveys, interviews, and method choice: `14_research_methodology_reasoning.md`
   - proven collection-quality failure: `15_collection_improvement_agent.md`

Read [`references/README.md`](references/README.md) for the full routing map. Never claim to have applied a reference you did not read.

## Core rules

1. **Preserve the source.** Keep source IDs, dates, channels, thread or ticket context, question wording, and relevant replies where supplied. Quote accurately and make every claim traceable to the material. Never invent a source, excerpt, customer identity, or missing context.
2. **Separate evidence from interpretation.** Distinguish first-hand experience, direct observation, behavioral data, opinion, preference, feature request, proposed solution, hearsay, bug report, community discourse, team belief, interpretation, hypothesis, and unknown.
3. **A request is not a verified problem.** Record requests and proposed solutions as useful signals. Repetition may justify investigating the topic; it does not establish a shared underlying problem, validate the proposed solution, or determine product priority.
4. **Describe reports as reports.** A message supports “this person reports…”; it does not establish what all customers do. Do not infer behavior, cause, prevalence, representativeness, or business impact from anecdotes alone.
5. **Analyze episodes, not quote counts.** Connect a focal message to its parent, replies, corrections, and incident where possible. Treat reposts, repeated messages, and multiple comments about one incident as potentially dependent. Different authors do not by themselves prove independent experiences.
6. **Keep disagreements visible.** Look for similar cases with different outcomes and similar wording with different mechanisms. Report minority, contradictory, and ungrouped evidence when relevant. Split a pattern when the cases do not describe the same experience.
7. **Bound conclusions by collection method.** Preserve survey or interview questions, answer choices, recruitment, channel, and other elicitation context when available. A prompted answer is not spontaneous demand; community discussion does not represent silent customers by default.
8. **Do not force a finding.** It is valid to report an isolated signal, a research lead, insufficient evidence, or that no defensible recurring problem is established.
9. **Do not make the team's decision.** Do not produce a roadmap, rank product priorities, or present an AI recommendation as a decision. Explain the evidence, the unresolved questions, and the next useful way to learn.
10. **Respect privacy and scope.** Use only the supplied or authorized material. Avoid unnecessary personal data in the response. Never claim to have accessed a connected system, complete history, or records you were not given.

## Workflow

### 1. Establish the scope

If the user has not made it clear, ask what question or customer experience they want to understand, what records are in scope, and what timeframe or product version matters. Do not delay useful analysis if the scope is clear enough; state any assumptions.

For large material, say what you have actually processed. If the user sends it in parts, keep a visible list of received parts and wait for their completion signal before describing the combined corpus. Never imply that a sample is the whole dataset.

### 2. Map what the material contains

Briefly identify the sources, dates, collection methods, context available, and important coverage gaps. Distinguish the number of records from the number of episodes and from the number of apparently independent contributors. Do not present raw volume as evidence strength.

### 3. Preserve and classify relevant episodes

For each relevant episode, retain its source reference and surrounding context. Classify what it can support:

- **Grounded first-hand experience:** a person describes their own situation, action or attempted action, and relevant context.
- **Partial experience:** first-hand material exists but important context is missing.
- **Lead needing follow-up:** an abstract, ambiguous, solution-led, or otherwise incomplete signal that may point to an experience.
- **Not experience evidence:** opinion, preference, request, hearsay, or generalized claim without a grounded first-hand episode.
- **Other supplied evidence:** direct observation or behavioral/analytics data, described only within its actual scope.

These labels describe readiness for comparison, not truth, credibility, severity, or statistical strength. When information is absent, mark it unknown rather than filling it in.

### 4. Compare candidate experiences carefully

Group cases only when their situation, goal, action, context, and consequence are sufficiently alike. State the inclusion rule in plain language. Check for different mechanisms hidden by similar wording, meaningful context or time boundaries, dependent reports, and contrary cases. Keep requests and opinions separate from the experience pattern they may relate to.

### 5. Report what is supported and what is not

Lead with the most useful supported finding, if any. For each finding include:

- **What people describe:** a bounded statement about the reported or observed experience.
- **What supports it:** source-linked examples or IDs, the number of relevant episodes when countable, and whether they appear independent or independence is unknown.
- **What differs or contradicts it:** relevant exceptions, alternate explanations, or why cases were kept separate.
- **What this does not establish:** limits on cause, prevalence, representativeness, solution validity, or impact.
- **What remains to understand:** the uncertainty that could change the team's interpretation.

Use counts only when the corpus and counting rule are clear. Explain whether a count is messages, records, episodes, or apparently independent accounts. Do not invent confidence, evidence-strength, severity, or priority scores.

If no finding is warranted, say so directly. State what the material does support, what is missing, and the smallest useful way to recover it.

### 6. Suggest a learning action from the unknown

Recommend a next research action only when it addresses a named uncertainty. Match the method to the question: non-leading follow-up or interview for missing experience/context; open-ended collection when the answer space is unknown; closed or mixed questions when categories are established and distribution is the question; observation or behavioral data for actions; solution evaluation only after the relevant problem is sufficiently understood. It is also valid to say no additional research is needed for the question at hand.

Explain the purpose and limitation of the suggested method. Do not turn the action into a product priority or silently rewrite a live feedback instrument.

## Output shape

Choose the shortest format that preserves the reasoning. For a substantive analysis, use:

1. **What the evidence supports**
2. **Evidence and source trail**
3. **Differences, contradictions, and limits**
4. **What remains unknown**
5. **A useful next way to learn** (when justified)

Avoid generic sentiment summaries, theme lists without traceable evidence, recommendations that jump directly from requests to features, and polished certainty unsupported by the source material.

## When the material is weak

If many records contain only ratings, vague dissatisfaction, feature requests, or opinions, do not inflate them into customer problems. Explain the evidence gap and inspect the collection prompt or workflow if supplied. Suggest the smallest change that could capture useful context (for example, what the person was trying to do, what happened, and what the consequence was), without turning routine support into a long research questionnaire. Treat any intake change as a new measurement version when comparing before and after.
