# embeddings-benchmark/mteb #5929: fix: don't consume iterator models/tasks in ResultCache.load&#95;results and get&#95;cache&#95;paths

- **Status:** merged 2026-11-18 by @Samoed
- **Pull request:** https://github.com/embeddings-benchmark/mteb/pull/5929
- **Size:** +63 / -7 in 2 files, 2 commit(s)

## Problem

`ResultCache.load_results` and `get_cache_paths` consumed generators and iterators by peeking at the first item, so models were dropped, and empty `models` or `tasks` raised `StopIteration` or `IndexError`.

## Fix

Materialized `models` and `tasks` into lists once at entry so iterators and empty inputs work.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`dc124db4`](https://github.com/embeddings-benchmark/mteb/pull/5929/commits/dc124db4aeca0289ab1eaa97e99ee0ac3b45e72c) | 2026-11-18 | MaiAditya | fix: don't consume iterator models/tasks in ResultCache.load&#95;results and get&#95;cache&#95;paths |
| [`bf583c92`](https://github.com/embeddings-benchmark/mteb/pull/5929/commits/bf583c92a4ef0f5631b0c197455e5f6bcac3351c) | 2026-11-18 | Samoed | improve tests |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>mteb/cache/result&#95;cache.py</code> | +25 | -7 |
| <code>tests/test&#95;result&#95;cache.py</code> | +38 | -0 |
