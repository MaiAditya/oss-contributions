# huggingface/sentence-transformers #4383: &#91;fix&#93; Always evaluate `main_similarity` when `similarity_fn_names` omits it

- **Status:** merged 2026-11-16 by @tomaarsen
- **Pull request:** https://github.com/huggingface/sentence-transformers/pull/4383
- **Size:** +277 / -86 in 13 files, 4 commit(s)

## Problem

When `similarity_fn_names` or `score_functions` omitted the main similarity, evaluators named a primary metric they never computed, so `SequentialEvaluator` raised `KeyError`.

## Fix

Added the main similarity to the STS and triplet evaluators, and made IR evaluators raise a `ValueError` at construction.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`032f101f`](https://github.com/huggingface/sentence-transformers/pull/4383/commits/032f101f7c7d5ff43b51fbc383764bbb288e5fda) | 2026-11-16 | MaiAditya | &#91;fix&#93; Always evaluate `main_similarity` when `similarity_fn_names` omits it |
| [`db19a08a`](https://github.com/huggingface/sentence-transformers/pull/4383/commits/db19a08a7f916255ebbd644edb4496170331ce2d) | 2026-11-16 | tomaarsen | &#91;fix&#93; Align evaluator similarity selection and validation |
| [`8e8804f9`](https://github.com/huggingface/sentence-transformers/pull/4383/commits/8e8804f9f9df033f9abd0b93d7afabb8fd1a7437) | 2026-11-16 | tomaarsen | Consolidate shared evaluator tests in test&#95;misc.py |
| [`1b3bec8f`](https://github.com/huggingface/sentence-transformers/pull/4383/commits/1b3bec8ff3f672753f14180068d722da10083308) | 2026-11-16 | tomaarsen | Trim redundant evaluator test cases |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>sentence&#95;transformers/multi&#95;vector&#95;encoder/evaluation/information&#95;retrieval.py</code> | +3 | -2 |
| <code>sentence&#95;transformers/multi&#95;vector&#95;encoder/evaluation/nano&#95;beir.py</code> | +3 | -2 |
| <code>sentence&#95;transformers/sentence&#95;transformer/evaluation/binary&#95;classification.py</code> | +34 | -25 |
| <code>sentence&#95;transformers/sentence&#95;transformer/evaluation/embedding&#95;similarity.py</code> | +31 | -27 |
| <code>sentence&#95;transformers/sentence&#95;transformer/evaluation/information&#95;retrieval.py</code> | +12 | -1 |
| <code>sentence&#95;transformers/sentence&#95;transformer/evaluation/nano&#95;beir.py</code> | +3 | -1 |
| <code>sentence&#95;transformers/sentence&#95;transformer/evaluation/triplet.py</code> | +16 | -15 |
| <code>sentence&#95;transformers/sparse&#95;encoder/evaluation/sparse&#95;binary&#95;classification.py</code> | +2 | -1 |
| <code>sentence&#95;transformers/sparse&#95;encoder/evaluation/sparse&#95;embedding&#95;similarity.py</code> | +5 | -4 |
| <code>sentence&#95;transformers/sparse&#95;encoder/evaluation/sparse&#95;information&#95;retrieval.py</code> | +3 | -1 |
| <code>sentence&#95;transformers/sparse&#95;encoder/evaluation/sparse&#95;nano&#95;beir.py</code> | +3 | -1 |
| <code>sentence&#95;transformers/sparse&#95;encoder/evaluation/sparse&#95;triplet.py</code> | +5 | -6 |
| <code>tests/base/evaluation/test&#95;misc.py</code> | +157 | -0 |
