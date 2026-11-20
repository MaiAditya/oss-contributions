# google/adk-python #8260: fix(live): retry 1008 "already connected" and back off on reconnect

- **Status:** in review (opened 2026-11-19)
- **Pull request:** https://github.com/google/adk-python/pull/8260
- **Issue:** https://github.com/google/adk-python/issues/8258
- **Size:** +282 / -4 in 3 files, 2 commit(s)

## Problem

When `run_live` reconnected with a session resumption handle, the server could reject it with close code 1008 "already connected to an existing client", which ended the stream.

## Fix

Retried that 1008 on the reconnect path and added bounded exponential backoff between reconnect attempts.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`eda6c12f`](https://github.com/google/adk-python/pull/8260/commits/eda6c12f8cdf3bb617b8dc7175b5eacf8390da97) | 2026-11-19 | MaiAditya | fix(live): retry 1008 "already connected" and back off on reconnect |
| [`6d6c11f5`](https://github.com/google/adk-python/pull/8260/commits/6d6c11f5140c9cabbeb4c8f11f2f5e698172f19e) | 2026-11-20 | MaiAditya | test(live): cover backoff reset after a connection delivers an event |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/google/adk/live/&#95;flow&#95;utils.py</code> | +5 | -0 |
| <code>src/google/adk/live/&#95;live&#95;llm&#95;flow.py</code> | +59 | -4 |
| <code>tests/unittests/live/test&#95;live&#95;llm&#95;flow.py</code> | +218 | -0 |
