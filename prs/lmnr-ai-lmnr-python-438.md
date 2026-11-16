# lmnr-ai/lmnr-python #438: fix(observe): keep positional-only and &#42;args values when a &#42;&#42;kwargs key shares their name

- **Status:** in review (opened 2026-11-15)
- **Pull request:** https://github.com/lmnr-ai/lmnr-python/pull/438
- **Issue:** https://github.com/lmnr-ai/lmnr-python/issues/437
- **Size:** +23 / -5 in 3 files, 1 commit(s)

## Problem

`@observe` lost a bound value from the span input when a `**kwargs` key matched a positional-only parameter or the `*args` name.

## Fix

Recorded `**kwargs` as a dict under its own parameter name when a key collides, leaving other calls unchanged.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`a2022467`](https://github.com/lmnr-ai/lmnr-python/pull/438/commits/a2022467c6e64b07ff9640e6eab410786591234b) | 2026-11-15 | MaiAditya | fix(observe): keep positional-only and &#42;args values when a &#42;&#42;kwargs key shares their name |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/lmnr/sdk/AGENTS.md</code> | +1 | -1 |
| <code>src/lmnr/sdk/utils.py</code> | +8 | -4 |
| <code>tests/test&#95;observe.py</code> | +14 | -0 |
