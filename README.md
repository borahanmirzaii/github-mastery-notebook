# github-mastery-notebook

> A private knowledge base that treats **GitHub as a programmable platform** — not just a place to host code — and feeds it into an LLM notebook (NotebookLM / Claude) for self-paced learning.

## Why this exists

We run an AI-agentic, automation-first workflow (WezTerm → Zellij → `gh` → Claude Code). Every layer scripts the layer above, and **GitHub is the single source of truth** for state: Issues, PRs, Projects, Discussions, Releases, Actions. To push that further — agents that open issues, branch, review, deploy, and report back — we need fluency in GitHub's *programmable surface*, not just its web UI.

This repo extracts that surface into study material so an LLM notebook can teach it back to us on demand, and maps each primitive to where it earns its keep in an agentic pipeline.

## What's inside

| Path | What it is | Author |
|---|---|---|
| [`MANIFESTO.md`](MANIFESTO.md) | Why mastering GitHub matters, and a map from our AI-agentic / automation workflow → GitHub primitives | core |
| [`sources.md`](sources.md) | Canonical doc URLs, grouped by area — paste these straight into NotebookLM (it ingests URLs natively) | core |
| [`notebook/`](notebook/) | Heavy verbatim extraction of the docs, one file per platform area — paste these in when you want the text in the notebook itself | core |

### `notebook/` layout

| File | Area | Source |
|---|---|---|
| `00-overview.md` | GitHub docs home / platform overview | https://docs.github.com/en |
| `01-apps.md` | GitHub Apps | https://docs.github.com/en/apps |
| `02-rest-api.md` | REST API (`apiVersion=2026-03-10`) | https://docs.github.com/en/rest |
| `03-graphql.md` | GraphQL API | https://docs.github.com/en/graphql |
| `04-webhooks.md` | Webhooks | https://docs.github.com/en/webhooks |
| `05-discussions.md` | Discussions | https://docs.github.com/en/discussions |
| `06-pages.md` | Pages | https://docs.github.com/en/pages |
| `07-actions.md` | Actions | https://docs.github.com/en/actions |
| `08-github-cli.md` | GitHub CLI (`gh`) | https://docs.github.com/en/github-cli |

## How to use it with an LLM notebook

1. **Fastest path — URLs.** Open NotebookLM, create a notebook, and add the URLs from [`sources.md`](sources.md) as sources. NotebookLM fetches and indexes them itself.
2. **Offline / pinned text.** When you want the exact text frozen in the notebook (docs change), paste the relevant `notebook/NN-*.md` file contents as a source instead.
3. **Start with the map, not the reference.** Read [`MANIFESTO.md`](MANIFESTO.md) first so each primitive lands against a *use case* ("this is how an agent opens a PR and waits for checks"), then drill into the area files.

## Conventions

- **Single source of truth is GitHub.** Briefs are Issue bodies; work is tracked in Issues/PRs, never side-channel docs.
- **Branch model:** `dev` = integration, `main` = release-only. Work branches off `dev`.
- **Identity:** pinned per repo via `.sid-identity` + `.envrc` (both gitignored). SSH-only remote.
