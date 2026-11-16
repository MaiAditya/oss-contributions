# PostHog/posthog-python #1256: fix(ai): give Claude Agent SDK generations their tool results and every output block

- **Status:** merged 2026-11-16 by @marandaneto
- **Pull request:** https://github.com/PostHog/posthog-python/pull/1256
- **Size:** +341 / -25 in 5 files, 1 commit(s)

## Problem

In the Claude Agent SDK integration, generations after a tool call had no `$ai_input`, and `$ai_output_choices` kept only the last content block.

## Fix

Appended output blocks and tool results per generation and promoted queued input at the next `message_start`.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`0940a6af`](https://github.com/PostHog/posthog-python/pull/1256/commits/0940a6af6366c17d70b83192a4ce498ef6871fc4) | 2026-11-14 | MaiAditya | fix(ai): give Claude Agent SDK generations their tool results and every output block |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>.sampo/changesets/claude-agent-sdk-tool-results.md</code> | +5 | -0 |
| <code>posthog/ai/claude&#95;agent&#95;sdk/client.py</code> | +25 | -7 |
| <code>posthog/ai/claude&#95;agent&#95;sdk/formatting.py</code> | +36 | -2 |
| <code>posthog/ai/claude&#95;agent&#95;sdk/processor.py</code> | +50 | -16 |
| <code>posthog/test/ai/claude&#95;agent&#95;sdk/test&#95;client.py</code> | +225 | -0 |
