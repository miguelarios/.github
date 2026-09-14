<!--
Title format: type: user-facing description
Types: feat, fix, refactor, chore, docs, build.
Add a parenthesized scope only when it adds clarity.

  Good:  fix(auth): session cookie is dropped when the request is proxied
  Bad:   fix: update middleware config

For fixes, describe the visible symptom and its trigger, not the code change.

Other templates in this repo, opt in by appending to the compare URL:
  ?template=deploy.md   - container/image deploys
  ?template=hotfix.md   - production incident fixes

Template names are case-sensitive and vary per repo. Confirm before using -T:
  gh api graphql -f query='{ repository(owner:"OWNER", name:"REPO") {
    pullRequestTemplates { filename } } }'
-->

## What problem this solves

<!--
The concrete problem in one or two plain sentences. Name the affected
workflow, not the code-level cause.
For fixes: "Fixes: <what goes wrong> when <trigger>."
-->

## Bug fixes only

<!-- Delete this whole section if this is not a bug fix. -->

- **Current behaviour:**
- **Expected behaviour:**
- **Reproduction:**

<!-- Say what the root cause turned out to be, not just the symptom. -->

## What changed

<!--
The shipped solution, briefly. Leave file-by-file walkthroughs to the diff.
Include the decisions a reviewer would otherwise reverse-engineer: why this
approach, what was rejected, what a future reader would trip over.
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

## Release

<!--
Version bumps and changelog entries, or "no release".

Check this repo's own conventions before filling this in — what a release
means, and what merging triggers, differs per repo. Where merging a version
bump publishes automatically, "no release" is a claim worth stating rather
than an absence a reviewer has to interpret.
-->

## Related

<!--
`Closes #N` for each issue this finishes, one per line.
Reference without closing for partial work. Delete if nothing is related.
-->

## Checklist

- [ ] Tests or a lint gate ran and passed, output pasted above
- [ ] No secrets, tokens, or internal hostnames in the diff
- [ ] Docs updated if behavior changed
- [ ] Breaking changes and required manual steps called out above
