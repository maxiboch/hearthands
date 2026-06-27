---
id: hearthands-parallel-care
name: Hearthands Parallel Care
source: hearthands
description: Use when facing 2+ independent tasks that can be worked on without shared state or sequential dependencies - coordinates parallel work without context loss or fragmentation
---

# Hearthands Parallel Care

Use this when facing multiple independent tasks that can run without shared state or sequential dependencies.

## Principle

Coordination without context loss. Parallel work is care when it does not fragment the project, lose context between agents, or create cleanup burden that outweighs the time saved.

## Pattern

1. Identify independent problem domains. Group failures or tasks by what is broken or needed.
2. Confirm no shared state between domains. If fixing one would affect another, keep them sequential.
3. Create focused tasks. Each task gets specific scope, clear goal, constraints, and expected output.
4. Dispatch tasks in parallel. Issue all dispatches in the same context so they run concurrently.
5. Review and integrate. Read each result, verify fixes do not conflict, run the full test suite, then integrate.

## When to Use

- Multiple test files failing with different root causes.
- Multiple subsystems broken independently.
- Each problem can be understood without context from others.
- No shared state between investigations.

## When NOT to Use

- Failures are related (fixing one might fix others).
- Need to understand full system state.
- Agents would interfere with each other.
- Exploratory debugging where the full picture is not yet known.

## Guardrails

- Do not dispatch parallel tasks when failures share state or root cause.
- Do not hand over accumulated prior-task summaries into later dispatches.
- Do not skip the integration review. Parallel fixes can conflict in subtle ways.
- Do not treat parallel work as free. Each agent burns context and creates integration surface.

## Output

Summaries from each parallel task, integration check results, and any conflicts resolved or deferred.
