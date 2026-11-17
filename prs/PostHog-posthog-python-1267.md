# PostHog/posthog-python #1267: fix: mark an exception taken from sys.exc&#95;info() as captured

- **Status:** merged 2026-11-17 by @hpouillot
- **Pull request:** https://github.com/PostHog/posthog-python/pull/1267
- **Size:** +67 / -5 in 4 files, 1 commit(s)

## Problem

`capture_exception()` without an argument did not mark the `sys.exc_info()` exception as captured, so a re-raised error was sent twice.

## Fix

Marked the resolved `exc_info` as captured and skipped already-marked ones in `Client` and `AsyncClient`.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`fd668655`](https://github.com/PostHog/posthog-python/pull/1267/commits/fd668655a8042f2e88e78087c285f89bc1ede6f4) | 2026-11-14 | MaiAditya | fix: mark an exception taken from sys.exc&#95;info() as captured |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>.sampo/changesets/capture-exception-no-arg-dedupe.md</code> | +5 | -0 |
| <code>posthog/async&#95;client.py</code> | +8 | -2 |
| <code>posthog/client.py</code> | +8 | -3 |
| <code>posthog/test/test&#95;exception&#95;capture.py</code> | +46 | -0 |
