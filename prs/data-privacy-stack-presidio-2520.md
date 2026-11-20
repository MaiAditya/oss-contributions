# data-privacy-stack/presidio #2520: fix(analyzer): count context words glued to an entity with ":"

- **Status:** in review (opened 2026-11-20)
- **Pull request:** https://github.com/data-privacy-stack/presidio/pull/2520
- **Issue:** https://github.com/data-privacy-stack/presidio/issues/2519
- **Size:** +68 / -4 in 4 files, 1 commit(s)

## Problem

A context word glued to an entity with a colon, like `Phone:617-555-0134`, never counted as context, so the entity kept its lower pattern score.

## Fix

Split lemmas on `:` and counted the keyword parts as context words in the lemma and phrase enhancers.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`9aab0d13`](https://github.com/data-privacy-stack/presidio/pull/2520/commits/9aab0d13a48c186c9dbdbf7a2649d744df5ae28f) | 2026-11-20 | MaiAditya | fix(analyzer): count context words glued to an entity with ":" |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>presidio-analyzer/presidio&#95;analyzer/context&#95;aware&#95;enhancers/context&#95;aware&#95;enhancer.py</code> | +13 | -1 |
| <code>presidio-analyzer/presidio&#95;analyzer/context&#95;aware&#95;enhancers/lemma&#95;context&#95;aware&#95;enhancer.py</code> | +5 | -3 |
| <code>presidio-analyzer/tests/test&#95;context&#95;support.py</code> | +33 | -0 |
| <code>presidio-analyzer/tests/test&#95;phrase&#95;context&#95;aware&#95;enhancer.py</code> | +17 | -0 |
