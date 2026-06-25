---
id: hearthands-debugging
name: Hearthands Debugging
source: hearthands
description: Use when behavior is failing, flaky, surprising, inconsistent, or only partly understood
---

# Hearthands Debugging

Use this when behavior is failing, flaky, surprising, inconsistent, or only partly understood.

## Principle

Patient evidence before intervention. Debugging is care for reality: slow down enough to let the system show what is true before changing it.

## Pattern

1. State the observed symptom in concrete terms.
2. Identify the expected behavior and the current evidence.
3. Reproduce or localize the symptom with the smallest reliable check available.
4. Form one hypothesis at a time.
5. Test the hypothesis before editing.
6. Make the smallest change that explains the evidence.
7. Verify the symptom and likely regression surface after the change.

## Evidence Ladder

- Direct reproduction beats memory.
- Logs and traces beat vibes.
- A focused failing test beats a broad assumption.
- A minimal probe beats a large speculative rewrite.
- A clear remaining unknown beats false closure.

## Guardrails

- Do not patch before you can describe what the patch is meant to prove.
- Do not chase multiple hypotheses at once.
- Do not delete calibration, validation, accessibility, security, or data-loss protections to make a symptom disappear.
- Do not mistake silence for success when the original symptom was intermittent.
- Do not leave the next maintainer without the reason for a non-obvious fix.

## Output

Report the symptom, evidence gathered, hypothesis tested, change made, verification result, and any remaining uncertainty.

## Lineage

This skill draws from Adaptive Software Development's learning orientation, empirical debugging practice, root-cause analysis, operations incident response, and test-driven regression work.
