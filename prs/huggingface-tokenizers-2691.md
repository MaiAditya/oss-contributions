# huggingface/tokenizers #2691: fix(bpe): keep byte-level vocab entries outside the byte alphabet as written

- **Status:** in review (opened 2026-11-13)
- **Pull request:** https://github.com/huggingface/tokenizers/pull/2691
- **Issue:** https://github.com/huggingface/tokenizers/issues/2690
- **Size:** +92 / -10 in 4 files, 1 commit(s)

## Problem

Byte-level vocab entries outside the byte alphabet, such as DeepSeek-V3's `<｜begin▁of▁sentence｜>`, were misspelled by the vocab APIs and got different ids after saving.

## Fix

Kept those entries by id in `PipelineBPE` so the vocab lookups and `to_config` return them as written.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`4440f838`](https://github.com/huggingface/tokenizers/pull/2691/commits/4440f83845abd24430a35bf3f71050f20c8ea49b) | 2026-11-13 | MaiAditya | fix(bpe): keep byte-level vocab entries outside the byte alphabet as written |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>tokenizers/tk-encode/src/models/bpe/model.rs</code> | +16 | -3 |
| <code>tokenizers/tk-encode/src/models/bpe/serialization.rs</code> | +16 | -1 |
| <code>tokenizers/tk-encode/src/models/bpe/tests.rs</code> | +38 | -0 |
| <code>tokenizers/tk-encode/src/utils/byte&#95;level.rs</code> | +22 | -6 |
