# embeddings-benchmark/mteb #5864: fix: delegate pairwise similarity to the sentence-transformers model

- **Status:** merged 2026-11-10 by @Samoed
- **Pull request:** https://github.com/embeddings-benchmark/mteb/pull/5864
- **Issue:** https://github.com/embeddings-benchmark/mteb/issues/5863
- **Size:** +37 / -0 in 2 files, 1 commit(s)

## Problem

STS and pair classification raised `ValueError: Similarity function not specified` for sentence-transformers models with euclidean or manhattan similarity.

## Fix

Delegated pairwise similarity to the sentence-transformers model's own `similarity_pairwise`.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`3bf81237`](https://github.com/embeddings-benchmark/mteb/pull/5864/commits/3bf812372789b9b1fbac78f332e81557e87d6837) | 2026-11-09 | MaiAditya | fix: delegate pairwise similarity to the sentence-transformers model |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>mteb/models/sentence&#95;transformer&#95;wrapper.py</code> | +15 | -0 |
| <code>tests/test&#95;similarity&#95;functions.py</code> | +22 | -0 |
