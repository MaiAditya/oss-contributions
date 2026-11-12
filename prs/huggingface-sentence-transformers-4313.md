# huggingface/sentence-transformers #4313: &#91;fix&#93; Score ParaphraseMiningEvaluator with the model's similarity function

- **Status:** merged 2026-11-09 by @tomaarsen
- **Pull request:** https://github.com/huggingface/sentence-transformers/pull/4313
- **Size:** +23 / -2 in 2 files, 1 commit(s)

## Problem

`ParaphraseMiningEvaluator` always ranked pairs by cosine similarity, so models trained for dot product or distances got wrong scores and thresholds.

## Fix

Scored paraphrase mining with the model's own similarity function.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`70c4f9b8`](https://github.com/huggingface/sentence-transformers/pull/4313/commits/70c4f9b881458d707f871b2b16d7e8cdf329d8aa) | 2026-11-02 | MaiAditya | &#91;fix&#93; Score ParaphraseMiningEvaluator with the model's similarity function |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>sentence&#95;transformers/sentence&#95;transformer/evaluation/paraphrase&#95;mining.py</code> | +3 | -2 |
| <code>tests/sentence&#95;transformer/evaluation/test&#95;paraphrase&#95;mining&#95;evaluator.py</code> | +20 | -0 |
