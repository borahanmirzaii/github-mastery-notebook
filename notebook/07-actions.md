# GitHub Actions

> **Source root:** https://docs.github.com/en/actions
> **Fetched:** 2026-05-26
> **Area:** 07 — Actions

## Table of contents

- [GitHub Actions documentation (landing)](#github-actions-documentation-landing)
- [Understanding GitHub Actions](#understanding-github-actions)
- [Workflow syntax for GitHub Actions](#workflow-syntax-for-github-actions)
- [Events that trigger workflows](#events-that-trigger-workflows)
- [Contexts reference](#contexts-reference)
- [Evaluate expressions in workflows and actions](#evaluate-expressions-in-workflows-and-actions)
- [Using secrets in GitHub Actions](#using-secrets-in-github-actions)
- [OpenID Connect](#openid-connect)
- [Reuse workflows](#reuse-workflows)
- [GitHub-hosted runners (use + reference specs)](#github-hosted-runners-use--reference-specs)

> **Extraction note:** docs.github.com Actions reference pages are very large. The fetch backend reproduced several pages fully verbatim (Understanding, Events, Contexts, OIDC, Reuse workflows, runner spec tables). For two pages (Workflow syntax, Expressions) the backend compressed long prose descriptions while preserving all headings, tables, operators, function syntax, and YAML examples; those sections are marked. For the Secrets how-to page the backend heavily compressed prose; the captured commands/YAML/structure are preserved with a note. Several listed task URLs (old paths) now redirect to canonical `reference/`, `concepts/`, and `how-tos/` URLs — the redirect targets actually fetched are recorded under each section's `> Source:` line.

---

## GitHub Actions documentation (landing)

> Source: https://docs.github.com/en/actions

# GitHub Actions documentation

Automate, customize, and execute your software development workflows right in your repository with GitHub Actions. You can discover, create, and share actions to perform any job you'd like, including CI/CD, and combine actions in a completely customized workflow.

## Recommended

* [Quickstart for GitHub Actions](/en/actions/get-started/quickstart) — Try out the core features of GitHub Actions in minutes.
* [Understanding GitHub Actions](/en/actions/get-started/understand-github-actions) — Learn the basics of core concepts and essential terminology in GitHub Actions.
* [Using GitHub-hosted runners](/en/actions/how-tos/manage-runners/github-hosted-runners/use-github-hosted-runners) — You can assign a job to run on a virtual machine hosted by GitHub.
* [Workflow syntax for GitHub Actions](/en/actions/reference/workflows-and-actions/workflow-syntax) — A workflow is a configurable automated process made up of one or more jobs. You must create a YAML file to define your workflow configuration.
* [Events that trigger workflows](/en/actions/reference/workflows-and-actions/events-that-trigger-workflows) — You can configure your workflows to run when specific activity on GitHub happens, at a scheduled time, or when an event outside of GitHub occurs.
* [Using artifact attestations to establish provenance for builds](/en/actions/how-tos/secure-your-work/use-artifact-attestations/use-artifact-attestations) — Artifact attestations enable you to increase the supply chain security of your builds by establishing where and how your software was built.
* [Migrating to GitHub Actions](/en/actions/tutorials/migrate-to-github-actions) — Learn how to migrate your existing CI/CD workflows to GitHub Actions.
* [Reuse workflows](/en/actions/how-tos/reuse-automations/reuse-workflows) — Learn how to avoid duplication when creating a workflow by reusing existing workflows.
* [Viewing GitHub Actions metrics](/en/actions/how-tos/administer/view-metrics) — You can view metrics to monitor where your organization or repositories use GitHub Actions and how they are performing.

## Articles (selected index)

**Getting started**

* [Understanding GitHub Actions](/en/actions/get-started/understand-github-actions) — Learn the basics of core concepts and essential terminology in GitHub Actions.
* [Quickstart for GitHub Actions](/en/actions/get-started/quickstart) — Try out the core features of GitHub Actions in minutes.
* [Continuous integration](/en/actions/get-started/continuous-integration) — You can create custom continuous integration (CI) workflows directly in your GitHub repository with GitHub Actions.
* [Continuous deployment](/en/actions/get-started/continuous-deployment) — You can create custom continuous deployment (CD) workflows directly in your GitHub repository with GitHub Actions.
* [GitHub Actions vs GitHub Apps](/en/actions/get-started/actions-vs-apps) — Learn about the key differences between GitHub Actions and GitHub Apps to help you decide which is right for your use cases.

**Concepts — Workflows and actions**

* [Workflows](/en/actions/concepts/workflows-and-actions/workflows)
* [Variables](/en/actions/concepts/workflows-and-actions/variables)
* [Contexts](/en/actions/concepts/workflows-and-actions/contexts)
* [Expressions](/en/actions/concepts/workflows-and-actions/expressions)
* [Reusing workflow configurations](/en/actions/concepts/workflows-and-actions/reusing-workflow-configurations)
* [About custom actions](/en/actions/concepts/workflows-and-actions/custom-actions)
* [Deployment environments](/en/actions/concepts/workflows-and-actions/deployment-environments)
* [Concurrency](/en/actions/concepts/workflows-and-actions/concurrency)
* [Workflow artifacts](/en/actions/concepts/workflows-and-actions/workflow-artifacts)
* [Dependency caching](/en/actions/concepts/workflows-and-actions/dependency-caching)
* [Notifications for workflow runs](/en/actions/concepts/workflows-and-actions/notifications-for-workflow-runs)

**Concepts — Runners**

* [GitHub-hosted runners](/en/actions/concepts/runners/github-hosted-runners)
* [Larger runners](/en/actions/concepts/runners/larger-runners)
* [Self-hosted runners](/en/actions/concepts/runners/self-hosted-runners)
* [Private networking with GitHub-hosted runners](/en/actions/concepts/runners/private-networking)
* [Runner groups](/en/actions/concepts/runners/runner-groups)
* [Runner scale sets](/en/actions/concepts/runners/runner-scale-sets)
* [Actions Runner Controller](/en/actions/concepts/runners/actions-runner-controller)
* [Support for Actions Runner Controller](/en/actions/concepts/runners/support-for-arc)

**Concepts — Security**

* [Secrets](/en/actions/concepts/security/secrets)
* [GITHUB_TOKEN](/en/actions/concepts/security/github_token)
* [OpenID Connect](/en/actions/concepts/security/openid-connect)
* [Artifact attestations](/en/actions/concepts/security/artifact-attestations)
* [Script injections](/en/actions/concepts/security/script-injections)
* [Compromised runners](/en/actions/concepts/security/compromised-runners)
* [Kubernetes admissions controller](/en/actions/concepts/security/kubernetes-admissions-controller)

**Concepts — other**

* [About GitHub Actions metrics](/en/actions/concepts/metrics)
* [Billing and usage](/en/actions/concepts/billing-and-usage)

**How-tos — Write workflows**

* [Using workflow templates](/en/actions/how-tos/write-workflows/use-workflow-templates)
* [Triggering a workflow](/en/actions/how-tos/write-workflows/choose-when-workflows-run/trigger-a-workflow)
* [Using conditions to control job execution](/en/actions/how-tos/write-workflows/choose-when-workflows-run/control-jobs-with-conditions)
* [Control the concurrency of workflows and jobs](/en/actions/how-tos/write-workflows/choose-when-workflows-run/control-workflow-concurrency)
* [Choosing the runner for a job](/en/actions/how-tos/write-workflows/choose-where-workflows-run/choose-the-runner-for-a-job)
* [Running jobs in a container](/en/actions/how-tos/write-workflows/choose-where-workflows-run/run-jobs-in-a-container)
* [Using jobs in a workflow](/en/actions/how-tos/write-workflows/choose-what-workflows-do/use-jobs)
* [Using pre-written building blocks in your workflow](/en/actions/how-tos/write-workflows/choose-what-workflows-do/find-and-customize-actions)
* [Using GitHub CLI in workflows](/en/actions/how-tos/write-workflows/choose-what-workflows-do/use-github-cli)
* [Adding scripts to your workflow](/en/actions/how-tos/write-workflows/choose-what-workflows-do/add-scripts)
* [Using secrets in GitHub Actions](/en/actions/how-tos/write-workflows/choose-what-workflows-do/use-secrets)
* [Store information in variables](/en/actions/how-tos/write-workflows/choose-what-workflows-do/use-variables)
* [Passing information between jobs](/en/actions/how-tos/write-workflows/choose-what-workflows-do/pass-job-outputs)
* [Setting a default shell and working directory](/en/actions/how-tos/write-workflows/choose-what-workflows-do/set-default-values-for-jobs)
* [Deploying to a specific environment](/en/actions/how-tos/write-workflows/choose-what-workflows-do/deploy-to-environment)
* [Running variations of jobs in a workflow](/en/actions/how-tos/write-workflows/choose-what-workflows-do/run-job-variations)

**How-tos — Reuse automations**

* [Reuse workflows](/en/actions/how-tos/reuse-automations/reuse-workflows)
* [Creating workflow templates for your organization](/en/actions/how-tos/reuse-automations/create-workflow-templates)
* [Sharing actions and workflows from your private repository](/en/actions/how-tos/reuse-automations/share-across-private-repositories)
* [Sharing actions and workflows with your organization](/en/actions/how-tos/reuse-automations/share-with-your-organization)

**How-tos — Secure your work / harden deployments (OIDC)**

* [Using artifact attestations to establish provenance for builds](/en/actions/how-tos/secure-your-work/use-artifact-attestations/use-artifact-attestations)
* [Configuring OpenID Connect in Amazon Web Services](/en/actions/how-tos/secure-your-work/security-harden-deployments/oidc-in-aws)
* [Configuring OpenID Connect in Azure](/en/actions/how-tos/secure-your-work/security-harden-deployments/oidc-in-azure)
* [Configuring OpenID Connect in Google Cloud Platform](/en/actions/how-tos/secure-your-work/security-harden-deployments/oidc-in-google-cloud-platform)
* [Configuring OpenID Connect in HashiCorp Vault](/en/actions/how-tos/secure-your-work/security-harden-deployments/oidc-in-hashicorp-vault)
* [Configuring OpenID Connect in cloud providers](/en/actions/how-tos/secure-your-work/security-harden-deployments/oidc-in-cloud-providers)
* [Using OpenID Connect with reusable workflows](/en/actions/how-tos/secure-your-work/security-harden-deployments/oidc-with-reusable-workflows)

**Reference — Workflows and actions**

* [Workflow syntax for GitHub Actions](/en/actions/reference/workflows-and-actions/workflow-syntax)
* [Events that trigger workflows](/en/actions/reference/workflows-and-actions/events-that-trigger-workflows)
* [Workflow commands for GitHub Actions](/en/actions/reference/workflows-and-actions/workflow-commands)
* [Variables reference](/en/actions/reference/workflows-and-actions/variables)
* [Evaluate expressions in workflows and actions](/en/actions/reference/workflows-and-actions/expressions)
* [Contexts reference](/en/actions/reference/workflows-and-actions/contexts)
* [Deployments and environments](/en/actions/reference/workflows-and-actions/deployments-and-environments)
* [Dependency caching reference](/en/actions/reference/workflows-and-actions/dependency-caching)
* [Reusing workflow configurations](/en/actions/reference/workflows-and-actions/reusing-workflow-configurations)
* [Metadata syntax reference](/en/actions/reference/workflows-and-actions/metadata-syntax)
* [Workflow cancellation reference](/en/actions/reference/workflows-and-actions/workflow-cancellation)
* [Dockerfile support for GitHub Actions](/en/actions/reference/workflows-and-actions/dockerfile-support)

**Reference — Runners**

* [GitHub-hosted runners reference](/en/actions/reference/runners/github-hosted-runners)
* [Larger runners reference](/en/actions/reference/runners/larger-runners)
* [Self-hosted runners reference](/en/actions/reference/runners/self-hosted-runners)

**Reference — Security & limits**

* [Secure use reference](/en/actions/reference/security/secure-use)
* [Secrets reference](/en/actions/reference/security/secrets)
* [OpenID Connect reference](/en/actions/reference/security/oidc)
* [Actions limits](/en/actions/reference/limits)

---

## Understanding GitHub Actions

> Source: https://docs.github.com/en/actions/get-started/understand-github-actions
> (Listed task URL `/en/actions/about-github-actions/understanding-github-actions` redirects here.)

# Understanding GitHub Actions

Learn the basics of core concepts and essential terminology in GitHub Actions.

## Overview

GitHub Actions is a continuous integration and continuous delivery (CI/CD) platform that allows you to automate your build, test, and deployment pipeline. You can create workflows that build and test every pull request to your repository, or deploy merged pull requests to production.

GitHub Actions goes beyond just DevOps and lets you run workflows when other events happen in your repository. For example, you can run a workflow to automatically add the appropriate labels whenever someone creates a new issue in your repository.

GitHub provides Linux, Windows, and macOS virtual machines to run your workflows, or you can host your own self-hosted runners in your own data center or cloud infrastructure.

## The components of GitHub Actions

You can configure a GitHub Actions **workflow** to be triggered when an **event** occurs in your repository, such as a pull request being opened or an issue being created. Your workflow contains one or more **jobs** which can run in sequential order or in parallel. Each job will run inside its own virtual machine **runner**, or inside a container, and has one or more **steps** that either run a script that you define or run an **action**, which is a reusable extension that can simplify your workflow.

### Workflows

A **workflow** is a configurable automated process that will run one or more jobs. Workflows are defined by a YAML file checked in to your repository and will run when triggered by an event in your repository, or they can be triggered manually, or at a defined schedule.

Workflows are defined in the `.github/workflows` directory in a repository. A repository can have multiple workflows, each of which can perform a different set of tasks such as:

* Building and testing pull requests
* Deploying your application every time a release is created
* Adding a label whenever a new issue is opened

You can reference a workflow within another workflow. For more information, see [Reuse workflows](/en/actions/using-workflows/reusing-workflows).

For more information, see [Writing workflows](/en/actions/using-workflows).

### Events

An **event** is a specific activity in a repository that triggers a **workflow** run. For example, an activity can originate from GitHub when someone creates a pull request, opens an issue, or pushes a commit to a repository. You can also trigger a workflow to run on a [schedule](/en/actions/using-workflows/events-that-trigger-workflows#schedule), by [posting to a REST API](/en/rest/repos/repos#create-a-repository-dispatch-event), or manually.

For a complete list of events that can be used to trigger workflows, see [Events that trigger workflows](/en/actions/using-workflows/events-that-trigger-workflows).

### Jobs

A **job** is a set of **steps** in a workflow that is executed on the same **runner**. Each step is either a shell script that will be executed, or an **action** that will be run. Steps are executed in order and are dependent on each other. Since each step is executed on the same runner, you can share data from one step to another. For example, you can have a step that builds your application followed by a step that tests the application that was built.

You can configure a job's dependencies with other jobs; by default, jobs have no dependencies and run in parallel. When a job takes a dependency on another job, it waits for the dependent job to complete before running.

You can also use a **matrix** to run the same job multiple times, each with a different combination of variables—like operating systems or language versions.

For example, you might configure multiple build jobs for different architectures without any job dependencies and a packaging job that depends on those builds. The build jobs run in parallel, and once they complete successfully, the packaging job runs.

For more information, see [Choosing what your workflow does](/en/actions/using-jobs).

### Actions

An **action** is a pre-defined, reusable set of jobs or code that performs specific tasks within a **workflow**, reducing the amount of repetitive code you write in your workflow files. Actions can perform tasks such as:

* Pulling your Git repository from GitHub
* Setting up the correct toolchain for your build environment
* Setting up authentication to your cloud provider

You can write your own actions, or you can find actions to use in your workflows in the GitHub Marketplace.

For more information on actions, see [Reusing automations](/en/actions/creating-actions).

### Runners

A **runner** is a server that runs your workflows when they're triggered. Each runner can run a single **job** at a time. GitHub provides Ubuntu Linux, Microsoft Windows, and macOS runners to run your **workflows**. Each workflow run executes in a fresh, newly-provisioned virtual machine.

GitHub also offers larger runners, which are available in larger configurations. For more information, see [Using larger runners](/en/actions/using-github-hosted-runners/using-larger-runners).

If you need a different operating system or require a specific hardware configuration, you can host your own runners.

For more information about self-hosted runners, see [Managing self-hosted runners](/en/actions/how-tos/managing-self-hosted-runners).

## Next steps

GitHub Actions can help you automate nearly every aspect of your application development processes. Ready to get started? Here are some helpful resources for taking your next steps with GitHub Actions:

* To create a GitHub Actions workflow, see [Using workflow templates](/en/actions/learn-github-actions/using-starter-workflows).
* For continuous integration (CI) workflows, see [Building and testing your code](/en/actions/automating-builds-and-tests).
* For building and publishing packages, see [Publishing packages](/en/actions/publishing-packages).
* For deploying projects, see [Deploying to third-party platforms](/en/actions/deployment).
* For automating tasks and processes on GitHub, see [Managing your work with GitHub Actions](/en/actions/managing-issues-and-pull-requests).
* For examples that demonstrate more complex features of GitHub Actions, see [Managing your work with GitHub Actions](/en/actions/examples). These detailed examples explain how to test your code on a runner, access the GitHub CLI, and use advanced features such as concurrency and test matrices.
* To certify your proficiency in automating workflows and accelerating development with GitHub Actions, earn a GitHub Actions certificate with GitHub Certifications. For more information, see [About GitHub Certifications](/en/get-started/showcase-your-expertise-with-github-certifications/about-github-certifications).

---

## Workflow syntax for GitHub Actions

> Source: https://docs.github.com/en/actions/reference/workflows-and-actions/workflow-syntax
> (Listed task URL `/en/actions/writing-workflows/workflow-syntax-for-github-actions` redirects here.)
> **Fidelity note:** the fetch backend preserved all headings, tables, operators, and YAML examples but compressed some long prose descriptions. Structure and all syntax examples below are verbatim; consult the source URL for the complete per-key prose.

# Workflow Syntax for GitHub Actions

## About YAML Syntax for Workflows

Workflow files use YAML syntax and must have either a `.yml` or `.yaml` file extension. Workflow files must be stored in the `.github/workflows` directory of a repository.

## `name`

The workflow's display name shown under the repository's "Actions" tab. If omitted, GitHub displays the workflow file path relative to the repository root.

## `run-name`

The name for workflow runs generated from the workflow. This value can include expressions and reference the `github` and `inputs` contexts. If omitted or whitespace-only, the run name defaults to event-specific information such as commit messages or pull request titles.

```yaml
run-name: Deploy to ${{ inputs.deploy_target }} by @${{ github.actor }}
```

## `on`

Defines which events trigger the workflow automatically. You can specify single or multiple events, activity types, filters, or time schedules.

Single event:

```yaml
on: push
```

Multiple events:

```yaml
on: [push, fork]
```

### `on.<event_name>.types`

Narrows down which activity types trigger the workflow. For example, the `label` event can be triggered by `created`, `edited`, or `deleted` activities.

```yaml
on:
  label:
    types:
      - created
```

### Branch and tag filters (`branches`, `branches-ignore`, `tags`, `tags-ignore`)

For `push` and `pull_request` events, use `branches`, `branches-ignore`, `tags`, and `tags-ignore` to control execution:

```yaml
on:
  push:
    branches:
      - main
      - 'releases/**'
    tags:
      - v2
      - v1.*
```

You cannot use both `branches` and `branches-ignore` for the same event, nor both `tags` and `tags-ignore`. To include and exclude patterns, use the `!` character:

```yaml
on:
  push:
    branches:
      - 'releases/**'
      - '!releases/**-alpha'
```

### Path filters (`paths`, `paths-ignore`)

For `push` and `pull_request` events, use `paths` and `paths-ignore` to filter based on changed files:

```yaml
on:
  push:
    paths:
      - '**.js'
```

Exclude paths:

```yaml
on:
  push:
    paths-ignore:
      - 'docs/**'
```

Include and exclude:

```yaml
on:
  push:
    paths:
      - 'sub-project/**'
      - '!sub-project/docs/**'
```

### `on.schedule`

Schedule workflows using POSIX cron syntax. The shortest interval is once every 5 minutes.

Cron format:

```
┌───────────── minute (0 - 59)
│ ┌───────────── hour (0 - 23)
│ │ ┌───────────── day of the month (1 - 31)
│ │ │ ┌───────────── month (1 - 12 or JAN-DEC)
│ │ │ │ ┌───────────── day of the week (0 - 6 or SUN-SAT)
│ │ │ │ │
* * * * *
```

| Operator | Description | Example |
|----------|-------------|---------|
| `*` | Any value | `15 * * * *` runs at minute 15 of every hour |
| `,` | Value list separator | `2,10 4,5 * * *` runs at minute 2 and 10 of hours 4 and 5 |
| `-` | Range of values | `30 4-6 * * *` runs at minute 30 of hours 4, 5, and 6 |
| `/` | Step values | `20/15 * * * *` runs every 15 minutes starting from minute 20 |

```yaml
on:
  schedule:
    - cron: '30 5 * * 1-5'
      timezone: "America/New_York"
```

### `on.workflow_call`

Defines inputs and outputs for reusable workflows. Inputs require a `type` parameter (`boolean`, `number`, or `string`).

```yaml
on:
  workflow_call:
    inputs:
      username:
        description: 'A username passed from the caller workflow'
        default: 'john-doe'
        required: false
        type: string
```

### `on.workflow_dispatch`

Allows manual workflow triggering with optional inputs. Supports `boolean`, `choice`, `number`, `environment`, and `string` types.

```yaml
on:
  workflow_dispatch:
    inputs:
      logLevel:
        description: 'Log level'
        required: true
        default: 'warning'
        type: choice
        options:
          - info
          - warning
          - debug
```

## `permissions`

The `permissions` key modifies default permissions granted to `GITHUB_TOKEN`. You can set `read`, `write`, or `none` for each permission. All unspecified permissions default to `none`.

Available permissions:

- `actions`
- `artifact-metadata`
- `attestations`
- `checks`
- `code-quality`
- `contents`
- `deployments`
- `discussions`
- `id-token`
- `issues`
- `models`
- `packages`
- `pages`
- `pull-requests`
- `security-events`
- `statuses`
- `vulnerability-alerts`

```yaml
permissions:
  contents: read
  pull-requests: write
```

Shortcuts:

```yaml
permissions: read-all
permissions: write-all
permissions: {}
```

Permissions can be defined at the workflow level or the job level, with job-level settings overriding workflow defaults.

## `env`

Defines variables available to all jobs in the workflow:

```yaml
env:
  SERVER: production
```

Variables cannot be defined in terms of other variables in the same map.

* `jobs.<job_id>.env` — Defines variables for a specific job. Job-level variables override workflow-level ones.
* `jobs.<job_id>.steps[*].env` — Defines variables for a specific step, with the highest precedence.

## `defaults`

Sets default options applying to all jobs. Job-level defaults override workflow-level ones.

### `defaults.run`

Sets default `shell` and `working-directory` for all `run` steps:

```yaml
defaults:
  run:
    shell: bash
    working-directory: ./scripts
```

Supported shells:

| Platform | Shell | Description |
|----------|-------|-------------|
| Linux/macOS | unspecified | Default shell; runs `bash -e {0}` if found, else `sh` |
| All | `bash` | Runs `bash --noprofile --norc -eo pipefail {0}` |
| All | `pwsh` | PowerShell Core |
| All | `python` | Python |
| Linux/macOS | `sh` | Fallback if bash unavailable |
| Windows | `cmd` | Command Prompt |
| Windows | `pwsh` | PowerShell Core (default on Windows) |
| Windows | `powershell` | PowerShell Desktop |

## `concurrency`

Controls parallel execution of jobs or workflows using the same concurrency group:

```yaml
concurrency:
  group: ${{ github.workflow }}-${{ github.ref }}
  cancel-in-progress: true
```

Options:

- `cancel-in-progress: true` — Cancels any running job in the group
- `queue: max` — Queues up to 100 pending runs instead of canceling them
- `queue: single` (default) — Replaces pending runs with new ones

Cannot combine `queue: max` with `cancel-in-progress: true`.

## `jobs`

### `jobs.<job_id>`

Defines a job with a unique identifier. Must start with a letter or `_` and contain only alphanumeric characters, `-`, or `_`.

```yaml
jobs:
  my_first_job:
    name: My first job
  my_second_job:
    name: My second job
```

* `jobs.<job_id>.name` — Display name for the job shown in the GitHub UI.
* `jobs.<job_id>.permissions` — Sets permissions for `GITHUB_TOKEN` at the job level, overriding workflow-level settings.
* `jobs.<job_id>.runs-on` — Specifies the runner environment for the job (e.g., `ubuntu-latest`, `windows-latest`, `macos-latest`, or self-hosted runner labels).
* `jobs.<job_id>.needs` — Manages dependencies between jobs; jobs run in parallel by default.
* `jobs.<job_id>.steps` — Contains the steps executed by the job in order.

### Step keys

* `jobs.<job_id>.steps[*].name` — Display name for the step.
* `jobs.<job_id>.steps[*].uses` — Specifies an action to run:

  ```yaml
  - uses: actions/checkout@v4
  ```

* `jobs.<job_id>.steps[*].run` — Executes shell commands:

  ```yaml
  - run: npm install
    shell: bash
  ```

* `jobs.<job_id>.steps[*].with` — Provides input parameters to an action:

  ```yaml
  - uses: actions/upload-artifact@v3
    with:
      name: my-artifact
      path: path/to/artifact
  ```

* `jobs.<job_id>.steps[*].env` — Sets environment variables for a specific step.

---

## Events that trigger workflows

> Source: https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows
> (Listed task URL `/en/actions/writing-workflows/choosing-when-your-workflow-runs/events-that-trigger-workflows` redirects here.)

# Events that trigger workflows

You can configure your workflows to run when specific activity on GitHub happens, at a scheduled time, or when an event outside of GitHub occurs.

## About events that trigger workflows

Workflow triggers are events that cause a workflow to run. For more information about how to use workflow triggers, see [Triggering a workflow](/en/actions/using-workflows/triggering-a-workflow).

Some events have multiple activity types. For these events, you can specify which activity types will trigger a workflow run. For more information about what each activity type means, see [Webhook events and payloads](/en/webhooks-and-events/webhooks/webhook-events-and-payloads).

> [!NOTE]
> Not all webhook events trigger workflows.

## `branch_protection_rule`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `branch_protection_rule` | - `created`<br/>- `edited`<br/>- `deleted` | Last commit on default branch | Default branch |

> [!NOTE]
> * More than one activity type triggers this event. By default, all activity types trigger workflows that run on this event. You can limit your workflow runs to specific activity types using the `types` keyword.
> * This event will only trigger a workflow run if the workflow file exists on the default branch.

Runs your workflow when branch protection rules in the workflow repository are changed.

```yaml
on:
  branch_protection_rule:
    types: [created, deleted]
```

## `check_run`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `check_run` | - `created`<br/>- `rerequested`<br/>- `completed`<br/>- `requested_action` | Last commit on default branch | Default branch |

> [!NOTE]
> * More than one activity type triggers this event. By default, all activity types trigger workflows that run on this event. You can limit your workflow runs to specific activity types using the `types` keyword.
> * This event will only trigger a workflow run if the workflow file exists on the default branch.
> * To prevent recursive workflows, this event does not trigger workflows if the check run's check suite was created by GitHub Actions or if the check suite's head SHA is associated with GitHub Actions.

Runs your workflow when activity related to a check run occurs. A check run is an individual test that is part of a check suite.

```yaml
on:
  check_run:
    types: [rerequested, completed]
```

## `check_suite`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `check_suite` | - `completed` | Last commit on default branch | Default branch |

> [!NOTE]
> * More than one activity type triggers this event. Although only the `completed` activity type is supported, specifying the activity type will keep your workflow specific if more activity types are added in the future.
> * This event will only trigger a workflow run if the workflow file exists on the default branch.
> * To prevent recursive workflows, this event does not trigger workflows if the check suite was created by GitHub Actions or if the check suite's head SHA is associated with GitHub Actions.

Runs your workflow when check suite activity occurs. A check suite is a collection of the check runs created for a specific commit.

```yaml
on:
  check_suite:
    types: [completed]
```

## `create`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `create` | Not applicable | Last commit on the created branch or tag | Branch or tag created |

> [!NOTE]
> An event will not be created when you create more than three tags at once.

Runs your workflow when someone creates a Git reference (Git branch or tag) in the workflow's repository.

```yaml
on:
  create
```

## `delete`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `delete` | Not applicable | Last commit on default branch | Default branch |

> [!NOTE]
> * This event will only trigger a workflow run if the workflow file exists on the default branch.
> * An event will not be created when you delete more than three tags at once.

Runs your workflow when someone deletes a Git reference (Git branch or tag) in the workflow's repository.

```yaml
on:
  delete
```

## `deployment`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `deployment` | Not applicable | Commit to be deployed | Branch or tag to be deployed (empty if created with a commit SHA) |

Runs your workflow when someone creates a deployment in the workflow's repository. Deployments created with a commit SHA may not have a Git ref.

```yaml
on:
  deployment
```

## `deployment_status`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `deployment_status` | Not applicable | Commit to be deployed | Branch or tag to be deployed (empty if commit) |

> [!NOTE]
> When a deployment status's state is set to `inactive`, a workflow run will not be triggered.

Runs your workflow when a third party provides a deployment status.

```yaml
on:
  deployment_status
```

## `discussion`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `discussion` | - `created`<br/>- `edited`<br/>- `deleted`<br/>- `transferred`<br/>- `pinned`<br/>- `unpinned`<br/>- `labeled`<br/>- `unlabeled`<br/>- `locked`<br/>- `unlocked`<br/>- `category_changed`<br/>- `answered`<br/>- `unanswered` | Last commit on default branch | Default branch |

> [!NOTE]
> * More than one activity type triggers this event. By default, all activity types trigger workflows that run on this event.
> * This event will only trigger a workflow run if the workflow file exists on the default branch.
> * Webhook events for GitHub Discussions are currently in public preview and subject to change.

Runs your workflow when a discussion in the workflow's repository is created or modified.

```yaml
on:
  discussion:
    types: [created, edited, answered]
```

## `discussion_comment`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `discussion_comment` | - `created`<br/>- `edited`<br/>- `deleted` | Last commit on default branch | Default branch |

> [!NOTE]
> * More than one activity type triggers this event. By default, all activity types trigger workflows.
> * This event will only trigger a workflow run if the workflow file exists on the default branch.
> * Webhook events for GitHub Discussions are currently in public preview and subject to change.

Runs your workflow when a comment on a discussion in the workflow's repository is created or modified.

```yaml
on:
  discussion_comment:
    types: [created, deleted]
```

## `fork`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `fork` | Not applicable | Last commit on default branch | Default branch |

> [!NOTE]
> This event will only trigger a workflow run if the workflow file exists on the default branch.

Runs your workflow when someone forks a repository.

```yaml
on:
  fork
```

## `gollum`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `gollum` | Not applicable | Last commit on default branch | Default branch |

> [!NOTE]
> This event will only trigger a workflow run if the workflow file exists on the default branch.

Runs your workflow when someone creates or updates a Wiki page.

```yaml
on:
  gollum
```

## `image_version`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| Not applicable | Not applicable | Last commit on default branch | Default branch |

Runs your workflow when a new version of a specified image becomes available for use. This event is typically triggered after a successful image version creation, allowing you to automate actions such as deployment or notifications in response to new image versions.

This event supports glob patterns for both image names and versions. The example below triggers when a new image version matches any of the specified name and version combinations. For example, `["MyNewImage", 1.0.0]`, `["MyNewImage", 2.53.0]`, `["MyOtherImage", 1.0.0]`, and `["MyOtherImage", 2.0.0]`.

```yaml
on:
  image_version:
    names:
    - "MyNewImage"
    - "MyOtherImage"
    versions:
    - 1.*
    - 2.*
```

## `issue_comment`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `issue_comment` | - `created`<br/>- `edited`<br/>- `deleted` | Last commit on default branch | Default branch |

> [!NOTE]
> * More than one activity type triggers this event. By default, all activity types trigger workflows.
> * This event will only trigger a workflow run if the workflow file exists on the default branch.

Runs your workflow when an issue or pull request comment is created, edited, or deleted.

```yaml
on:
  issue_comment:
    types: [created, deleted]
```

### `issue_comment` on issues only or pull requests only

The `issue_comment` event occurs for comments on both issues and pull requests. You can use the `github.event.issue.pull_request` property in a conditional to take different action depending on whether the triggering object was an issue or pull request.

```yaml
on: issue_comment

jobs:
  pr_commented:
    # This job only runs for pull request comments
    name: PR comment
    if: ${{ github.event.issue.pull_request }}
    runs-on: ubuntu-latest
    steps:
      - run: |
          echo A comment on PR $NUMBER
        env:
          NUMBER: ${{ github.event.issue.number }}

  issue_commented:
    # This job only runs for issue comments
    name: Issue comment
    if: ${{ !github.event.issue.pull_request }}
    runs-on: ubuntu-latest
    steps:
      - run: |
          echo A comment on issue $NUMBER
        env:
          NUMBER: ${{ github.event.issue.number }}
```

## `issues`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `issues` | - `opened`<br/>- `edited`<br/>- `deleted`<br/>- `transferred`<br/>- `pinned`<br/>- `unpinned`<br/>- `closed`<br/>- `reopened`<br/>- `assigned`<br/>- `unassigned`<br/>- `labeled`<br/>- `unlabeled`<br/>- `locked`<br/>- `unlocked`<br/>- `milestoned`<br/>- `demilestoned`<br/>- `typed`<br/>- `untyped` | Last commit on default branch | Default branch |

> [!NOTE]
> * More than one activity type triggers this event. By default, all activity types trigger workflows.
> * This event will only trigger a workflow run if the workflow file exists on the default branch.

Runs your workflow when an issue in the workflow's repository is created or modified.

```yaml
on:
  issues:
    types: [opened, edited, milestoned]
```

## `label`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `label` | - `created`<br/>- `edited`<br/>- `deleted` | Last commit on default branch | Default branch |

> [!NOTE]
> * More than one activity type triggers this event. By default, all activity types trigger workflows.
> * This event will only trigger a workflow run if the workflow file exists on the default branch.

Runs your workflow when a label in your workflow's repository is created or modified.

If you want to run your workflow when a label is added to or removed from an issue, pull request, or discussion, use the `labeled` or `unlabeled` activity types for the `issues`, `pull_request`, `pull_request_target`, or `discussion` events instead.

```yaml
on:
  label:
    types: [created, deleted]
```

## `merge_group`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `merge_group` | `checks_requested` | SHA of the merge group | Ref of the merge group |

> [!NOTE]
> * More than one activity type triggers this event. Although only the `checks_requested` activity type is supported, specifying the activity type will keep your workflow specific if more activity types are added in the future.
> * If your repository uses GitHub Actions to perform required checks on pull requests, you need to update the workflows to include the `merge_group` event as an additional trigger. Otherwise, status checks will not be triggered when you add a pull request to a merge queue. The `merge_group` event is separate from the `pull_request` and `push` events.

Runs your workflow when a pull request is added to a merge queue, which adds the pull request to a merge group.

```yaml
on:
  pull_request:
    branches: [ "main" ]
  merge_group:
    types: [checks_requested]
```

## `milestone`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `milestone` | - `created`<br/>- `closed`<br/>- `opened`<br/>- `edited`<br/>- `deleted` | Last commit on default branch | Default branch |

> [!NOTE]
> * More than one activity type triggers this event. By default, all activity types trigger workflows.
> * This event will only trigger a workflow run if the workflow file exists on the default branch.

Runs your workflow when a milestone in the workflow's repository is created or modified.

If you want to run your workflow when an issue is added to or removed from a milestone, use the `milestoned` or `demilestoned` activity types for the `issues` event instead.

```yaml
on:
  milestone:
    types: [opened, deleted]
```

## `page_build`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `page_build` | Not applicable | Last commit on default branch | Default branch |

> [!NOTE]
> This event will only trigger a workflow run if the workflow file exists on the default branch.

Runs your workflow when someone pushes to a branch that is the publishing source for GitHub Pages, if GitHub Pages is enabled for the repository.

```yaml
on:
  page_build
```

## `public`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `public` | Not applicable | Last commit on default branch | Default branch |

> [!NOTE]
> This event will only trigger a workflow run if the workflow file exists on the default branch.

Runs your workflow when your workflow's repository changes from private to public.

```yaml
on:
  public
```

## `pull_request`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `pull_request` | - `assigned`<br/>- `unassigned`<br/>- `labeled`<br/>- `unlabeled`<br/>- `opened`<br/>- `edited`<br/>- `closed`<br/>- `reopened`<br/>- `synchronize`<br/>- `converted_to_draft`<br/>- `locked`<br/>- `unlocked`<br/>- `enqueued`<br/>- `dequeued`<br/>- `milestoned`<br/>- `demilestoned`<br/>- `ready_for_review`<br/>- `review_requested`<br/>- `review_request_removed`<br/>- `auto_merge_enabled`<br/>- `auto_merge_disabled` | Last merge commit on the `GITHUB_REF` branch | PR merge branch `refs/pull/PULL_REQUEST_NUMBER/merge` |

> [!NOTE]
> * More than one activity type triggers this event. By default, a workflow only runs when a `pull_request` event's activity type is `opened`, `synchronize`, or `reopened`. To trigger workflows by different activity types, use the `types` keyword.
> * Workflows will not run on `pull_request` activity if the pull request has a merge conflict. The merge conflict must be resolved first. Conversely, workflows with the `pull_request_target` event will run even if the pull request has a merge conflict. Before using the `pull_request_target` trigger, you should be aware of the security risks.
> * The `pull_request` webhook event payload is empty for merged pull requests and pull requests that come from forked repositories.
> * When a pull request is created or updated by a workflow using `GITHUB_TOKEN`, `pull_request` events with the `opened`, `synchronize`, or `reopened` activity types create workflow runs that require approval. A user with write access to the repository can approve these runs from the pull request page. With the exception of `workflow_dispatch` and `repository_dispatch`, other `GITHUB_TOKEN`-triggered events do not create workflow runs at all.
> * The value of `GITHUB_REF` varies for a closed pull request depending on whether the pull request has been merged or not. If a pull request was closed but not merged, it will be `refs/pull/PULL_REQUEST_NUMBER/merge`. If a pull request was closed as a result of being merged, it will be the fully qualified `ref` of the branch it was merged into, for example `/refs/heads/main`.

Runs your workflow when activity on a pull request in the workflow's repository occurs. For example, if no activity types are specified, the workflow runs when a pull request is opened or reopened or when the head branch of the pull request is updated.

Note that `GITHUB_SHA` for this event is the last merge commit of the pull request merge branch. If you want to get the commit ID for the last commit to the head branch of the pull request, use `github.event.pull_request.head.sha` instead.

### How the merge branch affects your workflow

For open, mergeable pull requests, workflows triggered by the `pull_request` event set `GITHUB_REF` to the merge branch. Because `actions/checkout` uses `GITHUB_REF` by default, it checks out the merge branch. Your CI tests run against the merged result, not just the head branch alone:

* `GITHUB_REF` is set to `refs/pull/PULL_REQUEST_NUMBER/merge`
* `GITHUB_SHA` is the SHA of the merge commit on the merge branch

To test only the head branch commits without simulating a merge, check out the head branch using `github.event.pull_request.head.sha` in your workflow.

```yaml
on:
  pull_request:
    types: [opened, reopened]
```

You can use the event context to further control when jobs in your workflow will run:

```yaml
on:
  pull_request:
    types: [review_requested]
jobs:
  specific_review_requested:
    runs-on: ubuntu-latest
    if: ${{ github.event.requested_team.name == 'octo-team'}}
    steps:
      - run: echo 'A review from octo-team was requested'
```

### Running your `pull_request` workflow based on the head or base branch

```yaml
on:
  pull_request:
    types:
      - opened
    branches:
      - 'releases/**'
```

> [!NOTE]
> If you use both the `branches` filter and the `paths` filter, the workflow will only run when both filters are satisfied.
>
> ```yaml
> on:
>   pull_request:
>     types:
>       - opened
>     branches:
>       - 'releases/**'
>     paths:
>       - '**.js'
> ```

To run a job based on the pull request's head branch name, use the `github.head_ref` context in a conditional:

```yaml
on:
  pull_request:
    types:
      - opened
jobs:
  run_if:
    if: startsWith(github.head_ref, 'releases/')
    runs-on: ubuntu-latest
    steps:
      - run: echo "The head of this PR starts with 'releases/'"
```

### Running your `pull_request` workflow based on files changed

```yaml
on:
  pull_request:
    paths:
      - '**.js'
```

### Running your `pull_request` workflow when a pull request merges

```yaml
on:
  pull_request:
    types:
      - closed

jobs:
  if_merged:
    if: github.event.pull_request.merged == true
    runs-on: ubuntu-latest
    steps:
    - run: |
        echo The PR was merged
```

#### Workflows in forked repositories

Workflows don't run in forked repositories by default. You must enable GitHub Actions in the **Actions** tab of the forked repository.

With the exception of `GITHUB_TOKEN`, secrets are not passed to the runner when a workflow is triggered from a forked repository. The `GITHUB_TOKEN` has read-only permissions in pull requests from forked repositories.

#### Pull request events for forked repositories

For pull requests from a forked repository to the base repository, GitHub sends the `pull_request`, `issue_comment`, `pull_request_review_comment`, `pull_request_review`, and `pull_request_target` events to the base repository. No pull request events occur on the forked repository.

When a first-time contributor submits a pull request to a public repository, a maintainer with write access may need to approve running workflows on the pull request.

> [!NOTE]
> Workflows triggered by Dependabot pull requests are treated as though they are from a forked repository, and are also subject to these restrictions.

## `pull_request_comment` (use `issue_comment`)

To run your workflow when a comment on a pull request (not on a pull request's diff) is created, edited, or deleted, use the `issue_comment` event. For activity related to pull request reviews or pull request review comments, use the `pull_request_review` or `pull_request_review_comment` events.

## `pull_request_review`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `pull_request_review` | - `submitted`<br/>- `edited`<br/>- `dismissed` | Last merge commit on the `GITHUB_REF` branch | PR merge branch `refs/pull/PULL_REQUEST_NUMBER/merge` |

> [!NOTE]
> More than one activity type triggers this event. By default, all activity types trigger workflows.

Runs your workflow when a pull request review is submitted, edited, or dismissed.

```yaml
on:
  pull_request_review:
    types: [edited, dismissed]
```

### Running a workflow when a pull request is approved

```yaml
on:
  pull_request_review:
    types: [submitted]

jobs:
  approved:
    if: github.event.review.state == 'approved'
    runs-on: ubuntu-latest
    steps:
      - run: echo "This PR was approved"
```

(Forked-repository notes are identical to those under `pull_request`.)

## `pull_request_review_comment`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `pull_request_review_comment` | - `created`<br/>- `edited`<br/>- `deleted` | Last merge commit on the `GITHUB_REF` branch | PR merge branch `refs/pull/PULL_REQUEST_NUMBER/merge` |

> [!NOTE]
> More than one activity type triggers this event. By default, all activity types trigger workflows.

Runs your workflow when a pull request review comment is modified. A pull request review comment is a comment on a pull request's diff.

```yaml
on:
  pull_request_review_comment:
    types: [created, deleted]
```

(Forked-repository notes are identical to those under `pull_request`.)

## `pull_request_target`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `pull_request` | - `assigned`<br/>- `unassigned`<br/>- `labeled`<br/>- `unlabeled`<br/>- `opened`<br/>- `edited`<br/>- `closed`<br/>- `reopened`<br/>- `synchronize`<br/>- `converted_to_draft`<br/>- `locked`<br/>- `unlocked`<br/>- `enqueued`<br/>- `dequeued`<br/>- `milestoned`<br/>- `demilestoned`<br/>- `ready_for_review`<br/>- `review_requested`<br/>- `review_request_removed`<br/>- `auto_merge_enabled`<br/>- `auto_merge_disabled` | Last commit on default branch | Default branch |

> [!NOTE]
> More than one activity type triggers this event. By default, a workflow only runs when a `pull_request_target` event's activity type is `opened`, `synchronize`, or `reopened`. To trigger workflows by different activity types, use the `types` keyword.

Runs your workflow when activity on a pull request in the workflow's repository occurs. This event runs in the context of the default branch of the base repository, rather than in the context of the merge commit, as the `pull_request` event does. This prevents execution of unsafe code from the head of the pull request that could alter your repository or steal any secrets you use in your workflow. This event allows your workflow to do things like label or comment on pull requests from forks. Avoid using this event if you need to build or run code from the pull request.

To ensure repository security, branches with names that match certain patterns (such as those which look similar to SHAs) may not trigger workflows with the `pull_request_target` event.

> [!WARNING]
> Running untrusted code on the `pull_request_target` trigger may lead to security vulnerabilities. These vulnerabilities include cache poisoning and granting unintended access to write privileges or secrets. For more information, see [Preventing pwn requests](https://securitylab.github.com/research/github-actions-preventing-pwn-requests) on the GitHub Security Lab website.

```yaml
on:
  pull_request_target:
    types: [assigned, opened, synchronize, reopened]
```

The `branches`/`paths` filters, `github.head_ref` conditionals, and `closed`+`merged` patterns work identically to `pull_request` (see above), substituting `pull_request_target`.

## `push`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `push` | Not applicable | Tip commit pushed to the ref. When you delete a branch, the SHA in the workflow run (and its associated refs) reverts to the default branch of the repository. | Updated ref |

> [!NOTE]
> * The webhook payload available to GitHub Actions does not include the `added`, `removed`, and `modified` attributes in the `commit` object. You can retrieve the full commit object using the API.
> * Events will not be created if more than 5,000 branches are pushed at once. Events will not be created for tags when more than three tags are pushed at once.

Runs your workflow when you push a commit or tag, or when you create a repository from a template.

```yaml
on:
  push
```

> [!NOTE]
> When a `push` webhook event triggers a workflow run, the Actions UI's "pushed by" field shows the account of the pusher and not the author or committer. However, if the changes are pushed to a repository using SSH authentication with a deploy key, then the "pushed by" field will be the repository admin who verified the deploy key when it was added to a repository.

### Running your workflow only when a push to specific branches occurs

```yaml
on:
  push:
    branches:
      - 'main'
      - 'releases/**'
```

### Running your workflow only when a push of specific tags occurs

```yaml
on:
  push:
    tags:
      - v1.**
```

### Running your workflow only when a push affects specific files

```yaml
on:
  push:
    paths:
      - '**.js'
```

## `registry_package`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `registry_package` | - `published`<br/>- `updated` | Commit of the published package | Branch or tag of the published package |

> [!NOTE]
> * More than one activity type triggers this event. By default, all activity types trigger workflows.
> * This event will only trigger a workflow run if the workflow file exists on the default branch.
> * When pushing multi-architecture container images, this event occurs once per manifest, so you might observe your workflow triggering multiple times.

Runs your workflow when activity related to GitHub Packages occurs in your repository.

```yaml
on:
  registry_package:
    types: [published]
```

## `release`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `release` | - `published`<br/>- `unpublished`<br/>- `created`<br/>- `edited`<br/>- `deleted`<br/>- `prereleased`<br/>- `released` | Last commit in the tagged release | Tag ref of release `refs/tags/<tag_name>` |

> [!NOTE]
> * More than one activity type triggers this event. By default, all activity types trigger workflows.
> * Workflows are not triggered for the `created`, `edited`, or `deleted` activity types for draft releases. When you create your release through the GitHub UI, your release may automatically be saved as a draft.
> * The `prereleased` type will not trigger for pre-releases published from draft releases, but the `published` type will trigger. If you want a workflow to run when stable *and* pre-releases publish, subscribe to `published` instead of `released` and `prereleased`.

Runs your workflow when release activity in your repository occurs.

```yaml
on:
  release:
    types: [published]
```

## `repository_dispatch`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `repository_dispatch` | Custom | Last commit on default branch | Default branch |

> [!NOTE]
> This event will only trigger a workflow run if the workflow file exists on the default branch.

You can use the GitHub API to trigger a webhook event called `repository_dispatch` when you want to trigger a workflow for activity that happens outside of GitHub.

When you make a request to create a `repository_dispatch` event, you must specify an `event_type` to describe the activity type. By default, all `repository_dispatch` activity types trigger a workflow to run. You can use the `types` keyword to limit your workflow to run when a specific `event_type` value is sent in the `repository_dispatch` webhook payload.

```yaml
on:
  repository_dispatch:
    types: [test_result]
```

> [!NOTE]
> The `event_type` value is limited to 100 characters.

Any data that you send through the `client_payload` parameter will be available in the `github.event` context. For example, if you send this request body:

```json
{
  "event_type": "test_result",
  "client_payload": {
    "passed": false,
    "message": "Error: timeout"
  }
}
```

then you can access the payload in a workflow like this:

```yaml
on:
  repository_dispatch:
    types: [test_result]

jobs:
  run_if_failure:
    if: ${{ !github.event.client_payload.passed }}
    runs-on: ubuntu-latest
    steps:
      - env:
          MESSAGE: ${{ github.event.client_payload.message }}
        run: echo $MESSAGE
```

> [!NOTE]
> * The maximum number of top-level properties in `client_payload` is 10.
> * The payload can contain a maximum of 65,535 characters.

## `schedule`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| Not applicable | Not applicable | Last commit on default branch | Default branch |

> [!NOTE]
> * The `schedule` event can be delayed during periods of high loads of GitHub Actions workflow runs. High load times include the start of every hour. If the load is sufficiently high enough, some queued jobs may be dropped. To decrease the chance of delay, schedule your workflow to run at a different time of the hour.
> * This event will only trigger a workflow run if the workflow file exists on the default branch.
> * Scheduled workflows will only run on the default branch.
> * In a public repository, scheduled workflows are automatically disabled when no repository activity has occurred in 60 days.

The `schedule` event allows you to trigger a workflow at a scheduled time.

```yaml
on:
  schedule:
    - cron: "15 4,5 * * *"
```

Use POSIX cron syntax to schedule workflows to run at specific times. By default, scheduled workflows run in UTC. You can optionally specify a timezone using an IANA timezone string for timezone-aware scheduling. Scheduled workflows run on the latest commit on the default branch. The shortest interval you can run scheduled workflows is once every 5 minutes.

> [!NOTE]
> For schedules that set `timezone` to a time zone that observes daylight saving time (DST), during DST spring-forward transitions, scheduled workflows in skipped hours advance to the next valid time. For example, a 2:30 AM schedule advances to 3:00 AM.

Cron syntax has five fields separated by a space, and each field represents a unit of time.

```text
┌───────────── minute (0 - 59)
│ ┌───────────── hour (0 - 23)
│ │ ┌───────────── day of the month (1 - 31)
│ │ │ ┌───────────── month (1 - 12 or JAN-DEC)
│ │ │ │ ┌───────────── day of the week (0 - 6 or SUN-SAT)
│ │ │ │ │
* * * * *
```

You can use these operators in any of the five fields:

| Operator | Description | Example |
|---|---|---|
| \* | Any value | `15 * * * *` runs at every minute 15 of every hour of every day. |
| , | Value list separator | `2,10 4,5 * * *` runs at minute 2 and 10 of the 4th and 5th hour of every day. |
| - | Range of values | `30 4-6 * * *` runs at minute 30 of the 4th, 5th, and 6th hour. |
| / | Step values | `20/15 * * * *` runs every 15 minutes starting from minute 20 through 59 (minutes 20, 35, and 50). |

This example triggers the workflow to run at 5:30 AM in the America/New_York timezone every Monday through Friday:

```yaml
on:
  schedule:
    - cron: '30 5 * * 1-5'
      timezone: "America/New_York"
```

A single workflow can be triggered by multiple `schedule` events. Access the `schedule` event that triggered the workflow through the `github.event.schedule` context.

```yaml
on:
  schedule:
    - cron: '30 5 * * 1,3'
    - cron: '30 5,17 * * 2,4'

jobs:
  test_schedule:
    runs-on: ubuntu-latest
    steps:
      - name: Not on Monday or Wednesday
        if: github.event.schedule != '30 5 * * 1,3'
        run: echo "This step will be skipped on Monday and Wednesday"
      - name: Every time
        run: echo "This step will always run"
```

> [!NOTE]
> GitHub Actions does not support the non-standard syntax `@yearly`, `@monthly`, `@weekly`, `@daily`, `@hourly`, and `@reboot`.

You can use [crontab guru](https://crontab.guru/) to help generate your cron syntax and confirm what time it will run.

### `actor` for scheduled workflows

Certain repository events change the `actor` associated with the workflow. For example, a user who changes the default branch of the repository, which changes the branch on which scheduled workflows run, becomes `actor` for those scheduled workflows.

For a deactivated scheduled workflow, if a user with `write` permissions to the repository makes a commit that changes the `cron` schedule on the workflow, the workflow will be reactivated, and that user will become the `actor` associated with any workflow runs.

Notifications for scheduled workflows are sent to the user who last modified the cron syntax in the workflow file.

> [!NOTE]
> For an enterprise with Enterprise Managed Users, triggering a scheduled workflow requires that the status of the `actor` user account associated with the workflow is currently active (i.e. not suspended or deleted).

## `status`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `status` | Not applicable | Last commit on default branch | Default branch |

> [!NOTE]
> This event will only trigger a workflow run if the workflow file exists on the default branch.

Runs your workflow when the status of a Git commit changes. For example, commits can be marked as `error`, `failure`, `pending`, or `success`.

```yaml
on:
  status
```

If you want to run a job based on the new commit state, you can use the `github.event.state` context:

```yaml
on:
  status
jobs:
  if_error_or_failure:
    runs-on: ubuntu-latest
    if: >-
      github.event.state == 'error' ||
      github.event.state == 'failure'
    steps:
      - env:
          DESCRIPTION: ${{ github.event.description }}
        run: |
          echo The status is error or failed: $DESCRIPTION
```

## `watch`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `watch` | - `started` | Last commit on default branch | Default branch |

> [!NOTE]
> * More than one activity type triggers this event. Although only the `started` activity type is supported, specifying the activity type will keep your workflow specific if more activity types are added in the future.
> * This event will only trigger a workflow run if the workflow file exists on the default branch.

Runs your workflow when the workflow's repository is starred.

```yaml
on:
  watch:
    types: [started]
```

## `workflow_call`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| Same as the caller workflow | Not applicable | Same as the caller workflow | Same as the caller workflow |

`workflow_call` is used to indicate that a workflow can be called by another workflow. When a workflow is triggered with the `workflow_call` event, the event payload in the called workflow is the same event payload from the calling workflow.

```yaml
on: workflow_call
```

## `workflow_dispatch`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `workflow_dispatch` | Not applicable | Last commit on the `GITHUB_REF` branch or tag | Branch or tag that received dispatch |

> [!NOTE]
> This event will only trigger a workflow run if the workflow file exists on the default branch.

To enable a workflow to be triggered manually, you need to configure the `workflow_dispatch` event. You can manually trigger a workflow run using the GitHub API, GitHub CLI, or the GitHub UI.

```yaml
on: workflow_dispatch
```

### Providing inputs

You can configure custom-defined input properties, default input values, and required inputs for the event directly in your workflow. When you trigger the event, you can provide the `ref` and any `inputs`. When the workflow runs, you can access the input values in the `inputs` context.

> [!NOTE]
> * The workflow will also receive the inputs in the `github.event.inputs` context. The information in the `inputs` context and `github.event.inputs` context is identical except that the `inputs` context preserves Boolean values as Booleans instead of converting them to strings. The `choice` type resolves to a string and is a single selectable option.
> * The maximum number of top-level properties for `inputs` is 25.
> * The maximum payload for `inputs` is 65,535 characters.

```yaml
on:
  workflow_dispatch:
    inputs:
      logLevel:
        description: 'Log level'
        required: true
        default: 'warning'
        type: choice
        options:
        - info
        - warning
        - debug
      tags:
        description: 'Test scenario tags'
        required: false
        type: boolean
      environment:
        description: 'Environment to run tests against'
        type: environment
        required: true

jobs:
  log-the-inputs:
    runs-on: ubuntu-latest
    steps:
      - run: |
          echo "Log level: $LEVEL"
          echo "Tags: $TAGS"
          echo "Environment: $ENVIRONMENT"
        env:
          LEVEL: ${{ inputs.logLevel }}
          TAGS: ${{ inputs.tags }}
          ENVIRONMENT: ${{ inputs.environment }}
```

You can also pass inputs when you run a workflow from a script, or by using GitHub CLI:

```shell
gh workflow run run-tests.yml -f logLevel=warning -f tags=false -f environment=staging
```

## `workflow_run`

| Webhook event payload | Activity types | `GITHUB_SHA` | `GITHUB_REF` |
|---|---|---|---|
| `workflow_run` | - `completed`<br/>- `requested`<br/>- `in_progress` | Last commit on default branch | Default branch |

> [!NOTE]
> * More than one activity type triggers this event. The `requested` activity type does not occur when a workflow is re-run. By default, all activity types trigger workflows.
> * This event will only trigger a workflow run if the workflow file exists on the default branch.
> * You can't use `workflow_run` to chain together more than three levels of workflows. For example, if you attempt to trigger five workflows (named `B` to `F`) to run sequentially after an initial workflow `A` has run (that is: `A` → `B` → `C` → `D` → `E` → `F`), workflows `E` and `F` will not be run.

This event occurs when a workflow run is requested or completed. It allows you to execute a workflow based on execution or completion of another workflow. The workflow started by the `workflow_run` event is able to access secrets and write tokens, even if the previous workflow was not.

> [!WARNING]
> Running untrusted code on the `workflow_run` trigger may lead to security vulnerabilities.

```yaml
on:
  workflow_run:
    workflows: [Run Tests]
    types:
      - completed
```

If you specify multiple `workflows`, only one of the workflows needs to run:

```yaml
on:
  workflow_run:
    workflows: [Staging, Lab]
    types:
      - completed
```

### Running a workflow based on the conclusion of another workflow

```yaml
on:
  workflow_run:
    workflows: [Build]
    types: [completed]

jobs:
  on-success:
    runs-on: ubuntu-latest
    if: ${{ github.event.workflow_run.conclusion == 'success' }}
    steps:
      - run: echo 'The triggering workflow passed'
  on-failure:
    runs-on: ubuntu-latest
    if: ${{ github.event.workflow_run.conclusion == 'failure' }}
    steps:
      - run: echo 'The triggering workflow failed'
```

### Limiting your workflow to run based on branches

```yaml
on:
  workflow_run:
    workflows: [Build]
    types: [requested]
    branches: [canary]
```

### Using data from the triggering workflow

The following workflow uploads data as an artifact (the data is the pull request number):

```yaml
name: Upload data

on:
  pull_request:

jobs:
  upload:
    runs-on: ubuntu-latest

    steps:
      - name: Save PR number
        env:
          PR_NUMBER: ${{ github.event.number }}
        run: |
          mkdir -p ./pr
          echo $PR_NUMBER > ./pr/pr_number
      - uses: actions/upload-artifact@v4
        with:
          name: pr_number
          path: pr/
```

When a run of the above workflow completes, it triggers a run of the following workflow, which downloads the artifact and comments on the pull request:

```yaml
name: Use the data

on:
  workflow_run:
    workflows: [Upload data]
    types:
      - completed

jobs:
  download:
    runs-on: ubuntu-latest
    steps:
      - name: 'Download artifact'
        uses: actions/github-script@v8
        with:
          script: |
            let allArtifacts = await github.rest.actions.listWorkflowRunArtifacts({
               owner: context.repo.owner,
               repo: context.repo.repo,
               run_id: context.payload.workflow_run.id,
            });
            let matchArtifact = allArtifacts.data.artifacts.filter((artifact) => {
              return artifact.name == "pr_number"
            })[0];
            let download = await github.rest.actions.downloadArtifact({
               owner: context.repo.owner,
               repo: context.repo.repo,
               artifact_id: matchArtifact.id,
               archive_format: 'zip',
            });
            const fs = require('fs');
            const path = require('path');
            const temp = '${{ runner.temp }}/artifacts';
            if (!fs.existsSync(temp)){
              fs.mkdirSync(temp);
            }
            fs.writeFileSync(path.join(temp, 'pr_number.zip'), Buffer.from(download.data));

      - name: 'Unzip artifact'
        run: unzip "${{ runner.temp }}/artifacts/pr_number.zip" -d "${{ runner.temp }}/artifacts"

      - name: 'Comment on PR'
        uses: actions/github-script@v8
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
          script: |
            const fs = require('fs');
            const path = require('path');
            const temp = '${{ runner.temp }}/artifacts';
            const issue_number = Number(fs.readFileSync(path.join(temp, 'pr_number')));
            await github.rest.issues.createComment({
              owner: context.repo.owner,
              repo: context.repo.repo,
              issue_number: issue_number,
              body: 'Thank you for the PR!'
            });
```

---

## Contexts reference

> Source: https://docs.github.com/en/actions/reference/workflows-and-actions/contexts
> (Listed task URL `/en/actions/writing-workflows/choosing-what-your-workflow-does/contexts` redirects here.)

# Contexts Reference

Find information about contexts available in GitHub Actions workflows, including available properties, access methods, and usage examples.

## Available Contexts

| Context name | Type     | Description |
| ------------ | -------- | ----------- |
| `github`     | `object` | Information about the workflow run. |
| `env`        | `object` | Contains variables set in a workflow, job, or step. |
| `vars`       | `object` | Contains variables set at the repository, organization, or environment levels. |
| `job`        | `object` | Information about the currently running job. |
| `jobs`       | `object` | For reusable workflows only, contains outputs of jobs from the reusable workflow. |
| `steps`      | `object` | Information about the steps that have been run in the current job. |
| `runner`     | `object` | Information about the runner that is running the current job. |
| `secrets`    | `object` | Contains the names and values of secrets that are available to a workflow run. |
| `strategy`   | `object` | Information about the matrix execution strategy for the current job. |
| `matrix`     | `object` | Contains the matrix properties defined in the workflow that apply to the current job. |
| `needs`      | `object` | Contains the outputs of all jobs that are defined as a dependency of the current job. |
| `inputs`     | `object` | Contains the inputs of a reusable or manually triggered workflow. |

As part of an expression, you can access context information using one of two syntaxes.

* Index syntax: `github['sha']`
* Property dereference syntax: `github.sha`

In order to use property dereference syntax, the property name must start with a letter or `_` and contain only alphanumeric characters, `-`, or `_`.

If you attempt to dereference a nonexistent property, it will evaluate to an empty string.

### Determining When to Use Contexts

GitHub Actions includes a collection of variables called *contexts* and a similar collection of variables called *default variables*. These variables are intended for use at different points in the workflow:

* **Default environment variables:** These environment variables exist only on the runner that is executing your job.
* **Contexts:** You can use most contexts at any point in your workflow, including when *default variables* would be unavailable. For example, you can use contexts with expressions to perform initial processing before the job is routed to a runner for execution; this allows you to use a context with the conditional `if` keyword to determine whether a step should run. Once the job is running, you can also retrieve context variables from the runner that is executing the job, such as `runner.os`.

```yaml
name: CI
on: push
jobs:
  prod-check:
    if: ${{ github.ref == 'refs/heads/main' }}
    runs-on: ubuntu-latest
    steps:
      - run: echo "Deploying to production server on branch $GITHUB_REF"
```

In this example, the `if` statement checks the `github.ref` context to determine the current branch name; if the name is `refs/heads/main`, then the subsequent steps are executed. The `if` check is processed by GitHub Actions, and the job is only sent to the runner if the result is `true`. Once the job is sent to the runner, the step is executed and refers to the `$GITHUB_REF` variable from the runner.

### Context Availability

Different contexts are available throughout a workflow run. The following table lists the restrictions on where each context and special function can be used within a workflow. The listed contexts are only available for the given workflow key, and may not be used anywhere else. Unless listed below, a function can be used anywhere.

| Workflow key                                       | Context                                                                           | Special functions                                |
| -------------------------------------------------- | --------------------------------------------------------------------------------- | ------------------------------------------------ |
| `run-name`                                         | `github, inputs, vars`                                                            | None                                             |
| `concurrency`                                      | `github, inputs, vars`                                                            | None                                             |
| `env`                                              | `github, secrets, inputs, vars`                                                   | None                                             |
| `jobs.<job_id>.concurrency`                        | `github, needs, strategy, matrix, inputs, vars`                                   | None                                             |
| `jobs.<job_id>.container`                          | `github, needs, strategy, matrix, vars, inputs`                                   | None                                             |
| `jobs.<job_id>.container.credentials`              | `github, needs, strategy, matrix, env, vars, secrets, inputs`                     | None                                             |
| `jobs.<job_id>.container.env.<env_id>`             | `github, needs, strategy, matrix, job, runner, env, vars, secrets, inputs`        | None                                             |
| `jobs.<job_id>.container.image`                    | `github, needs, strategy, matrix, vars, inputs`                                   | None                                             |
| `jobs.<job_id>.continue-on-error`                  | `github, needs, strategy, vars, matrix, inputs`                                   | None                                             |
| `jobs.<job_id>.defaults.run`                       | `github, needs, strategy, matrix, env, vars, inputs`                              | None                                             |
| `jobs.<job_id>.env`                                | `github, needs, strategy, matrix, vars, secrets, inputs`                          | None                                             |
| `jobs.<job_id>.environment`                        | `github, needs, strategy, matrix, vars, inputs`                                   | None                                             |
| `jobs.<job_id>.environment.url`                    | `github, needs, strategy, matrix, job, runner, env, vars, steps, inputs`          | None                                             |
| `jobs.<job_id>.if`                                 | `github, needs, vars, inputs`                                                     | `always, cancelled, success, failure`            |
| `jobs.<job_id>.name`                               | `github, needs, strategy, matrix, vars, inputs`                                   | None                                             |
| `jobs.<job_id>.outputs.<output_id>`                | `github, needs, strategy, matrix, job, runner, env, vars, secrets, steps, inputs` | None                                             |
| `jobs.<job_id>.runs-on`                            | `github, needs, strategy, matrix, vars, inputs`                                   | None                                             |
| `jobs.<job_id>.secrets.<secrets_id>`               | `github, needs, strategy, matrix, secrets, inputs, vars`                          | None                                             |
| `jobs.<job_id>.services`                           | `github, needs, strategy, matrix, vars, inputs`                                   | None                                             |
| `jobs.<job_id>.services.<service_id>.credentials`  | `github, needs, strategy, matrix, env, vars, secrets, inputs`                     | None                                             |
| `jobs.<job_id>.services.<service_id>.env.<env_id>` | `github, needs, strategy, matrix, job, runner, env, vars, secrets, inputs`        | None                                             |
| `jobs.<job_id>.steps.continue-on-error`            | `github, needs, strategy, matrix, job, runner, env, vars, secrets, steps, inputs` | `hashFiles`                                      |
| `jobs.<job_id>.steps.env`                          | `github, needs, strategy, matrix, job, runner, env, vars, secrets, steps, inputs` | `hashFiles`                                      |
| `jobs.<job_id>.steps.if`                           | `github, needs, strategy, matrix, job, runner, env, vars, steps, inputs`          | `always, cancelled, success, failure, hashFiles` |
| `jobs.<job_id>.steps.name`                         | `github, needs, strategy, matrix, job, runner, env, vars, secrets, steps, inputs` | `hashFiles`                                      |
| `jobs.<job_id>.steps.run`                          | `github, needs, strategy, matrix, job, runner, env, vars, secrets, steps, inputs` | `hashFiles`                                      |
| `jobs.<job_id>.steps.timeout-minutes`              | `github, needs, strategy, matrix, job, runner, env, vars, secrets, steps, inputs` | `hashFiles`                                      |
| `jobs.<job_id>.steps.with`                         | `github, needs, strategy, matrix, job, runner, env, vars, secrets, steps, inputs` | `hashFiles`                                      |
| `jobs.<job_id>.steps.working-directory`            | `github, needs, strategy, matrix, job, runner, env, vars, secrets, steps, inputs` | `hashFiles`                                      |
| `jobs.<job_id>.strategy`                           | `github, needs, vars, inputs`                                                     | None                                             |
| `jobs.<job_id>.timeout-minutes`                    | `github, needs, strategy, matrix, vars, inputs`                                   | None                                             |
| `jobs.<job_id>.with.<with_id>`                     | `github, needs, strategy, matrix, inputs, vars`                                   | None                                             |
| `on.workflow_call.inputs.<inputs_id>.default`      | `github, inputs, vars`                                                            | None                                             |
| `on.workflow_call.outputs.<output_id>.value`       | `github, jobs, vars, inputs`                                                      | None                                             |

### Example: Printing Context Information to the Log

You can print the contents of contexts to the log for debugging. The `toJSON` function is required to pretty-print JSON objects to the log.

When using the whole `github` context, be mindful that it includes sensitive information such as `github.token`. GitHub masks secrets when they are printed to the console, but you should be cautious when exporting or printing the context.

```yaml
name: Context testing
on: push

jobs:
  dump_contexts_to_log:
    runs-on: ubuntu-latest
    steps:
      - name: Dump GitHub context
        env:
          GITHUB_CONTEXT: ${{ toJson(github) }}
        run: echo "$GITHUB_CONTEXT"
      - name: Dump job context
        env:
          JOB_CONTEXT: ${{ toJson(job) }}
        run: echo "$JOB_CONTEXT"
      - name: Dump steps context
        env:
          STEPS_CONTEXT: ${{ toJson(steps) }}
        run: echo "$STEPS_CONTEXT"
      - name: Dump runner context
        env:
          RUNNER_CONTEXT: ${{ toJson(runner) }}
        run: echo "$RUNNER_CONTEXT"
      - name: Dump strategy context
        env:
          STRATEGY_CONTEXT: ${{ toJson(strategy) }}
        run: echo "$STRATEGY_CONTEXT"
      - name: Dump matrix context
        env:
          MATRIX_CONTEXT: ${{ toJson(matrix) }}
        run: echo "$MATRIX_CONTEXT"
```

## `github` Context

The `github` context contains information about the workflow run and the event that triggered the run. You can read most of the `github` context data in environment variables.

When using the whole `github` context, be mindful that it includes sensitive information such as `github.token`. GitHub masks secrets when they are printed to the console, but you should be cautious when exporting or printing the context.

When creating workflows and actions, you should always consider whether your code might execute untrusted input from possible attackers. Certain contexts should be treated as untrusted input, as an attacker could insert their own malicious content.

| Property name                | Type      | Description |
| ---------------------------- | --------- | ----------- |
| `github`                     | `object`  | The top-level context available during any job or step in a workflow. |
| `github.action`              | `string`  | The name of the action currently running, or the `id` of a step. GitHub removes special characters, and uses the name `__run` when the current step runs a script without an `id`. If you use the same action more than once in the same job, the name will include a suffix with the sequence number with underscore before it. For example, the first script you run will have the name `__run`, and the second script will be named `__run_2`. Similarly, the second invocation of `actions/checkout` will be `actionscheckout2`. |
| `github.action_path`         | `string`  | The path where an action is located. This property is only supported in composite actions. You can use this path to access files located in the same repository as the action, for example by changing directories to the path: `cd "$GITHUB_ACTION_PATH"`. |
| `github.action_ref`          | `string`  | For a step executing an action, this is the ref of the action being executed. For example, `v2`. Do not use in the `run` keyword. |
| `github.action_repository`   | `string`  | For a step executing an action, this is the owner and repository name of the action. For example, `actions/checkout`. Do not use in the `run` keyword. |
| `github.action_status`       | `string`  | For a composite action, the current result of the composite action. |
| `github.actor`               | `string`  | The username of the user that triggered the initial workflow run. If the workflow run is a re-run, this value may differ from `github.triggering_actor`. Any workflow re-runs will use the privileges of `github.actor`, even if the actor initiating the re-run (`github.triggering_actor`) has different privileges. |
| `github.actor_id`            | `string`  | The account ID of the person or app that triggered the initial workflow run. For example, `1234567`. Note that this is different from the actor username. |
| `github.api_url`             | `string`  | The URL of the GitHub REST API. |
| `github.base_ref`            | `string`  | The `base_ref` or target branch of the pull request in a workflow run. This property is only available when the event that triggers a workflow run is either `pull_request` or `pull_request_target`. |
| `github.env`                 | `string`  | Path on the runner to the file that sets environment variables from workflow commands. This file is unique to the current step and is a different file for each step in a job. |
| `github.event`               | `object`  | The full event webhook payload. You can access individual properties of the event using this context. This object is identical to the webhook payload of the event that triggered the workflow run, and is different for each event. |
| `github.event_name`          | `string`  | The name of the event that triggered the workflow run. |
| `github.event_path`          | `string`  | The path to the file on the runner that contains the full event webhook payload. |
| `github.graphql_url`         | `string`  | The URL of the GitHub GraphQL API. |
| `github.head_ref`            | `string`  | The `head_ref` or source branch of the pull request in a workflow run. This property is only available when the event that triggers a workflow run is either `pull_request` or `pull_request_target`. |
| `github.job`                 | `string`  | The `job_id` of the current job. Note: This context property is set by the Actions runner, and is only available within the execution `steps` of a job. Otherwise, the value of this property will be `null`. |
| `github.path`                | `string`  | Path on the runner to the file that sets system `PATH` variables from workflow commands. This file is unique to the current step and is a different file for each step in a job. |
| `github.ref`                 | `string`  | The fully-formed ref of the branch or tag that triggered the workflow run. For workflows triggered by `push`, this is the branch or tag ref that was pushed. For workflows triggered by `pull_request` that were not merged, this is the pull request merge branch. If the pull request was merged, this is the branch it was merged into. For workflows triggered by `release`, this is the release tag created. For other triggers, this is the branch or tag ref that triggered the workflow run. The ref given is fully-formed, meaning that for branches the format is `refs/heads/<branch_name>`. For pull request events except `pull_request_target` that were not merged, it is `refs/pull/<pr_number>/merge`. `pull_request_target` events have the `ref` from the base branch. For tags it is `refs/tags/<tag_name>`. For example, `refs/heads/feature-branch-1`. |
| `github.ref_name`            | `string`  | The short ref name of the branch or tag that triggered the workflow run. This value matches the branch or tag name shown on GitHub. For example, `feature-branch-1`. For pull requests that were not merged, the format is `<pr_number>/merge`. |
| `github.ref_protected`       | `boolean` | `true` if branch protections or rulesets are configured for the ref that triggered the workflow run. |
| `github.ref_type`            | `string`  | The type of ref that triggered the workflow run. Valid values are `branch` or `tag`. |
| `github.repository`          | `string`  | The owner and repository name. For example, `octocat/Hello-World`. |
| `github.repository_id`       | `string`  | The ID of the repository. For example, `123456789`. Note that this is different from the repository name. |
| `github.repository_owner`    | `string`  | The repository owner's username. For example, `octocat`. |
| `github.repository_owner_id` | `string`  | The repository owner's account ID. For example, `1234567`. Note that this is different from the owner's name. |
| `github.repositoryUrl`       | `string`  | The Git URL to the repository. For example, `git://github.com/octocat/hello-world.git`. |
| `github.retention_days`      | `string`  | The number of days that workflow run logs and artifacts are kept. |
| `github.run_id`              | `string`  | A unique number for each workflow run within a repository. This number does not change if you re-run the workflow run. |
| `github.run_number`          | `string`  | A unique number for each run of a particular workflow in a repository. This number begins at 1 for the workflow's first run, and increments with each new run. This number does not change if you re-run the workflow run. |
| `github.run_attempt`         | `string`  | A unique number for each attempt of a particular workflow run in a repository. This number begins at 1 for the workflow run's first attempt, and increments with each re-run. |
| `github.secret_source`       | `string`  | The source of a secret used in a workflow. Possible values are `None`, `Actions`, `Codespaces`, or `Dependabot`. |
| `github.server_url`          | `string`  | The URL of the GitHub server. For example: `https://github.com`. |
| `github.sha`                 | `string`  | The commit SHA that triggered the workflow. The value of this commit SHA depends on the event that triggered the workflow. For example, `ffac537e6cbbf934b08745a378932722df287a53`. |
| `github.token`               | `string`  | A token to authenticate on behalf of the GitHub App installed on your repository. This is functionally equivalent to the `GITHUB_TOKEN` secret. Note: This context property is set by the Actions runner, and is only available within the execution `steps` of a job. Otherwise, the value of this property will be `null`. |
| `github.triggering_actor`    | `string`  | The username of the user that initiated the workflow run. If the workflow run is a re-run, this value may differ from `github.actor`. Any workflow re-runs will use the privileges of `github.actor`, even if the actor initiating the re-run (`github.triggering_actor`) has different privileges. |
| `github.workflow`            | `string`  | The name of the workflow. If the workflow file doesn't specify a `name`, the value of this property is the full path of the workflow file in the repository. |
| `github.workflow_ref`        | `string`  | The ref path to the workflow. For example, `octocat/hello-world/.github/workflows/my-workflow.yml@refs/heads/my_branch`. |
| `github.workflow_sha`        | `string`  | The commit SHA for the workflow file. |
| `github.workspace`           | `string`  | The default working directory on the runner for steps, and the default location of your repository when using the `checkout` action. |

### Example Contents of the `github` Context

```json
{
  "token": "***",
  "job": "dump_contexts_to_log",
  "ref": "refs/heads/my_branch",
  "sha": "c27d339ee6075c1f744c5d4b200f7901aad2c369",
  "repository": "octocat/hello-world",
  "repository_owner": "octocat",
  "repositoryUrl": "git://github.com/octocat/hello-world.git",
  "run_id": "1536140711",
  "run_number": "314",
  "retention_days": "90",
  "run_attempt": "1",
  "actor": "octocat",
  "workflow": "Context testing",
  "head_ref": "",
  "base_ref": "",
  "event_name": "push",
  "event": {
    ...
  },
  "server_url": "https://github.com",
  "api_url": "https://api.github.com",
  "graphql_url": "https://api.github.com/graphql",
  "ref_name": "my_branch",
  "ref_protected": false,
  "ref_type": "branch",
  "secret_source": "Actions",
  "workspace": "/home/runner/work/hello-world/hello-world",
  "action": "github_step",
  "event_path": "/home/runner/work/_temp/_github_workflow/event.json",
  "action_repository": "",
  "action_ref": "",
  "path": "/home/runner/work/_temp/_runner_file_commands/add_path_b037e7b5-1c88-48e2-bf78-eaaab5e02602",
  "env": "/home/runner/work/_temp/_runner_file_commands/set_env_b037e7b5-1c88-48e2-bf78-eaaab5e02602"
}
```

### Example Usage of the `github` Context

```yaml
name: Run CI
on: [push, pull_request]

jobs:
  normal_ci:
    runs-on: ubuntu-latest
    steps:
      - name: Run normal CI
        run: echo "Running normal CI"

  pull_request_ci:
    runs-on: ubuntu-latest
    if: ${{ github.event_name == 'pull_request' }}
    steps:
      - name: Run PR CI
        run: echo "Running PR only CI"
```

## `env` Context

The `env` context contains variables that have been set in a workflow, job, or step. It does not contain variables inherited by the runner process. You can use the `env` context in any key in a workflow step except for the `id` and `uses` keys. If you want to use the value of a variable inside a runner, use the runner operating system's normal method for reading environment variables.

| Property name    | Type     | Description |
| ---------------- | -------- | ----------- |
| `env`            | `object` | This context changes for each step in a job. You can access this context from any step in a job. |
| `env.<env_name>` | `string` | The value of a specific environment variable. |

### Example Contents of the `env` Context

```json
{
  "first_name": "Mona",
  "super_duper_var": "totally_awesome"
}
```

### Example Usage of the `env` Context

When more than one environment variable is defined with the same name, GitHub uses the most specific variable. For example, an environment variable defined in a step will override job and workflow environment variables with the same name, while the step executes. An environment variable defined for a job will override a workflow variable with the same name, while the job executes.

```yaml
name: Hi Mascot
on: push
env:
  mascot: Mona
  super_duper_var: totally_awesome

jobs:
  windows_job:
    runs-on: windows-latest
    steps:
      - run: echo 'Hi ${{ env.mascot }}'  # Hi Mona
      - run: echo 'Hi ${{ env.mascot }}'  # Hi Octocat
        env:
          mascot: Octocat
  linux_job:
    runs-on: ubuntu-latest
    env:
      mascot: Tux
    steps:
      - run: echo 'Hi ${{ env.mascot }}'  # Hi Tux
```

## `vars` Context

The `vars` context contains custom configuration variables set at the organization, repository, and environment levels.

### Example Contents of the `vars` Context

```json
{
  "mascot": "Mona"
}
```

### Example Usage of the `vars` Context

Configuration variables at the environment level are automatically available after their environment is declared by the runner. If a configuration variable has not been set, the return value of a context referencing the variable will be an empty string.

```yaml
on:
  workflow_dispatch:
env:
  # Setting an environment variable with the value of a configuration variable
  env_var: ${{ vars.ENV_CONTEXT_VAR }}

jobs:
  display-variables:
    name: ${{ vars.JOB_NAME }}
    # You can use configuration variables with the `vars` context for dynamic jobs
    if: ${{ vars.USE_VARIABLES == 'true' }}
    runs-on: ${{ vars.RUNNER }}
    environment: ${{ vars.ENVIRONMENT_STAGE }}
    steps:
    - name: Use variables
      run: |
        echo "repository variable : $REPOSITORY_VAR"
        echo "organization variable : $ORGANIZATION_VAR"
        echo "overridden variable : $OVERRIDE_VAR"
        echo "variable from shell environment : $env_var"
      env:
        REPOSITORY_VAR: ${{ vars.REPOSITORY_VAR }}
        ORGANIZATION_VAR: ${{ vars.ORGANIZATION_VAR }}
        OVERRIDE_VAR: ${{ vars.OVERRIDE_VAR }}

    - name: ${{ vars.HELLO_WORLD_STEP }}
      if: ${{ vars.HELLO_WORLD_ENABLED == 'true' }}
      uses: actions/hello-world-javascript-action@main
      with:
        who-to-greet: ${{ vars.GREET_NAME }}
```

## `job` Context

The `job` context contains information about the currently running job.

| Property name                       | Type     | Description |
| ----------------------------------- | -------- | ----------- |
| `job`                               | `object` | This context changes for each job in a workflow run. You can access this context from any step in a job. |
| `job.check_run_id`                  | `number` | The check run ID of the current job. |
| `job.container`                     | `object` | Information about the job's container. |
| `job.container.id`                  | `string` | The ID of the container. |
| `job.container.network`             | `string` | The ID of the container network. The runner creates the network used by all containers in a job. |
| `job.services`                      | `object` | The service containers created for a job. |
| `job.services.<service_id>.id`      | `string` | The ID of the service container. |
| `job.services.<service_id>.network` | `string` | The ID of the service container network. The runner creates the network used by all containers in a job. |
| `job.services.<service_id>.ports`   | `object` | The exposed ports of the service container. |
| `job.status`                        | `string` | The current status of the job. Possible values are `success`, `failure`, or `cancelled`. |
| `job.workflow_ref`                  | `string` | The full ref of the workflow file that defines the current job. For example, `octo-org/octo-repo/.github/workflows/deploy.yml@refs/heads/main`. For jobs defined directly in a workflow file, this is the same as `github.workflow_ref`. For jobs defined in a reusable workflow, this refers to the reusable workflow file. (not available on GitHub Enterprise Server) |
| `job.workflow_sha`                  | `string` | The commit SHA of the workflow file that defines the current job. (not available on GitHub Enterprise Server) |
| `job.workflow_repository`           | `string` | The `owner/repo` of the repository containing the workflow file that defines the current job. For example, `octo-org/octo-repo`. (not available on GitHub Enterprise Server) |
| `job.workflow_file_path`            | `string` | The file path of the workflow file that defines the current job, relative to the repository root. For example, `.github/workflows/deploy.yml`. (not available on GitHub Enterprise Server) |

### Example Contents of the `job` Context

```json
{
  "status": "success",
  "check_run_id": 51725241954,
  "workflow_ref": "octo-org/octo-repo/.github/workflows/deploy.yml@refs/heads/main",
  "workflow_sha": "abc123def456789abc123def456789abc123def4",
  "workflow_repository": "octo-org/octo-repo",
  "workflow_file_path": ".github/workflows/deploy.yml",
  "container": {
    "network": "github_network_53269bd575974817b43f4733536b200c"
  },
  "services": {
    "postgres": {
      "id": "60972d9aa486605e66b0dad4abb638dc3d9116f566579e418166eedb8abb9105",
      "ports": {
        "5432": "49153"
      },
      "network": "github_network_53269bd575974817b43f4733536b200c"
    }
  }
}
```

### Example Usage of the `job` Context

```yaml
name: PostgreSQL Service Example
on: push
jobs:
  postgres-job:
    runs-on: ubuntu-latest
    services:
      postgres:
        image: postgres
        env:
          POSTGRES_PASSWORD: postgres
        options: --health-cmd pg_isready --health-interval 10s --health-timeout 5s --health-retries 5
        ports:
          # Maps TCP port 5432 in the service container to a randomly chosen available port on the host.
          - 5432

    steps:
      - run: pg_isready -h localhost -p ${{ job.services.postgres.ports[5432] }}
      - run: echo "Run tests against Postgres"
```

### Example Usage of `job` Context Workflow Identity

The `job.workflow_*` context properties are not available on GitHub Enterprise Server.

```yaml
# In a reusable workflow (e.g., octo-org/shared-workflows/.github/workflows/deploy.yml)
name: Reusable deploy workflow
on:
  workflow_call:

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v6
        with:
          repository: ${{ job.workflow_repository }}
          ref: ${{ job.workflow_sha }}

      - run: echo "Deploying from ${{ job.workflow_ref }}"
      - run: echo "Workflow file path is ${{ job.workflow_file_path }}"
```

## `jobs` Context

The `jobs` context is only available in reusable workflows, and can only be used to set outputs for a reusable workflow.

| Property name                         | Type     | Description |
| ------------------------------------- | -------- | ----------- |
| `jobs`                                | `object` | This is only available in reusable workflows, and can only be used to set outputs for a reusable workflow. |
| `jobs.<job_id>.result`                | `string` | The result of a job in the reusable workflow. Possible values are `success`, `failure`, `cancelled`, or `skipped`. |
| `jobs.<job_id>.outputs`               | `object` | The set of outputs of a job in a reusable workflow. |
| `jobs.<job_id>.outputs.<output_name>` | `string` | The value of a specific output for a job in a reusable workflow. |

### Example Contents of the `jobs` Context

```json
{
  "example_job": {
    "result": "success",
    "outputs": {
      "output1": "hello",
      "output2": "world"
    }
  }
}
```

### Example Usage of the `jobs` Context

```yaml
name: Reusable workflow

on:
  workflow_call:
    # Map the workflow outputs to job outputs
    outputs:
      firstword:
        description: "The first output string"
        value: ${{ jobs.example_job.outputs.output1 }}
      secondword:
        description: "The second output string"
        value: ${{ jobs.example_job.outputs.output2 }}

jobs:
  example_job:
    name: Generate output
    runs-on: ubuntu-latest
    # Map the job outputs to step outputs
    outputs:
      output1: ${{ steps.step1.outputs.firstword }}
      output2: ${{ steps.step2.outputs.secondword }}
    steps:
      - id: step1
        run: echo "firstword=hello" >> $GITHUB_OUTPUT
      - id: step2
        run: echo "secondword=world" >> $GITHUB_OUTPUT
```

## `steps` Context

The `steps` context contains information about the steps in the current job that have an `id` specified and have already run.

| Property name                           | Type     | Description |
| --------------------------------------- | -------- | ----------- |
| `steps`                                 | `object` | This context changes for each step in a job. You can access this context from any step in a job. |
| `steps.<step_id>.outputs`               | `object` | The set of outputs defined for the step. |
| `steps.<step_id>.conclusion`            | `string` | The result of a completed step after `continue-on-error` is applied. Possible values are `success`, `failure`, `cancelled`, or `skipped`. When a `continue-on-error` step fails, the `outcome` is `failure`, but the final `conclusion` is `success`. |
| `steps.<step_id>.outcome`               | `string` | The result of a completed step before `continue-on-error` is applied. Possible values are `success`, `failure`, `cancelled`, or `skipped`. When a `continue-on-error` step fails, the `outcome` is `failure`, but the final `conclusion` is `success`. |
| `steps.<step_id>.outputs.<output_name>` | `string` | The value of a specific output. |

### Example Contents of the `steps` Context

```json
{
  "checkout": {
    "outputs": {},
    "outcome": "success",
    "conclusion": "success"
  },
  "generate_number": {
    "outputs": {
      "random_number": "1"
    },
    "outcome": "success",
    "conclusion": "success"
  }
}
```

### Example Usage of the `steps` Context

```yaml
name: Generate random failure
on: push
jobs:
  randomly-failing-job:
    runs-on: ubuntu-latest
    steps:
      - name: Generate 0 or 1
        id: generate_number
        run: echo "random_number=$(($RANDOM % 2))" >> $GITHUB_OUTPUT
      - name: Pass or fail
        run: |
          if [[ ${{ steps.generate_number.outputs.random_number }} == 0 ]]; then exit 0; else exit 1; fi
```

## `runner` Context

The `runner` context contains information about the runner that is executing the current job.

| Property name        | Type     | Description |
| -------------------- | -------- | ----------- |
| `runner`             | `object` | This context changes for each job in a workflow run. |
| `runner.name`        | `string` | The name of the runner executing the job. This name may not be unique in a workflow run as runners at the repository and organization levels could use the same name. |
| `runner.os`          | `string` | The operating system of the runner executing the job. Possible values are `Linux`, `Windows`, or `macOS`. |
| `runner.arch`        | `string` | The architecture of the runner executing the job. Possible values are `X86`, `X64`, `ARM`, or `ARM64`. |
| `runner.temp`        | `string` | The path to a temporary directory on the runner. This directory is emptied at the beginning and end of each job. Note that files will not be removed if the runner's user account does not have permission to delete them. |
| `runner.tool_cache`  | `string` | The path to the directory containing preinstalled tools for GitHub-hosted runners. |
| `runner.debug`       | `string` | This is set only if debug logging is enabled, and always has the value of `1`. It can be useful as an indicator to enable additional debugging or verbose logging in your own job steps. |
| `runner.environment` | `string` | The environment of the runner executing the job. Possible values are: `github-hosted` for GitHub-hosted runners provided by GitHub, and `self-hosted` for self-hosted runners configured by the repository owner. |

### Example Contents of the `runner` Context

```json
{
  "os": "Linux",
  "arch": "X64",
  "name": "GitHub Actions 2",
  "tool_cache": "/opt/hostedtoolcache",
  "temp": "/home/runner/work/_temp"
}
```

### Example Usage of the `runner` Context

```yaml
name: Build
on: push

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v6
      - name: Build with logs
        run: |
          mkdir ${{ runner.temp }}/build_logs
          echo "Logs from building" > ${{ runner.temp }}/build_logs/build.logs
          exit 1
      - name: Upload logs on fail
        if: ${{ failure() }}
        uses: actions/upload-artifact@v4
        with:
          name: Build failure logs
          path: ${{ runner.temp }}/build_logs
```

## `secrets` Context

The `secrets` context contains the names and values of secrets that are available to a workflow run. The `secrets` context is not available for composite actions due to security reasons. If you want to pass a secret to a composite action, you need to do it explicitly as an input.

`GITHUB_TOKEN` is a secret that is automatically created for every workflow run, and is always included in the `secrets` context.

If a secret is used in a workflow job, GitHub automatically redacts secrets printed to the log. You should avoid printing secrets to the log intentionally.

| Property name           | Type     | Description |
| ----------------------- | -------- | ----------- |
| `secrets`               | `object` | This context is the same for each job in a workflow run. You can access this context from any step in a job. |
| `secrets.GITHUB_TOKEN`  | `string` | Automatically created token for each workflow run. |
| `secrets.<secret_name>` | `string` | The value of a specific secret. |

### Example Contents of the `secrets` Context

```json
{
  "github_token": "***",
  "NPM_TOKEN": "***",
  "SUPERSECRET": "***"
}
```

### Example Usage of the `secrets` Context

```yaml
name: Open new issue
on: workflow_dispatch

jobs:
  open-issue:
    runs-on: ubuntu-latest
    permissions:
      contents: read
      issues: write
    steps:
      - run: |
          gh issue --repo ${{ github.repository }} \
            create --title "Issue title" --body "Issue body"
        env:
          GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

## `strategy` Context

For workflows with a matrix, the `strategy` context contains information about the matrix execution strategy for the current job.

| Property name           | Type      | Description |
| ----------------------- | --------- | ----------- |
| `strategy`              | `object`  | This context changes for each job in a workflow run. You can access this context from any job or step in a workflow. |
| `strategy.fail-fast`    | `boolean` | When this evaluates to `true`, all in-progress jobs are canceled if any job in a matrix fails. |
| `strategy.job-index`    | `number`  | The index of the current job in the matrix. **Note:** This number is a zero-based number. The first job's index in a matrix is `0`. |
| `strategy.max-parallel` | `number`  | The maximum number of jobs that can run simultaneously when using a matrix job strategy. |

### Example Contents of the `strategy` Context

```json
{
  "fail-fast": true,
  "job-index": 1,
  "max-parallel": 2
}
```

### Example Usage of the `strategy` Context

```yaml
name: Test matrix
on: push

jobs:
  test:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        test-group: [1, 2]
        node-version: [14, 16]
    steps:
      - uses: actions/checkout@v6
      - uses: actions/setup-node@v4
        with:
          node-version: ${{ matrix.node-version }}
      - run: npm test > test-output-${{ strategy.job-index }}.txt
      - uses: actions/upload-artifact@v4
        if: always()
        with:
          name: test-output-${{ strategy.job-index }}
          path: test-output-${{ strategy.job-index }}.txt
```

## `matrix` Context

The `matrix` context contains the matrix properties defined in the workflow that apply to the current job. For example, if you configure a matrix with the `os` and `node` versions, the `matrix` context object contains the `os` and `node` versions of the current job.

| Property name        | Type     | Description |
| -------------------- | -------- | ----------- |
| `matrix`             | `object` | This context only exists for jobs in a workflow run, and is different for each job in a matrix. You can access this context from any job or step. |
| `matrix.<property>` | `string` | The value of a matrix property. For example, the current value of the `os` or `node` property if your matrix job is executing a build for those values. |

### Example Contents of the `matrix` Context

```json
{
  "os": "ubuntu-latest",
  "node": 16
}
```

### Example Usage of the `matrix` Context

```yaml
name: Test matrix
on: push

jobs:
  test:
    runs-on: ${{ matrix.os }}
    strategy:
      matrix:
        os: [ubuntu-latest, windows-latest]
        node: [14, 16]
    steps:
      - uses: actions/checkout@v6
      - uses: actions/setup-node@v4
        with:
          node-version: ${{ matrix.node }}
      - name: Run tests
        run: npm test
      - name: Log matrix values
        run: |
          echo "Running tests on ${{ matrix.os }} with Node.js ${{ matrix.node }}"
```

## `needs` Context

The `needs` context contains outputs from all jobs that are defined as a dependency of the current job.

| Property name                   | Type     | Description |
| ------------------------------- | -------- | ----------- |
| `needs`                         | `object` | This context only exists for jobs that have dependencies. You can access this context from any job that needs other jobs. |
| `needs.<job_id>`                | `object` | A single job that the current job depends on. |
| `needs.<job_id>.outputs`        | `object` | The set of outputs of a job that the current job depends on. |
| `needs.<job_id>.outputs.<name>` | `string` | The value of a specific output for a job that the current job depends on. |
| `needs.<job_id>.result`         | `string` | The result of a job that the current job depends on. Possible values are `success`, `failure`, `cancelled`, or `skipped`. |

### Example Contents of the `needs` Context

```json
{
  "build": {
    "result": "success",
    "outputs": {
      "build_id": "ABC123"
    }
  },
  "deploy": {
    "result": "failure",
    "outputs": {}
  }
}
```

### Example Usage of the `needs` Context

```yaml
name: Build and deploy

on: push

jobs:
  build:
    runs-on: ubuntu-latest
    outputs:
      build_id: ${{ steps.build.outputs.build_id }}
    steps:
      - uses: actions/checkout@v6
      - name: Build
        id: build
        run: |
          echo "build_id=ABC123" >> $GITHUB_OUTPUT

  deploy:
    needs: build
    runs-on: ubuntu-latest
    steps:
      - name: Deploy
        run: echo "Deploying build ${{ needs.build.outputs.build_id }}"

  report:
    needs: [build, deploy]
    runs-on: ubuntu-latest
    if: always()
    steps:
      - name: Report results
        run: |
          echo "Build result: ${{ needs.build.result }}"
          echo "Deploy result: ${{ needs.deploy.result }}"
```

## `inputs` Context

The `inputs` context contains input properties passed to an action, a job in a reusable workflow, or a manually triggered workflow. For a workflow event triggered by `workflow_dispatch`, you can optionally provide inputs that are passed through the GitHub API.

For reusable workflows called with `jobs.<job_id>.uses`, the inputs are defined in the workflow that is called with `on.workflow_call.inputs`. The `inputs` context is available for a reusable workflow that is called from a job using `jobs.<job_id>.with`.

Unlike `github.event.inputs`, the `inputs` context is available regardless of how the workflow is triggered.

| Property name      | Type     | Description |
| ------------------ | -------- | ----------- |
| `inputs`           | `object` | This context is only available in reusable workflows or in workflows triggered with `workflow_dispatch`. You can access this context from any job or step in a job. |
| `inputs.<input_id>` | `string` | The value of a specific input. If the input is a boolean, the string value is `'true'` or `'false'`. If the input is a choice, the value is the selected option. |

### Example Contents of the `inputs` Context

```json
{
  "environment": "production",
  "username": "octocat",
  "enable-debug": "true"
}
```

### Example Usage of the `inputs` Context

```yaml
name: Reusable workflow

on:
  workflow_dispatch:
    inputs:
      environment:
        required: true
        type: choice
        options:
          - production
          - staging
      username:
        required: false
        type: string
      enable-debug:
        required: false
        type: boolean

jobs:
  log-inputs:
    runs-on: ubuntu-latest
    steps:
      - name: Log inputs
        run: |
          echo "Environment: ${{ inputs.environment }}"
          echo "Username: ${{ inputs.username }}"
          echo "Debug mode: ${{ inputs.enable-debug }}"
```

---

## Evaluate expressions in workflows and actions

> Source: https://docs.github.com/en/actions/reference/workflows-and-actions/expressions
> (Listed task URL `/en/actions/writing-workflows/choosing-what-your-workflow-does/evaluate-expressions-in-workflows-and-actions` redirects here.)
> **Fidelity note:** the fetch backend preserved all tables, operators, function signatures, and examples but compressed some prose. The status-check functions and object filters are summarized at the description level; consult the source URL for full per-function prose and additional YAML examples.

# Evaluate Expressions in Workflows and Actions

GitHub Actions supports expressions that enable dynamic workflow configuration.

## Literals

Available data types include `boolean`, `null`, `number`, and `string`.

| Data type | Literal value |
| --------- | ------------- |
| `boolean` | `true` or `false` |
| `null` | `null` |
| `number` | Any JSON-supported number format |
| `string` | Enclose in single quotes if using `${{ }}` syntax; escape literal single quotes with `''`; double quotes cause errors |

Falsy values (`false`, `0`, `-0`, `""`, `''`, `null`) coerce to `false`; truthy values coerce to `true` in conditionals.

## Operators

| Operator | Description |
| -------- | ----------- |
| `( )` | Logical grouping |
| `[ ]` | Index |
| `.` | Property de-reference |
| `!` | Not |
| `<` | Less than |
| `<=` | Less than or equal |
| `>` | Greater than |
| `>=` | Greater than or equal |
| `==` | Equal |
| `!=` | Not equal |
| `&&` | And |
| `\|\|` | Or |

GitHub performs loose equality comparisons and coerces types to numbers:

| Type | Result |
| ---- | ------ |
| Null | `0` |
| Boolean | `true` returns `1`; `false` returns `0` |
| String | Parsed as JSON number; empty string returns `0`; otherwise `NaN` |
| Array | `NaN` |
| Object | `NaN` |

String comparisons are case-insensitive; objects/arrays are equal only when identical instances.

## Functions

### contains

`contains( search, item )` returns `true` if `search` contains `item`. Works with arrays and strings (case-insensitive).

Example: `contains('Hello world', 'llo')` returns `true`

### startsWith

`startsWith( searchString, searchValue )` returns `true` when string begins with specified value (case-insensitive).

Example: `startsWith('Hello world', 'He')` returns `true`

### endsWith

`endsWith( searchString, searchValue )` returns `true` when string ends with specified value (case-insensitive).

Example: `endsWith('Hello world', 'ld')` returns `true`

### format

`format( string, replaceValue0, replaceValue1, ..., replaceValueN)` replaces `{N}` placeholders with values.

Example: `format('Hello {0} {1} {2}', 'Mona', 'the', 'Octocat')` returns `'Hello Mona the Octocat'`

(To output a literal brace, double it: `{{` and `}}`.)

### join

`join( array, optionalSeparator )` concatenates array values into a string, using default comma separator or provided separator.

Example: `join(github.event.issue.labels.*.name, ', ')` may return `'bug, help wanted'`

### toJSON

`toJSON(value)` returns pretty-printed JSON representation for debugging context information.

### fromJSON

`fromJSON(value)` converts JSON strings to objects or data types. Enables passing JSON matrices between jobs and converting environment variables to appropriate types.

### hashFiles

`hashFiles(path)` calculates SHA-256 hash for matched files. Supports glob patterns and multiple comma-separated patterns.

Example: `hashFiles('**/package-lock.json')` matches any `package-lock.json` file

### case

`case( pred1, val1, pred2, val2, ..., default )` evaluates predicates in order and returns value matching first true predicate or default.

## Status Check Functions

You can use the following status check functions as expressions in `if` conditionals. A default status check of `success()` is applied unless you include one of these functions.

### success

Returns `true` when all previous steps/jobs succeed.

### always

Causes step to always execute and returns `true`, even when canceled. Use `if: ${{ !cancelled() }}` as preferred alternative for critical tasks.

### cancelled

Returns `true` if the workflow was canceled.

### failure

Returns `true` when any previous step fails. With dependent jobs, returns `true` if any ancestor job fails.

## Object Filters

Use `*` syntax to filter collections. Example: `fruits.*.name` on an array of fruit objects returns just the name values. Order isn't guaranteed for objects.

---

## Using secrets in GitHub Actions

> Source: https://docs.github.com/en/actions/how-tos/write-workflows/choose-what-workflows-do/use-secrets
> (Listed task URL `/en/actions/security-for-github-actions/security-guides/using-secrets-in-github-actions` redirects here.)
> **Fidelity note:** the fetch backend heavily compressed the prose on this page. Captured below are the CLI commands, the secret levels and their permission requirements, the in-workflow usage YAML, and the large-secret guidance. Consult the source URL and the Secrets reference (`/en/actions/reference/security/secrets`) for full naming rules and limits prose.

# Using secrets in GitHub Actions

Secrets allow you to store sensitive information, such as access tokens, in your repository, repository environments, or organization. GitHub supports secrets at three levels:

* **Repository secrets** — require write access (or collaborator status for personal repos).
* **Environment secrets** — require owner status (personal) or admin access (organization repositories).
* **Organization secrets** — restricted to organization owners; unavailable for private repositories on GitHub Free plans. You can use access policies to control which repositories can use organization secrets.

## Naming your secrets

The following rules apply to secret names (verify against the Secrets reference for the authoritative list):

* Names can only contain alphanumeric characters (`[a-z]`, `[A-Z]`, `[0-9]`) or underscores (`_`). Spaces are not allowed.
* Names must not start with the `GITHUB_` prefix.
* Names must not start with a number.
* Names are case insensitive.
* Names must be unique at the level they are created.

## Creating secrets for a repository

In the web UI: navigate to **Settings > Secrets and variables > Actions**, click **New repository secret**, enter the name and value, then click **Add secret**.

With GitHub CLI:

```shell
gh secret set SECRET_NAME
```

You can also read the value from a file:

```shell
gh secret set SECRET_NAME < secret.txt
```

## Creating secrets for an environment

In the web UI: navigate to **Settings > Environments**, select your environment, then click **Add secret** under Environment secrets. (Environment-level secrets require admin access in organization repositories.)

With GitHub CLI:

```shell
gh secret set --env ENV_NAME SECRET_NAME
```

## Creating secrets for an organization

In the web UI: navigate to your organization's **Settings > Secrets and variables > Actions**, then click **New organization secret**. You can configure repository access policies for the secret.

With GitHub CLI (requires the `admin:org` scope):

```shell
gh secret set --org ORG_NAME SECRET_NAME
```

Use `--visibility all` to make the secret available to all repositories, or `--repos REPO-NAME-1,REPO-NAME-2` to specify selected repositories:

```shell
gh secret set --org ORG_NAME SECRET_NAME --repos REPO-NAME-1,REPO-NAME-2
```

## Using secrets in a workflow

To provide an action with a secret as an input or environment variable, you can use the `secrets` context to access secrets you've created in your repository.

```yaml
steps:
  - name: Hello world action
    with: # Set the secret as an input
      super_secret: ${{ secrets.SuperSecret }}
    env: # Or as an environment variable
      super_secret: ${{ secrets.SuperSecret }}
```

Notes:

* Secrets cannot be directly referenced in `if:` conditionals. Instead, set the secret as a job- or step-level environment variable, then reference the environment variable to conditionally run steps in the job.
* With the exception of `GITHUB_TOKEN`, secrets are not passed to the runner when a workflow is triggered from a forked repository.
* Avoid passing secrets between processes from the command line whenever possible, as command-line processes may be visible to other users (using the `ps` command) or captured by security audit events. When you must pass secrets on the command line, wrap them in proper quoting (the docs provide bash, PowerShell, and Cmd.exe examples).

## Limits / storing large secrets

* The maximum size for an individual secret is 48 KB.
* To store larger secrets, encrypt the value (for example with GPG using a passphrase), store the encrypted file in your repository, and store the passphrase as a separate secret; the workflow decrypts the file at runtime.
* For large binary blobs, Base64-encode the value before storing it as a secret (note Base64 encoding does not count as encryption).

## Redacting secrets from workflow run logs

If a secret is used in a workflow job, GitHub automatically redacts the secret value when it is printed to the log. You should still avoid printing secrets to the log intentionally, and avoid using structured data (such as JSON, XML, or YAML) as a secret value, because redaction of these values is not guaranteed.

---

## OpenID Connect

> Source: https://docs.github.com/en/actions/concepts/security/openid-connect
> (Listed task URL `/en/actions/security-for-github-actions/security-hardening-your-deployments/about-security-hardening-with-openid-connect` redirects here.)

# OpenID Connect

OpenID Connect allows your workflows to exchange short-lived tokens directly from your cloud provider.

## Overview of OpenID Connect (OIDC)

GitHub Actions workflows are often designed to access a cloud provider (such as AWS, Azure, GCP, HashiCorp Vault, and others) in order to deploy software or use the cloud's services. Before the workflow can access these resources, it will supply credentials, such as a password or token, to the cloud provider. These credentials are usually stored as a secret in GitHub, and the workflow presents this secret to the cloud provider every time it runs.

However, using hardcoded secrets requires you to create credentials in the cloud provider and then duplicate them in GitHub as a secret.

After you have established a trust connection with a cloud provider that supports OIDC, you can configure your workflow to request a short-lived access token directly from the cloud provider.

## Benefits of using OIDC

By updating your workflows to use OIDC tokens, you can adopt the following good security practices:

* **No cloud secrets:** You won't need to duplicate your cloud credentials as long-lived GitHub secrets. Instead, you can configure the OIDC trust on your cloud provider, and then update your workflows to request a short-lived access token from the cloud provider through OIDC.
* **Authentication and authorization management:** You have more granular control over how workflows can use credentials, using your cloud provider's authentication (authN) and authorization (authZ) tools to control access to cloud resources.
* **Rotating credentials:** With OIDC, your cloud provider issues a short-lived access token that is only valid for a single job, and then automatically expires.

## How OIDC integrates with GitHub Actions

The following diagram gives an overview of how GitHub's OIDC provider integrates with your workflows and cloud provider:

1. You establish an OIDC trust relationship in the cloud provider, allowing specific GitHub workflows to request cloud access tokens on behalf of a defined cloud role.
2. Every time your job runs, GitHub's OIDC provider auto-generates an OIDC token. This token contains multiple claims to establish a security-hardened and verifiable identity about the specific workflow that is trying to authenticate.
3. A step or action in the workflow job can request a token from GitHub's OIDC provider, which can then be presented to the cloud provider as proof of the workflow's identity.
4. Once the cloud provider successfully validates the claims presented in the token, it then provides a short-lived cloud access token that is available only for the duration of the job.

## Understanding the OIDC token

Each job requests an OIDC token from GitHub's OIDC provider, which responds with an automatically generated JSON web token (JWT) that is unique for each workflow job where it is generated. When the job runs, the OIDC token is presented to the cloud provider. To validate the token, the cloud provider checks if the OIDC token's subject and other claims are a match for the conditions that were preconfigured on the cloud role's OIDC trust definition.

The following example OIDC token uses a subject (`sub`) that references a job environment named `prod` in the `octo-org/octo-repo` repository.

```yaml
{
  "typ": "JWT",
  "alg": "RS256",
  "x5t": "example-thumbprint",
  "kid": "example-key-id"
}
{
  "jti": "example-id",
  "sub": "repo:octo-org/octo-repo:environment:prod",
  "environment": "prod",
  "aud": "https://github.com/octo-org",
  "ref": "refs/heads/main",
  "sha": "example-sha",
  "repository": "octo-org/octo-repo",
  "repository_owner": "octo-org",
  "actor_id": "12",
  "repository_visibility": "private",
  "repository_id": "74",
  "repository_owner_id": "65",
  "run_id": "example-run-id",
  "run_number": "10",
  "run_attempt": "2",
  "runner_environment": "github-hosted",
  "actor": "octocat",
  "workflow": "example-workflow",
  "head_ref": "",
  "base_ref": "",
  "event_name": "workflow_dispatch",
  "repo_property_workspace_id": "ws-abc123",
  "ref_type": "branch",
  "job_workflow_ref": "octo-org/octo-automation/.github/workflows/oidc.yml@refs/heads/main",
  "iss": "https://token.actions.githubusercontent.com",
  "nbf": 1632492967,
  "exp": 1632493867,
  "iat": 1632493567
}
```

## Authenticating custom actions using OIDC

Custom actions use the `getIDToken()` method from the Actions toolkit or a `curl` command to authenticate using OIDC.

For more information, see [OpenID Connect reference](/en/actions/reference/openid-connect-reference#methods-for-requesting-the-oidc-token).

## Updating your workflows for OIDC

GitHub Actions workflows can use OIDC tokens instead of secrets to authenticate with cloud providers. Many popular cloud providers offer official login actions that simplify the process of using OIDC in your workflows. For more information about updating your workflows with specific cloud providers, see [Security hardening your deployments](/en/actions/how-tos/security-for-github-actions/security-hardening-your-deployments).

## Using repository custom properties as OIDC claims

Organization and enterprise admins can include repository custom properties as claims in OIDC tokens. This enables attribute-based access control (ABAC) policies in your cloud provider, artifact registry, or secrets manager that are driven by repository metadata rather than hard-coded allow lists.

### How custom property claims work

The end-to-end flow for using custom properties as OIDC claims is as follows:

1. **Define custom properties.** An organization or enterprise admin creates custom properties (for example, `business_unit`, `data_classification`, or `environment_tier`) and assigns values to repositories.
2. **Enable properties in OIDC tokens.** An organization or enterprise admin selects which custom properties should be included in OIDC tokens, using the settings UI or the REST API.
3. **Claims appear automatically.** Every workflow run in a repository that has a value set for an enabled property will include that value in its OIDC token, prefixed with `repo_property_`. No workflow-level configuration changes are required.
4. **Update cloud trust policies.** You update your cloud provider's trust conditions to evaluate the new `repo_property_*` claims, enabling fine-grained, attribute-based access decisions.

Because this builds on GitHub's existing OIDC short-lived credential model, no long-lived secrets are required, and every token is scoped, auditable, and automatically rotated per workflow run.

### Prerequisites

* Custom properties must already be defined at the organization or enterprise level.
* You must be an organization admin or enterprise admin.

### Adding a custom property to OIDC token claims

To include a custom property in OIDC tokens, use the REST API or the settings UI for your organization or enterprise.

* **Using the settings UI:** Navigate to your organization or enterprise's Actions OIDC settings page to view and manage which custom properties are included in OIDC tokens.
* **Using the REST API:** Send a `POST` request to the `/orgs/{org}/actions/oidc/customization/properties/repo` endpoint to add a custom property to the OIDC token claims for your organization.

### Example OIDC token with custom properties

The following example shows an OIDC token that includes two custom properties: a single-select property `business_unit` and a string property `workspace_id`. Each custom property appears in the token with the `repo_property_` prefix.

```json
{
  "sub": "repo:my-org/my-repo:ref:refs/heads/main",
  "aud": "https://github.com/my-org",
  "repository": "my-org/my-repo",
  "repository_owner": "my-org",
  "ref": "refs/heads/main",
  "repo_property_business_unit": "payments",
  "repo_property_workspace_id": "ws-abc123"
}
```

You can use the `repo_property_*` claims in your cloud provider's trust conditions to create flexible, attribute-based access control policies.

## OIDC support for Dependabot

Dependabot can use OIDC to authenticate with private registries, eliminating the need to store long-lived credentials as repository secrets. With OIDC-based authentication, Dependabot update jobs can dynamically obtain short-lived credentials from your cloud identity provider.

Dependabot supports OIDC authentication for any registry type that uses `username` and `password` authentication, when the registry is hosted on AWS CodeArtifact, Azure DevOps Artifacts, or JFrog Artifactory.

The benefits of OIDC authentication for Dependabot are:

* **Enhanced security:** Eliminates static, long-lived credentials from your repositories.
* **Simpler management:** Enables secure, policy-compliant access to private registries.
* **Avoid rate limiting:** Dynamic credentials help you avoid hitting rate limits associated with static tokens.

## Next steps

For more information about configuring OIDC, see [Security hardening your deployments](/en/actions/how-tos/security-for-github-actions/security-hardening-your-deployments).

For reference information about OIDC, see [OpenID Connect reference](/en/actions/reference/openid-connect-reference).

---

## Reuse workflows

> Source: https://docs.github.com/en/actions/how-tos/reuse-automations/reuse-workflows
> (Listed task URL `/en/actions/sharing-automations/reusing-workflows` redirects here.)

# Reuse workflows

Learn how to avoid duplication when creating a workflow by reusing existing workflows.

## Creating a reusable workflow

Reusable workflows are YAML-formatted files, very similar to any other workflow file. As with other workflow files, you locate reusable workflows in the `.github/workflows` directory of a repository. Subdirectories of the `workflows` directory are not supported.

For a workflow to be reusable, the values for `on` must include `workflow_call`:

```yaml
on:
  workflow_call:
```

## Using inputs and secrets in a reusable workflow

You can define inputs and secrets, which can be passed from the caller workflow and then used within the called workflow. There are three stages to using an input or a secret in a reusable workflow.

1. In the reusable workflow, use the `inputs` and `secrets` keywords to define inputs or secrets that will be passed from a caller workflow.

```yaml
on:
  workflow_call:
    inputs:
      config-path:
        required: true
        type: string
    secrets:
      personal_access_token:
        required: true
```

2. In the reusable workflow, reference the input or secret that you defined in the `on` key in the previous step.

> [!NOTE]
> If the secrets are inherited by using `secrets: inherit` in the calling workflow, you can reference them even if they are not explicitly defined in the `on` key.

```yaml
jobs:
  reusable_workflow_job:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/labeler@v6
      with:
        repo-token: ${{ secrets.personal_access_token }}
        configuration-path: ${{ inputs.config-path }}
```

In the example above, `personal_access_token` is a secret that's defined at the repository or organization level.

> [!WARNING]
> Environment secrets cannot be passed from the caller workflow as `on.workflow_call` does not support the `environment` keyword. If you include `environment` in the reusable workflow at the job level, the environment secret will be used, and not the secret passed from the caller workflow.

3. Pass the input or secret from the caller workflow.

To pass named inputs to a called workflow, use the `with` keyword in a job. Use the `secrets` keyword to pass named secrets. For inputs, the data type of the input value must match the type specified in the called workflow (either boolean, number, or string).

```yaml
jobs:
  call-workflow-passing-data:
    uses: octo-org/example-repo/.github/workflows/reusable-workflow.yml@main
    with:
      config-path: .github/labeler.yml
    secrets:
      personal_access_token: ${{ secrets.token }}
```

Workflows that call reusable workflows in the same organization or enterprise can use the `inherit` keyword to implicitly pass the secrets.

```yaml
jobs:
  call-workflow-passing-data:
    uses: octo-org/example-repo/.github/workflows/reusable-workflow.yml@main
    with:
      config-path: .github/labeler.yml
    secrets: inherit
```

### Example reusable workflow

This reusable workflow file named `workflow-B.yml` takes an input string and a secret from the caller workflow and uses them in an action.

```yaml
name: Reusable workflow example

on:
  workflow_call:
    inputs:
      config-path:
        required: true
        type: string
    secrets:
      token:
        required: true

jobs:
  triage:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/labeler@v6
      with:
        repo-token: ${{ secrets.token }}
        configuration-path: ${{ inputs.config-path }}
```

## Calling a reusable workflow

You call a reusable workflow by using the `uses` keyword. Unlike when you are using actions within a workflow, you call reusable workflows directly within a job, and not from within job steps.

You reference reusable workflow files using one of the following syntaxes:

* `{owner}/{repo}/.github/workflows/{filename}@{ref}` for reusable workflows in public and private repositories.
* `./.github/workflows/{filename}` for reusable workflows in the same repository.

In the first option, `{ref}` can be a SHA, a release tag, or a branch name. If a release tag and a branch have the same name, the release tag takes precedence over the branch name. Using the commit SHA is the safest option for stability and security.

If you use the second syntax option (without `{owner}/{repo}` and `@{ref}`) the called workflow is from the same commit as the caller workflow. Ref prefixes such as `refs/heads` and `refs/tags` are not allowed. You cannot use contexts or expressions in this keyword.

You can call multiple workflows, referencing each in a separate job.

```yaml
jobs:
  call-workflow-1-in-local-repo:
    uses: octo-org/this-repo/.github/workflows/workflow-1.yml@172239021f7ba04fe7327647b213799853a9eb89
  call-workflow-2-in-local-repo:
    uses: ./.github/workflows/workflow-2.yml
  call-workflow-in-another-repo:
    uses: octo-org/another-repo/.github/workflows/workflow.yml@v1
```

### Example caller workflow

This workflow file calls two workflow files. The second of these, `workflow-B.yml`, is passed an input (`config-path`) and a secret (`token`).

```yaml
name: Call a reusable workflow

on:
  pull_request:
    branches:
      - main

jobs:
  call-workflow:
    uses: octo-org/example-repo/.github/workflows/workflow-A.yml@v1

  call-workflow-passing-data:
    permissions:
      contents: read
      pull-requests: write
    uses: octo-org/example-repo/.github/workflows/workflow-B.yml@main
    with:
      config-path: .github/labeler.yml
    secrets:
      token: ${{ secrets.GITHUB_TOKEN }}
```

## Passing inputs and secrets to a reusable workflow

To pass named inputs to a called workflow, use the `with` keyword in a job. Use the `secrets` keyword to pass named secrets. For inputs, the data type of the input value must match the type specified in the called workflow (either boolean, number, or string).

```yaml
jobs:
  call-workflow-passing-data:
    uses: octo-org/example-repo/.github/workflows/reusable-workflow.yml@main
    with:
      config-path: .github/labeler.yml
    secrets:
      personal_access_token: ${{ secrets.token }}
```

Workflows that call reusable workflows in the same organization or enterprise can use the `inherit` keyword to implicitly pass the secrets.

```yaml
jobs:
  call-workflow-passing-data:
    uses: octo-org/example-repo/.github/workflows/reusable-workflow.yml@main
    with:
      config-path: .github/labeler.yml
    secrets: inherit
```

## Using a matrix strategy with a reusable workflow

Jobs using the matrix strategy can call a reusable workflow.

A matrix strategy lets you use variables in a single job definition to automatically create multiple job runs that are based on the combinations of the variables. For example, you can use a matrix strategy to pass different inputs to a reusable workflow.

This example job below calls a reusable workflow and references the matrix context by defining the variable `target` with the values `[dev, stage, prod]`. It will run three jobs, one for each value in the variable.

```yaml
jobs:
  ReusableMatrixJobForDeployment:
    strategy:
      matrix:
        target: [dev, stage, prod]
    uses: octocat/octo-repo/.github/workflows/deployment.yml@main
    with:
      target: ${{ matrix.target }}
```

## Nesting reusable workflows

You can connect a maximum of ten levels of workflows - that is, the top-level caller workflow and up to nine levels of reusable workflows. For example: *caller-workflow.yml* → *called-workflow-1.yml* → *called-workflow-2.yml* → *called-workflow-3.yml* → ... → *called-workflow-9.yml*.

Loops in the workflow tree are not permitted.

> [!NOTE]
> Nested reusable workflows require all workflows in the chain to be accessible to the caller, and permissions can only be maintained or reduced—not elevated—throughout the chain.

From within a reusable workflow you can call another reusable workflow.

```yaml
name: Reusable workflow

on:
  workflow_call:

jobs:
  call-another-reusable:
    uses: octo-org/example-repo/.github/workflows/another-reusable.yml@v1
```

## Passing secrets to nested workflows

You can use `jobs.<job_id>.secrets` in a calling workflow to pass named secrets to a directly called workflow. Alternatively, you can use `jobs.<job_id>.secrets.inherit` to pass all of the calling workflow's secrets to a directly called workflow. Secrets are only passed to directly called workflows, so in the workflow chain A > B > C, workflow C will only receive secrets from A if they have been passed from A to B, and then from B to C.

In the following example, workflow A passes all of its secrets to workflow B, by using the `inherit` keyword, but workflow B only passes one secret to workflow C. Any of the other secrets passed to workflow B are not available to workflow C.

```yaml
jobs:
  workflowA-calls-workflowB:
    uses: octo-org/example-repo/.github/workflows/B.yml@main
    secrets: inherit # pass all secrets
```

```yaml
jobs:
  workflowB-calls-workflowC:
    uses: different-org/example-repo/.github/workflows/C.yml@main
    secrets:
      repo-token: ${{ secrets.personal_access_token }} # pass just this secret
```

## Using outputs from a reusable workflow

A reusable workflow may generate data that you want to use in the caller workflow. To use these outputs, you must specify them as the outputs of the reusable workflow.

If a reusable workflow that sets an output is executed with a matrix strategy, the output will be the output set by the last successful completing reusable workflow of the matrix which actually sets a value. That means if the last successful completing reusable workflow sets an empty string for its output, and the second last successful completing reusable workflow sets an actual value for its output, the output will contain the value of the second last completing reusable workflow.

The following reusable workflow has a single job containing two steps. In each of these steps we set a single word as the output: "hello" and "world." In the `outputs` section of the job, we map these step outputs to job outputs called: `output1` and `output2`. In the `on.workflow_call.outputs` section we then define two outputs for the workflow itself, one called `firstword` which we map to `output1`, and one called `secondword` which we map to `output2`.

The `value` must be set to the value of a job-level output within the called workflow. Step-level outputs must first be mapped to job-level outputs as shown below.

```yaml
name: Reusable workflow

on:
  workflow_call:
    # Map the workflow outputs to job outputs
    outputs:
      firstword:
        description: "The first output string"
        value: ${{ jobs.example_job.outputs.output1 }}
      secondword:
        description: "The second output string"
        value: ${{ jobs.example_job.outputs.output2 }}

jobs:
  example_job:
    name: Generate output
    runs-on: ubuntu-latest
    # Map the job outputs to step outputs
    outputs:
      output1: ${{ steps.step1.outputs.firstword }}
      output2: ${{ steps.step2.outputs.secondword }}
    steps:
      - id: step1
        run: echo "firstword=hello" >> $GITHUB_OUTPUT
      - id: step2
        run: echo "secondword=world" >> $GITHUB_OUTPUT
```

We can now use the outputs in the caller workflow, in the same way you would use the outputs from a job within the same workflow. We reference the outputs using the names defined at the workflow level in the reusable workflow: `firstword` and `secondword`. In this workflow, `job1` calls the reusable workflow and `job2` prints the outputs from the reusable workflow ("hello world") to standard output in the workflow log.

```yaml
name: Call a reusable workflow and use its outputs

on:
  workflow_dispatch:

jobs:
  job1:
    uses: octo-org/example-repo/.github/workflows/called-workflow.yml@v1

  job2:
    runs-on: ubuntu-latest
    needs: job1
    steps:
      - run: echo ${{ needs.job1.outputs.firstword }} ${{ needs.job1.outputs.secondword }}
```

If you want to share something other than a variable (e.g. a build artifact) between workflows, see [Store and share data with workflow artifacts](/en/actions/using-workflows/storing-workflow-data-as-artifacts).

## Monitoring which workflows are being used

Organizations that use GitHub Enterprise Cloud can interact with the audit log via the GitHub REST API to monitor which workflows are being used.

## Next steps

To find information on the intricacies of reusing workflows, see [Reusing workflow configurations](/en/actions/reference/reusable-workflows-reference).

---

## GitHub-hosted runners (use + reference specs)

> Source (how-to): https://docs.github.com/en/actions/how-tos/manage-runners/github-hosted-runners/use-github-hosted-runners
> Source (reference specs): https://docs.github.com/en/actions/reference/runners/github-hosted-runners
> (Listed task URL `/en/actions/using-github-hosted-runners/about-github-hosted-runners` redirects into these pages.)
> **Fidelity note:** the how-to page's prose was compressed by the fetch backend; the key `runs-on` YAML example is verbatim below. The specification and limit tables are taken from the runners reference page.

# Using GitHub-hosted runners

GitHub-hosted runners are virtual machines that execute GitHub Actions workflows. When a job begins, GitHub automatically provisions a new VM, executes all job steps on it, and then decommissions it afterward.

To use a GitHub-hosted runner, configure the `runs-on` field in your workflow YAML, specifying the type of runner that will process the job, such as `ubuntu-latest`, `windows-latest`, or `macos-latest`.

Users with `repo: write` access can view available runners by navigating to the repository's Actions tab, then selecting **Runners** from the Management section in the left sidebar.

## Example workflow

```yaml
name: Run commands on different operating systems
on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  Run-npm-on-Ubuntu:
    name: Run npm on Ubuntu
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v6
      - uses: actions/setup-node@v4
        with:
          node-version: '14'
      - run: npm help

  Run-PSScriptAnalyzer-on-Windows:
    name: Run PSScriptAnalyzer on Windows
    runs-on: windows-latest
    steps:
      - uses: actions/checkout@v6
      - name: Install PSScriptAnalyzer module
        shell: pwsh
        run: |
          Set-PSRepository PSGallery -InstallationPolicy Trusted
          Install-Module PSScriptAnalyzer -ErrorAction Stop
      - name: Get list of rules
        shell: pwsh
        run: |
          Get-ScriptAnalyzerRule
```

## Standard runner specifications — public repositories

| Virtual Machine | Processor (CPU) | Memory (RAM) | Storage (SSD) | Architecture | Workflow Label |
|---|---|---|---|---|---|
| Linux | 1 | 5 GB | 14 GB | x64 | `ubuntu-slim` |
| Linux | 4 | 16 GB | 14 GB | x64 | `ubuntu-latest`, `ubuntu-24.04`, `ubuntu-22.04` |
| Windows | 4 | 16 GB | 14 GB | x64 | `windows-latest`, `windows-2025`, `windows-2025-vs2026`, `windows-2022` |
| Linux | 4 | 16 GB | 14 GB | arm64 | `ubuntu-24.04-arm`, `ubuntu-22.04-arm` |
| Windows | 4 | 16 GB | 14 GB | arm64 | `windows-11-arm` |
| macOS | 4 | 14 GB | 14 GB | Intel | `macos-15-intel`, `macos-26-intel` |
| macOS | 3 (M1) | 7 GB | 14 GB | arm64 | `macos-latest`, `macos-14`, `macos-15`, `macos-26` |

## Standard runner specifications — private repositories

| Virtual Machine | Processor (CPU) | Memory (RAM) | Storage (SSD) | Architecture | Workflow Label |
|---|---|---|---|---|---|
| Linux | 1 | 5 GB | 14 GB | x64 | `ubuntu-slim` |
| Linux | 2 | 8 GB | 14 GB | x64 | `ubuntu-latest`, `ubuntu-24.04`, `ubuntu-22.04` |
| Windows | 2 | 8 GB | 14 GB | x64 | `windows-latest`, `windows-2025`, `windows-2022` |
| Linux | 2 | 8 GB | 14 GB | arm64 | `ubuntu-24.04-arm`, `ubuntu-22.04-arm` |
| Windows | 2 | 8 GB | 14 GB | arm64 | `windows-11-arm` |
| macOS | 4 | 14 GB | 14 GB | Intel | `macos-15-intel`, `macos-26-intel` |
| macOS | 3 (M1) | 7 GB | 14 GB | arm64 | `macos-latest`, `macos-14`, `macos-15`, `macos-26` |

## Usage limits

Single-CPU runners (the `ubuntu-slim` label) have a maximum job timeout of 15 minutes. Standard runners follow the concurrency model determined by your GitHub plan. (See [Actions limits](/en/actions/reference/limits) for the authoritative per-plan concurrent-job counts, job execution time, workflow run time, API request, and matrix limits.)

## Communication requirements

Essential operations:

```
github.com
api.github.com
*.actions.githubusercontent.com
```

Downloading actions:

```
codeload.github.com
```

Artifacts, logs, caches:

```
results-receiver.actions.githubusercontent.com
*.blob.core.windows.net
```

Runner updates:

```
objects.githubusercontent.com
objects-origin.githubusercontent.com
github-releases.githubusercontent.com
github-registry-files.githubusercontent.com
```
