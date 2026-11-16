# huggingface/sentence-transformers #4383: &#91;fix&#93; Always evaluate `main_similarity` when `similarity_fn_names` omits it

- **Status:** in review (opened 2026-11-16)
- **Pull request:** https://github.com/huggingface/sentence-transformers/pull/4383
- **Size:** +119 / -14 in 12 files, 1 commit(s)

## Problem

When `similarity_fn_names` or `score_functions` omitted the main similarity, evaluators named a primary metric they never computed, so `SequentialEvaluator` raised `KeyError`.

## Fix

Added the main similarity to the STS and triplet evaluators, and made IR evaluators raise a `ValueError` at construction.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`032f101f`](https://github.com/huggingface/sentence-transformers/pull/4383/commits/032f101f7c7d5ff43b51fbc383764bbb288e5fda) | 2026-11-16 | MaiAditya | &#91;fix&#93; Always evaluate `main_similarity` when `similarity_fn_names` omits it |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>sentence&#95;transformers/multi&#95;vector&#95;encoder/evaluation/information&#95;retrieval.py</code> | +2 | -1 |
| <code>sentence&#95;transformers/multi&#95;vector&#95;encoder/evaluation/nano&#95;beir.py</code> | +2 | -1 |
| <code>sentence&#95;transformers/sentence&#95;transformer/evaluation/embedding&#95;similarity.py</code> | +6 | -4 |
| <code>sentence&#95;transformers/sentence&#95;transformer/evaluation/information&#95;retrieval.py</code> | +15 | -1 |
| <code>sentence&#95;transformers/sentence&#95;transformer/evaluation/nano&#95;beir.py</code> | +4 | -1 |
| <code>sentence&#95;transformers/sentence&#95;transformer/evaluation/triplet.py</code> | +7 | -3 |
| <code>sentence&#95;transformers/sparse&#95;encoder/evaluation/sparse&#95;information&#95;retrieval.py</code> | +2 | -1 |
| <code>sentence&#95;transformers/sparse&#95;encoder/evaluation/sparse&#95;nano&#95;beir.py</code> | +2 | -1 |
| <code>tests/sentence&#95;transformer/evaluation/test&#95;embedding&#95;similarity&#95;evaluator.py</code> | +20 | -0 |
| <code>tests/sentence&#95;transformer/evaluation/test&#95;information&#95;retrieval&#95;evaluator.py</code> | +33 | -1 |
| <code>tests/sentence&#95;transformer/evaluation/test&#95;nanobeir&#95;evaluator.py</code> | +12 | -0 |
| <code>tests/sentence&#95;transformer/evaluation/test&#95;triplet&#95;evaluator.py</code> | +14 | -0 |
