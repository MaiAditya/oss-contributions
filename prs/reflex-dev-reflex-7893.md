# reflex-dev/reflex #7893: fix: type a repeated &#64;rx.event as one handler

- **Status:** in review (opened 2026-11-13)
- **Pull request:** https://github.com/reflex-dev/reflex/pull/7893
- **Issue:** https://github.com/reflex-dev/reflex/issues/7847
- **Size:** +54 / -9 in 4 files, 1 commit(s)

## Problem

Pyright rejected stacked `@rx.event` decorators, because the outer decorator's argument was the `EventCallback` from the inner one, even though they worked at runtime.

## Fix

Added `EventCallback` overloads to `EventDecorator.__call__` and `EventNamespace.__new__`, and removed the test ignores.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`ebaf4b54`](https://github.com/reflex-dev/reflex/pull/7893/commits/ebaf4b54fcabbce43be7c9d0a6dedb25db1203aa) | 2026-11-13 | MaiAditya | fix: type a repeated &#64;rx.event as one handler |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>packages/reflex-base/news/+stacked-event-decorator-typing.bugfix.md</code> | +1 | -0 |
| <code>packages/reflex-base/src/reflex&#95;base/event/&#95;&#95;init&#95;&#95;.py</code> | +23 | -0 |
| <code>tests/type&#95;checking/event.py</code> | +20 | -0 |
| <code>tests/units/test&#95;event.py</code> | +10 | -9 |
