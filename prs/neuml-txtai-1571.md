# neuml/txtai #1571: Support case expressions in SQL queries

- **Status:** in review (opened 2026-11-14)
- **Pull request:** https://github.com/neuml/txtai/pull/1571
- **Issue:** https://github.com/neuml/txtai/issues/1570
- **Size:** +71 / -2 in 3 files, 2 commit(s)

## Problem

SQL queries with `case ... when ... then ... else ... end` expressions were not translated correctly, and `a = 1 and b = 2 x` left `b` unresolved.

## Fix

Added `case` keywords as conditionals and stopped treating the token after `and`/`or` as an alias.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`4a5a58e7`](https://github.com/neuml/txtai/pull/1571/commits/4a5a58e7482b9e70519937facbe9ecdd6755bf52) | 2026-11-11 | MaiAditya | Support case expressions in SQL queries |
| [`4e31329b`](https://github.com/neuml/txtai/pull/1571/commits/4e31329bb4d4feee19ef6e269d547df2c5e52b2f) | 2026-11-17 | davidmezzetti | Update build.yml |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>.github/workflows/build.yml</code> | +1 | -0 |
| <code>src/python/txtai/database/sql/token.py</code> | +24 | -2 |
| <code>test/python/testdatabase/testsql.py</code> | +46 | -0 |
