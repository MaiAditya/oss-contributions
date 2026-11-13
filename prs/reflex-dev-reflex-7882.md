# reflex-dev/reflex #7882: fix: reject page routes that match the same URLs

- **Status:** in review (opened 2026-11-13)
- **Pull request:** https://github.com/reflex-dev/reflex/pull/7882
- **Issue:** https://github.com/reflex-dev/reflex/issues/7833
- **Size:** +266 / -1 in 4 files, 2 commit(s)

## Problem

Routes like `/Foo` and `/foo` were both accepted although matching is case-insensitive, leaving one page unreachable with no warning.

## Fix

Made `add_page` raise `RouteValueError` for routes that match the same URLs, including plugin-contributed pages.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`2b54c97d`](https://github.com/reflex-dev/reflex/pull/7882/commits/2b54c97d4d24110782fa27ef35c4c4d68078aaf8) | 2026-11-13 | MaiAditya | fix: reject page routes that match the same URLs |
| [`656e9655`](https://github.com/reflex-dev/reflex/pull/7882/commits/656e96551fe97d97581409fd73d0f1a4a64dbf8c) | 2026-11-13 | MaiAditya | fix: keep the index route and literal keyword segments distinct |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>news/+route-case-collision.bugfix.md</code> | +1 | -0 |
| <code>reflex/app.py</code> | +61 | -1 |
| <code>tests/units/compiler/test&#95;compiler.py</code> | +94 | -0 |
| <code>tests/units/test&#95;app.py</code> | +110 | -0 |
