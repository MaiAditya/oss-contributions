# huggingface/sentence-transformers #4431: &#91;docs&#93; Fix the inference-free SPLADE learning&#95;rate&#95;mapping pattern for Router parameter names

- **Status:** merged 2026-11-25 by @tomaarsen
- **Pull request:** https://github.com/huggingface/sentence-transformers/pull/4431
- **Size:** +50 / -26 in 8 files, 2 commit(s)

## Problem

The inference-free SPLADE training example in the docs crashed at `trainer.train()` with `ValueError: No parameters found matching the pattern`, because the documented `learning_rate_mapping` pattern matched no parameter.

## Fix

Changed the documented pattern to `sub_modules\.query\.`, updated the docstrings, and added a regression test.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`6459de0d`](https://github.com/huggingface/sentence-transformers/pull/4431/commits/6459de0d7f962fdc10e12129e489b87b75409449) | 2026-11-19 | MaiAditya | &#91;docs&#93; Fix the inference-free SPLADE learning&#95;rate&#95;mapping pattern for Router parameter names |
| [`b8bfd737`](https://github.com/huggingface/sentence-transformers/pull/4431/commits/b8bfd737f1eb57e71b0da1509ee2993152077994) | 2026-11-25 | tomaarsen | &#91;docs&#93; Simplify learning rate mapping examples |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>docs/migration&#95;guide.md</code> | +2 | -2 |
| <code>docs/sparse&#95;encoder/training&#95;overview.md</code> | +3 | -3 |
| <code>sentence&#95;transformers/base/modules/router.py</code> | +2 | -2 |
| <code>sentence&#95;transformers/base/training&#95;args.py</code> | +4 | -7 |
| <code>sentence&#95;transformers/cross&#95;encoder/training&#95;args.py</code> | +2 | -4 |
| <code>sentence&#95;transformers/sentence&#95;transformer/training&#95;args.py</code> | +2 | -4 |
| <code>sentence&#95;transformers/sparse&#95;encoder/training&#95;args.py</code> | +2 | -4 |
| <code>tests/sparse&#95;encoder/test&#95;trainer.py</code> | +33 | -0 |
