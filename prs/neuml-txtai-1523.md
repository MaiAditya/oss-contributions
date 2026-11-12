# neuml/txtai #1523: Use each similar clause's own number of candidates when batching

- **Status:** merged 2026-11-06 by @davidmezzetti
- **Pull request:** https://github.com/neuml/txtai/pull/1523
- **Issue:** https://github.com/neuml/txtai/issues/1522
- **Size:** +33 / -8 in 2 files, 1 commit(s)

## Problem

In a batched query, a `similar()` clause without a candidate count borrowed the largest count of the other clauses, so batching changed its results.

## Fix

Made each `similar()` clause keep its own number of results when clauses are batched.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`a387e0ca`](https://github.com/neuml/txtai/pull/1523/commits/a387e0ca09a2272c8d34d5db34be6cec1866d4b1) | 2026-11-06 | MaiAditya | Use each similar clause's own number of candidates when batching |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/python/txtai/embeddings/search/scan.py</code> | +7 | -8 |
| <code>test/python/testembeddings.py</code> | +26 | -0 |
