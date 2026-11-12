# docling-project/docling #5244: fix(jats): keep the section title next to its label in headings

- **Status:** merged 2026-11-12 by @PeterStaar-IBM
- **Pull request:** https://github.com/docling-project/docling/pull/5244
- **Issue:** https://github.com/docling-project/docling/issues/5243
- **Size:** +89 / -50 in 5 files, 1 commit(s)

## Problem

Labelled sections in JATS articles got only their number as the heading (`## 1.`), so the section title was lost.

## Fix

Joined the section label and title into one heading, e.g. `## 1. Introduction`.

## Commits

| Commit | Date | Author | Message |
|---|---|---|---|
| [`d03c4564`](https://github.com/docling-project/docling/pull/5244/commits/d03c4564aff00c23aed1d243e8ecba0426832023) | 2026-11-08 | MaiAditya | fix(jats): keep the section title next to its label in headings |

## Files changed

| File | Added | Removed |
|---|---|---|
| <code>docling/backend/xml/jats&#95;backend.py</code> | +12 | -6 |
| <code>tests/data/jats/groundtruth/ptag100.xml.itxt</code> | +11 | -11 |
| <code>tests/data/jats/groundtruth/ptag100.xml.json</code> | +22 | -22 |
| <code>tests/data/jats/groundtruth/ptag100.xml.md</code> | +11 | -11 |
| <code>tests/test&#95;backend&#95;jats.py</code> | +33 | -0 |
