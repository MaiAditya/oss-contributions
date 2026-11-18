# neuml/txtai #1579: Use the SQL LIMIT clause when slicing merged Cluster results

- **Status:** merged 2026-11-17 by @davidmezzetti
- **Pull request:** https://github.com/neuml/txtai/pull/1579
- **Issue:** https://github.com/neuml/txtai/issues/1578
- **Size:** +48 / -3 in 3 files, 2 commit(s)

## Problem

`Cluster.search` and `batchsearch` ignored a query's SQL `LIMIT` when merging shard results, so `limit 20` returned 10 rows and `limit 2` returned one batch per shard.

## Fix

Added `Cluster.limit` to slice merged results by the query's `LIMIT`, falling back to the request limit.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`3e232e17`](https://github.com/neuml/txtai/pull/1579/commits/3e232e17d393b9a06890cde8e21d3a849ff2d53a) | 2026-11-16 | MaiAditya | Fix Cluster search and batchsearch ignoring SQL LIMIT clause |
| [`93784b80`](https://github.com/neuml/txtai/pull/1579/commits/93784b8094a1ff2d6482b63079abbec7ab50ba17) | 2026-11-17 | davidmezzetti | Update build.yml |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>.github/workflows/build.yml</code> | +2 | -0 |
| <code>src/python/txtai/api/cluster.py</code> | +19 | -3 |
| <code>test/python/testapi/testcluster.py</code> | +27 | -0 |
