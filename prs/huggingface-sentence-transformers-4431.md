# huggingface/sentence-transformers #4431: &#91;docs&#93; Fix the inference-free SPLADE learning&#95;rate&#95;mapping pattern for Router parameter names

- **Status:** in review (opened 2026-11-23)
- **Pull request:** https://github.com/huggingface/sentence-transformers/pull/4431
- **Size:** +57 / -21 in 8 files, 1 commit(s)

## Problem

The inference-free SPLADE training example in the docs crashed at `trainer.train()` with `ValueError: No parameters found matching the pattern`, because the documented `learning_rate_mapping` pattern matched no parameter.

## Fix

Changed the documented pattern to `sub_modules\.query\.`, updated the docstrings, and added a regression test.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`6459de0d`](https://github.com/huggingface/sentence-transformers/pull/4431/commits/6459de0d7f962fdc10e12129e489b87b75409449) | 2026-11-19 | MaiAditya | &#91;docs&#93; Fix the inference-free SPLADE learning&#95;rate&#95;mapping pattern for Router parameter names |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>docs/migration&#95;guide.md</code> | +2 | -2 |
| <code>docs/sparse&#95;encoder/training&#95;overview.md</code> | +3 | -3 |
| <code>sentence&#95;transformers/base/modules/router.py</code> | +5 | -3 |
| <code>sentence&#95;transformers/base/training&#95;args.py</code> | +4 | -4 |
| <code>sentence&#95;transformers/cross&#95;encoder/training&#95;args.py</code> | +3 | -3 |
| <code>sentence&#95;transformers/sentence&#95;transformer/training&#95;args.py</code> | +3 | -3 |
| <code>sentence&#95;transformers/sparse&#95;encoder/training&#95;args.py</code> | +3 | -3 |
| <code>tests/sparse&#95;encoder/test&#95;trainer.py</code> | +34 | -0 |
