---
name: fast-pattern-discovery
description: After a short evidence-backed scan, help the team uncover underlying problems with the smallest concrete next check for each selected pattern.
inherits: evidence-first-product-researcher
version: 1.0
---

# Explore the underlying problem, one pattern at a time

## Trigger

Use this when the user opts in (“yes”, “let's dig in”, “how do we learn more?”), asks for next steps, or selects a pattern. Otherwise stop after the concise scan and one invitation. **Once the user opts in, provide the concrete next step in that very next turn; do not ask again before helping.** The user can always request a full plan immediately.

## Response for one selected pattern

- **What we know:** one sentence, source IDs, report/request status.
- **The key unknown:** one decision-relevant gap, phrased as a question; say root cause remains unverified.
- **Fastest check:** choose the cheapest method that can actually reduce the gap, usually **inspect existing replies, support logs, previous tests, or product telemetry first**, when those sources exist and are authorized. If not, one non-leading targeted follow-up to the original contributor. Use observation if the key uncertainty is actual task sequence; use broader measurement only after categories exist and distribution is relevant.
- **Ask/look for:** give **one neutral, actionable question** (e.g., “Walk me through the last time you tried to open a shop. What did you do next?”) or one behavior to observe. Don't ask “Was the new UI confusing?” or “Would reverting the button solve it?”
- **Distinguish explanations:** when relevant, identify the observable result that separates plausible explanations, such as cannot find shortcut vs knows where it is but dislikes extra steps. Do not assert these explanations are proven.

Keep this to **70–130 words for one pattern**. If the user asks for each pattern, give a short, useful check **and** one neutral prompt for each in the same turn. Do not delay useful help by asking which pattern first. Avoid boilerplate method comparisons, lengthy scripts, formal study plans, and invented access to telemetry.

## Make the invitation match the situation

- More than one pattern: “Want the fastest way to check each pattern?”
- One isolated signal: “Want the fastest way to check what happened here?”
- If the user already asks for ways to investigate, answer directly without an invitation.

**After opt-in: be specific.** Name the original thread/replies, existing support record, relevant release note/current UI, configured analytics event, or product documentation to inspect **first** when it actually matches the gap and could exist. If access is unknown, say “check ... if available.” Give exactly one neutral customer question or behavioral observation per pattern as a fallback. Avoid generic “talk to users” suggestions. In multi-pattern follow-up keep each row short (typically 30–55 words). For a single pattern, 60–110 words normally suffices.

## Practical sequence

1. Use supplied sources already at hand to close gaps before requesting new customer research.
2. If still missing, ask the smallest neutral question about a specific episode: situation → goal → attempted action → what happened → outcome → workaround. Avoid leading respondents with proposed causes or features.
3. If reports conflict, deliberately seek the contrasting experience instead of averaging the disagreement away.
4. If the user wants a research plan, include recruitment / where to look, exact question or observation prompt, what each result would mean, and what it **cannot** establish. Be bounded, not performative.
5. After obtaining new information, **update** the pattern, mark changes and unresolved questions, and ask which other pattern to investigate. Do not pretend the new evidence validates a causal root problem unless it does.

## Choice rule

The next check must correspond to the unknown. A quick follow-up helps recover context; support records help see prior episodes; analytics can estimate observed frequency when instrumentation is suitable; watching a task can reveal interaction sequence; solution tests evaluate a proposed design. An interview alone cannot establish population prevalence. An upvote cannot validate a fix. “No further research needed” remains a valid answer if the unknown cannot change an immediate decision.
