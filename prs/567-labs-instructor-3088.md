# 567-labs/instructor #3088: fix(retry): report IncompleteOutputException to error hooks

- **Status:** in review (opened 2026-11-20)
- **Pull request:** https://github.com/567-labs/instructor/pull/3088
- **Issue:** https://github.com/567-labs/instructor/issues/3087
- **Size:** +132 / -3 in 3 files, 1 commit(s)

## Problem

In the v2 retry loop, `IncompleteOutputException` was re-raised without emitting hooks, so `completion:error` handlers never saw a response cut off by the token limit.

## Fix

Emitted `completion:error` and `completion:last_attempt` before re-raising, in both the sync and async loops.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`b67eebd6`](https://github.com/567-labs/instructor/pull/3088/commits/b67eebd6c771d2b7a619903b2956ce1930848e6c) | 2026-11-20 | MaiAditya | fix(retry): report IncompleteOutputException to error hooks |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>CHANGELOG.md</code> | +1 | -0 |
| <code>instructor/v2/core/retry.py</code> | +37 | -2 |
| <code>tests/v2/test&#95;retry&#95;runtime.py</code> | +94 | -1 |
