# huggingface/sentence-transformers #4354: &#91;fix&#93; Use the untruncated embedding dimension in MatryoshkaLoss and EmbedDistillLoss

- **Status:** in review (opened 2026-11-10)
- **Pull request:** https://github.com/huggingface/sentence-transformers/pull/4354
- **Issue:** https://github.com/huggingface/sentence-transformers/issues/4353
- **Size:** +80 / -5 in 6 files, 1 commit(s)

## Problem

With `truncate_dim` set on the student, `MatryoshkaLoss` and `EmbedDistillLoss` crashed with a shape mismatch at the first training step.

## Fix

Used the untruncated embedding dimension in `MatryoshkaLoss` and `EmbedDistillLoss`.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`b5ef7b4a`](https://github.com/huggingface/sentence-transformers/pull/4354/commits/b5ef7b4a697da96272b2a68c9e64b89a30591051) | 2026-11-10 | MaiAditya | &#91;fix&#93; Use the untruncated embedding dimension in MatryoshkaLoss and EmbedDistillLoss |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>sentence&#95;transformers/base/trainer.py</code> | +2 | -2 |
| <code>sentence&#95;transformers/sentence&#95;transformer/losses/embed&#95;distill.py</code> | +9 | -2 |
| <code>sentence&#95;transformers/sentence&#95;transformer/losses/matryoshka.py</code> | +1 | -1 |
| <code>tests/sentence&#95;transformer/losses/test&#95;embed&#95;distill.py</code> | +18 | -0 |
| <code>tests/sentence&#95;transformer/losses/test&#95;matryoshka.py</code> | +30 | -0 |
| <code>tests/sparse&#95;encoder/losses/test&#95;sparse&#95;mse.py</code> | +20 | -0 |
