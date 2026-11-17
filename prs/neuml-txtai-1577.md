# neuml/txtai #1577: Check that subindex ANN backends support upserts and deletes before changing any data

- **Status:** in review (opened 2026-11-16)
- **Pull request:** https://github.com/neuml/txtai/pull/1577
- **Issue:** https://github.com/neuml/txtai/issues/1576
- **Size:** +53 / -2 in 4 files, 2 commit(s)

## Problem

`upsert` and `delete` on an index with an ANN backend that doesn't support them in a subindex, such as Annoy, changed data before failing.

## Fix

Added `Indexes.implements` and checked subindex ANNs up front so these calls raise `NotImplementedError` first.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`91270dd4`](https://github.com/neuml/txtai/pull/1577/commits/91270dd41c30d5ff5f0a4b524cbc8fe2d6050c91) | 2026-11-16 | MaiAditya | Check that subindex ANN backends support upserts and deletes before changing any data |
| [`39acfdf2`](https://github.com/neuml/txtai/pull/1577/commits/39acfdf269e3ad63616d87a599cfa41d1d6b7e85) | 2026-11-17 | davidmezzetti | Update build.yml |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>.github/workflows/build.yml</code> | +1 | -0 |
| <code>src/python/txtai/embeddings/base.py</code> | +8 | -2 |
| <code>src/python/txtai/embeddings/index/indexes.py</code> | +12 | -0 |
| <code>test/python/testann/testdense/testannoy.py</code> | +32 | -0 |
