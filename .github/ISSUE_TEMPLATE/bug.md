---
name: Bug
about: Something behaves differently than it should
title: "fix: "
labels: bug
assignees: ''
---

<!--
Title format: fix: <user-visible symptom> when <trigger>
Good:  fix: the last audio chunk is dropped when input is under 3s
Bad:   fix: add null check in chunker

Fill every section below. Delete the comments, not the headings.
-->

## Symptom

<!-- What goes wrong, in one sentence, from the outside. -->

**Expected:**
**Actual:**

## Reproduction

<!--
Ordered, minimal, copy-pasteable. A failing command beats a paragraph.
If you cannot reproduce it on demand, say so and describe the conditions
when it last occurred. Do not guess at steps.
-->

1.
2.
3.

## Evidence

<!--
Logs, stack trace, screenshot, or command output. Redact tokens, API keys,
and internal hostnames before pasting. If you have nothing, write "none"
rather than leaving this empty.
-->

```
```

## Environment

<!-- Version or commit, OS, runtime, and where it runs (host, container, CI). -->

- Version/commit:
- OS:
- Runtime:
- Deployed on:

## Impact

<!-- Who or what is blocked, and whether a workaround exists. -->
