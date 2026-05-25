# Manifesto — GitHub as the operating system of an agentic workflow

> **TL;DR:** GitHub is not a place we *put* code. It is the runtime our agents *live in*. Every unit of state an autonomous builder needs — the brief, the work tree, the review, the gate, the audit log, the release — already has a first-class GitHub primitive. Master the programmable surface and one agent can own the entire loop, from "open the issue" to "cut the release," without a human at the keyboard.

---

## 1. Why master the platform

Our stack is a tower where every layer scripts the layer above it:

```
WezTerm  →  Zellij  →  Claude Code  →  gh / REST / GraphQL  →  GitHub state
(host)      (mux)       (agent)         (the hands)             (source of truth)
```

The terminal multiplexer spawns tabs. The agent drives the tabs. The agent's *hands* are `gh` and the API. And the thing those hands act on — the single, durable source of truth for everything — is **GitHub**.

Most teams treat GitHub as a code host with some project-management features bolted on. That framing leaves the leverage on the table. The real shape of GitHub is a **programmable platform**: a coherent API surface (REST + GraphQL), an event bus (Webhooks), an automation runtime with a scheduler (Actions + cron), an identity-and-permission model built for machines (Apps), durable long-form threads (Discussions), a publishing target (Pages), and board state (Projects) — all addressable from a CLI an agent can call.

The leverage is this: **an agent that is fluent in GitHub's API surface can own the whole loop.**

```
open issue → branch → worktree → commit → open PR → run checks → review → merge → release
```

Every arrow in that loop is a GitHub API call. A human is not required to move work from one arrow to the next — they are required only to *decide*. When the agent speaks the platform natively:

- **No side-channel state.** The brief is the issue body, not a Notion doc that drifts out of sync. The execution log is the issue thread, not a Slack scrollback that nobody can replay. If a tab dies, the next operator reconstructs everything from GitHub alone.
- **The loop is auditable.** Issues, PRs, reviews, merges, and releases are immutable, timestamped, and linked. The history *is* the audit trail — for free.
- **The loop is composable.** A webhook fires → an Action runs → the Action calls the API → the API updates an issue → the issue triggers another webhook. Agents slot into any seam.
- **Least privilege is native.** A GitHub App with fine-grained permissions and short-lived installation tokens is a far safer identity for an autonomous agent than a long-lived personal access token with the keys to everything.

Mastering the platform is therefore not a "nice to have" reference exercise. It is the difference between an agent that *asks a human to click things* and an agent that *runs the loop itself* and surfaces only the decisions that genuinely need a human.

---

## 2. Workflow → primitives map

Two views of the same truth: first the **solo-builder loop** (the steps), then the **platform areas** (the capabilities). Each row answers one question: *what does an agent actually use this for?*

### 2a. The solo-builder loop, step by step

| Loop step | GitHub primitive | Agentic use case |
|---|---|---|
| **IDEA / brief** | **Issue** (body) | The brief is the issue body. No `docs/agent-tasks/` indirection — the issue *is* the spec the worker reads via `gh issue view`. |
| **Task queue** | **Issues** (labels, milestones, assignees) | The open-issue list is the backlog. Labels (`area:`, `kind:`, `priority:`) and milestones let an agent triage and pick the next unit of work. |
| **Branch** | `gh issue develop` | Server-side links a branch to the issue, so the eventual PR auto-closes the issue on merge. The agent never has to remember the cross-link — the platform tracks it. |
| **Work + log** | **Issue comments** | The canonical execution log. The agent posts progress at each cadence trigger (Starting / Investigation / Blocker / PR opened / Wrap-up). Crash-resilient by construction. |
| **Checkpoint** | **Pull Request** (draft) | The PR is the unit of shippable work. Opened as a draft while in flight; the diff is the proposal. |
| **Gate** | **Actions** (checks) + `gh pr checks` | CI runs on the PR; the agent reads pass/fail programmatically and reacts (fix, re-run, escalate) without a human watching the spinner. |
| **Review** | **PR reviews** (`gh pr review`) | Approve / request-changes / comment — the decision surface. Multi-agent or human review attaches here. |
| **Merge** | `gh pr merge --squash` | The Lead's decision, executed as one API call. The linked issue auto-closes. |
| **Release** | **Releases** (`gh release create --generate-notes`) | Promote `dev → main`, tag, and auto-generate notes from merged PRs. The changelog writes itself. |
| **Board state** | **Projects v2** | As work moves (Todo → In Progress → In Review → Done), the agent updates the board so the human sees status at a glance without asking. |

### 2b. The platform areas, by leverage

| Area | What it is | Why it earns its keep for an agent |
|---|---|---|
| **Issues** | Work items with body, comments, labels, milestones, assignees | **The brief, the task queue, and the canonical execution log** — all in one durable, linkable, replayable object. The single source of truth for *what to do* and *what was done*. |
| **gh CLI** | The official command-line client | **The agent's hands on GitHub** — the default interface. Most of the loop is a one-liner. Scriptable, composable with shell, and it shells out to the API when needed. |
| **REST + GraphQL** | The programmatic API surface | **State read/write when `gh` isn't enough.** REST for resource CRUD and pagination; **GraphQL for Discussions, Projects v2, and bulk reads** where one query replaces dozens of REST round-trips. The escape hatch under every `gh` command. |
| **Webhooks** | Outbound event notifications (HTTP POST on events) | **The event triggers.** An agent reacts to *"PR opened"*, *"check failed"*, *"issue labeled"* — turning a polling loop into an event-driven pipeline. Validate the signature, then act. |
| **Actions** | CI/CD runtime with a cron scheduler | **The automation runtime and scheduler.** CI gates that block bad merges, plus `schedule:` cron that dispatches agents on a timer. The place where automation actually *runs*, server-side, on GitHub's compute. |
| **Apps** | Installable identity with fine-grained, scoped permissions | **The identity and least-privilege model for autonomous agents.** Installation tokens are short-lived and narrowly scoped — strictly superior to long-lived PATs for any agent that runs unattended in production. This is how you give an agent *exactly* the access it needs and nothing more. |
| **Discussions** | Threaded, long-form, durable conversations | **Durable RFC / design threads** that agents read and append to. Where a multi-step decision (the kind that outlives a single issue) accretes context before it converges into a spec. GraphQL-only to mutate — a good forcing function for API fluency. |
| **Pages** | Static-site hosting straight from a repo | **Publishing agent output** — dashboards, generated reports, status boards, rendered docs. The agent builds an artifact and ships it to a URL, no separate hosting required. |
| **Projects** | Cross-repo boards with custom fields | **Board state agents update** as work moves. The human-facing status layer; the agent keeps it honest so nobody has to ask "where is this?". |

---

## 3. The throughline

Read the two tables together and the pattern is unmistakable: **for every kind of state an autonomous builder needs, GitHub already has a first-class, API-addressable primitive.** There is no gap that forces us out to a side-channel tool.

That is *why* this notebook exists. To run the loop without a human in the keyboard, the agent has to be fluent — not just in *that* `gh` command, but in the REST endpoint underneath it, the GraphQL mutation when `gh` falls short, the webhook that should have triggered it, and the App permission that authorizes it. The rest of this repo is that fluency, extracted verbatim from the source and mapped, here, to where each piece earns its keep.

> **Start with this map, not the reference.** Each primitive lands harder when you already know the use case it serves. Then drill into the area files in [`notebook/`](notebook/) for the verbatim detail.
