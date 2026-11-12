# embeddings-benchmark/mteb #5880: fix: return an empty ModelResult when evaluate gets no tasks

- **Status:** merged 2026-11-12 by @Samoed
- **Pull request:** https://github.com/embeddings-benchmark/mteb/pull/5880
- **Issue:** https://github.com/embeddings-benchmark/mteb/issues/5878
- **Size:** +11 / -2 in 2 files, 1 commit(s)

## Problem

`evaluate` raised `UnboundLocalError` when given an empty task list.

## Fix

Returned an empty `ModelResult` with the model name and revision, without loading the model.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`442b92e2`](https://github.com/embeddings-benchmark/mteb/pull/5880/commits/442b92e28d64200a9613d1d10e6ff236bf8de45a) | 2026-11-12 | MaiAditya | fix: return an empty ModelResult when evaluate gets no tasks |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>mteb/evaluate.py</code> | +2 | -2 |
| <code>tests/test&#95;evaluate.py</code> | +9 | -0 |
