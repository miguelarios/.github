# .github

Default community health files for every repository owned by `miguelarios`.

GitHub serves these to any repo of mine that does not define its own equivalent,
regardless of whether that repo is public or private. This repo must stay
**public** for that inheritance to work — the files it contains are conventions,
not code, and nothing here is sensitive.

## Contents

| Path | Applies to |
| --- | --- |
| `CONTRIBUTING.md` | Issue and PR routing table. The canonical source of conventions. |
| `SECURITY.md` | Private vulnerability reporting. |
| `.github/ISSUE_TEMPLATE/` | `bug`, `feature`, `task`, `docs` templates plus `config.yml`. |
| `.github/PULL_REQUEST_TEMPLATE.md` | Default PR template. |
| `.github/PULL_REQUEST_TEMPLATE/` | Alternates: `deploy.md`, `hotfix.md`. Opt in with `?template=`. |
| `agent-conventions.md` | Block to paste into each repo's `CLAUDE.md`. Not inherited by GitHub. |

## Overriding per repo

Any repo that defines its own file of a given type wins. Issue templates
override at the **folder** level: a repo with its own `.github/ISSUE_TEMPLATE/`
ignores all four defaults, not just the ones it redefines.

## Why markdown and not YAML issue forms

YAML issue forms render nicely in the browser but are invisible to the GitHub
API, so `gh issue create -T` and every coding agent see nothing. Markdown
templates are exposed through the GraphQL `issueTemplates` field and work from
the CLI. These repos are filed against mostly by agents, so markdown wins.

## Important limitation

Default community health files are **not** included in clones. An agent working
in a local checkout cannot read them from disk — it has to hit the API. That is
what `agent-conventions.md` exists to solve.
