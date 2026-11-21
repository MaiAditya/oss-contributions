# pydantic/logfire #2857: Use the serialized value in the JSON schema of Pydantic fields with custom serializers

- **Status:** in review (opened 2026-11-21)
- **Pull request:** https://github.com/pydantic/logfire/pull/2857
- **Issue:** https://github.com/pydantic/logfire/issues/2856
- **Size:** +167 / -4 in 2 files, 1 commit(s)

## Problem

Pydantic fields with a custom serializer were logged in serialized form but given the schema of their original type, so the verbose console exporter crashed, e.g. `ValueError: Invalid isoformat string` on a `strftime` datetime field.

## Fix

Built the schema of fields with custom serializers from `model_dump()` output, falling back to attributes if it raises.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`30a37c42`](https://github.com/pydantic/logfire/pull/2857/commits/30a37c425242cdd8fa26a81375aa904891f73007) | 2026-11-21 | MaiAditya | Use the serialized value in the JSON schema of Pydantic fields with custom serializers |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>logfire-sdk/logfire/&#95;internal/json&#95;schema.py</code> | +49 | -3 |
| <code>tests/test&#95;json&#95;args.py</code> | +118 | -1 |
