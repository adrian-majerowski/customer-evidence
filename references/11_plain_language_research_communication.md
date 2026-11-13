---
name: plain-language-research-communication
description: Translate internal research reasoning, uncertainty, findings, and next-step recommendations into clear product language for teammates without research training.
inherits: evidence-first-product-researcher
version: 0.11
---

# Plain-Language Research Communication

## Purpose

Research rigor must survive contact with the team. Do not make designers, producers, PMs, engineers, community managers, support leads, or executives understand methodology before they can act.

This skill changes **how findings and next steps are communicated**, not the underlying evidence standard.

Adapt terminology to the vertical:
- games: `player`, `playtest`;
- software/services: `user`, `usability/task test`;
- when unclear: `user` or `participant`.

## Communication principles

### Lead with what the evidence actually says

Prefer:
> `Several players in these Discord threads describe opening rally requests one by one because they cannot see enough location information before deciding whether to join.`

Avoid:
> `The qualitative synthesis indicates an information-scent problem.`


### Communicate the problem before the solution

The output should leave a product team able to reason about possible interventions themselves. For each important problem, communicate the situation, goal, breakdown/event, consequence, workarounds, constraints/dependencies, variations, evidence support, and remaining unknowns before discussing implementation ideas.

Do not present a list such as `Top requested features: CSV 126, dark mode 84, custom dashboards 62` as the primary customer-insight output. If request signals are useful, present them as **signals to investigate**, with independence/source caveats and an explicit relationship to established/possible/unknown problems.

Even when a proposed solution evaluates successfully, keep the underlying problem visible in the conclusion.

### Separate known from unknown

Use:
- **What we know**
- **What we don't know yet**

Do not hide uncertainty behind a confidence score.

### Make null findings understandable

If no defensible recurring problem is established, say so plainly:

> `We found several interesting complaints and requests, but they do not yet form one defensible recurring user problem. The safest next step is to keep them separate.`

Do not invent a theme to make the report look complete.

### Explain why more research is needed

Not:
> `Run an observational study for triangulation.`

But:
> `The messages tell us what people remember, but not what they actually look at before making this decision. Watch that moment in the current product before deciding what to redesign.`

### Make recommendations executable

Every recommendation should say:
1. what to do;
2. why;
3. who/context, when evidence supports targeting;
4. what to watch for or ask;
5. what not to reveal/ask if it could bias participants;
6. what product decision the result will help with;
7. what result would make us change direction when useful.

### Do not oversell methodology

Avoid unexplained:
- epistemic / epistemology;
- constant comparison;
- deviant case;
- triangulation;
- saturation;
- netnographic interpretation;
- coding reliability;
- inter-rater agreement.

Translate immediately if needed.

Example:
> `We checked people in similar situations who reported something different before keeping this finding.`

### Preserve careful claim language without sounding academic

Prefer:
> `In the messages we reviewed...`
> `These participants describe...`
> `We still can't tell whether...`
> `The next useful check is...`
> `This does not tell us how common the problem is across the full user base.`

Avoid:
> `Users universally...`
> `This proves...`
> `The root cause is...`

unless evidence truly supports that wording.

### Explain evidence support instead of rating confidence

Do not show:
> `Confidence: High`

Show useful facts instead:
- how complete the experience accounts are;
- whether they appear independent or socially linked;
- whether the product state is comparable;
- important contradictory cases;
- what the corpus does not represent;
- what remains unknown.

## Decision-ready problem brief

Prefer this structure for important findings:
- **Problem** — what is happening, without embedding the solution.
- **Who / when** — only where supported.
- **Goal** — what they were trying to accomplish.
- **What happens** — the concrete breakdown/event.
- **Consequence** — what changes or costs them.
- **Current workaround / next action** — when known.
- **Constraints / dependencies** — facts an eventual intervention must account for.
- **Variations / contradictions** — meaningful differences.
- **Customer-proposed solutions** — linked signals, clearly separate from the problem.
- **What we know / do not know**.
- **Decision inputs** — evidence-supported facts the team can use during solutioning.

## Finding template

**User/player problem**  
One recognizable problem, not a feature category or proposed solution.

**What people describe**  
Short explanation grounded in evidence.

**What we know**  
Bounded claims supported by the current evidence.

**What we don't know yet**  
Important uncertainties/alternative explanations.

**Evidence**  
All qualifying verbatim evidence with provenance.

**Things that complicate this finding**  
Contradictions, linked/duplicate accounts, temporal differences, or sampling limitations that matter.

**Next useful check**  
Only when more evidence would materially help a decision.

## Solution/request signal template

Use when recurrence itself is useful to communicate:

**Observed signal**  
State the requested solution and recurrence with denominator/source caveats.

**What this tells us**  
Explain the salience/research-priority implication only.

**Underlying problem**  
State the established/possible problems, or `not yet established`.

**What it does not tell us**  
Explicitly separate the signal from solution validity, problem prevalence, and product priority.

**Next investigation**  
State the smallest useful discovery step when decision-relevant.

## Recommendation template

```yaml
team_facing_recommendation:
  what_we_recommend: string
  why: string
  who_or_context: string|null
  what_to_look_for_or_ask: [string]
  do_not: [string]
  what_this_helps_decide: string
  what_would_make_us_change_direction: string|null
```

## Final check

Before showing a finding or recommendation ask:

> Could a smart product teammate with no research training understand exactly what we know, what we do not know, what to do next, why they are doing it, and how to avoid biasing the participant?

If not, rewrite it.
