# reflex-dev/reflex #7867: Name every method decorated above &#64;rx.event in the deprecation warning

- **Status:** in review (opened 2026-11-12)
- **Pull request:** https://github.com/reflex-dev/reflex/pull/7867
- **Issue:** https://github.com/reflex-dev/reflex/issues/7840
- **Size:** +96 / -11 in 3 files, 2 commit(s)

## Problem

The deprecation warning for decorators placed above `@rx.event` named only the first affected method in a state, so users found the rest one restart at a time.

## Fix

Made the deprecation warning name every affected method once.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`3516f5b5`](https://github.com/reflex-dev/reflex/pull/7867/commits/3516f5b5592571c0ed60bf74a76a1a55e666181c) | 2026-11-12 | MaiAditya | Name every method decorated above &#64;rx.event in the deprecation warning |
| [`9cd99a46`](https://github.com/reflex-dev/reflex/pull/7867/commits/9cd99a462a93292d81a6529870fbb9c14df0eb69) | 2026-11-12 | MaiAditya | Compare the full deprecation warnings and name the feature once |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>news/+event-decorator-deprecation-all-methods.bugfix.md</code> | +1 | -0 |
| <code>reflex/state.py</code> | +24 | -11 |
| <code>tests/units/test&#95;state.py</code> | +71 | -0 |
