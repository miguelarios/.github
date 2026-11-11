# Agent conventions block

Paste the block below into each repo's `CLAUDE.md` (or `AGENTS.md`). It is the
layer that actually makes agents comply, because GitHub's default community
health files are **not** included in clones. An agent working in a checkout
cannot see `CONTRIBUTING.md` or the templates unless it queries the API.

Keep it short on purpose. It points at the canonical source rather than
duplicating it, so the routing table only has to be maintained in one place.

---

```markdown
## Filing issues and PRs

This repo inherits issue and PR templates from `miguelarios/.github`. They are
not in this checkout — resolve them through the API, never freehand the body.

Before filing, read the routing table:
https://github.com/miguelarios/.github/blob/main/CONTRIBUTING.md

Issues — pick the template by situation:

- `-T Bug` — wrong behavior. Requires expected vs actual, repro steps, logs,
  version, OS. Label `bug`.
- `-T Feature` — new capability. Requires a problem statement naming who is
  blocked, plus alternatives. Label `enhancement`.
- `-T Chore` — chore, refactor, bump, deploy. Requires acceptance criteria and
  rollback. Label `chore`.
- `-T Docs` — docs wrong or missing. Requires exact path, expected vs actual.
  Label `documentation`.

```bash
gh issue create -T Bug --title "fix: <symptom> when <trigger>" --label bug
```

PRs — always use the template and always link the issue:

```bash
gh pr create -T PULL_REQUEST_TEMPLATE.md --title "fix: <user-visible description>"
```

Alternate PR templates: `-T deploy.md` for container/image deploys,
`-T hotfix.md` for production incidents.

Rules that apply to every issue and PR here:

- Titles use Conventional Commit prefixes: `feat`, `fix`, `refactor`, `chore`,
  `docs`, `build`. Describe the user-visible effect, not the implementation.
- PRs carry a visible `Closes #<issue>` line.
- Every issue goes in a milestone (`--milestone "v<major>.<minor> <Theme>"`).
  Milestones are the roadmap; do not add a `ROADMAP.md`. File work as issues
  before building it.
- The verification section holds the real command and its real output. Never
  write "tested locally" or claim a passing test without pasting it. State
  explicitly what you could not verify.
- Redact tokens, API keys, and internal hostnames before pasting logs.
```
