---
id: hearthands-delegation
name: Hearthands Delegation
source: hearthands
description: Use when executing implementation plans with independent tasks in the current session - delegates work to specialized agents with reviewable handoffs, avoiding context pollution and outsourcing judgment
---

# Hearthands Delegation

Use this when executing implementation plans with independent tasks in the current session.

## Principle

Reviewable delegation is care. Delegate work in ways that preserve the ability to inspect, verify, and correct. Do not outsource judgment without leaving a trail the next worker can follow.

## Pattern

1. Read the plan once. Note global constraints and create todos.
2. Dispatch one agent per independent task. Give each agent focused scope, clear goal, constraints, and expected output.
3. Review each task before proceeding. Check spec compliance and code quality.
4. Fix issues before moving to the next task. Do not accumulate debt.
5. Track progress in a durable record that survives context loss.
6. After all tasks, perform a broad whole-branch review before handing off.

## Delegation Rules

- One agent per independent problem domain.
- Each agent gets exactly the context it needs — no more, no less.
- Do not hand over accumulated prior-task summaries into later dispatches.
- Answer agent questions before they proceed. Do not rush them into implementation.
- Do not dispatch multiple implementation agents in parallel when tasks share state.

## Review Rules

- Review after each task. Catch issues before they compound.
- A review reports two verdicts: spec compliance and code quality. Both are required.
- Fix issues before proceeding. Do not mark a task complete with open critical or important findings.
- The final whole-branch review checks the integrated result, not individual tasks in isolation.

## Guardrails

- Do not start implementation on main or master without explicit consent.
- Do not skip task reviews.
- Do not proceed with unfixed issues.
- Do not outsource judgment without leaving a reviewable record.
- Do not let a subagent's self-review replace actual review.

## Output

Per-task reports with commits, test results, and review verdicts. A final whole-branch review with any remaining findings and their resolution.
