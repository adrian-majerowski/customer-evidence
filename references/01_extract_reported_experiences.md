---
name: extract-reported-experiences
description: Build context-preserving evidence episodes across support, feedback, surveys, interviews, and other sources; extract first-hand experiences while separately preserving solution/request signals and elicitation provenance.
inherits: evidence-first-product-researcher
version: 0.11
---

# Extract Reported Experiences

## Objective

Transform raw customer/research material into structured, auditable **evidence episodes**, case-level experience records, and separate solution/request-signal candidates, including grounded subjective states such as confusion, boredom, frustration, perceived difficulty, trust, or unfairness.

Do not synthesize here.

## Hard guardrails

1. Never treat a proposed solution as the experience.
2. Never treat sentiment alone as the experience; preserve a subjective state only when first-hand and grounded in a concrete situation/episode.
3. Never treat “users/players/everyone/my guild says” as first-hand evidence for those other people.
4. Never invent missing context.
5. Preserve verbatim participant wording.
6. One message may contain multiple signal types. Split them.
7. `I think` is usually interpretation/opinion, not behavior.
8. Do not cluster during extraction.
9. Inspect thread/reply context before qualifying the focal message when available.
10. Preserve product/release/event context when available.
11. Separate **evidence readiness** from **independence**. A detailed report can still be socially linked or duplicated.
12. Preserve source type and how the response was elicited.
13. For interviews, preserve the interviewer turn that elicited the response. For surveys, preserve the exact question and answer options/context when relevant.
14. Do not infer broader claim scope merely from a response. Preserve enough method context for later `evidence_contribution` reasoning.

## Procedure

### Step 1 — Use the active research frame

Keep team hypotheses, proposed solutions, roadmap context, and business constraints outside user evidence records.

### Step 2 — Remove non-data noise and identify duplicates

Ignore bot acknowledgements, empty submissions, and system text unless they materially shape the interaction.

Detect exact/near duplicates and cross-posts. Preserve a duplicate link rather than counting each as independent evidence.

### Step 3 — Preserve source and elicitation context

Classify the source when possible: `support_ticket`, `feedback_submission`, `community_post`, `review`, `survey_open_text`, `survey_structured`, `interview_transcript`, `research_session`, `direct_observation`, `behavioral_data`, or `other`.

Preserve `elicitation_mode`: `unsolicited`, `prompted_open`, `prompted_problem`, `prompted_solution`, `prompted_rating`, `interviewer_led`, or `unknown`.

For surveys preserve the exact question, answer options when relevant, preceding context, and available sample/recruitment context. For interviews preserve speaker turns and the interviewer prompt/question. Do not detach an answer from a leading or solution-framed prompt.

### Step 4 — Build an evidence episode

For each potentially relevant focal message, attach available local context:
- root/parent message;
- thread replies;
- corrections/clarifications;
- author/source IDs;
- timestamp;
- channel/thread;
- reactions/upvotes as salience metadata;
- known patch/version/event/workflow/account state.

Do not flatten the thread into one synthesized quote.

### Step 5 — Segment the focal message

Separate passages into:
- reported experience;
- reported subjective experience;
- opinion/judgment;
- preference;
- proposed solution;
- hearsay/generalization;
- bug report;
- community discourse/norm;
- factual context supplied by participant.

### Step 6 — Inspect contextual challenges

Ask whether replies/context:
- correct a factual misunderstanding;
- dispute the proposed cause;
- show an existing workaround/function;
- reveal the issue applies only to a specific product state;
- materially change the meaning of the focal report.

Preserve both report and challenge. Do not erase the participant's experience just because their explanation may be wrong.

### Step 7 — Detect first-hand grounding

Look for concrete markers such as:
- I tried...
- I was doing...
- when I...
- after I...
- on my account/device/server...
- I stopped / logged off / skipped / changed...

### Step 8 — Reconstruct only what is explicit

Extract when supported:
- context;
- user/player goal;
- what happened;
- expectation;
- response/next action;
- consequence;
- subjective state.

Use `unknown` for missing information.

### Step 9 — Assign evidence readiness, not “strength”

`comparison_ready`
- first-hand;
- concrete enough to compare with other cases;
- the relevant event/outcome is understandable;
- no missing detail makes the core comparison misleading.

`partial_experience`
- first-hand and relevant;
- some concrete experience is present;
- material context/sequence/consequence remains missing.

`follow_up_candidate`
- potentially useful first-hand signal;
- too abstract, solution-led, context-poor, or causally ambiguous to safely use in a pattern yet.

`not_experience_evidence`
- opinion/preference/solution/hearsay/generalization without qualifying first-hand experience.

These states describe **readiness for qualitative comparison**, not truth, prevalence, corroboration, or confidence.

### Step 10 — Assess evidence independence separately

When possible classify the relationship of this episode to other evidence:

- `same_incident` — appears to describe the same underlying event as another record;
- `duplicate_or_repost` — repeated/cross-posted content;
- `socially_linked` — likely shaped by the same thread, campaign, copied framing, or explicit shared account;
- `apparently_independent` — no obvious linkage is visible in the available corpus;
- `independence_unknown` — cannot determine.

If a shared incident can be identified, assign the same `incident_id`.

Do not infer independence solely from different author IDs.

### Step 11 — Detect research leads

If a solution/opinion/discourse signal recurs, retain it as a research lead candidate and, when useful, emit a `solution_request_signal_candidate`.

Record the requested solution verbatim/normalized label, source mix, elicitation mix, time/product context, participant/requester and occurrence counts where available, and whether recurrence is apparently independent, socially linked, duplicated, or unknown. Do not convert recurrence into experience evidence.

### Step 12 — Preserve provenance and time boundaries

Never remove source/date/thread/product-state metadata from qualifying evidence.

## Output schema

```yaml
evidence_episode:
  episode_id: string
  incident_id: string|null
  source_context:
    source_kind: support_ticket|feedback_submission|community_post|review|survey_open_text|survey_structured|interview_transcript|research_session|direct_observation|behavioral_data|other
    elicitation_mode: unsolicited|prompted_open|prompted_problem|prompted_solution|prompted_rating|interviewer_led|unknown
    prompt_or_question_verbatim: string|null
    answer_options: [string]
    preceding_context: string|null
    sample_or_recruitment_context: string|null
    interviewer_turn_verbatim: string|null
    methodological_context_note: string|null
  focal_message:
    source_id: string
    author_id: string|null
    timestamp: string|null
    verbatim: string
  parent_or_root:
    source_id: string|null
    verbatim: string|null
  relevant_replies:
    - source_id: string
      author_id: string|null
      timestamp: string|null
      verbatim: string
      relation: correction|contradiction|clarification|agreement|other
  location:
    channel: string|null
    thread: string|null
  salience_metadata:
    reactions_or_upvotes: number|null
  product_context:
    version_or_patch: string|unknown
    event_workflow_or_account_state: string|unknown
  classifications:
    - reported_experience | reported_subjective_experience | opinion | preference | solution | hearsay | bug_report | community_discourse
  first_hand: true|false|unclear
  evidence_readiness: comparison_ready|partial_experience|follow_up_candidate|not_experience_evidence
  independence_status: same_incident|duplicate_or_repost|socially_linked|apparently_independent|independence_unknown
  linked_episode_ids: [string]
  experience:
    context: string|unknown
    goal: string|unknown
    happened: string|unknown
    expected: string|unknown
    next_action: string|unknown
    consequence: string|unknown
    subjective_state: string|unknown
  contextual_challenges: [string]
  missing_context: [string]
  research_lead_candidate: true|false
solution_request_signal_candidate:
  present: true|false
  requested_solution_verbatim: string|null
  normalized_solution_label: string|null
  requester_or_author_id: string|null
  source_kind: string|null
  elicitation_mode: string|null
  product_context: string|unknown
  independence_status: same_incident|duplicate_or_repost|socially_linked|apparently_independent|independence_unknown|null
  linked_episode_id: string|null
```

## Failure patterns

Reject:

`"Add practice mode" -> "Users cannot experiment"`

unless qualifying experience describes the current experimentation breakdown.

Reject counting five posts about one shared outage/incident as five independent experiences without checking linkage.
