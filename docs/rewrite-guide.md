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
7. Remove all historical grounding from the skill body — that content belongs in the project README.
8. Remove any Maxi-specific tool cues (emoji call syntax, Maxi import playbook references, platform-specific dispatch instructions). Those belong in the Maxi world layer that manages and imports skills.
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

No Lineage section. History belongs in the README.
```

## Rewrite Quality Bar

- The skill must change the agent's behavior, not just its vocabulary.
- The skill must be short enough to use and specific enough to constrain.
- The skill must name what care means in the situation.
- The skill must not turn care into vague niceness.
- The skill must preserve evidence, testing, and review where risk requires them.
- The skill must not quote private corpus material without explicit approval.
- The skill must not contain a Lineage section. History belongs in the README.
- The skill must not contain Maxi-specific tool cues. Those belong in the Maxi world layer.

## Historical Grounding Policy

Do not include history in skill files. Skills are tactical guidance for agents. History is context for humans.

Historical grounding belongs in the project README under a "Skill Lineage" or "Historical Grounding" section. The README can map each skill family to its tradition: Agile, Adaptive Software Development, XP, Lean, maintenance work, care ethics, etc.

When rewriting a skill, ask: "Does this lineage help an agent follow the skill right now?" If the answer is no, it belongs in the README.

## Maxi Tool Cues Policy

Do not include Maxi-specific tool cues in skill files. This includes:

- Emoji call syntax (e.g., `📁📖`, `⚡▶️`, `🌿📊`)
- Maxi import playbook references
- Platform-specific dispatch instructions
- References to Maxi-specific concepts like "category", "emoji flags", "corner brackets"

These cues belong in the Maxi world layer that manages and imports skills, not in the skill repos themselves.

## Public/Private Boundary

The `.maxi/agent-history` corpus should shape the values, examples, and pressure scenarios. Public skills should paraphrase recurring patterns instead of exposing private transcript text.
