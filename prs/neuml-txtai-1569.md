# neuml/txtai #1569: Stop IS NULL from consuming the next token in SQL expressions

- **Status:** in review (opened 2026-11-14)
- **Pull request:** https://github.com/neuml/txtai/pull/1569
- **Issue:** https://github.com/neuml/txtai/issues/1568
- **Size:** +12 / -5 in 3 files, 2 commit(s)

## Problem

In txtai SQL, `is null` consumed the next token, so `sum(a is null)` raised "Unterminated clause" and `a is null as flag` failed.

## Fix

Moved `null` from `Token.OPERATORS` to the literals, next to `true` and `false`.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`fc01534c`](https://github.com/neuml/txtai/pull/1569/commits/fc01534cc51670095d9db7dfc240fda460007c9e) | 2026-11-08 | MaiAditya | Stop IS NULL from consuming the next token in SQL expressions |
| [`cf2aa07f`](https://github.com/neuml/txtai/pull/1569/commits/cf2aa07ff6a40bfb0002d922dc385052882df4ff) | 2026-11-17 | davidmezzetti | Update build.yml |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>.github/workflows/build.yml</code> | +1 | -0 |
| <code>src/python/txtai/database/sql/token.py</code> | +5 | -5 |
| <code>test/python/testdatabase/testsql.py</code> | +6 | -0 |
