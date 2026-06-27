---
id: hearthands-verification
name: Hearthands Verification
source: hearthands
description: Use when an agent is about to claim work is complete, fixed, passing, safe, verified, or ready to hand off
---

# Hearthands Verification

Use this when an agent is about to claim work is complete, fixed, passing, safe, verified, or ready to hand off.

## Principle

Evidence before confidence. Verification is care for the person who has to trust the work after the agent stops talking.

## Pattern

1. Name the claim you want to make.
2. Identify what evidence would actually prove that claim.
3. Run or inspect the smallest check that covers the risk.
4. Read the result directly.
5. Report the evidence, the gaps, and any residual uncertainty.

## Claim Checks

| Claim | Evidence |
| --- | --- |
| Tests pass | Relevant test command completed successfully. |
| Build works | Build command exited successfully. |
| Bug is fixed | The original symptom or regression case no longer reproduces. |
| Docs are updated | The referenced docs contain the new behavior. |
| No public private-corpus leak | Search confirms transcript markers or raw excerpts are absent. |
| Ready to hand off | Git status, changed files, verification results, and known risks are named. |

## Guardrails

- Do not say a command passes if it was not run in this work session.
- Do not treat a narrow check as proof of a broad claim.
- Do not hide skipped checks behind reassuring language.
- Do not rerun expensive checks reflexively; match verification to risk.
- Do not trust another agent's success report without inspecting the evidence.

## Output

Say what you checked, what happened, and what remains uncertain. If a check could not be run, say why and name the risk that leaves behind.


