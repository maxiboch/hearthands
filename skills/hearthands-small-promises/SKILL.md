---
id: hearthands-small-promises
name: Hearthands Small Promises
source: hearthands
description: Use when implementing any feature or bugfix, before writing implementation code - writes a failing test first, watches it fail, writes minimal code, and refactors, treating each test as a promise to the next maintainer
---

# Hearthands Small Promises

Use this when implementing any feature or bugfix, before writing implementation code.

## Principle

Witnessed behavior before trust. A test you watched fail is a promise to the next maintainer that the code does what you claim. A test you wrote after the code is a wish, not evidence.

## Pattern

1. Write one minimal test for one behavior.
2. Run it. Confirm it fails for the expected reason.
3. Write the simplest code that passes the test.
4. Run it. Confirm it passes. Confirm other tests still pass.
5. Refactor only after green: remove duplication, improve names, extract helpers.
6. Repeat for the next behavior.

## The Iron Law

```
NO PRODUCTION CODE WITHOUT A FAILING TEST FIRST
```

Write code before the test? Delete it. Start over.

**No exceptions:**
- Don't keep it as "reference."
- Don't "adapt" it while writing tests.
- Don't look at it.
- Delete means delete.

## Guardrails

- Do not skip the "watch it fail" step. A passing test proves nothing.
- Do not add features, refactor other code, or "improve" beyond the test during the green phase.
- Do not treat tests-after as equivalent. Tests-after answer "what does this do?" Tests-first answer "what should this do?"
- Do not rationalize with "spirit not ritual." Violating the letter is violating the spirit.
- Do not leave mocks in place that hide the behavior you promised to test.

## Output

Each cycle produces a passing test, minimal production code, and a clean refactor. Before claiming the work is done, verify every new behavior has a test that failed first.

## Lineage

This skill draws from Extreme Programming, test-first development, and the maintenance understanding that untested code is a debt someone else will pay. TDD is not dogma; it is the cheapest way to build trust with the person who reads your code next.
