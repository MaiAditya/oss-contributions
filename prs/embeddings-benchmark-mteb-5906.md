# embeddings-benchmark/mteb #5906: fix: keep run&#95;settings of cached subsets when resuming an evaluation

- **Status:** merged 2026-11-17 by @Samoed
- **Pull request:** https://github.com/embeddings-benchmark/mteb/pull/5906
- **Size:** +76 / -7 in 3 files, 2 commit(s)

## Problem

Resuming an evaluation rewrote `run_settings.jsonl` for subsets loaded from the cache with the current run's `encode_kwargs` and package versions.

## Fix

Added an `evaluated_splits` argument to `save_to_cache` so only subsets that were actually run get run settings.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`1f37c6f1`](https://github.com/embeddings-benchmark/mteb/pull/5906/commits/1f37c6f1f23338bb076ea82aa42ec24c5d0d4b77) | 2026-11-17 | MaiAditya | fix: keep run&#95;settings of cached subsets when resuming an evaluation |
| [`523e1331`](https://github.com/embeddings-benchmark/mteb/pull/5906/commits/523e133185cb593d18a5f436da4f878a24c20081) | 2026-11-17 | Samoed | update |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>mteb/cache/result&#95;cache.py</code> | +12 | -6 |
| <code>mteb/evaluate.py</code> | +8 | -1 |
| <code>tests/test&#95;run&#95;settings&#95;jsonl.py</code> | +56 | -0 |
