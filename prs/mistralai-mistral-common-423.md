# mistralai/mistral-common #423: Raise InvalidToolCallError on malformed v11+ tool call outputs

- **Status:** in review (opened 2026-10-29)
- **Pull request:** https://github.com/mistralai/mistral-common/pull/423
- **Issue:** https://github.com/mistralai/mistral-common/issues/345
- **Size:** +183 / -31 in 2 files, 2 commit(s)

## Problem

Malformed v11+ tool call outputs raised raw `ValidationError` or `ValueError`, or were silently accepted, instead of `InvalidToolCallError`.

## Fix

Raised `InvalidToolCallError` and `InvalidArgsToolCallError` for malformed v11+ tool call outputs.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`7718f481`](https://github.com/mistralai/mistral-common/pull/423/commits/7718f481aef084e8357378582773325836362468) | 2026-10-29 | MaiAditya | Raise InvalidToolCallError on malformed v11+ tool call outputs |
| [`c3c3a62b`](https://github.com/mistralai/mistral-common/pull/423/commits/c3c3a62bebb2cf0efa21248c9408c1c8a18af143) | 2026-10-29 | MaiAditya | Document InvalidToolCallError in &#95;decode&#95;tool&#95;calls |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>src/mistral&#95;common/experimental/tools.py</code> | +77 | -31 |
| <code>tests/unit/mistral&#95;common/experimental/test&#95;tools.py</code> | +106 | -0 |
