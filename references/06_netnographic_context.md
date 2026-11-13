---
name: netnographic-context
description: Analyse the social and cultural context of online community discourse without allowing popularity, repeated solutions, or inferred community roles to substitute for product-research evidence.
inherits: evidence-first-product-researcher
version: 0.11
---

# Netnographic Context

## Purpose

Analyse the online community as a social setting **separately from user-problem synthesis**.

This layer helps teams understand how discourse is formed, amplified, contested, and shaped by the channel.

## Questions this skill may answer

- Which narratives recur?
- Which values/norms appear important?
- Are people independently describing something or repeating a shared framing?
- Did a request spread from one thread/post?
- Are subgroups framing the same situation differently?
- Which voices appear to dominate the corpus, when that is actually evidenced?
- Which likely user groups are missing?
- Did discourse change after a release/event/incident?

## Team-framing boundary

Do not treat company/team narratives about the community as community narratives unless the corpus independently contains them.

Keep `team_hypothesis` and `team_assumption` separate.

## Hard boundary

Netnographic context must not independently generate a user-problem finding.

Example:

50 people repeat:
`"Add file upload."`

This skill may conclude:
- file upload is a salient request in this corpus;
- later messages repeat similar wording;
- the request appears socially amplified if linkage is visible.

It may **not** conclude:
- users cannot complete bug reports;
- users need file sharing;
- file upload is the right solution.

Those require experience evidence and/or additional research.

## Analyse

### Narrative formation

Track how recurring claims/solutions appear and spread.

### Independence and social linkage

Distinguish:
- apparently independent accounts;
- same-incident retellings;
- copied/reinforced framing;
- explicit coordination/campaigning;
- independence unknown.

Do not infer independence just from different authors.

### Community roles — provenance required

Only label someone as `moderator`, `guild leader`, `staff`, `expert`, `high-frequency contributor`, `high-status`, or `influential` when supported by:
- explicit role metadata;
- observed interaction structure in the corpus;
- self-description;
- clear repeated posting/reply patterns for `high-frequency contributor`.

Do not infer status/influence from eloquence, upvotes, confidence, or tone alone.

When influence is only suspected, label it as an interpretation and state the evidence.

### Norms and values

Identify recurring cultural meanings carefully, such as fairness, effort, legitimacy, trust, status, ownership, or community responsibility.

Keep them labeled as interpretations/context.

### Subgroups and disagreement

Retain disagreement instead of producing one “community opinion.”

Do not invent subgroup membership from language/tone. Require explicit metadata, self-description, or observable participation context.

### Temporal context

Where dates allow, inspect whether discourse changes after updates, incidents, policy changes, or community events.

## Output schema

```yaml
netnographic_context:
  recurring_narratives:
    - label: string
      supporting_message_ids: [string]
      interpretation: string
      linkage_status: apparently_independent|socially_linked|mixed|unknown
  norms_or_values:
    - interpretation: string
      evidence_ids: [string]
  amplification_signals: [string]
  contributor_roles:
    - participant_id: string
      role_or_pattern: string
      evidence_for_label: [string]
      certainty: explicit|observed_pattern|interpretive
  subgroup_differences:
    - description: string
      evidence_for_membership: string
  temporal_changes: [string]
  sampling_caveats: [string]
  research_leads:
    - signal: string
      why_worth_investigating: string
      can_support_user_problem: false
```

## Language

Prefer:
- “Within this corpus, a recurring narrative frames...”
- “This request appears socially amplified...”
- “Several posters repeat the same solution framing...”

Do not write:
- “Users need...”
- “The product problem is...”

unless primary evidence synthesis independently established it.
