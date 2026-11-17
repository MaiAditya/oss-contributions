# huggingface/sentence-transformers #4397: &#91;fix&#93; Resolve similarity per call in pairwise evaluators instead of latching onto the first model

- **Status:** merged 2026-11-17 by @tomaarsen
- **Pull request:** https://github.com/huggingface/sentence-transformers/pull/4397
- **Size:** +36 / -3 in 4 files, 2 commit(s)

## Problem

Reusing `EmbeddingSimilarityEvaluator`, `TripletEvaluator` or `BinaryClassificationEvaluator` on a model with a different similarity function kept scoring and labeling with the first model's one.

## Fix

Resolved the default similarity function names on each call and rebuilt the CSV headers when they changed.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`3fa0e083`](https://github.com/huggingface/sentence-transformers/pull/4397/commits/3fa0e0836a3e463c866324b2d27710e46b552cdd) | 2026-11-17 | MaiAditya | &#91;fix&#93; Resolve similarity per call in pairwise evaluators instead of latching onto the first model |
| [`c1904394`](https://github.com/huggingface/sentence-transformers/pull/4397/commits/c1904394d0d56534801671819684e063d03df942) | 2026-11-17 | tomaarsen | Keep evaluator reuse fix focused and consolidate tests |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>sentence&#95;transformers/sentence&#95;transformer/evaluation/binary&#95;classification.py</code> | +3 | -1 |
| <code>sentence&#95;transformers/sentence&#95;transformer/evaluation/embedding&#95;similarity.py</code> | +3 | -1 |
| <code>sentence&#95;transformers/sentence&#95;transformer/evaluation/triplet.py</code> | +3 | -1 |
| <code>tests/base/evaluation/test&#95;misc.py</code> | +27 | -0 |
