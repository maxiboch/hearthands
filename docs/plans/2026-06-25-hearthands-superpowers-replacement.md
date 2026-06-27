# Hearthands Superpowers Replacement Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a grounded migration path for Hearthands to become a care-oriented replacement for Superpowers by extracting values from Max's agent-history corpus, mapping Superpowers skills to Hearthands principles, and rewriting accepted skills through that framework.

**Architecture:** Treat Superpowers as upstream inventory and Hearthands as a replacement lineage, not a cosmetic rename. Keep private corpus analysis separate from public skill text, then distill recurring values into public principles, skill mappings, and rewritten skill documents.

**Tech Stack:** Markdown docs, existing Hearthands skill repo structure, local shell tools (`find`, `rg`, `wc`, `sed`), Git for reviewable commits.

**North Star:** See `docs/goal.md` for the project goal statement that governs this roadmap.

## Global Constraints

- Do not quote private `.maxi/agent-history` material in public docs unless Max explicitly approves the exact excerpt.
- Preserve `hearthands` as the library/repo identity for care-oriented replacements.
- Treat Superpowers as source inventory until Hearthands has contextual equivalents for the relevant skill set.
- Each rewritten skill must be tactical enough for an agent to use: trigger, pattern, guardrails, and output expectations.
- Use historically grounded hat tips where they clarify lineage; do not make the framework ahistorical.
- Keep skill names install-safe: lowercase letters, numbers, and hyphens only.
- Public docs should not include visible `Maxi Emoji Call` sections; Maxi-specific emoji call context belongs in import/generated playbooks.

---

## File Structure

- Create: `docs/research/agent-history-corpus-map.md`
  - Records where the corpus lives, approximate size, file types, date range if discoverable, and privacy handling rules.
- Create: `docs/goal.md`
  - States the replacement goal and the commitments that guide Hearthands skill rewrites.
- Create: `docs/research/hearthands-values-map.md`
  - Distills recurring values, frustrations, preferred agent behaviors, writing style, code taste, and reusable metaphors from the corpus.
- Create: `docs/superpowers-map.md`
  - Maps each Superpowers skill to `adopt`, `reframe`, `merge`, `reject`, or `pending`, with the Hearthands principle that should govern it.
- Create: `docs/rewrite-guide.md`
  - Gives future agents a repeatable method for turning a Superpowers skill into a Hearthands skill.
- Create later: `skills/hearthands-verification/SKILL.md`
- Create later: `skills/hearthands-debugging/SKILL.md`
- Create later: `skills/hearthands-planning/SKILL.md`
  - Later tasks use these first-batch skills to establish the rewrite pattern.

## Task 1: Locate and Characterize the Agent-History Corpus

**Files:**
- Create: `docs/research/agent-history-corpus-map.md`

**Interfaces:**
- Consumes: local `.maxi/agent-history` corpus, wherever found.
- Produces: a stable corpus map that later tasks can cite without rediscovering paths.

- [ ] **Step 1: Locate likely corpus paths**

Run:

```bash
find "$HOME/.maxi" -maxdepth 4 -iname '*agent*history*' -print 2>/dev/null
find "/Users/mboch/Dev/maxi-tools" -maxdepth 5 -path '*/.maxi/*' -iname '*agent*history*' -print 2>/dev/null
```

Expected: one or more files or directories containing agent-history material. If the first command reports no paths, the second command should still complete without permission errors.

- [ ] **Step 2: Measure the corpus without reading it deeply**

Run each command with the discovered path substituted once by the implementer:

```bash
find "$HOME/.maxi" -maxdepth 4 -type f -iname '*agent*history*' -print 2>/dev/null | wc -l
find "$HOME/.maxi" -maxdepth 4 -type f -iname '*agent*history*' -print 2>/dev/null | xargs wc -c 2>/dev/null | tail -n 1
```

Expected: a file count and byte total, or zero if the corpus is stored under project-local `.maxi` paths instead of `$HOME/.maxi`.

- [ ] **Step 3: Write the corpus map**

Create `docs/research/agent-history-corpus-map.md` with this structure:

```markdown
# Agent History Corpus Map

## Purpose

This corpus is private field material for Hearthands. It is used to identify Max's values, code taste, agent frustrations, preferred metaphors, and writing style. Public Hearthands docs should distill from it rather than quote it directly.

## Located Paths

- `$HOME/.maxi/...`: record exact discovered paths and whether each is a file or directory.
- `/Users/mboch/Dev/maxi-tools/.../.maxi/...`: record exact discovered paths and whether each is a file or directory.

## Size Notes

- File count: record the measured count.
- Approximate bytes: record the measured total.
- Date range: record only if visible from filenames or metadata without expensive parsing.

## Privacy Rule

Do not copy private conversation text into public docs. Use paraphrase and distillation unless Max approves a specific quote.

## Extraction Targets

- Values Max repeatedly defends.
- Agent behaviors Max rejects.
- Code style and review preferences.
- Writing style and metaphor preferences.
- Repeated moments that should become Hearthands skills.
```

- [ ] **Step 4: Verify the doc has no accidental private excerpts**

Run:

```bash
rg -n 'User:|Assistant:|<message|BEGIN|turn_' docs/research/agent-history-corpus-map.md
```

Expected: no matches.

## Task 2: Extract Hearthands Values From the Corpus

**Files:**
- Create: `docs/research/hearthands-values-map.md`

**Interfaces:**
- Consumes: `docs/research/agent-history-corpus-map.md` and sampled local corpus files.
- Produces: named principles that future skill rewrites can cite.

- [ ] **Step 1: Sample the corpus in small batches**

Run:

```bash
rg -n -i 'care|maintain|verify|overclaim|certainty|small|boring|test|review|frustrat|loath|toxic|history|ground|metaphor|style|commit|attribution|emoji|maxi' "$HOME/.maxi" 2>/dev/null | head -n 200
```

Expected: up to 200 matching lines for local analysis. Do not paste raw lines into public docs.

- [ ] **Step 2: Group findings into values**

Create `docs/research/hearthands-values-map.md` with these sections:

```markdown
# Hearthands Values Map

## Purpose

This doc distills recurring values from Max's agent-history corpus into principles for Hearthands skills. It paraphrases private material rather than quoting it.

## Core Values

### Care Over Heroics

Agents should make software easier to continue, not perform competence through dramatic intervention.

### Evidence Before Confidence

Agents should verify before claiming completion, name uncertainty honestly, and avoid presenting guesses as facts.

### Smallest Responsible Ownership

Agents should avoid creating machinery someone has to maintain unless the burden is justified.

### Historical Grounding

Agents should place practices in their lineage when lineage matters, including Agile, Adaptive Software Development, XP, Lean, maintenance work, and care ethics.

### Reversibility and Containment

Agents should prefer changes that are easy to inspect, test, back out, and reason about.

### Taste Is Real Context

Agents should treat Max's writing style, code style, metaphors, and aesthetic objections as technical context rather than decoration.

## Rejected Agent Behaviors

- Overclaiming completion without evidence.
- Cosmetic rebrands without conceptual change.
- Process ceremony that does not reduce risk or burden.
- Needlessly broad rewrites.
- Flattening politics, identity, taste, or care into neutral-sounding productivity language.

## Writing Style Notes

- Direct, historically aware, emotionally precise.
- Warm without being saccharine.
- Vivid metaphors are welcome when they clarify behavior.
- Public docs should be useful first and charming second.

## Candidate Skill Families

- Hearthands: care loop, brainstorming, planning, verification, review, debugging.
- Hairflip: dusting and haircut for smallest responsible change.
- Future families: evidence, containment, handoff, maintenance, history, style.
```

- [ ] **Step 3: Verify the values map has no raw transcript markers**

Run:

```bash
rg -n 'User:|Assistant:|<message|BEGIN|turn_' docs/research/hearthands-values-map.md
```

Expected: no matches.

## Task 3: Build the Superpowers-to-Hearthands Map

**Files:**
- Create: `docs/superpowers-map.md`

**Interfaces:**
- Consumes: installed Superpowers skill inventory and `docs/research/hearthands-values-map.md`.
- Produces: a migration map used to prioritize rewrites.

- [ ] **Step 1: Inventory installed Superpowers skills**

Run:

```bash
find "$HOME/.codex/skills" -maxdepth 2 -name SKILL.md -print | sort
```

Expected: paths for installed skills including Superpowers-derived skills.

- [ ] **Step 2: Extract skill ids and descriptions**

Run:

```bash
for f in "$HOME"/.codex/skills/*/SKILL.md; do printf '\n## %s\n' "$f"; sed -n '1,8p' "$f"; done
```

Expected: frontmatter snippets for each installed skill.

- [ ] **Step 3: Create the migration map**

Create `docs/superpowers-map.md` with this structure and initial entries:

```markdown
# Superpowers to Hearthands Map

## Purpose

This map tracks how Hearthands replaces Superpowers through care-oriented equivalents. Superpowers remains upstream inventory until each relevant behavior has a Hearthands-contextual skill.

## Status Labels

- `adopt`: keep the behavior with light Hearthands framing.
- `reframe`: rewrite the skill from a Hearthands principle.
- `merge`: combine several Superpowers skills into one Hearthands skill.
- `reject`: do not carry forward because it conflicts with the framework or is not useful here.
- `pending`: needs more corpus review or user judgment.

## Map

| Superpowers Skill | Status | Hearthands Equivalent | Governing Principle | Notes |
| --- | --- | --- | --- | --- |
| brainstorming | reframe | hearthands-brainstorming | shared sensemaking before ownership | Existing draft should be expanded from values map. |
| writing-plans | reframe | hearthands-planning | care through clear handoff | Keep tactical rigor, remove hostile/performative tone. |
| verification-before-completion | reframe | hearthands-verification | evidence before confidence | Strong candidate for early rewrite. |
| systematic-debugging | reframe | hearthands-debugging | patient evidence before intervention | Preserve root-cause discipline. |
| requesting-code-review | reframe | hearthands-review-request | care for the next reader | Align with review as stewardship. |
| receiving-code-review | reframe | hearthands-review-response | humility and evidence | Preserve technical rigor without performative agreement. |
| using-git-worktrees | reframe | hearthands-containment | reversibility and containment | Treat worktrees as care for shared state. |
| writing-skills | reframe | hearthands-skillwriting | durable care instructions | Needed before broad rewrite. |
| dispatching-parallel-agents | pending | hearthands-parallel-care | parallel work without context loss | Needs judgment about sustainability. |
| test-driven-development | reframe | hearthands-small-promises | witnessed behavior before trust | Translate TDD into care language. |
```

- [ ] **Step 4: Check that every mapped equivalent has an action**

Run:

```bash
rg -n '\| pending \||\| reframe \||\| adopt \||\| merge \||\| reject \|' docs/superpowers-map.md
```

Expected: each row has one of the five status labels.

## Task 4: Write the Hearthands Rewrite Guide

**Files:**
- Create: `docs/rewrite-guide.md`

**Interfaces:**
- Consumes: `docs/research/hearthands-values-map.md` and `docs/superpowers-map.md`.
- Produces: repeatable instructions for rewriting each skill.

- [ ] **Step 1: Create the guide**

Create `docs/rewrite-guide.md` with this structure:

```markdown
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
7. Add historical grounding when it clarifies the practice.
8. Remove public Maxi-specific call sections; keep emoji call context in Maxi import playbooks.
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

1. Identify the claim the agent wants to make.
2. Run verification proportionate to the risk of that claim.
3. Report the evidence, including failures, skipped checks, and remaining uncertainty.

## Guardrails

- Do not say tests pass unless the relevant test command completed successfully.
- Do not hide skipped checks behind vague wording.

## Output

Name the command or inspection used, the result, and any residual risk.

No Lineage section — history belongs in the README.
```

## Rewrite Quality Bar

- The skill must change the agent's behavior, not just its vocabulary.
- The skill must be short enough to use and specific enough to constrain.
- The skill must name what care means in the situation.
- The skill must not turn care into vague niceness.
- The skill must preserve evidence, testing, and review where risk requires them.
```

- [ ] **Step 2: Verify the guide avoids placeholder language**

Run:

```bash
rg -n 'TBD|TODO|implement later|fill in details|appropriate error handling|similar to Task' docs/rewrite-guide.md
```

Expected: no matches.

## Task 5: Choose the First Rewrite Batch

**Files:**
- Modify: `docs/superpowers-map.md`
- Create later: `skills/hearthands-verification/SKILL.md`, `skills/hearthands-debugging/SKILL.md`, `skills/hearthands-planning/SKILL.md`

**Interfaces:**
- Consumes: `docs/superpowers-map.md`.
- Produces: a prioritized first batch of rewritten skills.

- [ ] **Step 1: Add a first-batch section to the map**

Append this section to `docs/superpowers-map.md`:

```markdown
## First Rewrite Batch

1. `hearthands-verification`: evidence before confidence.
2. `hearthands-debugging`: patient evidence before intervention.
3. `hearthands-planning`: clear handoff as care.

These are first because they affect agent honesty, risk, and handoff quality across nearly every development task.
```

- [ ] **Step 2: Verify the batch references mapped equivalents**

Run:

```bash
rg -n 'hearthands-verification|hearthands-debugging|hearthands-planning' docs/superpowers-map.md
```

Expected: matches in both the map table and the first-batch section.

## Task 6: Review and Commit the Plan Artifacts

**Files:**
- Review: `docs/research/agent-history-corpus-map.md`
- Review: `docs/research/hearthands-values-map.md`
- Review: `docs/superpowers-map.md`
- Review: `docs/rewrite-guide.md`

**Interfaces:**
- Consumes: all plan artifacts.
- Produces: a clean commit with the Hearthands replacement framework.

- [ ] **Step 1: Run final scans**

Run:

```bash
rg -n 'Maxi Emoji Call|Maxi-world call|TBD|TODO|User:|Assistant:|<message|turn_' docs skills
```

Expected: no matches in public docs unless the match is inside this implementation plan documenting the forbidden strings.

- [ ] **Step 2: Check git status**

Run:

```bash
git status --short
```

Expected: only intentional Hearthands docs and skill edits are listed.

- [ ] **Step 3: Commit with a simple message**

Run:

```bash
git add docs skills README.md AGENTS.md .codex-plugin/plugin.json gemini-extension.json opencode.json
git commit -m "Plan Hearthands replacement"
```

Expected: one commit with no co-author trailers or AI attribution.

## Self-Review

- Spec coverage: The plan covers corpus mapping, values extraction, Superpowers skill mapping, rewrite guidance, first rewrite batch selection, and verification.
- Placeholder scan: The remaining literal placeholder-warning strings appear only inside verification commands that future agents should run against generated docs.
- Type consistency: The core docs referenced across tasks use stable paths: `docs/research/agent-history-corpus-map.md`, `docs/research/hearthands-values-map.md`, `docs/superpowers-map.md`, and `docs/rewrite-guide.md`.
