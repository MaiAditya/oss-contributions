# PostHog/posthog-python #1299: fix(ai): don't double-count Gemini reasoning tokens in the LangChain callback handler

- **Status:** in review (opened 2026-11-24)
- **Pull request:** https://github.com/PostHog/posthog-python/pull/1299
- **Issue:** https://github.com/PostHog/posthog-python/issues/1298
- **Size:** +109 / -0 in 3 files, 1 commit(s)

## Problem

The LangChain callback handler counted Gemini thinking tokens twice for `ChatGoogleGenerativeAI`, so output was priced at 1603 tokens when 826 were billed.

## Fix

Subtracted reasoning from `output_tokens` for Gemini only when the output already includes it.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`8fe9aab8`](https://github.com/PostHog/posthog-python/pull/1299/commits/8fe9aab89c201090464ee5ee69df795bc5fbc672) | 2026-11-24 | MaiAditya | fix(ai): don't double-count Gemini reasoning tokens in the LangChain callback handler |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>.sampo/changesets/langchain-gemini-reasoning-output-tokens.md</code> | +5 | -0 |
| <code>posthog/ai/langchain/callbacks.py</code> | +25 | -0 |
| <code>posthog/test/ai/langchain/test&#95;callbacks.py</code> | +79 | -0 |
