# neuml/txtai #1535: Split signs from operators when tokenizing SQL

- **Status:** in review (opened 2026-11-08)
- **Pull request:** https://github.com/neuml/txtai/pull/1535
- **Issue:** https://github.com/neuml/txtai/issues/1534
- **Size:** +13 / -3 in 2 files, 3 commit(s)

## Problem

SQL comparisons followed by a sign, such as `a=-1` or `a<-2`, failed because `=-` was read as a column name.

## Fix

Split signs from operators when tokenizing SQL.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`314e02ce`](https://github.com/neuml/txtai/pull/1535/commits/314e02ce16db16455ec74c3db33a117b4fc1c954) | 2026-11-08 | MaiAditya | Split signs from operators when tokenizing SQL |
| [`150649b0`](https://github.com/neuml/txtai/pull/1535/commits/150649b0d34112a534581b0739de3600cda6dc8f) | 2026-11-10 | MaiAditya | Tokenize arithmetic operators as standalone tokens instead of splitting signs |
| [`3645c29e`](https://github.com/neuml/txtai/pull/1535/commits/3645c29e255595c0948660e69a6e917feb97dea8) | 2026-11-12 | MaiAditya | Merge remote-tracking branch 'origin/master' into fix/sql-signed-number-after-operator |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/python/txtai/database/sql/base.py</code> | +5 | -3 |
| <code>test/python/testdatabase/testsql.py</code> | +8 | -0 |
