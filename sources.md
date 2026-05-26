# Sources — canonical doc URL manifest

> **Fast path for NotebookLM:** NotebookLM ingests URLs natively — paste any of the URLs below straight in as a "Website" source and it fetches and indexes the page itself. Start with the **landing URL** of each area (NotebookLM follows enough structure to be useful), then add the specific sub-pages you want pinned. For text you want *frozen* against doc drift, paste the matching [`notebook/NN-*.md`](notebook/) file contents as a source instead.

All URLs fetched **2026-05-26** from `docs.github.com` (English) and `cli.github.com`. Where a requested URL redirected or 404'd, the **actual fetched URL** is listed and annotated, so this manifest matches what's in the notebook files.

---

## 00 — Overview (`notebook/00-overview.md`)

**Landing:** https://docs.github.com/en

- https://docs.github.com/en
- https://docs.github.com/en/get-started/start-your-journey/about-github-and-git
- https://docs.github.com/en/get-started/learning-about-github/githubs-plans
- https://docs.github.com/en/get-started/using-github/github-flow
- https://docs.github.com/en/get-started/onboarding/getting-started-with-github-team
- https://docs.github.com/en/get-started/using-git/about-git

_Note: the `/en` landing page is a navigation hub (links, little prose); the substantive overview content lives in the Get-started sub-pages above._

---

## 01 — GitHub Apps (`notebook/01-apps.md`)

**Landing:** https://docs.github.com/en/apps

- https://docs.github.com/en/apps
- https://docs.github.com/en/apps/overview
- https://docs.github.com/en/apps/creating-github-apps/about-creating-github-apps/about-creating-github-apps
- https://docs.github.com/en/apps/creating-github-apps/registering-a-github-app/registering-a-github-app
- https://docs.github.com/en/apps/creating-github-apps/authenticating-with-a-github-app/about-authentication-with-a-github-app
- https://docs.github.com/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-json-web-token-jwt-for-a-github-app
- https://docs.github.com/en/apps/creating-github-apps/authenticating-with-a-github-app/authenticating-as-a-github-app-installation
- https://docs.github.com/en/apps/creating-github-apps/registering-a-github-app/choosing-permissions-for-a-github-app
- https://docs.github.com/en/apps/creating-github-apps/about-creating-github-apps/deciding-when-to-build-a-github-app
- https://docs.github.com/en/apps/oauth-apps/building-oauth-apps/differences-between-github-apps-and-oauth-apps

---

## 02 — REST API (`notebook/02-rest-api.md`) — `apiVersion=2026-03-10`

**Landing:** https://docs.github.com/en/rest?apiVersion=2026-03-10

- https://docs.github.com/en/rest?apiVersion=2026-03-10
- https://docs.github.com/en/rest/about-the-rest-api/about-the-rest-api?apiVersion=2026-03-10
- https://docs.github.com/en/rest/authentication/authenticating-to-the-rest-api?apiVersion=2026-03-10
- https://docs.github.com/en/rest/about-the-rest-api/api-versions?apiVersion=2026-03-10
- https://docs.github.com/en/rest/using-the-rest-api/rate-limits-for-the-rest-api?apiVersion=2026-03-10
- https://docs.github.com/en/rest/using-the-rest-api/using-pagination-in-the-rest-api?apiVersion=2026-03-10
- https://docs.github.com/en/rest/using-the-rest-api/getting-started-with-the-rest-api?apiVersion=2026-03-10
- https://docs.github.com/en/rest/using-the-rest-api/media-types?apiVersion=2026-03-10
- https://docs.github.com/en/rest/using-the-rest-api/troubleshooting-the-rest-api?apiVersion=2026-03-10

---

## 03 — GraphQL API (`notebook/03-graphql.md`)

**Landing:** https://docs.github.com/en/graphql

- https://docs.github.com/en/graphql
- https://docs.github.com/en/graphql/guides/introduction-to-graphql
- https://docs.github.com/en/graphql/overview/about-the-graphql-api
- https://docs.github.com/en/graphql/guides/forming-calls-with-graphql
- https://docs.github.com/en/graphql/overview/public-schema
- https://docs.github.com/en/graphql/guides/using-pagination-in-the-graphql-api
- https://docs.github.com/en/graphql/guides/using-graphql-clients _(was `guides/using-the-explorer`; the GraphQL Explorer page was retired 2025-11-11 and now redirects here)_
- https://docs.github.com/en/graphql/overview/rate-limits-and-query-limits-for-the-graphql-api _(was `overview/resource-limitations`; renamed)_

---

## 04 — Webhooks (`notebook/04-webhooks.md`)

**Landing:** https://docs.github.com/en/webhooks

- https://docs.github.com/en/webhooks
- https://docs.github.com/en/webhooks/about-webhooks
- https://docs.github.com/en/webhooks/types-of-webhooks
- https://docs.github.com/en/webhooks/using-webhooks/creating-webhooks
- https://docs.github.com/en/webhooks/webhook-events-and-payloads
- https://docs.github.com/en/webhooks/using-webhooks/validating-webhook-deliveries
- https://docs.github.com/en/webhooks/using-webhooks/handling-webhook-deliveries
- https://docs.github.com/en/webhooks/using-webhooks/best-practices-for-using-webhooks
- https://docs.github.com/en/webhooks/testing-and-troubleshooting-webhooks/redelivering-webhooks _(the requested `using-webhooks/redelivering-webhooks` 404s; this is the live path)_

_Note: `webhook-events-and-payloads` is a ~85-event reference dump too large to reproduce verbatim in full — the notebook captures the intro, delivery headers, common payload properties, and the complete event-type list; consult the source for per-event payload schemas._

---

## 05 — Discussions (`notebook/05-discussions.md`)

**Landing:** https://docs.github.com/en/discussions

- https://docs.github.com/en/discussions
- https://docs.github.com/en/discussions/collaborating-with-your-community-using-discussions/about-discussions
- https://docs.github.com/en/discussions/quickstart
- https://docs.github.com/en/discussions/managing-discussions-for-your-community/managing-categories-for-discussions _(requested `...-in-your-repository` suffix redirects here)_
- https://docs.github.com/en/discussions/managing-discussions-for-your-community/moderating-discussions
- https://docs.github.com/en/discussions/collaborating-with-your-community-using-discussions/collaborating-with-maintainers-using-discussions
- https://docs.github.com/en/discussions/guides/granting-higher-permissions-to-top-contributors _(requested `managing-discussions-for-your-community/...` 404s; this is the live path)_
- https://docs.github.com/en/graphql/reference/objects#discussion _(bonus: the GraphQL `Discussion` object reference — discussions are mutated via GraphQL, not `gh`)_

---

## 06 — Pages (`notebook/06-pages.md`)

**Landing:** https://docs.github.com/en/pages

- https://docs.github.com/en/pages
- https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages
- https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site
- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages
- https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages
- https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll

---

## 07 — Actions (`notebook/07-actions.md`)

**Landing:** https://docs.github.com/en/actions

The Actions docs were reorganized into `concepts/`, `reference/`, and `how-tos/` paths; the older URLs redirect to these canonical ones (listed below as fetched):

- https://docs.github.com/en/actions
- https://docs.github.com/en/actions/get-started/understand-github-actions
- https://docs.github.com/en/actions/reference/workflows-and-actions/workflow-syntax
- https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows
- https://docs.github.com/en/actions/reference/workflows-and-actions/contexts
- https://docs.github.com/en/actions/reference/workflows-and-actions/expressions
- https://docs.github.com/en/actions/how-tos/write-workflows/choose-what-workflows-do/use-secrets
- https://docs.github.com/en/actions/concepts/security/openid-connect
- https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows
- https://docs.github.com/en/actions/how-tos/manage-runners/github-hosted-runners/use-github-hosted-runners
- https://docs.github.com/en/actions/reference/runners/github-hosted-runners

---

## 08 — GitHub CLI (`notebook/08-github-cli.md`)

**Landing:** https://docs.github.com/en/github-cli

- https://docs.github.com/en/github-cli
- https://docs.github.com/en/github-cli/github-cli/about-github-cli
- https://docs.github.com/en/github-cli/github-cli/quickstart
- https://docs.github.com/en/github-cli/github-cli/creating-github-cli-extensions
- https://docs.github.com/en/github-cli/github-cli/using-github-cli-extensions
- https://cli.github.com/manual/ _(the full command/manual reference)_
- https://cli.github.com/manual/gh_api
- https://cli.github.com/manual/gh_help_formatting
- https://cli.github.com/manual/gh_help_environment

---

### Extraction-fidelity note

Most pages were extracted verbatim. A few of the larger pages were fetched through a tool whose summarizer compressed some connective prose while preserving all code blocks, tables, syntax, and direct quotes verbatim; affected sections carry an inline fidelity note pointing back to the canonical source URL. For word-for-word authority, treat the source URLs in this file as canonical and the notebook files as a pinned, mostly-verbatim mirror.
