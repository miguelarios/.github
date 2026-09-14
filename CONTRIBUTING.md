# Contributing

These conventions apply to every repository owned by `miguelarios` that does not
define its own. They are written for both humans and coding agents. Agents should
read the routing table first and pick a template before creating anything.

## Issue and PR routing

Start here. Pick the row that matches the situation, use that template, and supply
the listed evidence. An issue missing its required evidence will be sent back.

| Situation | Use | Required evidence |
| --- | --- | --- |
| Something behaves incorrectly: crash, regression, wrong output | `bug.md` (`-T Bug`) | Expected vs actual, reproduction steps, logs or output, version/commit, OS and runtime, impact |
| A capability that does not exist yet | `feature.md` (`-T Feature`) | Problem statement naming who is blocked, proposed approach, alternatives including do-nothing, scope, done-when checklist |
| Chore, refactor, dependency bump, deploy, migration | `chore.md` (`-T Chore`) | Goal, acceptance criteria, risk and rollback |
| Docs missing, wrong, or contradicting the code | `docs.md` (`-T Docs`) | Exact file path or URL, expected content, actual content quoted |
| Code is wrong *and* docs are wrong | `bug.md` | File the bug; fix docs in the same PR |
| A question, a support request, or an idea with no concrete change behind it | Do not file an issue | Open a discussion or raise it in your working thread first |
| Security vulnerability | Private advisory, never a public issue | See `SECURITY.md` |
| Opening a PR | `PULL_REQUEST_TEMPLATE.md` | Visible `Closes #<issue>`, problem, what changed, verification output, risk and rollback |

## Conventions

**Titles** use Conventional Commit prefixes: `feat`, `fix`, `refactor`, `chore`,
`docs`, `build`. Describe the user-visible effect, not the implementation.

    fix: uploads over 50MB fail silently when the disk cache is full
    feat: add a --dry-run flag to the sync command

**Labels.** `bug`, `enhancement`, `documentation`, and `chore`. The first three
ship with every GitHub repo; `chore` has to be created per repo.

**Evidence beats assertion.** Every bug needs reproduction steps. Every PR needs
the command that proves it works, with its real output. If something could not be
verified, say which part and why. Do not claim a test passed without pasting it.

**Never commit secrets.** Redact tokens, API keys, and internal hostnames from
logs, screenshots, and config before pasting them anywhere.

## Filing from the command line

Templates resolve through the GitHub API, so these work in any repo owned by this
account even when the repo contains no template files of its own.

```bash
# List what is available in the current repo, including inherited defaults
gh api graphql -f query='{ repository(owner:"miguelarios", name:"REPO") {
  issueTemplates { name filename }
  pullRequestTemplates { filename }
} }'

# File an issue against a template
gh issue create -T Bug --title "fix: ..." --label bug

# Open a PR against the default template
gh pr create -T PULL_REQUEST_TEMPLATE.md --title "fix: ..." --fill-verbose

# Opt into an alternate PR template
gh pr create -T deploy.md --title "chore: bump the search service to 2.14.0"
```

Note that `gh` reads markdown templates only. YAML issue forms are invisible to
the API, which is why the templates here are `.md`.
Template filenames are case-sensitive and differ per repo: a repo with its own
`pull_request_template.md` shadows the inherited `PULL_REQUEST_TEMPLATE.md`.
Always confirm with the GraphQL query above before passing `-T`.

