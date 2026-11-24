# Arize-ai/phoenix #18129: docs(client): fix PromptVersion and get&#95;traces examples in README

- **Status:** merged 2026-11-24 by @mikeldking
- **Pull request:** https://github.com/Arize-ai/phoenix/pull/18129
- **Issue:** https://github.com/Arize-ai/phoenix/issues/18128
- **Size:** +8 / -5 in 2 files, 1 commit(s)

## Problem

Two `phoenix-client` README examples failed when run: `PromptVersion(messages=...)` raised `TypeError` and the traces loop raised `AttributeError` on `get_traces` dicts.

## Fix

Passed the messages positionally and read trace dict keys, computing latency from `start_time` and `end_time`.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`8dd593fa`](https://github.com/Arize-ai/phoenix/pull/18129/commits/8dd593fa02d89314a9ddf25ae41709823c3225d7) | 2026-11-19 | MaiAditya | docs(client): fix PromptVersion and get&#95;traces examples in README |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>packages/phoenix-client/README.md</code> | +7 | -4 |
| <code>packages/phoenix-client/docs/source/index.md</code> | +1 | -1 |
