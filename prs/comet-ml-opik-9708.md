# comet-ml/opik #9708: &#91;issue-9707&#93; &#91;SDK&#93; fix: keep tool calls, finish reason and usage for non-OpenAI aisuite providers

- **Status:** in review (opened 2026-11-23)
- **Pull request:** https://github.com/comet-ml/opik/pull/9708
- **Issue:** https://github.com/comet-ml/opik/issues/9707
- **Size:** +107 / -2 in 5 files, 2 commit(s)

## Problem

`track_aisuite` logged only `message.content` for non-OpenAI aisuite providers, so tool calls, the finish reason and token usage were missing from the span.

## Fix

Logged the whole message and `finish_reason`, and filled span usage from `response.usage` with the OpenAI parser.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`95efdf44`](https://github.com/comet-ml/opik/pull/9708/commits/95efdf44abe3a1687e7e1051584d9ec8f754376f) | 2026-11-23 | MaiAditya | &#91;issue-9707&#93; &#91;SDK&#93; fix: keep tool calls, finish reason and usage for non-OpenAI aisuite providers |
| [`27fe0cdf`](https://github.com/comet-ml/opik/pull/9708/commits/27fe0cdf19a4561c030cc5bf6ef294e30a69e7da) | 2026-11-23 | MaiAditya | &#91;issue-9707&#93; &#91;SDK&#93; test: use shared aisuite model constant |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>sdks/python/src/opik/integrations/aisuite/aisuite&#95;decorator.py</code> | +20 | -1 |
| <code>sdks/python/tests/library&#95;integration/aisuite/test&#95;aisuite.py</code> | +7 | -1 |
| <code>sdks/python/tests/unit/integrations/aisuite/&#95;&#95;init&#95;&#95;.py</code> | +0 | -0 |
| <code>sdks/python/tests/unit/integrations/aisuite/test&#95;aisuite&#95;non&#95;openai&#95;response.py</code> | +79 | -0 |
| <code>sdks/python/tests/unit/test&#95;requirements.txt</code> | +1 | -0 |
