# neuml/txtai #1624: Use the configured name and description for typed function tools

- **Status:** merged 2026-11-21 by @davidmezzetti
- **Pull request:** https://github.com/neuml/txtai/pull/1624
- **Issue:** https://github.com/neuml/txtai/issues/1623
- **Size:** +33 / -2 in 2 files, 1 commit(s)

## Problem

A function tool with full type hints ignored the `name` and `description` from its dictionary configuration, so the agent saw the function name and docstring instead.

## Fix

Set the configured `name` and `description` on tools built by `smolagents.tool`, keeping the function values if unset.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`2dd653bc`](https://github.com/neuml/txtai/pull/1624/commits/2dd653bcb9058b64ac5ef29e2e700c9295a8cc22) | 2026-11-20 | MaiAditya | Use the configured name and description for typed function tools |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/python/txtai/agent/tool/factory.py</code> | +10 | -2 |
| <code>test/python/testagent.py</code> | +23 | -0 |
