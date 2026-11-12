# confident-ai/deepeval #3644: fix: escape test data and reasons in the console report

- **Status:** in review (opened 2026-11-12)
- **Pull request:** https://github.com/confident-ai/deepeval/pull/3644
- **Issue:** https://github.com/confident-ai/deepeval/issues/3642
- **Size:** +217 / -22 in 4 files, 1 commit(s)

## Problem

Test data like `[/INST]` in inputs or reasons raised `MarkupError` in the console report after metrics ran, and text like `[red]x[/red]` was swallowed.

## Fix

Escaped user-derived text with `rich.markup.escape` in the console report, results table and prompt panels.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`9b4ef874`](https://github.com/confident-ai/deepeval/pull/3644/commits/9b4ef87441f692e657015070f1cb6dbaee39fe10) | 2026-11-12 | MaiAditya | fix: escape test data and reasons in the console report |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>deepeval/evaluate/console&#95;report.py</code> | +24 | -14 |
| <code>deepeval/test&#95;run/test&#95;run.py</code> | +11 | -8 |
| <code>tests/test&#95;core/test&#95;evaluation/test&#95;console&#95;report.py</code> | +86 | -0 |
| <code>tests/test&#95;core/test&#95;run/test&#95;results&#95;table&#95;markup.py</code> | +96 | -0 |
