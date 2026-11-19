# huggingface/sentence-transformers #4354: &#91;fix&#93; Use the untruncated embedding dimension in MatryoshkaLoss and EmbedDistillLoss

- **Status:** merged 2026-11-19 by @tomaarsen
- **Pull request:** https://github.com/huggingface/sentence-transformers/pull/4354
- **Issue:** https://github.com/huggingface/sentence-transformers/issues/4353
- **Size:** +83 / -5 in 6 files, 3 commit(s)

## Problem

With `truncate_dim` set on the student, `MatryoshkaLoss` and `EmbedDistillLoss` crashed with a shape mismatch at the first training step.

## Fix

Used the untruncated embedding dimension in `MatryoshkaLoss` and `EmbedDistillLoss`.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`b5ef7b4a`](https://github.com/huggingface/sentence-transformers/pull/4354/commits/b5ef7b4a697da96272b2a68c9e64b89a30591051) | 2026-11-10 | MaiAditya | &#91;fix&#93; Use the untruncated embedding dimension in MatryoshkaLoss and EmbedDistillLoss |
| [`74851201`](https://github.com/huggingface/sentence-transformers/pull/4354/commits/748512011c52bbd77ef2f6e61c2bfa459af7406e) | 2026-11-19 | tomaarsen | Inline embedding dimension lookup in EmbedDistillLoss |
| [`005c54fd`](https://github.com/huggingface/sentence-transformers/pull/4354/commits/005c54fdbd2c02e6a05db672845674ab60da2fa8) | 2026-11-19 | tomaarsen | Strengthen truncation and projection regression tests |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>sentence&#95;transformers/base/trainer.py</code> | +2 | -2 |
| <code>sentence&#95;transformers/sentence&#95;transformer/losses/embed&#95;distill.py</code> | +6 | -2 |
| <code>sentence&#95;transformers/sentence&#95;transformer/losses/matryoshka.py</code> | +1 | -1 |
| <code>tests/sentence&#95;transformer/losses/test&#95;embed&#95;distill.py</code> | +18 | -0 |
| <code>tests/sentence&#95;transformer/losses/test&#95;matryoshka.py</code> | +37 | -0 |
| <code>tests/sparse&#95;encoder/losses/test&#95;sparse&#95;mse.py</code> | +19 | -0 |
