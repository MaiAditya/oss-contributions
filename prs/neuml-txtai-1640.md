# neuml/txtai #1640: Add OpenAI client LLM and Vectors providers

- **Status:** merged 2026-11-22 by @davidmezzetti
- **Pull request:** https://github.com/neuml/txtai/pull/1640
- **Issue:** https://github.com/neuml/txtai/issues/1639
- **Size:** +569 / -5 in 14 files, 3 commit(s)

## Problem

txtai could only call OpenAI-compatible endpoints through LiteLLM, which pulls in about 60 dependencies, so users who only needed the OpenAI API had to install all of them.

## Fix

Added `OpenAI` LLM and vectors providers on the OpenAI client, with LiteLLM still checked first in autodetect.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`a035e4bb`](https://github.com/neuml/txtai/pull/1640/commits/a035e4bba01ca61342337d3cab37f0d94f5bcb0a) | 2026-11-22 | MaiAditya | Add OpenAI client LLM and Vectors providers, closes &#35;1639 |
| [`5ffcb946`](https://github.com/neuml/txtai/pull/1640/commits/5ffcb946778e3831e88c54fe7e1600007a885188) | 2026-11-22 | MaiAditya | Simplify OpenAI docs |
| [`0505d377`](https://github.com/neuml/txtai/pull/1640/commits/0505d3771d853d71aacd1768d66b49cef104f248) | 2026-11-22 | MaiAditya | Increase OpenAI provider test coverage |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>docs/embeddings/configuration/vectors.md</code> | +7 | -3 |
| <code>docs/install.md</code> | +1 | -1 |
| <code>docs/pipeline/llm/llm.md</code> | +8 | -0 |
| <code>setup.py</code> | +2 | -1 |
| <code>src/python/txtai/pipeline/llm/&#95;&#95;init&#95;&#95;.py</code> | +1 | -0 |
| <code>src/python/txtai/pipeline/llm/factory.py</code> | +7 | -0 |
| <code>src/python/txtai/pipeline/llm/llm.py</code> | +1 | -0 |
| <code>src/python/txtai/pipeline/llm/openai.py</code> | +109 | -0 |
| <code>src/python/txtai/vectors/dense/&#95;&#95;init&#95;&#95;.py</code> | +1 | -0 |
| <code>src/python/txtai/vectors/dense/factory.py</code> | +8 | -0 |
| <code>src/python/txtai/vectors/dense/openai.py</code> | +88 | -0 |
| <code>test/python/testoptional.py</code> | +8 | -0 |
| <code>test/python/testpipeline/testllm/testopenai.py</code> | +172 | -0 |
| <code>test/python/testvectors/testdense/testopenai.py</code> | +156 | -0 |
