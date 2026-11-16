# neuml/txtai #1577: Check that subindex ANN backends support upserts and deletes before changing any data

- **Status:** in review (opened 2026-11-16)
- **Pull request:** https://github.com/neuml/txtai/pull/1577
- **Issue:** https://github.com/neuml/txtai/issues/1576
- **Size:** +52 / -2 in 3 files, 1 commit(s)

## Problem

`upsert` and `delete` on an index with an ANN backend that doesn't support them in a subindex, such as Annoy, changed data before failing.

## Fix

Added `Indexes.implements` and checked subindex ANNs up front so these calls raise `NotImplementedError` first.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`91270dd4`](https://github.com/neuml/txtai/pull/1577/commits/91270dd41c30d5ff5f0a4b524cbc8fe2d6050c91) | 2026-11-16 | MaiAditya | Check that subindex ANN backends support upserts and deletes before changing any data |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/python/txtai/embeddings/base.py</code> | +8 | -2 |
| <code>src/python/txtai/embeddings/index/indexes.py</code> | +12 | -0 |
| <code>test/python/testann/testdense/testannoy.py</code> | +32 | -0 |
