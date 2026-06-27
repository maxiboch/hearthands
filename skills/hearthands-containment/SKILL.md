---
id: hearthands-containment
name: Hearthands Containment
source: hearthands
description: Use when starting feature work that needs isolation from current workspace, or before executing implementation plans - ensures an isolated workspace exists via native tools or git worktree fallback, treating containment as care for shared state
---

# Hearthands Containment

Use this when starting feature work that needs isolation from current workspace, or before executing implementation plans.

## Principle

Reversibility and containment are care for shared state. An isolated workspace protects the main branch from experiment, lets the next worker continue without interference, and makes mistakes easy to inspect and reverse.

## Pattern

1. Detect existing isolation before creating anything.
2. If already isolated: report state and skip creation.
3. If not isolated: ask for consent before creating a worktree.
4. Prefer native worktree tools over manual git worktrees.
5. Verify the worktree directory is ignored before creating.
6. Run project setup and baseline tests in the new workspace.
7. Report ready state with path, branch, and test results.

## Detection

```bash
GIT_DIR=$(cd "$(git rev-parse --git-dir 2>/dev/null)" 2>/dev/null && pwd -P)
GIT_COMMON=$(cd "$(git rev-parse --git-common-dir 2>/dev/null)" 2>/dev/null && pwd -P)
BRANCH=$(git branch --show-current)
```

- `GIT_DIR` is non-empty and `GIT_DIR != GIT_COMMON` (and not a submodule): already in a linked worktree.
- `GIT_DIR` is empty or `GIT_DIR == GIT_COMMON` or in a submodule: normal repo checkout.

## Creation Priority

1. Native worktree tool (preferred).
2. Git worktree fallback (only if no native tool).
3. Project-local directory: `.worktrees/` preferred over `worktrees/`.
4. Always verify directory is ignored before creating.

## Guardrails

- Do not create a worktree when detection finds existing isolation.
- Do not use `git worktree add` when a native worktree tool is available.
- Do not skip ignore verification for project-local directories.
- Do not proceed with failing baseline tests without asking.
- Do not leave the next maintainer without context about the workspace choice.

## Output

Report the workspace path, branch name, whether it was newly created or detected, baseline test results, and any sandbox fallback taken.


