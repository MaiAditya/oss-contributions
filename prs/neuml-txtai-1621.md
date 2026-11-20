# neuml/txtai #1621: Create function tools from docstrings when smolagents rejects their type hints

- **Status:** in review (opened 2026-11-20)
- **Pull request:** https://github.com/neuml/txtai/pull/1621
- **Issue:** https://github.com/neuml/txtai/issues/1620
- **Size:** +32 / -1 in 2 files, 1 commit(s)

## Problem

Passing a function without type hints, or without a return hint, in agent `tools` raised a `TypeHintParsingException` instead of building the tool from its docstring.

## Fix

Caught the `smolagents` exception in `ToolFactory.createtool` so the docstring fallback runs, and added tests.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`ace2d903`](https://github.com/neuml/txtai/pull/1621/commits/ace2d9033edcc44002d2df1a27a940e8c02361c1) | 2026-11-20 | MaiAditya | Create function tools from docstrings when smolagents rejects their type hints, closes &#35;1620 |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/python/txtai/agent/tool/factory.py</code> | +2 | -1 |
| <code>test/python/testagent.py</code> | +30 | -0 |
