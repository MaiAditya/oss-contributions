# neuml/txtai #1602: Return no results for a search limit of 0 with dense and hybrid indexes

- **Status:** in review (opened 2026-11-18)
- **Pull request:** https://github.com/neuml/txtai/pull/1602
- **Size:** +13 / -0 in 2 files, 2 commit(s)

## Problem

Searching a dense or hybrid index with `limit=0` failed because Faiss requires a limit of at least 1, unlike the keyword index.

## Fix

Returned an empty result per query in the Faiss ANN backend's `search` when the limit is 0, and added dense and hybrid tests.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`6c387971`](https://github.com/neuml/txtai/pull/1602/commits/6c3879713b960ef807d6acbd50cc26d0259d940a) | 2026-11-18 | MaiAditya | Return no results for a search limit of 0 with dense and hybrid indexes |
| [`9df49049`](https://github.com/neuml/txtai/pull/1602/commits/9df490491e59e948cb2a8b654f10738d6a4690b4) | 2026-11-18 | MaiAditya | Skip the Faiss search for a limit of 0 instead of guarding Search.search |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/python/txtai/ann/dense/faiss.py</code> | +4 | -0 |
| <code>test/python/testembeddings.py</code> | +9 | -0 |
