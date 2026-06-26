---
id: hearthands-execution
name: Hearthands Execution
source: hearthands
description: Use when you have a written implementation plan to execute with review checkpoints, and need to balance steady follow-through with care for the work and its maintainers
---

# Hearthands Execution

Use this when you have a written implementation plan to execute in a separate session with review checkpoints.

## Principle

Steady follow-through is care. Execute the plan as a living document, not a script. Verify at each step, raise concerns early, and leave the project easier to continue than you found it.

## Pattern

1. Load the plan and read it critically before touching code.
2. Raise concerns with your human partner before starting if the plan has gaps, contradictions, or hidden risk.
3. Create todos for the plan items and proceed only when aligned.
4. For each task: mark in_progress, follow the steps, run verifications, mark completed.
5. When blocked: stop immediately. Do not guess. Ask for clarification.
6. When the plan changes: return to review, update todos, then continue.
7. When all tasks complete: hand off using `hearthands-handoff`.

## Guardrails

- Do not skip verifications because the step feels obvious.
- Do not force through blockers to preserve momentum.
- Do not start implementation on main or master without explicit consent.
- Do not treat the plan as immutable; if reality contradicts it, say so.
- Do not leave the next maintainer without context about why a step was skipped or altered.

## Output

Report progress against the plan, name any deviations with reasons, and hand off with verification results and known risks.

## Lineage

This skill draws from Agile iteration, Adaptive Software Development's learning orientation, release engineering, and maintenance handoff practice. Execution is not blind marching; it is careful follow-through with room to correct course.
