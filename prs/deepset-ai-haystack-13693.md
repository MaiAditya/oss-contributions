# deepset-ai/haystack #13693: fix: avoid whitespace-only and over-long chunks in RecursiveDocumentSplitter

- **Status:** in review (opened 2026-11-11)
- **Pull request:** https://github.com/deepset-ai/haystack/pull/13693
- **Issue:** https://github.com/deepset-ai/haystack/issues/13692
- **Size:** +108 / -8 in 3 files, 1 commit(s)

## Problem

`RecursiveDocumentSplitter` produced whitespace-only chunks for text with long runs of newlines, and with the sentence separator could exceed `split_length`.

## Fix

Joined whitespace-only chunks to their neighbours and kept sentence chunks within `split_length`.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`37fb7afa`](https://github.com/deepset-ai/haystack/pull/13693/commits/37fb7afa0ba1e57492a78ea5a9c1357fcb02b591) | 2026-11-11 | MaiAditya | fix: avoid whitespace-only and over-long chunks in RecursiveDocumentSplitter |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>haystack/components/preprocessors/recursive&#95;splitter.py</code> | +23 | -7 |
| <code>releasenotes/notes/fix-recursive-splitter-whitespace-only-chunks-7a3474416529c4bf.yaml</code> | +15 | -0 |
| <code>test/components/preprocessors/test&#95;recursive&#95;splitter.py</code> | +70 | -1 |
