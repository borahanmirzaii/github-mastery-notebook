# GitHub REST API

> **Source root:** https://docs.github.com/en/rest?apiVersion=2026-03-10
> **Fetched:** 2026-05-26
> **Area:** 02 — REST API (apiVersion=2026-03-10)

## Table of contents

- [REST API documentation (landing)](#rest-api-documentation-landing)
- [About the REST API](#about-the-rest-api)
- [Authenticating to the REST API](#authenticating-to-the-rest-api)
- [API Versions](#api-versions)
- [Rate limits for the REST API](#rate-limits-for-the-rest-api)
- [Using pagination in the REST API](#using-pagination-in-the-rest-api)
- [Getting started with the REST API](#getting-started-with-the-rest-api)
- [Media types](#media-types)
- [Troubleshooting the REST API](#troubleshooting-the-rest-api)

---

## REST API documentation (landing)

> Source: https://docs.github.com/en/rest?apiVersion=2026-03-10

This page serves as the central hub for GitHub's REST API documentation, offering resources for developers to build integrations, retrieve data, and automate workflows.

### Key Sections

**Recommended Resources** include foundational guides like the quickstart, authentication methods, best practices, rate limits, security guidelines, and pagination tutorials.

**Getting Started** materials help developers understand the REST API fundamentals and compare it with GraphQL alternatives.

**Core Topics Covered:**

The documentation encompasses extensive endpoint references across numerous categories:

- Actions (workflows, jobs, artifacts, secrets, runners)
- Activity (events, feeds, notifications, starring, watching)
- Authentication and permissions
- Repositories (contents, forks, webhooks, branch protection)
- Issues and pull requests (with comments, reviews, events)
- Commits, tags, and Git objects
- Deployments and environments
- Organizations and teams
- Users and accounts
- Projects and boards
- Packages and releases
- Code scanning and security advisories
- Codespaces management
- GitHub Apps and OAuth applications

**Specialized Guides** address specific use cases such as scripting with JavaScript or Ruby, working with comments, building CI servers, interacting with Git databases, managing secrets, and rendering data as graphs.

The documentation emphasizes security practices, rate limit management, and proper credential handling throughout.

> _Note: the landing page is a navigation hub; the fetched rendering returned a structured digest of its sections rather than raw link lists. The substantive content lives in the linked sub-pages reproduced below._

---

## About the REST API

> Source: https://docs.github.com/en/rest/about-the-rest-api/about-the-rest-api?apiVersion=2026-03-10

Get oriented to the REST API documentation.

You can use GitHub's API to build scripts and applications that automate processes, integrate with GitHub, and extend GitHub. For example, you could use the API to triage issues, build an analytics dashboard, or manage releases.

Each REST API endpoint is documented individually, and the endpoints are categorized by the resource that they primarily affect. For example, you can find endpoints relating to issues in REST API endpoints for issues.

### Getting started with the REST API

**If you are new to REST APIs**, you may find it helpful to refer to the Quickstart or Getting Started guide for an introduction. For more information, see:

* Quickstart for GitHub REST API
* Getting started with the REST API

**If you are familiar with REST APIs** but new to GitHub's REST API, you may find it helpful to refer to the authentication documentation. For more information, see:

* Authenticating to the REST API

**If you are building scripts or applications** that use the REST API, you may find some of the following guides helpful. For examples of scripting with the REST API, see:

* Scripting with the REST API and JavaScript
* Scripting with the REST API and Ruby
* Building a GitHub App that responds to webhook events
* Building a CLI with a GitHub App
* Automatically redelivering failed deliveries for a repository webhook

For a list of libraries to facilitate scripting with the REST API, see Libraries for the REST API.

If you are building scripts or applications that use the REST API, you might also be interested in using webhooks to get notified about events or a GitHub App to access resources on behalf of a user or in an organization. For more information, see About webhooks and Deciding when to build a GitHub App.

### Further reading

* Comparing GitHub's REST API and GraphQL API
* Best practices for using the REST API
* Keeping your API credentials secure
* Troubleshooting the REST API

---

## Authenticating to the REST API

> Source: https://docs.github.com/en/rest/authentication/authenticating-to-the-rest-api?apiVersion=2026-03-10

You can authenticate to the REST API to access more endpoints and have a higher rate limit.

### About authentication

Many REST API endpoints require authentication or return additional information if you are authenticated. Additionally, you can make more requests per hour when you are authenticated.

To authenticate your request, you will need to provide an authentication token with the required scopes or permissions. There a few different ways to get a token: You can create a personal access token, generate a token with a GitHub App, or use the built-in `GITHUB_TOKEN` in a GitHub Actions workflow.

After creating a token, you can authenticate your request by sending the token in the `Authorization` header of your request. For example, in the following request, replace `YOUR-TOKEN` with a reference to your token:

```shell
curl --request GET \
--url "https://api.github.com/octocat" \
--header "Authorization: Bearer YOUR-TOKEN" \
--header "X-GitHub-Api-Version: 2026-03-10"
```

> [!NOTE]
> In most cases, you can use `Authorization: Bearer` or `Authorization: token` to pass a token. However, if you are passing a JSON web token (JWT), you must use `Authorization: Bearer`.

#### Failed login limit

If you try to use a REST API endpoint without a token or with a token that has insufficient permissions, you will receive a `404 Not Found` or `403 Forbidden` response. Authenticating with invalid credentials will initially return a `401 Unauthorized` response.

After detecting several requests with invalid credentials within a short period, the API will temporarily reject all authentication attempts for that user (including ones with valid credentials) with a `403 Forbidden` response. For more information, see [Rate limits for the REST API](/en/rest/overview/rate-limits-for-the-rest-api).

### Authenticating with a personal access token

If you want to use the GitHub REST API for personal use, you can create a personal access token. If possible, GitHub recommends that you use a fine-grained personal access token instead of a personal access token (classic). For more information about creating a personal access token, see [Managing your personal access tokens](/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token).

If you are using a fine-grained personal access token, your fine-grained personal access token requires specific permissions in order to access each REST API endpoint. The REST API reference document for each endpoint states whether the endpoint works with fine-grained personal access tokens and states what permissions are required in order for the token to use the endpoint. Some endpoints may require multiple permissions, and some endpoints may require one of multiple permissions. For an overview of which REST API endpoints a fine-grained personal access token can access with each permission, see [Permissions required for fine-grained personal access tokens](/en/rest/overview/permissions-required-for-fine-grained-personal-access-tokens).

If you are using a personal access token (classic), it requires specific scopes in order to access each REST API endpoint. For general guidance about what scopes to choose, see [Scopes for OAuth apps](/en/apps/oauth-apps/building-oauth-apps/scopes-for-oauth-apps#available-scopes).

Personal access tokens act as your identity (limited by the scopes or permissions you selected) when you make requests to the REST API. As such, it is important to keep your personal access tokens secure. For more information about keeping your personal access tokens secure, see [Keeping your API credentials secure](/en/rest/authentication/keeping-your-api-credentials-secure?apiVersion=2022-11-28).

#### Personal access tokens and SAML SSO

If you use a personal access token (classic) to access an organization that enforces SAML single sign-on (SSO) for authentication, you will need to authorize your token after creation. Fine-grained personal access tokens are authorized during token creation, before access to the organization is granted. For more information, see [Authorizing a personal access token for use with single sign-on](/en/authentication/authenticating-with-saml-single-sign-on/authorizing-a-personal-access-token-for-use-with-saml-single-sign-on).

If you do not authorize your personal access token (classic) for SAML SSO before you try to use it to access a single organization that enforces SAML SSO, you may receive a `404 Not Found` or a `403 Forbidden` error. If you receive a `403 Forbidden` error, the `X-GitHub-SSO` header will include a URL that you can follow to authorize your token. The URL expires after one hour.

If you do not authorize your personal access token (classic) for SAML SSO before you try to use it to access multiple organizations, the API will not return results from the organizations that require SAML SSO and the `X-GitHub-SSO` header will indicate the ID of the organizations that require SAML SSO authorization of your personal access token (classic). For example: `X-GitHub-SSO: partial-results; organizations=21955855,20582480`.

### Authenticating with a token generated by an app

If you want to use the API for an organization or on behalf of another user, GitHub recommends that you use a GitHub App. For more information, see [About authentication with a GitHub App](/en/apps/creating-github-apps/authenticating-with-a-github-app/about-authentication-with-a-github-app).

The REST API reference documentation for each endpoint states whether the endpoint works with GitHub Apps and states what permissions are required in order for the app to use the endpoint. Some endpoints may require multiple permissions, and some endpoints may require one of multiple permissions. For an overview of which REST API endpoints a GitHub App can access with each permission, see [Permissions required for GitHub Apps](/en/rest/overview/permissions-required-for-github-apps).

You can also create an OAuth token with an OAuth app to access the REST API. However, GitHub recommends that you use a GitHub App instead. GitHub Apps allow more control over the access and permission that the app has.

Access tokens created by apps are automatically authorized for SAML SSO.

#### Using basic authentication

Some REST API endpoints for GitHub Apps and OAuth apps require you to use basic authentication to access the endpoint. You will use the app's client ID as the username and the app's client secret as the password.

For example:

```shell
curl --request POST \
--url "https://api.github.com/applications/YOUR_CLIENT_ID/token" \
--user "YOUR_CLIENT_ID:YOUR_CLIENT_SECRET" \
--header "Accept: application/vnd.github+json" \
--header "X-GitHub-Api-Version: 2026-03-10" \
--data '{
  "access_token": "ACCESS_TOKEN_TO_CHECK"
}'
```

The client ID and client secret are associated with the app, not with the owner of the app or a user who authorized the app. They are used to perform operations on behalf of the app, such as creating access tokens.

If you are the owner of a GitHub App or OAuth app, or if you are an app manager for a GitHub App, you can find the client ID and generate a client secret on the settings page for your app. To navigate to your app's settings page:

1. In the upper-right corner of any page on GitHub, click your profile picture.
2. Navigate to your account settings.
   * For an app owned by a personal account, click **Settings**.
   * For an app owned by an organization:
     1. Click **Your organizations**.
     2. To the right of the organization, click **Settings**.
3. In the left sidebar, click **Developer settings**.
4. In the left sidebar, click **GitHub Apps** or **OAuth apps**.
5. For GitHub Apps, to the right of the GitHub App you want to access, click **Edit**. For OAuth apps, click the app that you want to access.
6. Next to **Client ID**, you will see the client ID for your app.
7. Next to **Client secrets**, click **Generate a new client secret** to generate a client secret for your app.

### Authenticating in a GitHub Actions workflow

If you want to use the API in a GitHub Actions workflow, GitHub recommends that you authenticate with the built-in `GITHUB_TOKEN` instead of creating a token. You can grant permissions to the `GITHUB_TOKEN` with the `permissions` key. For more information, see [Use GITHUB_TOKEN for authentication in workflows](/en/actions/security-guides/automatic-token-authentication#modifying-the-permissions-for-the-github_token).

If this is not possible, you can store your token as a secret and use the name of your secret in your GitHub Actions workflow. For more information about secrets, see [Using secrets in GitHub Actions](/en/actions/security-guides/encrypted-secrets).

#### Authenticating in a GitHub Actions workflow using GitHub CLI

To make an authenticated request to the API in a GitHub Actions workflow using GitHub CLI, you can store the value of `GITHUB_TOKEN` as an environment variable, and use the `run` keyword to execute the GitHub CLI `api` subcommand. For more information about the `run` keyword, see [Workflow syntax for GitHub Actions](/en/actions/using-workflows/workflow-syntax-for-github-actions#jobsjob_idstepsrun).

In the following example workflow, replace `PATH` with the path of the endpoint. For more information about the path, see [Getting started with the REST API](/en/rest/guides/getting-started-with-the-rest-api?tool=cli#path).

```yaml
jobs:
  use_api:
    runs-on: ubuntu-latest
    permissions: {}
    steps:
      - env:
          GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        run: |
          gh api /PATH
```

#### Authenticating in a GitHub Actions workflow using `curl`

To make an authenticated request to the API in a GitHub Actions workflow using `curl`, you can store the value of `GITHUB_TOKEN` as an environment variable, and use the `run` keyword to execute a `curl` request to the API. For more information about the `run` keyword, see [Workflow syntax for GitHub Actions](/en/actions/using-workflows/workflow-syntax-for-github-actions#jobsjob_idstepsrun).

In the following example workflow, replace `PATH` with the path of the endpoint. For more information about the path, see [Getting started with the REST API](/en/rest/guides/getting-started-with-the-rest-api?tool=cli#path).

```yaml
jobs:
  use_api:
    runs-on: ubuntu-latest
    permissions: {}
    steps:
      - env:
          GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        run: |
          curl --request GET \
          --url "https://api.github.com/PATH" \
          --header "Authorization: Bearer $GH_TOKEN"
```

#### Authenticating in a GitHub Actions workflow using JavaScript

For an example of how to authenticate in a GitHub Actions workflow using JavaScript, see [Scripting with the REST API and JavaScript](/en/rest/guides/scripting-with-the-rest-api-and-javascript#authenticating-in-github-actions).

### Authenticating with username and password

"Authentication with username and password is not supported." If you attempt this method, you will receive a 4xx error.

### Further reading

* [Keeping your API credentials secure](/en/rest/overview/keeping-your-api-credentials-secure)
* [Getting started with the REST API](/en/rest/guides/getting-started-with-the-rest-api#authentication)

---

## API Versions

> Source: https://docs.github.com/en/rest/about-the-rest-api/api-versions?apiVersion=2026-03-10

Learn how to specify which REST API version to use whenever you make a request to the REST API.

### About API versioning

The GitHub REST API is versioned. The API version name is based on the date when the API version was released. For example, the API version `2026-03-10` was released on Tue, 10 Mar 2026.

Breaking changes are changes that can potentially break an integration. Breaking changes will be released in a new API version. We will provide advance notice before releasing breaking changes. Breaking changes include:

* Removing an entire operation
* Removing or renaming a parameter
* Removing or renaming a response field
* Adding a new required parameter
* Making a previously optional parameter required
* Changing the type of a parameter or response field
* Removing enum values
* Adding a new validation rule to an existing parameter
* Changing authentication or authorization requirements

Any additive (non-breaking) changes will be available in all supported API versions. Additive changes are changes that should not break an integration. Additive changes include:

* Adding an operation
* Adding an optional parameter
* Adding an optional request header
* Adding a response field
* Adding a response header
* Adding enum values

When a new REST API version is released, the previous API version will be supported for at least 24 more months following the release of the new API version.

### Specifying an API version

You should use the `X-GitHub-Api-Version` header to specify an API version. For example:

```shell
curl --header "X-GitHub-Api-Version:2026-03-10" https://api.github.com/zen
```

Requests without the `X-GitHub-Api-Version` header will default to use the `2022-11-28` version.

If you specify an API version that is no longer supported, you will receive a `410 Gone` response.

### Upgrading to a new API version

Before upgrading to a new REST API version, you should read the changelog of breaking changes for the new API version to understand what breaking changes are included and to learn more about how to upgrade to that specific API version. For more information, see [Breaking changes](/en/rest/overview/breaking-changes).

When you update your integration to specify the new API version in the `X-GitHub-Api-Version` header, you'll also need to make any changes required for your integration to work with the new API version.

Once your integration is updated, test your integration to verify that it works with the new API version.

### API version closing down

API versions are supported for 24 months after a newer API version is released.

While a version is within its support window but approaching closing down, GitHub includes the following headers in API responses to help you prepare for migration:

* `Deprecation` — The date when the API version will be closing down, formatted as an HTTP date per [RFC 7231](https://tools.ietf.org/html/rfc7231#section-7.1.1.1). For example: `Wed, 27 Nov 2019 14:34:29 GMT`.
* `Sunset` — The date when the API version will be completely removed (retired), after which requests will return a `410 Gone` response. Follows [RFC 8594](https://tools.ietf.org/html/rfc8594). For example: `Fri, 27 Nov 2020 14:34:29 GMT`.

After the support window ends:

* Requests that specify a closing down API version receive a `410 Gone` response.
* Requests that do not specify an API version default to the next oldest supported version, not the closing down version. If you rely on unversioned requests, you may observe behavioral changes as older versions are removed from support.

For more information on migrating to a newer API version, see [Breaking changes](/en/rest/about-the-rest-api/breaking-changes).

### Exceptions to standard versioning

In rare cases, GitHub may make changes outside the normal API versioning cadence. These are exceptional interventions that do not alter the standard versioning guarantees for most integrators.

#### Security, availability, and reliability issues

Critical security vulnerabilities, data exposure risks, or severe reliability issues may require changes outside the normal release schedule. GitHub may release an unscheduled API version, backport fixes to supported versions, or in rare cases, introduce a breaking change to an existing version to protect users and platform integrity.

GitHub will communicate such changes through release notes, changelogs, and direct communication explaining what changed and why. Where feasible, advance notice will be provided. Immediate action may be taken without advance notice when required.

#### Low-usage services

For certain services with very low usage, GitHub may deprecate functionality outside the standard versioning process. In these cases, GitHub will communicate the intent and reach out to affected integrators directly.

### Supported API versions

The following REST API versions are currently supported.

| API version  | End of support date |
| ------------ | ------------------- |
| `2026-03-10` | Not yet scheduled   |
| `2022-11-28` | March 10, 2028      |

You can also make an API request to get all of the supported API versions. For more information, see [REST API endpoints for meta data](/en/rest/meta/meta#get-all-api-versions).

---

## Rate limits for the REST API

> Source: https://docs.github.com/en/rest/using-the-rest-api/rate-limits-for-the-rest-api?apiVersion=2026-03-10

Learn about REST API rate limits, how to avoid exceeding them, and what to do if you do exceed them.

### About primary rate limits

GitHub limits the number of REST API requests that you can make within a specific amount of time. This limit helps prevent abuse and denial-of-service attacks, and ensures that the API remains available for all users.

Some endpoints, like the search endpoints, have more restrictive limits. For more information about these endpoints, see [REST API endpoints for rate limits](/en/rest/rate-limit/rate-limit). The GraphQL API also has a separate primary rate limit. See [Rate limits and query limits for the GraphQL API](/en/graphql/overview/resource-limitations).

In general, you can calculate your primary rate limit for the REST API based on your method of authentication, as described below.

#### Primary rate limit for unauthenticated users

You can make unauthenticated requests if you are only fetching public data. Unauthenticated requests are associated with the originating IP address, not with the user or application that made the request.

The primary rate limit for unauthenticated requests is 60 requests per hour.

#### Primary rate limit for authenticated users

You can use a personal access token to make API requests. Additionally, you can authorize a GitHub App or OAuth app, which can then make API requests on your behalf.

All of these requests count towards your personal rate limit of 5,000 requests per hour. Requests made on your behalf by a GitHub App that is owned by a GitHub Enterprise Cloud organization have a higher rate limit of 15,000 requests per hour. Similarly, requests made on your behalf by a OAuth app that is owned or approved by a GitHub Enterprise Cloud organization have a higher rate limit of 15,000 requests per hour if you are a member of the GitHub Enterprise Cloud organization. However, requests made by a higher-limit app reduce the remaining budget available for lower-limit authentication methods. For example, if an app with a 15,000 request limit makes 10,000 requests on your behalf, you will have exhausted the 5,000 request budget for your personal access tokens, even though the app has 5,000 requests remaining.

#### Primary rate limit for Git LFS access

API requests are required when you upload or download Git LFS content. These count towards a separate rate limiting bucket with a limit of 300 requests per minute for unauthenticated requests and 3,000 requests per minute for authenticated requests.

Git LFS uses a batch API which processes 100 Git LFS objects per API request by default. That means unauthenticated users can download 30,000 Git LFS objects per minute and authenticated users can upload/download 300,000 Git LFS objects per minute.

#### Primary rate limit for GitHub App installations

GitHub Apps authenticating with an installation access token use the installation's minimum rate limit of 5,000 requests per hour. If the installation is on a GitHub Enterprise Cloud organization, the installation has a rate limit of 15,000 requests per hour.

For installations that are not on a GitHub Enterprise Cloud organization, the rate limit for the installation will scale with the number of users and repositories. Installations that have more than 20 repositories receive another 50 requests per hour for each repository. Installations that are on an organization that have more than 20 users receive another 50 requests per hour for each user. The rate limit cannot increase beyond 12,500 requests per hour.

Primary rate limits for GitHub App user access tokens (as opposed to installation access tokens) are dictated by the primary rate limits for the authenticated user. This rate limit is combined with any requests that another GitHub App or OAuth app makes on that user's behalf and any requests that the user makes with a personal access token. For more information, see [Rate limits for the REST API](/en/rest/using-the-rest-api/rate-limits-for-the-rest-api#primary-rate-limit-for-authenticated-users).

#### Primary rate limit for OAuth apps

Primary rate limits for OAuth access tokens generated by a OAuth app are dictated by the primary rate limits for authenticated users. This rate limit is combined with any requests that another GitHub App or OAuth app makes on that user's behalf and any requests that the user makes with a personal access token. See [Primary rate limit for authenticated users](#primary-rate-limit-for-authenticated-users).

OAuth apps can also use their client ID and client secret to fetch public data. For example:

```shell
curl -u YOUR_CLIENT_ID:YOUR_CLIENT_SECRET -I https://api.github.com/meta
```

For these requests, the rate limit is 5,000 requests per hour per OAuth app. If the app is owned by a GitHub Enterprise Cloud organization, the rate limit is 15,000 requests per hour.

> [!NOTE]
> Never include your app's client secret in client-side code or in code that runs on a user device. The client secret can be used to generate OAuth access tokens for users who have authorized your app, so you should always keep the client secret secure.

#### Primary rate limit for `GITHUB_TOKEN` in GitHub Actions

You can use the built-in `GITHUB_TOKEN` to authenticate requests in GitHub Actions workflows. See [Use GITHUB_TOKEN for authentication in workflows](/en/actions/security-guides/automatic-token-authentication).

The rate limit for `GITHUB_TOKEN` is 1,000 requests per hour per repository. For requests to resources that belong to a GitHub Enterprise Cloud account, the limit is 15,000 requests per hour per repository.

### About secondary rate limits

In addition to primary rate limits, GitHub enforces secondary rate limits in order to prevent abuse and keep the API available for all users.

You may encounter a secondary rate limit if you:

* Make too many concurrent requests. No more than 100 concurrent requests are allowed. This limit is shared across the REST API and GraphQL API.
* Make too many requests to a single endpoint per minute. No more than 900 points per minute are allowed for REST API endpoints, and no more than 2,000 points per minute are allowed for the GraphQL API endpoint. For more information about points, see [Calculating points for the secondary rate limit](#calculating-points-for-the-secondary-rate-limit).
* Make too many requests per minute. No more than 90 seconds of CPU time per 60 seconds of real time is allowed. No more than 60 seconds of this CPU time may be for the GraphQL API. You can roughly estimate the CPU time by measuring the total response time for your API requests.
* Make too many requests that consume excessive compute resources in a short period of time.
* Create too much content on GitHub in a short amount of time. In general, no more than 80 content-generating requests per minute and no more than 500 content-generating requests per hour are allowed. Some endpoints have lower content creation limits. Content creation limits include actions taken on the GitHub web interface as well as via the REST API and GraphQL API.
* Make too many OAuth access token requests in a short period of time. No more than 2,000 OAuth access token requests per hour are allowed for GitHub Apps and OAuth apps.

These secondary rate limits are subject to change without notice. You may also encounter a secondary rate limit for undisclosed reasons.

#### Calculating points for the secondary rate limit

Some secondary rate limits are determined by the point values of requests. For GraphQL requests, these point values are separate from the point value calculations for the primary rate limit.

| Request                                                    | Points |
| ---------------------------------------------------------- | ------ |
| GraphQL requests without mutations                         | 1      |
| GraphQL requests with mutations                            | 5      |
| Most REST API `GET`, `HEAD`, and `OPTIONS` requests        | 1      |
| Most REST API `POST`, `PATCH`, `PUT`, or `DELETE` requests | 5      |

Some REST API endpoints have a different point cost that is not shared publicly.

### Checking the status of your rate limit

You can use the headers that are sent with each response to determine the current status of your primary rate limit.

| Header name             | Description                                                                                                                                                                                                                              |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `x-ratelimit-limit`     | The maximum number of requests that you can make per hour                                                                                                                                                                                |
| `x-ratelimit-remaining` | The number of requests remaining in the current rate limit window                                                                                                                                                                        |
| `x-ratelimit-used`      | The number of requests you have made in the current rate limit window                                                                                                                                                                    |
| `x-ratelimit-reset`     | The time at which the current rate limit window resets, in UTC epoch seconds                                                                                                                                                             |
| `x-ratelimit-resource`  | The rate limit resource that the request counted against. For more information about the different resources, see [REST API endpoints for rate limits](/en/rest/rate-limit/rate-limit#get-rate-limit-status-for-the-authenticated-user). |

You can also call the `GET /rate_limit` endpoint to check your rate limit. Calling this endpoint does not count against your primary rate limit, but it can count against your secondary rate limit. See [REST API endpoints for rate limits](/en/rest/rate-limit/rate-limit). When possible, you should use the rate limit response headers instead of calling the API to check your rate limit.

There is not a way to check the status of your secondary rate limit.

### Exceeding the rate limit

If you exceed your primary rate limit, you will receive a `403` or `429` response, and the `x-ratelimit-remaining` header will be `0`. You should not retry your request until after the time specified by the `x-ratelimit-reset` header.

If you exceed a secondary rate limit, you will receive a `403` or `429` response and an error message that indicates that you exceeded a secondary rate limit. If the `retry-after` response header is present, you should not retry your request until after that many seconds has elapsed. If the `x-ratelimit-remaining` header is `0`, you should not retry your request until after the time, in UTC epoch seconds, specified by the `x-ratelimit-reset` header. Otherwise, wait for at least one minute before retrying. If your request continues to fail due to a secondary rate limit, wait for an exponentially increasing amount of time between retries, and throw an error after a specific number of retries.

Continuing to make requests while you are rate limited may result in the banning of your integration.

### Staying under the rate limit

You should follow best practices to help you stay under the rate limits. See [Best practices for using the REST API](/en/rest/guides/best-practices-for-using-the-rest-api).

### Getting a higher rate limit

If you want a higher primary rate limit, consider making authenticated requests instead of unauthenticated requests. Authenticated requests have a significantly higher rate limit than unauthenticated requests.

If you are using a personal access token for automation in your organization, consider whether a GitHub App will work instead. The rate limit for GitHub Apps using an installation access token scales with the number of repositories and number of organization users. See [About creating GitHub Apps](/en/apps/creating-github-apps/about-creating-github-apps/about-creating-github-apps).

If you are using GitHub Apps or OAuth apps, consider upgrading to GitHub Enterprise Cloud. GitHub Apps or OAuth apps have higher rate limits for organizations that use GitHub Enterprise Cloud.

---

## Using pagination in the REST API

> Source: https://docs.github.com/en/rest/using-the-rest-api/using-pagination-in-the-rest-api?apiVersion=2026-03-10

Learn how to navigate through paginated responses from the REST API.

### About Pagination

When REST API responses would contain numerous results, GitHub implements pagination to return a subset. For instance, retrieving issues from a repository returns 30 results by default, even if thousands exist. This approach improves server performance and usability.

You can use the `link` header to request additional pages, and the `per_page` query parameter lets you control result counts per page.

### Using Link Headers

Paginated responses include a `link` header containing URLs for fetching additional result pages. To view response headers, use curl or GitHub CLI with the `--include` flag:

```shell
curl --include --request GET \
--url "https://api.github.com/repos/octocat/Spoon-Knife/issues" \
--header "Accept: application/vnd.github+json"
```

The `link` header contains URLs with relationship indicators:

* `rel="prev"` — previous page
* `rel="next"` — next page
* `rel="last"` — final page
* `rel="first"` — initial page

Some links may be unavailable depending on your current position. To request the last page from a paginated response:

```shell
curl --include --request GET \
--url "https://api.github.com/repositories/1300192/issues?page=515" \
--header "Accept: application/vnd.github+json"
```

Paginated endpoints use `page`, `before`/`after`, or `since` query parameters. The `link` header URLs provide the correct parameters for fetching additional pages.

### Changing Items Per Page

Endpoints supporting the `per_page` query parameter allow control over result quantities:

```shell
curl --include --request GET \
--url "https://api.github.com/repos/octocat/Spoon-Knife/issues?per_page=2" \
--header "Accept: application/vnd.github+json"
```

The `per_page` parameter automatically appears in subsequent `link` headers.

### Scripting with Pagination

#### Using Octokit.js Pagination Method

The `octokit.paginate()` method automatically fetches all pages and returns results as a single array:

```javascript copy
import { Octokit } from "octokit";

const octokit = new Octokit({ });

const data = await octokit.paginate("GET /repos/{owner}/{repo}/issues", {
  owner: "octocat",
  repo: "Spoon-Knife",
  per_page: 100,
  headers: {
    "X-GitHub-Api-Version": "2026-03-10",
  },
});

console.log(data)
```

You can pass a map function to control pagination behavior or use `octokit.paginate.iterator()` for single-page iteration.

#### Building a Custom Pagination Method

For libraries without built-in pagination support, create your own approach:

```javascript copy
import { Octokit } from "octokit";

const octokit = new Octokit({ });

async function getPaginatedData(url) {
  const nextPattern = /(?<=<)([\S]*)(?=>; rel="next")/i;
  let pagesRemaining = true;
  let data = [];

  while (pagesRemaining) {
    const response = await octokit.request(`GET ${url}`, {
      per_page: 100,
      headers: {
        "X-GitHub-Api-Version":
          "2026-03-10",
      },
    });

    const parsedData = parseData(response.data)
    data = [...data, ...parsedData];

    const linkHeader = response.headers.link;

    pagesRemaining = linkHeader && linkHeader.includes(`rel=\"next\"`);

    if (pagesRemaining) {
      url = linkHeader.match(nextPattern)[0];
    }
  }

  return data;
}

function parseData(data) {
  // If the data is an array, return that
    if (Array.isArray(data)) {
      return data
    }

  // Some endpoints respond with 204 No Content instead of empty array
  //   when there is no data. In that case, return an empty array.
  if (!data) {
    return []
  }

  // Otherwise, the array of items that we want is in an object
  // Delete keys that don't include the array of items
  delete data.incomplete_results;
  delete data.repository_selection;
  delete data.total_count;
  // Pull out the array of items
  const namespaceKey = Object.keys(data)[0];
  data = data[namespaceKey];

  return data;
}

const data = await getPaginatedData("/repos/octocat/Spoon-Knife/issues");

console.log(data);
```

---

## Getting started with the REST API

> Source: https://docs.github.com/en/rest/using-the-rest-api/getting-started-with-the-rest-api?apiVersion=2026-03-10

Learn how to use the GitHub REST API.

### Introduction

This article describes how to use the GitHub REST API with GitHub CLI, `curl`, or JavaScript. For a quickstart guide, see [Quickstart for GitHub REST API](/en/rest/quickstart).

### About requests to the REST API

This section describes the elements that make up an API request:

* [HTTP method](#http-method)
* [Path](#path)
* [Headers](#headers)
* [Media types](#media-types)
* [Authentication](#authentication)
* [Parameters](#parameters)

Every request to the REST API includes an HTTP method and a path. Depending on the REST API endpoint, you might also need to specify request headers, authentication information, query parameters, or body parameters.

The REST API reference documentation describes the HTTP method, path, and parameters for every endpoint. It also displays example requests and responses for each endpoint. For more information, see the [REST reference documentation](/en/rest).

#### HTTP method

The HTTP method of an endpoint defines the type of action it performs on a given resource. Some common HTTP methods are `GET`, `POST`, `DELETE`, and `PATCH`. The REST API reference documentation provides the HTTP method for every endpoint.

For example, the HTTP method for the ["List repository issues" endpoint](/en/rest/issues/issues#list-repository-issues) is `GET`.

Where possible, the GitHub REST API strives to use an appropriate HTTP method for each action.

* `GET`: Used for retrieving resources.
* `POST`: Used for creating resources.
* `PATCH`: Used for updating properties of resources.
* `PUT`: Used for replacing resources or collections of resources.
* `DELETE`: Used for deleting resources.

#### Path

Each endpoint has a path. The REST API reference documentation gives the path for every endpoint. For example, the path for the ["List repository issues" endpoint](/en/rest/issues/issues#list-repository-issues) is `/repos/{owner}/{repo}/issues`.

The curly brackets `{}` in a path denote path parameters that you need to specify. Path parameters modify the endpoint path and are required in your request. For example, the path parameters for the ["List repository issues" endpoint](/en/rest/issues/issues#list-repository-issues) are `{owner}` and `{repo}`. To use this path in your API request, replace `{repo}` with the name of the repository where you would like to request a list of issues, and replace `{owner}` with the name of the account that owns the repository.

#### Headers

Headers provide extra information about the request and the desired response. Following are some examples of headers that you can use in your requests to the GitHub REST API. For an example of a request that uses headers, see [Making a request](#making-a-request).

##### `Accept`

Most GitHub REST API endpoints specify that you should pass an `Accept` header with a value of `application/vnd.github+json`. The value of the `Accept` header is a media type. For more information about media types, see [Media types](#media-types).

##### `X-GitHub-Api-Version`

You should use this header to specify a version of the REST API to use for your request. For more information, see [API Versions](/en/rest/overview/api-versions).

##### `User-Agent`

All API requests must include a valid `User-Agent` header. The `User-Agent` header identifies the user or application that is making the request.

By default, GitHub CLI sends a valid `User-Agent` header. However, GitHub recommends using your GitHub username, or the name of your application, for the `User-Agent` header value. This allows GitHub to contact you if there are problems.

By default, `curl` sends a valid `User-Agent` header. However GitHub recommends using your GitHub username, or the name of your application, for the `User-Agent` header value. This allows GitHub to contact you if there are problems.

If you use the Octokit.js SDK, the SDK will send a valid `User-Agent` header for you. However, GitHub recommends using your GitHub username, or the name of your application, for the `User-Agent` header value. This allows GitHub to contact you if there are problems.

The following is an example `User-Agent` for an app named `Awesome-Octocat-App`:

```shell
User-Agent: Awesome-Octocat-App
```

Requests with no `User-Agent` header will be rejected. If you provide an invalid `User-Agent` header, you will receive a `403 Forbidden` response.

#### Media types

You can specify one or more media types by adding them to the `Accept` header of your request. For more information about the `Accept` header, see [`Accept`](#accept).

Media types specify the format of the data you want to consume from the API. Media types are specific to resources, allowing them to change independently and support formats that other resources don't. The documentation for each GitHub REST API endpoint will describe the media types that it supports. For more information, see the [GitHub REST API documentation](/en/rest).

The most common media types supported by the GitHub REST API are `application/vnd.github+json` and `application/json`.

There are custom media types that you can use with some endpoints. For example, the REST API to manage [commits](/en/rest/commits/commits#get-a-commit) and [pull requests](/en/rest/pulls/pulls) support the media types `diff`, `patch`, and `sha`. The media types `full`, `raw`, `text`, or `html` are used by some other endpoints.

All custom media types for GitHub look like this: `application/vnd.github.PARAM+json`, where `PARAM` is the name of the media type. For example, to specify the `raw` media type, you would use `application/vnd.github.raw+json`.

For an example of a request that uses media types, see [Making a request](#making-a-request).

#### Authentication

Many endpoints require authentication or return additional information if you are authenticated. Additionally, you can make more requests per hour when you are authenticated.

To authenticate your request, you will need to provide an authentication token with the required scopes or permissions. There a few different ways to get a token: You can create a personal access token, generate a token with a GitHub App, or use the built-in `GITHUB_TOKEN` in a GitHub Actions workflow. For more information, see [Authenticating to the REST API](/en/rest/overview/authenticating-to-the-rest-api).

For an example of a request that uses an authentication token, see [Making a request](#making-a-request).

> **Note**
> If you don't want to create a token, you can use GitHub CLI. GitHub CLI will take care of authentication for you, and help keep your account secure. For more information, see the [GitHub CLI version of this page](/en/rest/guides/getting-started-with-the-rest-api?tool=cli).

> **Warning**
> Treat your access token the same way you would treat your passwords or other sensitive credentials. For more information, see [Keeping your API credentials secure](/en/rest/overview/keeping-your-api-credentials-secure).

Although some REST API endpoints are accessible without authentication, GitHub CLI requires you to authenticate before you can use the `api` subcommand to make an API request. Use the `auth login` subcommand to authenticate to GitHub. For more information, see [Making a request](#making-a-request).

#### Parameters

Many API methods require or allow you to send additional information in parameters in your request. There are a few different types of parameters: Path parameters, body parameters, and query parameters.

##### Path parameters

Path parameters modify the endpoint path. These parameters are required in your request. For more information, see [Path](#path).

##### Body parameters

Body parameters allow you to pass additional data to the API. These parameters can be optional or required, depending on the endpoint. For example, a body parameter may allow you to specify an issue title when creating a new issue, or specify certain settings when enabling or disabling a feature. The documentation for each GitHub REST API endpoint will describe the body parameters that it supports. For more information, see the [GitHub REST API documentation](/en/rest).

For example, the ["Create an issue" endpoint](/en/rest/issues/issues#create-an-issue) requires that you specify a title for the new issue in your request. It also allows you to optionally specify other information, such as text to put in the issue body, users to assign to the new issue, or labels to apply to the new issue. For an example of a request that uses body parameters, see [Making a request](#making-a-request).

You must authenticate your request to pass body parameters. For more information, see [Authentication](#authentication).

##### Query parameters

Query parameters allow you to control what data is returned for a request. These parameters are usually optional. The documentation for each GitHub REST API endpoint will describe any query parameters that it supports. For more information, see the [GitHub REST API documentation](/en/rest).

For example, the ["List public events" endpoint](/en/rest/activity/events#list-public-events) returns thirty issues by default. You can use the `per_page` query parameter to return two issues instead of 30. You can use the `page` query parameter to fetch only the first page of results. For an example of a request that uses query parameters, see [Making a request](#making-a-request).

### Making a request

This section demonstrates how to make an authenticated request to the GitHub REST API using GitHub CLI.

#### 1. Setup

Install GitHub CLI on macOS, Windows, or Linux. For more information, see [Installation](https://github.com/cli/cli#installation) in the GitHub CLI repository.

#### 2. Authenticate

1. To authenticate to GitHub, run the following command from your terminal.

   ```shell
   gh auth login
   ```

   You can use the `--scopes` option to specify what scopes you want. If you want to authenticate with a token that you created, you can use the `--with-token` option. For more information, see the [GitHub CLI `auth login` documentation](https://cli.github.com/manual/gh_auth_login).

2. Select where you want to authenticate to:

   * If you access GitHub at GitHub.com, select **GitHub.com**.
   * If you access GitHub at a different domain, select **Other**, then enter your hostname (for example: `octocorp.ghe.com`).

3. Follow the rest of the on-screen prompts.

   GitHub CLI automatically stores your Git credentials for you when you choose HTTPS as your preferred protocol for Git operations and answer "yes" to the prompt asking if you would like to authenticate to Git with your GitHub credentials. This can be useful as it allows you to use Git commands like `git push` and `git pull` without needing to set up a separate credential manager or use SSH.

#### 3. Choose an endpoint for your request

1. Choose an endpoint to make a request to. You can explore GitHub's [REST API documentation](/en/rest) to discover endpoints that you can use to interact with GitHub.

2. Identify the HTTP method and path of the endpoint. You will send these with your request. For more information, see [HTTP method](#http-method) and [Path](#path).

   For example, the ["Create an issue" endpoint](/en/rest/issues/issues#create-an-issue) uses the HTTP method `POST` and the path `/repos/{owner}/{repo}/issues`.

3. Identify any required path parameters. Required path parameters appear in curly brackets `{}` in the path of the endpoint. Replace each parameter placeholder with the desired value. For more information, see [Path](#path).

   For example, the ["Create an issue" endpoint](/en/rest/issues/issues#create-an-issue) uses the path `/repos/{owner}/{repo}/issues`, and the path parameters are `{owner}` and `{repo}`. To use this path in your API request, replace `{repo}` with the name of the repository where you would like to create a new issue, and replace `{owner}` with the name of the account that owns the repository.

#### 4. Make a request with GitHub CLI

Use the GitHub CLI `api` subcommand to make your API request. For more information, see the [GitHub CLI `api` documentation](https://cli.github.com/manual/gh_api).

In your request, specify the following options and values:

* **--method** followed by the HTTP method and the path of the endpoint. For more information, see [HTTP method](#http-method) and [Path](#path).
* **--header:**
  * **`Accept`:** Pass the media type in an `Accept` header. To pass multiple media types in an `Accept` header, separate the media types with a comma: `Accept: application/vnd.github+json,application/vnd.github.diff`. For more information, see [`Accept`](#accept) and [Media types](#media-types).
  * **`X-GitHub-Api-Version`:** Pass the API version in a `X-GitHub-Api-Version` header. For more information, see [`X-GitHub-Api-Version`](#x-github-api-version).
* **`-f`** or **`-F`** followed by any body parameters or query parameters in `key=value` format. Use the `-F` option to pass a parameter that is a number, Boolean, or null. Use the `-f` option to pass string parameters.

  Some endpoints use query parameters that are arrays. To send an array in the query string, use the query parameter once per array item, and append `[]` after the query parameter name. For example, to provide an array of two repository IDs, use `-f repository_ids[]=REPOSITORY_A_ID -f repository_ids[]=REPOSITORY_B_ID`.

  If you do not need to specify any body parameters or query parameters in your request, omit this option. For more information, see [Body parameters](#body-parameters) and [Query parameters](#query-parameters). For examples, see [Example request using body parameters](#example-request-using-body-parameters) and [Example request using query parameters](#example-request-using-query-parameters).

##### Example request

The following example request uses the ["Get Octocat" endpoint](/en/rest/meta/meta#get-octocat) to return the octocat as ASCII art.

```shell
gh api --method GET /octocat \
--header 'Accept: application/vnd.github+json' \
--header "X-GitHub-Api-Version: 2022-11-28"
```

##### Example request using query parameters

The ["List public events" endpoint](/en/rest/activity/events#list-public-events) returns thirty issues by default. The following example uses the `per_page` query parameter to return two issues instead of 30, and the `page` query parameter to fetch only the first page of results.

```shell
gh api --method GET /events -F per_page=2 -F page=1
--header 'Accept: application/vnd.github+json' \
```

##### Example request using body parameters

The following example uses the ["Create an issue" endpoint](/en/rest/issues/issues#create-an-issue) to create a new issue in the octocat/Spoon-Knife repository. In the response, find the `html_url` of your issue, and navigate to your issue in the browser.

```shell
gh api --method POST /repos/octocat/Spoon-Knife/issues \
--header "Accept: application/vnd.github+json" \
--header "X-GitHub-Api-Version: 2022-11-28" \
-f title='Created with the REST API' \
-f body='This is a test issue created by the REST API' \
```

This section demonstrates how to make an authenticated request to the GitHub REST API using `curl`.

#### 1. Setup (curl)

You must have `curl` installed on your machine. To check if `curl` is already installed, run `curl --version` on the command line.

* If the output provides information about the version of `curl`, that means `curl` is installed.
* If you get a message similar to `command not found: curl`, that means `curl` is not installed. Download and install `curl`. For more information, see [the curl download page](https://curl.se/download.html).

#### 2. Choose an endpoint for your request (curl)

1. Choose an endpoint to make a request to. You can explore GitHub's [REST API documentation](/en/rest) to discover endpoints that you can use to interact with GitHub.

2. Identify the HTTP method and path of the endpoint. You will send these with your request. For more information, see [HTTP method](#http-method) and [Path](#path).

   For example, the ["Create an issue" endpoint](/en/rest/issues/issues#create-an-issue) uses the HTTP method `POST` and the path `/repos/{owner}/{repo}/issues`.

3. Identify any required path parameters. Required path parameters appear in curly brackets `{}` in the path of the endpoint. Replace each parameter placeholder with the desired value. For more information, see [Path](#path).

   For example, the ["Create an issue" endpoint](/en/rest/issues/issues#create-an-issue) uses the path `/repos/{owner}/{repo}/issues`, and the path parameters are `{owner}` and `{repo}`. To use this path in your API request, replace `{repo}` with the name of the repository where you would like to create a new issue, and replace `{owner}` with the name of the account that owns the repository.

#### 3. Create authentication credentials

Create an access token to authenticate your request. You can save your token and use it for multiple requests. Give the token any scopes or permissions that are required to access the endpoint. You will send this token in an `Authorization` header with your request. For more information, see [Authentication](#authentication).

#### 4. Make a `curl` request

Use the `curl` command to make your request. For more information, see [the curl documentation](https://curl.se/docs/manpage.html).

Specify the following options and values in your request:

* **`--request` or `-X`** followed by the HTTP method as the value. For more information, see [HTTP method](#http-method).
* **`--url`** followed by the full path as the value. The full path is a URL that includes the base URL for the GitHub REST API (`https://api.github.com`) and the path of the endpoint, like this: `https://api.github.com/PATH`. Replace `PATH` with the path of the endpoint. For more information, see [Path](#path).

  To use query parameters, add a `?` to the end of the path, then append your query parameter name and value in the form `parameter_name=value`. Separate multiple query parameters with `&`. If you need to send an array in the query string, use the query parameter once per array item, and append `[]` after the query parameter name. For example, to provide an array of two repository IDs, use `?repository_ids[]=REPOSITORY_A_ID&repository_ids[]=REPOSITORY_B_ID`. For more information, see [Query parameters](#query-parameters). For an example, see [Example request using query parameters](#example-request-using-query-parameters-1).
* **`--header` or `-H`:**
  * **`Accept`:** Pass the media type in an `Accept` header. To pass multiple media types in an `Accept` header, separate the media types with a comma, for example: `Accept: application/vnd.github+json,application/vnd.github.diff`. For more information, see [`Accept`](#accept) and [Media types](#media-types).
  * **`X-GitHub-Api-Version`:** Pass the API version in a `X-GitHub-Api-Version` header. For more information, see [`X-GitHub-Api-Version`](#x-github-api-version).
  * **`Authorization`:** Pass your authentication token in an `Authorization` header. Note that in most cases you can use `Authorization: Bearer` or `Authorization: token` to pass a token. However, if you are passing a JSON web token (JWT), you must use `Authorization: Bearer`. For more information, see [Authentication](#authentication). For an example of a request that uses an `Authorization` header, see [Example request using body parameters](#example-request-using-body-parameters-1).
* **`--data` or `-d`** followed by any body parameters within a JSON object. If you do not need to specify any body parameters in your request, omit this option. For more information, see [Body parameters](#body-parameters). For an example, see [Example request using body parameters](#example-request-using-body-parameters-1).

##### Example request (curl)

The following example request uses the ["Get Octocat" endpoint](/en/rest/meta/meta#get-octocat) to return the octocat as ASCII art.

```shell
curl --request GET \
--url "https://api.github.com/octocat" \
--header "Accept: application/vnd.github+json" \
--header "X-GitHub-Api-Version: 2022-11-28"
```

##### Example request using query parameters (curl)

The ["List public events" endpoint](/en/rest/activity/events#list-public-events) returns thirty issues by default. The following example uses the `per_page` query parameter to return two issues instead of 30, and the `page` query parameter to fetch only the first page of results.

```shell
curl --request GET \
--url "https://api.github.com/events?per_page=2&page=1" \
--header "Accept: application/vnd.github+json" \
--header "X-GitHub-Api-Version: 2022-11-28" \
  https://api.github.com/events
```

##### Example request using body parameters (curl)

The following example uses the [Create an issue](/en/rest/issues/issues#create-an-issue) endpoint to create a new issue in the octocat/Spoon-Knife repository. Replace `YOUR-TOKEN` with the authentication token you created in a previous step.

> **Note**
> If you are using a fine-grained personal access token, you must replace `octocat/Spoon-Knife` with a repository that you own or that is owned by an organization that you are a member of. Your token must have access to that repository and have read and write permissions for repository issues. For more information, see [Managing your personal access tokens](/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token).

```shell
curl \
--request POST \
--url "https://api.github.com/repos/octocat/Spoon-Knife/issues" \
--header "Accept: application/vnd.github+json" \
--header "X-GitHub-Api-Version: 2022-11-28" \
--header "Authorization: Bearer YOUR-TOKEN" \
--data '{
  "title": "Created with the REST API",
  "body": "This is a test issue created by the REST API"
}'
```

This section demonstrates how to make a request to the GitHub REST API using JavaScript and [Octokit.js](https://github.com/octokit/octokit.js). For a more detailed guide, see [Scripting with the REST API and JavaScript](/en/rest/guides/scripting-with-the-rest-api-and-javascript).

#### 1. Setup (JavaScript)

You must install `octokit` to use the Octokit.js library shown in the following examples.

* Install `octokit`. For example, `npm install octokit`. For other ways to install or load `octokit`, see [the Octokit.js README](https://github.com/octokit/octokit.js/#readme).

#### 2. Choose an endpoint for your request (JavaScript)

1. Choose an endpoint to make a request to. You can explore GitHub's [REST API documentation](/en/rest) to discover endpoints that you can use to interact with GitHub.

2. Identify the HTTP method and path of the endpoint. You will send these with your request. For more information, see [HTTP method](#http-method) and [Path](#path).

   For example, the ["Create an issue" endpoint](/en/rest/issues/issues#create-an-issue) uses the HTTP method `POST` and the path `/repos/{owner}/{repo}/issues`.

3. Identify any required path parameters. Required path parameters appear in curly brackets `{}` in the path of the endpoint. Replace each parameter placeholder with the desired value. For more information, see [Path](#path).

   For example, the ["Create an issue" endpoint](/en/rest/issues/issues#create-an-issue) uses the path `/repos/{owner}/{repo}/issues`, and the path parameters are `{owner}` and `{repo}`. To use this path in your API request, replace `{repo}` with the name of the repository where you would like to create a new issue, and replace `{owner}` with the name of the account that owns the repository.

#### 3. Create an access token

Create an access token to authenticate your request. You can save your token and use it for multiple requests. Give the token any scopes or permissions that are required to access the endpoint. You will send this token in an `Authorization` header with your request. For more information, see [Authentication](#authentication).

#### 4. Make a request with Octokit.js

1. Import `octokit` in your script. For example, `import { Octokit } from "octokit";`. For other ways to import `octokit`, see [the Octokit.js README](https://github.com/octokit/octokit.js/#readme).

2. Create an instance of `Octokit` with your token. Replace `YOUR-TOKEN` with your token.

   ```javascript
   const octokit = new Octokit({ 
     auth: 'YOUR-TOKEN'
   });
   ```

3. Use `octokit.request` to execute your request.

   * Send the HTTP method and path as the first argument to the `request` method. For more information, see [HTTP method](#http-method) and [Path](#path).
   * Specify all path, query, and body parameters in an object as the second argument to the `request` method. For more information, see [Parameters](#parameters).

   In the following example request, the HTTP method is `POST`, the path is `/repos/{owner}/{repo}/issues`, the path parameters are `owner: "octocat"` and `repo: "Spoon-Knife"`, and the body parameters are `title: "Created with the REST API"` and `body: "This is a test issue created by the REST API"`.

   > **Note**
   > If you are using a fine-grained personal access token, you must replace `octocat/Spoon-Knife` with a repository that you own or that is owned by an organization that you are a member of. Your token must have access to that repository and have read and write permissions for repository issues. For more information, see [Managing your personal access tokens](/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token).

   ```javascript
   await octokit.request("POST /repos/{owner}/{repo}/issues", {
     owner: "octocat",
     repo: "Spoon-Knife",
     title: "Created with the REST API",
     body: "This is a test issue created by the REST API",
   });
   ```

   The `request` method automatically passes the `Accept: application/vnd.github+json` header. To pass additional headers or a different `Accept` header, add a `headers` property to the object that is passed as a second argument. The value of the `headers` property is an object with the header names as keys and header values as values.

   For example, the following code will send a `content-type` header with a value of `text/plain` and a `X-GitHub-Api-Version` header with a value of `2026-03-10`.

   ```javascript
   await octokit.request("GET /octocat", {
     headers: {
       "content-type": "text/plain",
       "X-GitHub-Api-Version": "2026-03-10",
     },
   });
   ```

### Using the response

After you make a request, the API will return the response status code, response headers, and potentially a response body.

#### About the response code and headers

Every request will return an HTTP status code that indicates the success of the response. For more information about response codes, see [the MDN HTTP response status code documentation](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status).

Additionally, the response will include headers that give more details about the response. Headers that start with `X-` or `x-` are custom to GitHub. For example, the `x-ratelimit-remaining` and `x-ratelimit-reset` headers tell you how many requests you can make in a time period.

To view the status code and headers, use the `--include` or `--i` option when you send your request.

For example, this request gets a list of issues in the octocat/Spoon-Knife repository:

```shell
gh api \
--header 'Accept: application/vnd.github+json' \
--method GET /repos/octocat/Spoon-Knife/issues \
-F per_page=2 --include
```

And it returns a response code and headers that look something like this:

```shell
HTTP/2.0 200 OK
Access-Control-Allow-Origin: *
Access-Control-Expose-Headers: ETag, Link, Location, Retry-After, X-RateLimit-Limit, X-RateLimit-Remaining, X-RateLimit-Used, X-RateLimit-Resource, X-RateLimit-Reset, X-OAuth-Scopes, X-Accepted-OAuth-Scopes, X-Poll-Interval, X-GitHub-Media-Type, X-GitHub-SSO, X-GitHub-Request-Id, Deprecation, Sunset
Cache-Control: private, max-age=60, s-maxage=60
Content-Security-Policy: default-src 'none'
Content-Type: application/json; charset=utf-8
Date: Thu, 04 Aug 2022 19:56:41 GMT
Etag: W/"a63dfbcfdb73621e9d2e89551edcf9856731ced534bd7f1e114a5da1f5f73418"
Link: <https://api.github.com/repositories/1300192/issues?per_page=1&page=2>; rel="next", <https://api.github.com/repositories/1300192/issues?per_page=1&page=14817>; rel="last"
Referrer-Policy: origin-when-cross-origin, strict-origin-when-cross-origin
Server: GitHub.com
Strict-Transport-Security: max-age=31536000; includeSubdomains; preload
Vary: Accept, Authorization, Cookie, Accept-Encoding, Accept, X-Requested-With
X-Accepted-Oauth-Scopes: repo
X-Content-Type-Options: nosniff
X-Frame-Options: deny
X-Github-Api-Version-Selected: 2022-08-09
X-Github-Media-Type: github.v3; format=json
X-Github-Request-Id: 1C73:26D4:E2E500:1EF78F4:62EC2479
X-Oauth-Client-Id: 178c6fc778ccc68e1d6a
X-Oauth-Scopes: gist, read:org, repo, workflow
X-Ratelimit-Limit: 15000
X-Ratelimit-Remaining: 14996
X-Ratelimit-Reset: 1659645499
X-Ratelimit-Resource: core
X-Ratelimit-Used: 4
X-Xss-Protection: 0
```

In this example, the response code is `200`, which indicates a successful request.

When you make a request with Octokit.js, the `request` method returns a promise. If the request was successful, the promise resolves to an object that includes the HTTP status code of the response (`status`) and the response headers (`headers`). If an error occurs, the promise resolves to an object that includes the HTTP status code of the response (`status`) and the response headers (`response.headers`).

You can use a `try/catch` block to catch an error if it occurs. For example, if the request in the following script is successful, the script will log the status code and the value of the `x-ratelimit-remaining` header. If the request was not successful, the script will log the status code, the value of the `x-ratelimit-remaining` header, and the error message.

In the following example, replace `REPO-OWNER` with the name of the account that owns the repository, and `REPO-NAME` with the name of the repository.

```javascript
try {
  const result = await octokit.request("GET /repos/{owner}/{repo}/issues", {
    owner: "REPO-OWNER",
    repo: "REPO-NAME",
    per_page: 2,
  });

  console.log(`Success! Status: ${result.status}. Rate limit remaining: ${result.headers["x-ratelimit-remaining"]}`)

} catch (error) {
  console.log(`Error! Status: ${error.status}. Rate limit remaining: ${error.headers["x-ratelimit-remaining"]}. Message: ${error.response.data.message}`)
}
```

To view the status code and headers, use the `--include` or `--i` option when you send your request.

For example, this request gets a list of issues in the octocat/Spoon-Knife repository:

```shell
curl --request GET \
--url "https://api.github.com/repos/octocat/Spoon-Knife/issues?per_page=2" \
--header "Accept: application/vnd.github+json" \
--header "Authorization: Bearer YOUR-TOKEN" \
--include
```

And it returns a response code and headers that look something like this:

```shell
HTTP/2 200
server: GitHub.com
date: Thu, 04 Aug 2022 20:07:51 GMT
content-type: application/json; charset=utf-8
cache-control: public, max-age=60, s-maxage=60
vary: Accept, Accept-Encoding, Accept, X-Requested-With
etag: W/"7fceb7e8c958d3ec4d02524b042578dcc7b282192e6c939070f4a70390962e18"
x-github-media-type: github.v3; format=json
link: <https://api.github.com/repositories/1300192/issues?per_page=2&sort=updated&direction=asc&page=2>; rel="next", <https://api.github.com/repositories/1300192/issues?per_page=2&sort=updated&direction=asc&page=7409>; rel="last"
access-control-expose-headers: ETag, Link, Location, Retry-After, X-RateLimit-Limit, X-RateLimit-Remaining, X-RateLimit-Used, X-RateLimit-Resource, X-RateLimit-Reset, X-OAuth-Scopes, X-Accepted-OAuth-Scopes, X-Poll-Interval, X-GitHub-Media-Type, X-GitHub-SSO, X-GitHub-Request-Id, Deprecation, Sunset
access-control-allow-origin: *
strict-transport-security: max-age=31536000; includeSubdomains; preload
x-frame-options: deny
x-content-type-options: nosniff
x-xss-protection: 0
referrer-policy: origin-when-cross-origin, strict-origin-when-cross-origin
content-security-policy: default-src 'none'
x-ratelimit-limit: 15000
x-ratelimit-remaining: 14996
x-ratelimit-reset: 1659645535
x-ratelimit-resource: core
x-ratelimit-used: 4
accept-ranges: bytes
content-length: 4936
x-github-request-id: 14E0:4BC6:F1B8BA:208E317:62EC2715
```

In this example, the response code is `200`, which indicates a successful request.

#### About the response body

Many endpoints will return a response body. Unless otherwise specified, the response body is in JSON format. Blank fields are included as `null` instead of being omitted. All timestamps return in UTC time, ISO 8601 format: `YYYY-MM-DDTHH:MM:SSZ`.

Unlike the GraphQL API where you specify what information you want, the REST API typically returns more information than you need. If desired, you can parse the response to pull out specific pieces of information.

For example, you can use `>` to redirect the response to a file. In the following example, replace `REPO-OWNER` with the name of the account that owns the repository, and `REPO-NAME` with the name of the repository.

```shell
gh api \
--header 'Accept: application/vnd.github+json' \
--method GET /repos/REPO-OWNER/REPO-NAME/issues \
-F per_page=2 > data.json
```

Then you can use jq to get the title and author ID of each issue:

```shell
jq '.[] | {title: .title, authorID: .user.id}' data.json
```

The previous two commands return something like:

```json
{
  "title": "Update index.html",
  "authorID": 10701255
}
{
  "title": "Edit index file",
  "authorID": 53709285
}
```

For more information about jq, see [the jq documentation](https://stedolan.github.io/jq/).

For example, you can get the title and author ID of each issue. In the following example, replace `REPO-OWNER` with the name of the account that owns the repository, and `REPO-NAME` with the name of the repository.

```javascript
try {
  const result = await octokit.request("GET /repos/{owner}/{repo}/issues", {
    owner: "REPO-OWNER",
    repo: "REPO-NAME",
    per_page: 2,
  });

  const titleAndAuthor = result.data.map(issue => {title: issue.title, authorID: issue.user.id})

  console.log(titleAndAuthor)

} catch (error) {
  console.log(`Error! Status: ${error.status}. Message: ${error.response.data.message}`)
}
```

For example, you can use `>` to redirect the response to a file. In the following example, replace `REPO-OWNER` with the name of the account that owns the repository, and `REPO-NAME` with the name of the repository.

```shell
curl --request GET \
--url "https://api.github.com/repos/REPO-OWNER/REPO-NAME/issues?per_page=2" \
--header "Accept: application/vnd.github+json" \
--header "Authorization: Bearer YOUR-TOKEN" > data.json
```

Then you can use jq to get the title and author ID of each issue:

```shell
jq '.[] | {title: .title, authorID: .user.id}' data.json
```

The previous two commands return something like:

```json
{
  "title": "Update index.html",
  "authorID": 10701255
}
{
  "title": "Edit index file",
  "authorID": 53709285
}
```

For more information about jq, see [the jq documentation](https://stedolan.github.io/jq/).

##### Detailed versus summary representations

A response can include all attributes for a resource or only a subset of attributes, depending on whether you fetch an individual resource or a list of resources.

* When you fetch an *individual resource*, like a specific repository, the response will typically include all attributes for that resource. This is the "detailed" representation of the resource.
* When you fetch a *list of resources*, like a list of multiple repositories, the response will only include a subset of the attributes for each resource. This is the "summary" representation of the resource.

Note that authorization sometimes influences the amount of detail included in a representation.

The reason for this is because some attributes are computationally expensive for the API to provide, so GitHub excludes those attributes from the summary representation. To obtain those attributes, you can fetch the detailed representation.

The documentation provides an example response for each API method. The example response illustrates all attributes that are returned by that method.

##### Hypermedia

All resources may have one or more `*_url` properties linking to other resources. These are meant to provide explicit URLs so that proper API clients don't need to construct URLs on their own. It is highly recommended that API clients use these. Doing so will make future upgrades of the API easier for developers. All URLs are expected to be proper [RFC 6570](https://datatracker.ietf.org/doc/html/rfc6570) URI templates.

You can then expand these templates using something like the [uri\_template](https://github.com/hannesg/uri_template) gem:

```ruby
>> tmpl = URITemplate.new('/notifications{?since,all,participating}')
>> tmpl.expand
=> "/notifications"

>> tmpl.expand all: 1
=> "/notifications?all=1"

>> tmpl.expand all: 1, participating: 1
=> "/notifications?all=1&participating=1"
```

### Rate limiting

The GitHub REST API limits the number of requests you can make within a given time period. For more information about rate limits and how to check your current rate limit status, see [Rate limits for the REST API](/en/rest/using-the-rest-api/rate-limits-for-the-rest-api).

### Next steps

This article demonstrated how to list and create issues in a repository. For more practice, try to comment on an issue, edit the title of an issue, or close an issue. For more information, see the ["Create an issue comment" endpoint](/en/rest/issues/comments#create-an-issue-comment) and the ["Update an issue" endpoint](/en/rest/issues/issues#update-an-issue).

For more information about other endpoints that you can use, see the [REST reference documentation](/en/rest).

---

## Media types

> Source: https://docs.github.com/en/rest/using-the-rest-api/media-types?apiVersion=2026-03-10

> _Extraction note: the upstream fetcher repeatedly served the "Getting started with the REST API" page body when this URL was requested (the docs site renders Media types within the same collection shell). The verbatim core of the standalone Media types page is reproduced below from the clean fetch that did resolve. The page is short; its substantive content is the introduction plus the custom media-type list. The same "Media types" subsection (with identical wording) also appears inline under [Getting started → Media types](#media-types) above._

You can specify one or more media types by adding them to the `Accept` header of your request. For more information about the `Accept` header, see [`Accept`](#accept).

Media types specify the format of the data you want to consume from the API. Media types are specific to resources, allowing them to change independently and support formats that other resources don't. The documentation for each GitHub REST API endpoint will describe the media types that it supports. For more information, see the [GitHub REST API documentation](/en/rest).

The most common media types supported by the GitHub REST API are `application/vnd.github+json` and `application/json`.

There are custom media types that you can use with some endpoints. For example, the REST API to manage [commits](/en/rest/commits/commits#get-a-commit) and [pull requests](/en/rest/pulls/pulls) support the media types `diff`, `patch`, and `sha`. The media types `full`, `raw`, `text`, or `html` are used by some other endpoints.

All custom media types for GitHub look like this: `application/vnd.github.PARAM+json`, where `PARAM` is the name of the media type. For example, to specify the `raw` media type, you would use `application/vnd.github.raw+json`.

---

## Troubleshooting the REST API

> Source: https://docs.github.com/en/rest/using-the-rest-api/troubleshooting-the-rest-api?apiVersion=2026-03-10

Learn how to diagnose and resolve common problems for the REST API.

### Rate limit errors

GitHub enforces rate limits to ensure that the API stays available for all users. For more information, see [Rate limits for the REST API](/en/rest/overview/rate-limits-for-the-rest-api).

If you exceed your primary rate limit, you will receive a `403 Forbidden` or `429 Too Many Requests ` response, and the `x-ratelimit-remaining` header will be `0`. If you exceed a secondary rate limit, you will receive a `403 Forbidden` or `429 Too Many Requests ` response and an error message that indicates that you exceeded a secondary rate limit.

If you receive a rate limit error, you should stop making requests temporarily according to these guidelines:

* If the `retry-after` response header is present, you should not retry your request until after that many seconds has elapsed.
* If the `x-ratelimit-remaining` header is `0`, you should not make another request until after the time specified by the `x-ratelimit-reset` header. The `x-ratelimit-reset` header is in UTC epoch seconds.
* Otherwise, wait for at least one minute before retrying. If your request continues to fail due to a secondary rate limit, wait for an exponentially increasing amount of time between retries, and throw an error after a specific number of retries.

Continuing to make requests while you are rate limited may result in the banning of your integration.

For more information about how to avoid exceeding the rate limits, see [Best practices for using the REST API](/en/rest/guides/best-practices-for-using-the-rest-api).

### `404 Not Found` for an existing resource

If you make a request to access a private resource and your request isn't properly authenticated, you will receive a `404 Not Found` response. GitHub uses a `404 Not Found` response instead of a `403 Forbidden` response to avoid confirming the existence of private repositories.

If you get a `404 Not Found` response when you know that the resource that you are requesting exists, you should check your authentication. For example:

* If you are using a personal access token (classic), you should ensure that:
  * The token has the scopes that are required to use the endpoint. For more information, see [Scopes for OAuth apps](/en/apps/oauth-apps/building-oauth-apps/scopes-for-oauth-apps#available-scopes) and [Managing your personal access tokens](/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-fine-grained-personal-access-token).
  * The owner of the token has any permissions that are required to use the endpoint. For example, if an endpoint can only be used by organization owners, only users that are owners of the affected organization can use the endpoint.
  * The token has not been expired or revoked. For more information, see [Token expiration and revocation](/en/authentication/keeping-your-account-and-data-secure/token-expiration-and-revocation).
* If you are using a fine-grained personal access token, you should ensure that:
  * The token has the permissions that are required to use the endpoint. For more information about the required permissions, see the documentation for the endpoint.
  * The resource owner that was specified for the token matches the owner of the resource that the endpoint will affect. For more information, see [Managing your personal access tokens](/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-fine-grained-personal-access-token).
  * The token has access to any private repositories that the endpoint will affect. For more information, see [Managing your personal access tokens](/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-fine-grained-personal-access-token).
  * The owner of the token has any permissions that are required to use the endpoint. For example, if an endpoint can only be used by organization owners, only users that are owners of the affected organization can use the endpoint.
  * The token has not been expired or revoked. For more information, see [Token expiration and revocation](/en/authentication/keeping-your-account-and-data-secure/token-expiration-and-revocation).
* If you are using a GitHub App installation access token, you should ensure that:
  * The GitHub App has the permissions that are required to use the endpoint. For more information about the required permissions, see the documentation for the endpoint.
  * The endpoint is only affecting resources owned by the account where the GitHub App is installed.
  * The GitHub App has access to any repositories that the endpoint will affect.
  * The token has not been expired or revoked. For more information, see [Token expiration and revocation](/en/authentication/keeping-your-account-and-data-secure/token-expiration-and-revocation).
* If you are using a GitHub App user access token, you should ensure that:
  * The GitHub App has the permissions that are required to use the endpoint. For more information about the required permissions, see the documentation for the endpoint.
  * The user that authorized the token has any permissions that are required to use the endpoint. For example, if an endpoint can only be used by organization owners, only users that are owners of the affected organization can use the endpoint.
  * The GitHub App has access to any repositories that the endpoint will affect.
  * The user has access to any repositories that the endpoint will affect.
  * The user has approved any updated permissions for your GitHub App. For more information, see [Approving updated permissions for a GitHub App](/en/apps/using-github-apps/approving-updated-permissions-for-a-github-app).
* If you are using an OAuth app user access token, you should ensure that:
  * The token has the scopes that are required to use the endpoint. For more information, see [Scopes for OAuth apps](/en/apps/oauth-apps/building-oauth-apps/scopes-for-oauth-apps#available-scopes).
  * The user that authorized the token has any permissions that are required to use the endpoint. For example, if an endpoint can only be used by organization owners, only users that are owners of the affected organization can use the endpoint.
  * The organization has not blocked OAuth app access, if you are using an endpoint that will affect resources owned by an organization. App owners cannot see whether their app is blocked, but they can instruct users of the app to check this. For more information, see [About OAuth app access restrictions](/en/organizations/managing-oauth-access-to-your-organizations-data/about-oauth-app-access-restrictions).
  * The token has not been expired or revoked. For more information, see [Token expiration and revocation](/en/authentication/keeping-your-account-and-data-secure/token-expiration-and-revocation).
* If you are using `GITHUB_TOKEN` in a GitHub Actions workflow, you should ensure that:
  * The endpoint is only affecting resources owned by the repository where the workflow is running. If you need to access resources outside of that repository, such as resources owned by an organization or resources owned by another repository, you should use a personal access token or an access token for a GitHub App.

For more information about authentication, see [Authenticating to the REST API](/en/rest/overview/authenticating-to-the-rest-api).

You should also check for typos in your URL. For example, adding a trailing slash to the endpoint will result in a `404 Not Found`. You can refer to the reference documentation for the endpoint to confirm that you have the correct URL.

Additionally, any path parameters must be URL encoded. For example, any slashes in the parameter value must be replaced with `%2F`. If you don't properly encode any slashes in the parameter name, the endpoint URL will be misinterpreted.

### Missing results

Most endpoints that return a list of resources support pagination. For most of these endpoints, only the first 30 resources are returned by default. In order to see all of the resources, you need to paginate through the results. For more information, see [Using pagination in the REST API](/en/rest/guides/using-pagination-in-the-rest-api).

If you are using pagination correctly and still do not see all of the results that you expect, you should confirm that the authentication credentials that you used have access to all of the expected resources. For example, if you are using a GitHub App installation access token, if the installation was only granted access to a subset of repositories in an organization, any request for all repositories in that organization will return only the repositories that the app installation can access.

### Requires authentication when using basic authentication

Basic authentication with your username and password is not supported. Instead, you should use a personal access token or an access token for a GitHub App or OAuth app. For more information, see [Authenticating to the REST API](/en/rest/overview/authenticating-to-the-rest-api).

### Timeouts

If GitHub takes more than 10 seconds to process an API request, GitHub will terminate the request and you will receive a timeout response and a "Server Error" message.

GitHub reserves the right to change the timeout window to protect the speed and reliability of the API.

You can check the status of the REST API at [githubstatus.com](https://www.githubstatus.com/) to determine whether the timeout is due to a problem with the API. You can also try to simplify your request or try your request later. For example, if you are requesting 100 items on a page, you can try requesting fewer items.

### Resource not accessible

If you are using a GitHub App or fine-grained personal access token and you receive a "Resource not accessible by integration" or "Resource not accessible by personal access token" error, then your token has insufficient permissions. For more information about the required permissions, see the documentation for the endpoint.

You can use the `X-Accepted-GitHub-Permissions` header to identify the permissions that are required to access the REST API endpoint.

The value of the `X-Accepted-GitHub-Permissions` header is a comma separated list of the permissions that are required to use the endpoint. Occasionally, you can choose from multiple permission sets. In these cases, multiple comma-separated lists will be separated by a semicolon.

For example:

* `X-Accepted-GitHub-Permissions: contents=read` means that your GitHub App or fine-grained personal access token needs read access to the contents permission.
* `X-Accepted-GitHub-Permissions: pull_requests=write,contents=read` means that your GitHub App or fine-grained personal access token needs write access to the pull request permission and read access to the contents permission.
* `X-Accepted-GitHub-Permissions: pull_requests=read,contents=read; issues=read,contents=read` means that your GitHub App or fine-grained personal access token needs either read access to the pull request permission and read access to the contents permission, or read access to the issues permission and read access to the contents permission.

### Problems parsing JSON

If you send invalid JSON in the request body, you may receive a `400 Bad Request` response and a "Problems parsing JSON" error message. You can use a linter or JSON validator to help you identify errors in your JSON.

### Body should be a JSON object

If the endpoint expects a JSON object and you do not format your request body as a JSON object, you may receive a `400 Bad Request` response and a "Body should be a JSON object" error message.

### Invalid request

If you omit required parameters or you use the wrong type for a parameter, you may receive a `422 Unprocessable Entity` response and an "Invalid request" error message. For example, you will get this error if you specify a parameter value as an array but the endpoint is expecting a string. You can refer to the reference documentation for the endpoint to verify that you are using the correct parameter types and that you are including all of the required parameters.

### Validation Failed

If your request could not be processed, you may receive a `422 Unprocessable Entity` response and a "Validation Failed" error message. The response body will include an `errors` property, which includes a `code` property to help you diagnose the problem.

| Code             | Description                                                                                                                                       |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `missing`        | A resource does not exist.                                                                                                                        |
| `missing_field`  | A parameter that was required was not specified. Review the documentation for the endpoint to see what parameters are required.                   |
| `invalid`        | The formatting of a parameter is invalid. Review the endpoint documentation for more specific information.                                        |
| `already_exists` | Another resource has the same value as one of your parameters. This can happen in resources that must have some unique key (such as label names). |
| `unprocessable`  | The parameters that were provided were invalid.                                                                                                   |
| `custom`         | Refer to the `message` property to diagnose the error.                                                                                            |

### Not a supported version

You should use the `X-GitHub-Api-Version` header to specify an API version. For example:

```shell
curl --header "X-GitHub-Api-Version:2026-03-10" https://api.github.com/zen
```

If you specify a version that does not exist, you will receive a `400 Bad Request` error and a message about the version not being supported.

For more information, see [API Versions](/en/rest/overview/api-versions).

### User agent required

Requests without a valid `User-Agent` header will be rejected. You should use your username or the name of your application for the `User-Agent` value.

curl sends a valid `User-Agent` header by default.

### Other errors

If you observe an error that is not addressed here, you should refer to the error message that the API gives you. Most error messages will provide a clue about what is wrong and a link to relevant documentation.

If you observe unexpected failures, you can use [githubstatus.com](https://www.githubstatus.com/) or the [GitHub status API](https://www.githubstatus.com/api) to check for incidents affecting the API.

### Further reading

* [Best practices for using the REST API](/en/rest/guides/best-practices-for-using-the-rest-api)
* [Troubleshooting webhooks](/en/webhooks/testing-and-troubleshooting-webhooks/troubleshooting-webhooks)
* [Best practices for creating a GitHub App](/en/apps/creating-github-apps/about-creating-github-apps/best-practices-for-creating-a-github-app)
