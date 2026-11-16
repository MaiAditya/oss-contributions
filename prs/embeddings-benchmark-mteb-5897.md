# embeddings-benchmark/mteb #5897: fix: skip queries without reranking candidates

- **Status:** in review (opened 2026-11-16)
- **Pull request:** https://github.com/embeddings-benchmark/mteb/pull/5897
- **Issue:** https://github.com/embeddings-benchmark/mteb/issues/5896
- **Size:** +42 / -2 in 2 files, 2 commit(s)

## Problem

Reranking tasks where a query had a missing or empty `top_ranked` entry crashed the random ColBERT baseline with `KeyError` or `IndexError`.

## Fix

Excluded queries without reranking candidates in the shared retrieval filter, after maintainer review.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`29a5d8c1`](https://github.com/embeddings-benchmark/mteb/pull/5897/commits/29a5d8c1f365d633054ac45fbddb31623c1e69cb) | 2026-11-16 | MaiAditya | fix: skip queries without reranking candidates in the random ColBERT baseline |
| [`e02ecc59`](https://github.com/embeddings-benchmark/mteb/pull/5897/commits/e02ecc5956a4b4f6ee0f8df0c635fc7068a20196) | 2026-11-16 | Samoed | make better fix |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>mteb/abstasks/retrieval.py</code> | +10 | -2 |
| <code>tests/test&#95;models/test&#95;random&#95;colbert&#95;baseline.py</code> | +32 | -0 |
