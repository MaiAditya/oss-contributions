# PostHog/posthog-python #1287: fix(ai): read OpenAI Agents response span usage when sensitive data is off

- **Status:** merged 2026-11-23 by @dustinbyrne
- **Pull request:** https://github.com/PostHog/posthog-python/pull/1287
- **Size:** +49 / -3 in 3 files, 1 commit(s)

## Problem

With sensitive data tracing off, the OpenAI Agents processor read usage only from the missing response, so `$ai_generation` events had no input, output or cache-read tokens.

## Fix

Fell back to `span_data.usage` when the response span has no `Response` object.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`ea7f1d9d`](https://github.com/PostHog/posthog-python/pull/1287/commits/ea7f1d9d38b9b2db60e7ed1daef90195b1d5d75c) | 2026-11-20 | MaiAditya | fix(ai): read OpenAI Agents response span usage when sensitive data is off |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>.sampo/changesets/openai-agents-response-span-usage.md</code> | +5 | -0 |
| <code>posthog/ai/openai&#95;agents/processor.py</code> | +14 | -3 |
| <code>posthog/test/ai/openai&#95;agents/test&#95;processor.py</code> | +30 | -0 |
