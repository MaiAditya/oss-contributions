# huggingface/sentence-transformers #4420: &#91;fix&#93; Reject 'prompt' and 'task' dataset columns in CrossEncoderTrainer

- **Status:** in review (opened 2026-11-20)
- **Pull request:** https://github.com/huggingface/sentence-transformers/pull/4420
- **Size:** +26 / -1 in 3 files, 1 commit(s)

## Problem

In `CrossEncoderTrainer`, a dataset column named `prompt` or `task` was silently dropped from the batch, so training ran on the remaining columns with only a misleading warning.

## Fix

Made `prompt` and `task` reserved column names for the CrossEncoder trainer, so such datasets now fail with a clear error.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`7a23a57f`](https://github.com/huggingface/sentence-transformers/pull/4420/commits/7a23a57f161d6fe5e810cb434cd7dae8b566fcc9) | 2026-11-20 | MaiAditya | &#91;fix&#93; Reject 'prompt' and 'task' dataset columns in CrossEncoderTrainer |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>sentence&#95;transformers/base/trainer.py</code> | +3 | -1 |
| <code>sentence&#95;transformers/cross&#95;encoder/trainer.py</code> | +2 | -0 |
| <code>tests/cross&#95;encoder/test&#95;trainer.py</code> | +21 | -0 |
