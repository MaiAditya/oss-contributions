# reflex-dev/reflex #7866: Split strings by code points when the separator is empty

- **Status:** in review (opened 2026-11-12)
- **Pull request:** https://github.com/reflex-dev/reflex/pull/7866
- **Issue:** https://github.com/reflex-dev/reflex/issues/7842
- **Size:** +60 / -2 in 4 files, 2 commit(s)

## Problem

`StringVar.split()` with no or an empty separator split strings into UTF-16 code units, breaking emoji into surrogate halves.

## Fix

Split strings by Unicode code points when the separator is empty, including runtime separators.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`9ee6230e`](https://github.com/reflex-dev/reflex/pull/7866/commits/9ee6230e99bdbd0fbb4d619b8797f8465ad34574) | 2026-11-12 | MaiAditya | Split strings by code points when the separator is empty |
| [`d621546a`](https://github.com/reflex-dev/reflex/pull/7866/commits/d621546ad5fd829d4b84a2303700ac558a06d16e) | 2026-11-12 | MaiAditya | Evaluate a non-literal split separator once |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>packages/reflex-base/news/+string-split-code-points.bugfix.md</code> | +1 | -0 |
| <code>packages/reflex-base/src/reflex&#95;base/vars/sequence.py</code> | +13 | -2 |
| <code>tests/integration/tests&#95;playwright/test&#95;unicode&#95;string&#95;operations.py</code> | +23 | -0 |
| <code>tests/units/test&#95;var.py</code> | +23 | -0 |
