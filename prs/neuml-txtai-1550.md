# neuml/txtai #1550: Track nested parentheses in SQL function arguments

- **Status:** merged 2026-11-12 by @davidmezzetti
- **Pull request:** https://github.com/neuml/txtai/pull/1550
- **Issue:** https://github.com/neuml/txtai/issues/1549
- **Size:** +33 / -4 in 2 files, 1 commit(s)

## Problem

SQL functions with nested parentheses in their arguments, such as `round(a * (b + c), 1)`, were translated into broken SQL.

## Fix

Counted nested parentheses in function arguments so each function ends at its own closing paren.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`86ad2ce4`](https://github.com/neuml/txtai/pull/1550/commits/86ad2ce4d0a7930949f515b4b6bc3fa478b512ee) | 2026-11-11 | MaiAditya | Track nested parentheses in SQL function arguments |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/python/txtai/database/sql/expression.py</code> | +17 | -4 |
| <code>test/python/testdatabase/testsql.py</code> | +16 | -0 |
