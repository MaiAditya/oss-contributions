# run-llama/llama_index #24351: fix(core): read provider token counts from additional&#95;kwargs in TokenCountingHandler

- **Status:** in review (opened 2026-11-20)
- **Pull request:** https://github.com/run-llama/llama_index/pull/24351
- **Issue:** https://github.com/run-llama/llama_index/issues/24350
- **Size:** +91 / -20 in 2 files, 1 commit(s)

## Problem

`TokenCountingHandler` recorded local tokenizer estimates instead of the provider's counts for integrations like Bedrock Converse, e.g. 8/4 tokens for a reported 1200/345.

## Fix

Read token counts from `additional_kwargs` when raw `usage` has none, keeping raw `usage` first when it has counts.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`9ef6ae78`](https://github.com/run-llama/llama_index/pull/24351/commits/9ef6ae78f59a3e34da1a2b73e721da498df8a255) | 2026-11-20 | MaiAditya | fix(core): read provider token counts from additional&#95;kwargs in TokenCountingHandler |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>llama-index-core/llama&#95;index/core/callbacks/token&#95;counting.py</code> | +25 | -18 |
| <code>llama-index-core/tests/callbacks/test&#95;token&#95;counter.py</code> | +66 | -2 |
