# comet-ml/opik #9548: &#91;issue-9547&#93; &#91;SDK&#93; fix: ChrF scored identical short strings below 1.0

- **Status:** in review (opened 2026-11-13)
- **Pull request:** https://github.com/comet-ml/opik/pull/9548
- **Issue:** https://github.com/comet-ml/opik/issues/9547
- **Size:** +138 / -2 in 2 files, 2 commit(s)

## Problem

The default `ChrF` metric scored identical short strings below 1.0, e.g. `"a"` vs `"a"` gave 0.1667.

## Fix

Capped the n-gram order at the shorter text's length so only orders both sides can produce are averaged.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`05ab8895`](https://github.com/comet-ml/opik/pull/9548/commits/05ab88956ed492e6209acd8ec2d74b77f6325fa3) | 2026-11-13 | MaiAditya | &#91;issue-9547&#93; &#91;SDK&#93; fix: ChrF scored identical short strings below 1.0 |
| [`73d78f28`](https://github.com/comet-ml/opik/pull/9548/commits/73d78f28fbdd2cc38fd7aceb4087d269c1aa375a) | 2026-11-13 | MaiAditya | &#91;issue-9547&#93; &#91;SDK&#93; refactor: move the ChrF effective order to a module-level helper |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>sdks/python/src/opik/evaluation/metrics/heuristics/chrf.py</code> | +30 | -1 |
| <code>sdks/python/tests/unit/evaluation/metrics/test&#95;heuristics.py</code> | +108 | -1 |
