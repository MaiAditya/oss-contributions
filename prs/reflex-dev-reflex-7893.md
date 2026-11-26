# reflex-dev/reflex #7893: fix: type a repeated &#64;rx.event as one handler

- **Status:** merged 2026-11-25 by @FarhanAliRaza
- **Pull request:** https://github.com/reflex-dev/reflex/pull/7893
- **Issue:** https://github.com/reflex-dev/reflex/issues/7847
- **Size:** +54 / -9 in 4 files, 2 commit(s)

## Problem

Pyright rejected stacked `@rx.event` decorators, because the outer decorator's argument was the `EventCallback` from the inner one, even though they worked at runtime.

## Fix

Added `EventCallback` overloads to `EventDecorator.__call__` and `EventNamespace.__new__`, and removed the test ignores.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`ebaf4b54`](https://github.com/reflex-dev/reflex/pull/7893/commits/ebaf4b54fcabbce43be7c9d0a6dedb25db1203aa) | 2026-11-13 | MaiAditya | fix: type a repeated &#64;rx.event as one handler |
| [`b58f7a5f`](https://github.com/reflex-dev/reflex/pull/7893/commits/b58f7a5f43fece4b7d4b3882c3da1795de654dca) | 2026-11-25 | FarhanAliRaza | Merge upstream main into fix/stacked-event-decorator-typing |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>packages/reflex-base/news/+stacked-event-decorator-typing.bugfix.md</code> | +1 | -0 |
| <code>packages/reflex-base/src/reflex&#95;base/event/&#95;&#95;init&#95;&#95;.py</code> | +23 | -0 |
| <code>tests/type&#95;checking/event.py</code> | +20 | -0 |
| <code>tests/units/test&#95;event.py</code> | +10 | -9 |
