# Superpowers to Hearthands Map

## Purpose

This map tracks how Hearthands replaces Superpowers through care-oriented equivalents. Superpowers remains useful upstream inventory until each relevant behavior has a Hearthands-contextual skill.

## Status Labels

- `adopt`: keep the behavior with light Hearthands framing.
- `reframe`: rewrite the skill from a Hearthands principle.
- `merge`: combine several upstream skills into one Hearthands skill.
- `reject`: do not carry forward because it conflicts with the framework or is not useful here.
- `pending`: needs more corpus review or user judgment.

## Map

| Superpowers Skill | Status | Hearthands Equivalent | Governing Principle | Notes |
| --- | --- | --- | --- | --- |
| brainstorming | reframe | hearthands-brainstorming | shared sensemaking before ownership | Existing draft should be expanded from the values map. |
| writing-plans | reframe | hearthands-planning | clear handoff as care | Preserve tactical rigor while removing hostile or performative tone. |
| verification-before-completion | reframe | hearthands-verification | evidence before confidence | First-batch rewrite. |
| systematic-debugging | reframe | hearthands-debugging | patient evidence before intervention | First-batch rewrite. |
| requesting-code-review | merge | hearthands-review | care for the next reader | Merge with receiving-code-review. First batch complete. |
| receiving-code-review | merge | hearthands-review | humility with evidence | Merge with requesting-code-review. First batch complete. |
| using-git-worktrees | reframe | hearthands-containment | reversibility and containment | Treat isolated workspaces as care for shared state. Complete. |
| writing-skills | reframe | hearthands-skillwriting | durable care instructions | Needed before broad replacement. Pending. |
| dispatching-parallel-agents | pending | hearthands-parallel-care | coordination without context loss | Needs corpus review around sustainability and fragmentation. |
| subagent-driven-development | pending | hearthands-delegation | reviewable delegation | Needs careful framing to avoid outsourcing judgment. |
| executing-plans | reframe | hearthands-execution | steady follow-through | Should pair with planning and verification. Complete. |
| test-driven-development | reframe | hearthands-small-promises | witnessed behavior before trust | Translate TDD into care language without losing discipline. Complete. |
| finishing-a-development-branch | reframe | hearthands-handoff | leave the branch understandable | Connect integration choices to shared maintenance. Complete. |

## Completed Skills

### First Rewrite Batch

1. `hearthands-verification`: evidence before confidence.
2. `hearthands-debugging`: patient evidence before intervention.
3. `hearthands-planning`: clear handoff as care.

These are first because they affect agent honesty, risk, and handoff quality across nearly every development workflow.

### Second Rewrite Batch

1. `hearthands-execution`: steady follow-through with care.
2. `hearthands-handoff`: leave the branch understandable.
3. `hearthands-containment`: reversibility and containment.
4. `hearthands-small-promises`: witnessed behavior before trust.
5. `hearthands-review`: care for the next reader.

## Remaining Work

- `hearthands-skillwriting`: durable care instructions (from `writing-skills`).
- `hearthands-parallel-care`: coordination without context loss (from `dispatching-parallel-agents`).
- `hearthands-delegation`: reviewable delegation (from `subagent-driven-development`).

## Open Questions

- Which Superpowers skills should be rejected rather than reframed?
- Which skills belong as standalone Hearthands skills, and which should become sections inside larger skills?
- How much public historical grounding belongs in each skill versus in a shared background document?
- Which repeated moments from `.maxi/agent-history` deserve their own pressure scenarios?
