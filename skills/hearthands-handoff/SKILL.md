---
id: hearthands-handoff
name: Hearthands Handoff
source: hearthands
description: Use when implementation is complete, all tests pass, and you need to decide how to integrate the work - presents structured options for merge, PR, or cleanup as care for the next maintainer
---

# Hearthands Handoff

Use this when implementation is complete, all tests pass, and you need to decide how to integrate the work.

## Principle

Clear handoff is care. Present the next worker with honest options, verified state, and a workspace they can trust.

## Pattern

1. Verify tests pass before presenting options.
2. Detect workspace state: normal repo, named-branch worktree, or detached HEAD.
3. Determine the base branch.
4. Present exactly the options that match the workspace state.
5. Execute the chosen option without deviating.
6. Clean up only the workspaces you created.

## Options

### Normal repo or named-branch worktree

1. Merge back to `<base-branch>` locally
2. Push and create a Pull Request
3. Keep the branch as-is (I'll handle it later)
4. Discard this work

### Detached HEAD

1. Push as new branch and create a Pull Request
2. Keep as-is (I'll handle it later)
3. Discard this work

## Guardrails

- Do not proceed with failing tests.
- Do not merge without verifying tests on the merged result.
- Do not delete work without explicit typed confirmation.
- Do not clean up a worktree you did not create.
- Do not remove a worktree before confirming merge success.
- Do not run `git worktree remove` from inside the worktree being removed.

## Output

Name the chosen path, the verification performed, the cleanup taken, and any residual risk the next maintainer should know about.

## Lineage

This skill draws from release engineering, Git workflow discipline, maintenance handoff, and the understanding that integration is a social act as much as a technical one.
