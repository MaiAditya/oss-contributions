# huggingface/sentence-transformers #4410: &#91;fix&#93; Raise clear ValueErrors for empty or mismatched evaluator inputs

- **Status:** in review (opened 2026-11-18)
- **Pull request:** https://github.com/huggingface/sentence-transformers/pull/4410
- **Size:** +91 / -9 in 5 files, 1 commit(s)

## Problem

Evaluators given empty or mismatched inputs failed late with obscure errors or, for `TripletEvaluator`, silently returned 0.0.

## Fix

Replaced constructor `assert`s with `ValueError`s for empty input, length mismatch and non-0/1 binary labels.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`408fbd88`](https://github.com/huggingface/sentence-transformers/pull/4410/commits/408fbd8875a578b8f0d03d1d5b7ec757e4b6a02d) | 2026-11-18 | MaiAditya | &#91;fix&#93; Raise clear ValueErrors for empty or mismatched evaluator inputs |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>sentence&#95;transformers/sentence&#95;transformer/evaluation/binary&#95;classification.py</code> | +10 | -4 |
| <code>sentence&#95;transformers/sentence&#95;transformer/evaluation/embedding&#95;similarity.py</code> | +7 | -2 |
| <code>sentence&#95;transformers/sentence&#95;transformer/evaluation/translation.py</code> | +7 | -1 |
| <code>sentence&#95;transformers/sentence&#95;transformer/evaluation/triplet.py</code> | +7 | -2 |
| <code>tests/sentence&#95;transformer/evaluation/test&#95;input&#95;validation.py</code> | +60 | -0 |
