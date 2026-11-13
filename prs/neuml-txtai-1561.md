# neuml/txtai #1561: Resolve bracket expressions on the right side of SQL operators

- **Status:** in review (opened 2026-11-13)
- **Pull request:** https://github.com/neuml/txtai/pull/1561
- **Issue:** https://github.com/neuml/txtai/issues/1560
- **Size:** +10 / -1 in 2 files, 1 commit(s)

## Problem

SQL bracket expressions on the right side of an operator, such as `where price = [min price]`, were resolved as a column and failed.

## Fix

Routed a `[` after an operator to `bracket()` in `compound()` so these expressions translate correctly.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`9d57c63f`](https://github.com/neuml/txtai/pull/1561/commits/9d57c63fdf72039c5fbf933601c5a2b2dbaef032) | 2026-11-11 | MaiAditya | Resolve bracket expressions on the right side of SQL operators |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/python/txtai/database/sql/expression.py</code> | +4 | -1 |
| <code>test/python/testdatabase/testsql.py</code> | +6 | -0 |
