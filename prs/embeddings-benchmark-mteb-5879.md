# embeddings-benchmark/mteb #5879: fix: filter cached results to the task's splits and subsets in evaluate

- **Status:** merged 2026-11-12 by @Samoed
- **Pull request:** https://github.com/embeddings-benchmark/mteb/pull/5879
- **Issue:** https://github.com/embeddings-benchmark/mteb/issues/5877
- **Size:** +85 / -2 in 2 files, 1 commit(s)

## Problem

`evaluate` returned cached results with splits and subsets the task did not ask for, and extra cached subsets changed aggregate scores.

## Fix

Filtered cached and merged results to the task's splits and subsets after saving, leaving the cache file intact.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`b14e1352`](https://github.com/embeddings-benchmark/mteb/pull/5879/commits/b14e135273567e2a30656eeb0dc01ae24f1e5568) | 2026-11-12 | MaiAditya | fix: filter cached results to the task's splits and subsets in evaluate |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>mteb/evaluate.py</code> | +10 | -2 |
| <code>tests/test&#95;evaluate.py</code> | +75 | -0 |
