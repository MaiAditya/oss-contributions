# embeddings-benchmark/mteb #5870: fix: support euclidean and manhattan similarity in AbsEncoder

- **Status:** merged 2026-11-11 by @Samoed
- **Pull request:** https://github.com/embeddings-benchmark/mteb/pull/5870
- **Issue:** https://github.com/embeddings-benchmark/mteb/issues/5869
- **Size:** +146 / -47 in 3 files, 2 commit(s)

## Problem

Models using euclidean or manhattan similarity crashed with `Similarity function not specified` in tasks scored through `AbsEncoder`.

## Fix

Added euclidean and manhattan support to `AbsEncoder` and a memory-bounded chunked `manhattan_sim`.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`0a078d57`](https://github.com/embeddings-benchmark/mteb/pull/5870/commits/0a078d575c46c96db0755a5a0e84d59bfc37d971) | 2026-11-11 | MaiAditya | fix: support euclidean and manhattan similarity in AbsEncoder |
| [`4f409dd7`](https://github.com/embeddings-benchmark/mteb/pull/5870/commits/4f409dd7e299240086bac8e2ee3d9736b6bc6256) | 2026-11-11 | Samoed | update implementaion &amp; refactor tests |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>mteb/models/abs&#95;encoder.py</code> | +8 | -20 |
| <code>mteb/similarity&#95;functions.py</code> | +48 | -2 |
| <code>tests/test&#95;similarity&#95;functions.py</code> | +90 | -25 |
