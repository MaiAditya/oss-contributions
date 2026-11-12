# reflex-dev/reflex #7866: Split strings by code points when the separator is empty

- **Status:** merged 2026-11-12 by @FarhanAliRaza
- **Pull request:** https://github.com/reflex-dev/reflex/pull/7866
- **Issue:** https://github.com/reflex-dev/reflex/issues/7842
- **Size:** +73 / -2 in 7 files, 5 commit(s)

## Problem

`StringVar.split()` with no or an empty separator split strings into UTF-16 code units, breaking emoji into surrogate halves.

## Fix

Split strings by Unicode code points when the separator is empty, including runtime separators.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`9ee6230e`](https://github.com/reflex-dev/reflex/pull/7866/commits/9ee6230e99bdbd0fbb4d619b8797f8465ad34574) | 2026-11-12 | MaiAditya | Split strings by code points when the separator is empty |
| [`d621546a`](https://github.com/reflex-dev/reflex/pull/7866/commits/d621546ad5fd829d4b84a2303700ac558a06d16e) | 2026-11-12 | MaiAditya | Evaluate a non-literal split separator once |
| [`8b1f9c06`](https://github.com/reflex-dev/reflex/pull/7866/commits/8b1f9c0604f97496428ec8e8141cb715e231220a) | 2026-11-12 | FarhanAliRaza | Merge remote-tracking branch 'upstream/main' into pr-7866 |
| [`7a3a6a41`](https://github.com/reflex-dev/reflex/pull/7866/commits/7a3a6a4195fac26f8001dbbbe8f557cf6f7f3bd6) | 2026-11-12 | FarhanAliRaza | Compile a runtime split separator to a pyStrSplit helper |
| [`d1ad64f7`](https://github.com/reflex-dev/reflex/pull/7866/commits/d1ad64f794c17cc06d3620465b6e144ee7119ab0) | 2026-11-12 | FarhanAliRaza | Describe pyStrSplit as JS split with a code-point empty separator |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>packages/reflex-base/news/+string-split-code-points.bugfix.md</code> | +1 | -0 |
| <code>packages/reflex-base/src/reflex&#95;base/vars/sequence.py</code> | +15 | -2 |
| <code>packages/reflex-frontend/src/utils/state.js</code> | +10 | -0 |
| <code>packages/reflex-frontend/tests/public&#95;api.test.js</code> | +1 | -0 |
| <code>packages/reflex-frontend/tests/state.test.js</code> | +3 | -0 |
| <code>tests/integration/tests&#95;playwright/test&#95;unicode&#95;string&#95;operations.py</code> | +23 | -0 |
| <code>tests/units/test&#95;var.py</code> | +20 | -0 |
