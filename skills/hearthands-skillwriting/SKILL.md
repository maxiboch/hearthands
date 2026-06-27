---
id: hearthands-skillwriting
name: Hearthands Skillwriting
source: hearthands
description: Use when creating new skills, editing existing skills, or verifying skills work before deployment - treats skill creation as test-driven process documentation
---

# Hearthands Skillwriting

Use this when creating new skills, editing existing skills, or verifying skills work before deployment.

## Principle

Writing skills is test-driven development applied to process documentation. If you did not watch an agent fail without the skill, you do not know if the skill teaches the right thing.

## Pattern

1. Run a baseline scenario without the skill. Document what the agent does.
2. Write a minimal skill that addresses those specific failures.
3. Run the same scenario with the skill. Verify the agent now complies.
4. Close loopholes: find new rationalizations, add explicit counters, re-verify.
5. Deploy only after the skill passes its own tests.

## Skill Quality Bar

- The skill must change the agent's behavior, not just its vocabulary.
- The skill must be short enough to use and specific enough to constrain.
- The skill must name what care means in the situation.
- The skill must not turn care into vague niceness.
- The skill must preserve evidence, testing, and review where risk requires them.

## Description Rules

The description field is the discovery path. Future agents read it to decide whether to load the skill.

- Start with "Use when..." to focus on triggering conditions.
- Describe the problem, not the solution.
- Never summarize the skill's process or workflow in the description.
- Keep it under 500 characters if possible.

## Structure

```
skill-name/
  SKILL.md    # Main reference (required)
  supporting-file.*     # Only if needed
```

Keep principles and concepts inline. Move heavy reference material to separate files only when it exceeds the inline threshold.

## Guardrails

- Do not write the skill before watching a baseline failure.
- Do not deploy untested skills.
- Do not batch creation — test each skill before moving to the next.
- Do not quote private corpus material without explicit approval.

## Output

A tested skill that changes agent behavior under the pressures it was designed to address, with documented baseline failures and closed loopholes.
