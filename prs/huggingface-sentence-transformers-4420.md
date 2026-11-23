# huggingface/sentence-transformers #4420: &#91;fix&#93; Avoid CrossEncoder input column collisions with batch metadata

- **Status:** merged 2026-11-23 by @tomaarsen
- **Pull request:** https://github.com/huggingface/sentence-transformers/pull/4420
- **Size:** +50 / -7 in 3 files, 2 commit(s)

## Problem

In `CrossEncoderTrainer`, a dataset column named `prompt` or `task` was silently dropped from the batch, so training ran on the remaining columns with only a misleading warning.

## Fix

Made `prompt` and `task` reserved column names for the CrossEncoder trainer, so such datasets now fail with a clear error.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`7a23a57f`](https://github.com/huggingface/sentence-transformers/pull/4420/commits/7a23a57f161d6fe5e810cb434cd7dae8b566fcc9) | 2026-11-20 | MaiAditya | &#91;fix&#93; Reject 'prompt' and 'task' dataset columns in CrossEncoderTrainer |
| [`23825995`](https://github.com/huggingface/sentence-transformers/pull/4420/commits/238259955ac8f9bfebd74b66efcaa7ed906ec11d) | 2026-11-23 | tomaarsen | &#91;fix&#93; Keep CrossEncoder input columns separate from batch metadata |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>sentence&#95;transformers/cross&#95;encoder/data&#95;collator.py</code> | +3 | -3 |
| <code>tests/cross&#95;encoder/test&#95;data&#95;collator.py</code> | +3 | -3 |
| <code>tests/cross&#95;encoder/test&#95;trainer.py</code> | +44 | -1 |
