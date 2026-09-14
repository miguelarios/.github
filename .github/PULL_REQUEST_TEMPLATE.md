<!--
Title format: type: user-facing description
Types: feat, fix, refactor, chore, docs, build.
Add a parenthesized scope only when it adds clarity.

  Good:  fix(auth): session cookie is dropped when the request is proxied
  Bad:   fix: update middleware config

For fixes, describe the visible symptom and its trigger, not the code change.

Link the issue with a visible line below (not inside a comment):
  Closes #123      - merging this resolves the issue
  Related: #123    - connected, but does not close it

Other templates in this repo, opt in by appending to the compare URL:
  ?template=deploy.md   - container/image deploys
  ?template=hotfix.md   - production incident fixes
-->

## What problem this solves

<!--
The concrete problem in one or two plain sentences. Name the affected
workflow, not the code-level cause.
For fixes: "Fixes: <what goes wrong> when <trigger>."
-->

## What changed

<!--
The shipped solution, briefly. Leave file-by-file walkthroughs to the diff.
Include technical detail only where it explains behavior or a real tradeoff.
-->

## How it was verified

<!--
The actual command and its actual result. "Tested locally" is not evidence.
Paste the smallest meaningful gate: the test run, the lint pass, the curl,
the screenshot. Note anything you could NOT verify.
-->

```
```

## Risk and rollback

<!--
Blast radius, migrations, config changes, and the exact command to revert.
Write "Low: additive only, no migration" if that is genuinely the case.
Do not hide risks or required manual steps in a <details> block.
-->

## Checklist

- [ ] Tests or a lint gate ran and passed, output pasted above
- [ ] No secrets, tokens, or internal hostnames in the diff
- [ ] Docs updated if behavior changed
- [ ] Breaking changes and required manual steps called out above
