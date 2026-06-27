---
id: hearthands-review
name: Hearthands Review
source: hearthands
description: Use when completing tasks, implementing major features, receiving code review feedback, or before merging - review as stewardship, technical rigor over social comfort, evidence over performative agreement
---

# Hearthands Review

Use this when completing tasks, implementing major features, receiving code review feedback, or before merging.

## Principle

Review is stewardship, not theater. Both the reviewer and the reviewed serve the same person: the next maintainer who has to understand, trust, and extend the work. Technical correctness matters more than social comfort.

## Requesting Review

Request review when:
- After each task in a sequence
- After completing a major feature
- Before merging to main
- When stuck and need a fresh perspective
- Before refactoring, to establish a baseline
- After fixing a complex bug

Dispatch a reviewer with precise context: what was built, what it should do, and the diff range. Never hand over your session history. The reviewer should evaluate the work product, not your thought process.

## Receiving Feedback

Read complete feedback before reacting. Restate the technical requirement in your own words. Verify each item against the codebase before implementing. If feedback is unclear, stop and ask for clarification before touching anything.

## Response Rules

**Forbidden responses:**
- Performative agreement ("You're absolutely right!", "Great point!")
- Blind implementation before verification
- Gratitude expressions that replace action

**Required responses:**
- Restate the technical requirement or just act.
- Push back with technical reasoning when the feedback is wrong.
- Fix items one at a time, test each, verify no regressions.

## Pushback

Push back when:
- The suggestion breaks existing functionality
- The reviewer lacks full context
- It violates YAGNI (unused feature)
- It is technically incorrect for this stack
- Legacy or compatibility reasons exist
- It conflicts with prior architectural decisions

Push back with technical reasoning, not defensiveness. Reference working tests and code. If you pushed back and were wrong, state the correction factually and move on.

## Guardrails

- Do not skip review because "it's simple."
- Do not hide uncertainty behind cheerful closure.
- Do not treat external feedback as orders; evaluate it as suggestions.
- Do not batch fixes without testing each one.
- Do not leave the next maintainer without the reason for a non-obvious change.

## Output

Name the review performed, the issues found and fixed, any pushback with reasoning, the verification result, and any residual risk.

## Lineage

This skill draws from code review practice, operations handoff, and the understanding that review is a social act with technical content. The goal is not to win or lose; it is to leave code that the next person can trust.
