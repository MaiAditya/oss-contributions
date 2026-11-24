# neuml/txtai #1653: Strip thinking text when the chat template opens the think tag in the prompt

- **Status:** merged 2026-11-24 by @davidmezzetti
- **Pull request:** https://github.com/neuml/txtai/pull/1653
- **Issue:** https://github.com/neuml/txtai/issues/1652
- **Size:** +19 / -1 in 2 files, 3 commit(s)

## Problem

Chat templates that put `<think>` in the prompt left only a closing `</think>` in the output, so `stripthink=True` returned the reasoning text plus the answer.

## Fix

Made `cleanthink` also remove text up to a bare closing `</think>` tag, and added a test.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`7367792d`](https://github.com/neuml/txtai/pull/1653/commits/7367792dbf3aea4b5457719b3817ffb6a5b6b396) | 2026-11-23 | MaiAditya | Strip thinking text when the chat template opens the think tag in the prompt, closes &#35;1652 |
| [`a47ec2a4`](https://github.com/neuml/txtai/pull/1653/commits/a47ec2a44a4fe52c6e2ee12d62e8dd4f0fb285b3) | 2026-11-23 | MaiAditya | Consolidate thinking block removal into a single regex |
| [`01414885`](https://github.com/neuml/txtai/pull/1653/commits/01414885659809432de667a155eda2ddbf12b6d3) | 2026-11-23 | MaiAditya | Simplify thinking block regex |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/python/txtai/pipeline/llm/generation.py</code> | +4 | -1 |
| <code>test/python/testpipeline/testllm/testllm.py</code> | +15 | -0 |
