# Hearthands Rewrite Guide

## Purpose

This guide explains how to turn an upstream Superpowers skill into a Hearthands skill. The goal is replacement through care-oriented reframing, not cosmetic renaming.

## Rewrite Sequence

1. Identify the behavior the upstream skill protects.
2. Name the Hearthands principle behind that behavior.
3. Decide whether the behavior should be adopted, reframed, merged, rejected, or left pending.
4. Rewrite the trigger description so agents load the skill for the right situations.
5. Rewrite the body around care, sustainability, evidence, reversibility, and maintainer context.
6. Preserve tactical clarity: exact steps, guardrails, and output expectations.
7. Add historical grounding when it clarifies the practice.
8. Remove public Maxi-specific call sections; keep emoji call context in Maxi import playbooks.
9. Verify the skill has no private corpus quotes unless Max approved them.

## Skill Template

```markdown
---
id: hearthands-verification
name: Hearthands Verification
source: hearthands
description: Use when an agent is about to claim work is complete, fixed, passing, or ready to hand off
---

# Hearthands Verification

Use this when an agent is about to claim work is complete, fixed, passing, or ready to hand off.

## Principle

Evidence before confidence. Do not hand another person uncertainty disguised as completion.

## Pattern

1. Identify the exact claim the agent wants to make.
2. Run verification proportionate to the risk of that claim.
3. Read the output instead of trusting memory, intent, or another agent's report.
4. Report the evidence, including failures, skipped checks, and remaining uncertainty.

## Guardrails

- Do not say tests pass unless the relevant test command completed successfully.
- Do not hide skipped checks behind vague wording.
- Do not turn verification into ritual; match the check to the claim.

## Output

Name the command or inspection used, the result, and any residual risk.

## Lineage

Ground this in empirical software practice, test-first traditions, code review, operations handoff, and maintenance work.
```

## Rewrite Quality Bar

- The skill must change the agent's behavior, not just its vocabulary.
- The skill must be short enough to use and specific enough to constrain.
- The skill must name what care means in the situation.
- The skill must not turn care into vague niceness.
- The skill must preserve evidence, testing, and review where risk requires them.
- The skill must not quote private corpus material without explicit approval.

## Historical Grounding Prompts

Use these prompts when deciding what lineage to mention:

- Is this practice related to Agile, Adaptive Software Development, XP, Lean, DevOps, maintenance, operations, or code review traditions?
- Does historical grounding prevent the skill from sounding like a newly invented productivity slogan?
- Would a brief hat tip help future contributors understand why the skill exists?
- Is the lineage doing real explanatory work, or is it ornamental?

## Public/Private Boundary

The `.maxi/agent-history` corpus should shape the values, examples, and pressure scenarios. Public skills should paraphrase recurring patterns instead of exposing private transcript text.
