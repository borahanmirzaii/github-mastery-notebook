# GitHub Webhooks

> **Source root:** https://docs.github.com/en/webhooks
> **Fetched:** 2026-05-26
> **Area:** 04 — Webhooks

## Table of contents

- [Webhooks (landing / overview)](#webhooks-landing--overview)
- [About webhooks](#about-webhooks)
- [Types of webhooks](#types-of-webhooks)
- [Creating webhooks](#creating-webhooks)
- [Webhook events and payloads](#webhook-events-and-payloads)
- [Validating webhook deliveries](#validating-webhook-deliveries)
- [Handling webhook deliveries](#handling-webhook-deliveries)
- [Redelivering webhooks](#redelivering-webhooks)
- [Best practices for using webhooks](#best-practices-for-using-webhooks)

---

## Webhooks (landing / overview)

> Source: https://docs.github.com/en/webhooks

Webhooks can let your integrations take an action in response to events that occur on GitHub.

### Recommended

- About webhooks
- Creating webhooks
- Handling webhook deliveries
- Best practices for using webhooks
- Webhook events and payloads
- Troubleshooting webhooks

### Getting started

- About webhooks
- Webhook events and payloads

### Articles

- About webhooks
- Types of webhooks
- Webhook events and payloads
- Creating webhooks
- Handling webhook deliveries
- Validating webhook deliveries
- Delivering webhooks to private systems
- Editing webhooks
- Disabling webhooks
- Best practices for using webhooks
- Handling failed webhook deliveries
- Automatically redelivering failed deliveries for a repository webhook
- Automatically redelivering failed deliveries for an organization webhook
- Automatically redelivering failed deliveries for a GitHub App webhook
- Viewing webhook deliveries
- Redelivering webhooks
- Testing webhooks
- Troubleshooting webhooks
- Using the GitHub CLI to forward webhooks for testing

---

## About webhooks

> Source: https://docs.github.com/en/webhooks/about-webhooks

Webhooks provide a way for notifications to be delivered to an external web server whenever certain events occur on GitHub.

### About webhooks

Webhooks let you subscribe to events happening in a software system and automatically receive a delivery of data to your server whenever those events occur.

Rather than repeatedly checking an API, webhooks enable you to express interest in an event a single time during webhook creation. This approach contrasts with polling, which involves periodically calling an API to determine data availability.

Common applications for webhooks include:

- Triggering CI (continuous integration) pipelines on external servers like Jenkins or CircleCI when code gets pushed to a branch
- Sending event notifications to collaboration platforms such as Discord or Slack when pull request reviews occur
- Updating external issue trackers like Jira
- Deploying to production servers
- Recording GitHub events for audit and compliance purposes

### About webhooks on GitHub

When creating a webhook, you designate a URL and select which GitHub events to monitor. When an event that your webhook is subscribed to occurs, GitHub will send an HTTP request with data about the event to the URL that you specified.

Your server can then take appropriate action upon receiving these deliveries. Examples include deploying code, initiating CI pipelines, sending notifications, or creating GitHub projects for new team members.

You must create a webhook within a specific repository, organization, GitHub Marketplace account, GitHub Sponsors account, or GitHub App. Webhooks can only access resources available within their installation scope.

For additional guidance, see documentation on creating webhooks, webhook events and payloads, and handling deliveries.

> [!NOTE]
> GitHub webhooks do not currently support IPv6 but will in the future.

### Choosing webhooks or the REST API

Webhooks offer several advantages over API approaches:

- They require less effort and fewer resources than API polling
- They scale effectively when monitoring numerous resources, avoiding API rate limits
- They provide near real-time updates since triggering occurs when events happen

The API remains appropriate for one-time information requests or small resource sets without scaling needs.

> [!NOTE]
> GitHub Services is retired in favor of webhooks integration.

### Further reading

- Types of webhooks

---

## Types of webhooks

> Source: https://docs.github.com/en/webhooks/types-of-webhooks

You can create webhooks to subscribe to events that occur in a specific repository, organization, GitHub Marketplace account, GitHub Sponsors account, or GitHub App.

### About webhook types

A webhook can only access events that are available in the repository, organization, GitHub Marketplace account, GitHub Sponsors account, or GitHub App where it is installed.

You cannot create webhooks for individual user accounts, or for events that are specific to user resources, like personal notifications or mentions.

To create and manage webhooks, you must own or have admin access to the resource where the webhook is created and listening for events on. For example, to manage webhooks in an organization, you need admin permissions for that organization.

Some webhook events are unique to certain types of webhooks. For example, an organization webhook can subscribe to events that only occur at the organization level, which a repository webhook cannot subscribe to. For more information about the specific availability of each webhook, see [Webhook events and payloads](/en/webhooks/webhook-events-and-payloads).

For more information, see [About webhooks](/en/webhooks/about-webhooks).

### Repository webhooks

You can create webhooks in a repository to subscribe to events that occur in that repository. You must be a repository owner or have admin access in the repository to create and manage webhooks in a repository. You cannot create, edit, or delete webhooks in a repository where you do not have the required permissions.

You can create multiple webhooks in a single repository. However, you can only create up to 20 webhooks that subscribe to each individual event type. For example, in a single repository you could only create up to 20 different webhooks that each subscribe to the `push` event.

You can use the GitHub web interface or the REST API to manage repository webhooks. For more information, see [Creating webhooks](/en/webhooks/using-webhooks/creating-webhooks#creating-a-repository-webhook), [Editing webhooks](/en/webhooks/using-webhooks/editing-webhooks#editing-a-repository-webhook), and [Disabling webhooks](/en/webhooks/using-webhooks/disabling-webhooks#disabling-a-repository-webhook). For more information about using the REST API to manage repository webhooks, see [REST API endpoints for repository webhooks](/en/rest/webhooks).

### Organization webhooks

You can create webhooks in an organization to subscribe to events that occur in that organization. Organization webhooks can subscribe to events that happen in all repositories owned by the organization. They can also subscribe to events that happen at the organization level that are outside of any particular repository, like when a new member is added to the organization.

You must be an organization owner to create and manage webhooks in an organization.

You can create multiple webhooks in a single organization. However, you can only create up to 20 webhooks that subscribe to each individual event type. For example, in a single organization you could only create up to 20 different webhooks that each subscribe to the `push` event.

You can use the GitHub web interface or the REST API to manage organization webhooks. For more information, see [Creating webhooks](/en/webhooks/using-webhooks/creating-webhooks#creating-an-organization-webhook), [Editing webhooks](/en/webhooks/using-webhooks/editing-webhooks#editing-an-organization-webhook), and [Disabling webhooks](/en/webhooks/using-webhooks/disabling-webhooks#disabling-an-organization-webhook). For more information about using the REST API to manage organization webhooks, see [REST API endpoints for organization webhooks](/en/rest/orgs/webhooks).

### GitHub Marketplace webhooks

You can create a webhook to subscribe to events relating to an app that you published in GitHub Marketplace. You can only create one webhook for each app in GitHub Marketplace. Only the owner of the app, or an app manager with access to the app, can create and manage a GitHub Marketplace webhook.

A GitHub Marketplace webhook cannot be deleted, but you can deactivate it to stop receiving webhook deliveries.

You can use the GitHub web interface to manage a GitHub Marketplace webhook. For more information, see [Creating webhooks](/en/webhooks/using-webhooks/creating-webhooks#creating-a-github-marketplace-webhook), [Editing webhooks](/en/webhooks/using-webhooks/editing-webhooks#editing-a-github-marketplace-webhook), and [Disabling webhooks](/en/webhooks/using-webhooks/disabling-webhooks#disabling-a-github-marketplace-webhook).

### GitHub Sponsors webhooks

You can create webhooks to subscribe to events relating to GitHub Sponsors. You can only create up to 20 webhooks for a GitHub Sponsors account.

You must be an account owner or have admin access in the sponsored account to manage sponsorship webhooks.

You can use the GitHub web interface to manage GitHub Sponsors webhooks. For more information, see [Creating webhooks](/en/webhooks/using-webhooks/creating-webhooks#creating-a-github-sponsors-webhook), [Editing webhooks](/en/webhooks/using-webhooks/editing-webhooks#editing-a-github-sponsors-webhook), and [Disabling webhooks](/en/webhooks/using-webhooks/disabling-webhooks#disabling-a-github-sponsors-webhook).

### GitHub App webhooks

You can configure a GitHub App to receive webhooks when specific events occur in a repository or organization that the app has been granted access to.

Each GitHub App has a single webhook that is automatically created by GitHub. By default, the webhook is not subscribed to any events. You can configure the events that the webhook subscribes to. A GitHub App webhook cannot be deleted, but you can deactivate it to stop receiving webhook deliveries.

You can use the GitHub web interface or the REST API to manage a GitHub App webhook. For more information, see [Creating webhooks](/en/webhooks/using-webhooks/creating-webhooks#creating-webhooks-for-a-github-app), [Editing webhooks](/en/webhooks/using-webhooks/editing-webhooks#editing-webhooks-for-a-github-app), and [Disabling webhooks](/en/webhooks/using-webhooks/disabling-webhooks#disabling-webhooks-for-a-github-app). For more information about using the REST API to manage GitHub App webhooks, see [REST API endpoints for GitHub App webhooks](/en/rest/apps/webhooks).

---

## Creating webhooks

> Source: https://docs.github.com/en/webhooks/using-webhooks/creating-webhooks

You can create webhooks to subscribe to specific events that occur on GitHub.

### About creating webhooks

You can create webhooks to subscribe to specific events on GitHub that occur in a repository, organization, GitHub Marketplace account, GitHub Sponsors account, or GitHub App.

For more information about the different types of webhooks, see Types of webhooks.

For a complete list of webhook events, see Webhook events and payloads.

### Creating a repository webhook

You can create a webhook to subscribe to events that occur in a specific repository. You must be a repository owner or have admin access in the repository to create webhooks in that repository.

You can use the GitHub web interface or the REST API to create a repository webhook. For more information about using the REST API to create a repository webhook, see REST API endpoints for repository webhooks.

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click **Settings**. If you cannot see the "Settings" tab, select the dropdown menu, then click **Settings**.
3. In the left sidebar, click **Webhooks**.
4. Click **Add webhook**.
5. Under "Payload URL", type the URL where you'd like to receive payloads.
6. Optionally, select the **Content type** drop-down menu, and click a data format to receive the webhook payload in.
   - **application/json** will deliver the JSON payload directly as the body of the `POST` request.
   - **application/x-www-form-urlencoded** will send the JSON payload as a form parameter called `payload`.
7. Optionally, under "Secret", type a string to use as a `secret` key. You should choose a random string of text with high entropy. You can use the webhook secret to limit incoming requests to only those originating from GitHub. For more information, see Validating webhook deliveries.
8. Under "Which events would you like to trigger this webhook?", select the webhook events that you want to receive. You should only subscribe to the webhook events that you need.
9. If you chose **Let me select individual events**, select the events that you want to trigger the webhook.
10. To make the webhook active immediately after adding the configuration, select **Active**.
11. Click **Add webhook**.

After you create a new webhook, GitHub will send you a simple `ping` event to let you know you've set up the webhook correctly. For more information, see Webhook events and payloads.

### Creating an organization webhook

You can create a webhook to subscribe to events that occur in a specific organization. You must be an organization owner to create webhooks in that organization.

You can use the GitHub web interface or the REST API to create an organization webhook. For more information about using the REST API to create an organization webhook, see REST API endpoints for organization webhooks.

1. In the upper-right corner of any page on GitHub, click your profile picture.
2. Click **Your organizations**.
3. To the right of the organization, click **Settings**.
4. In the left sidebar, click **Webhooks**.
5. Click **Add webhook**.
6. Under "Payload URL", type the URL where you'd like to receive payloads.
7. Optionally, select the **Content type** drop-down menu, and click a data format to receive the webhook payload in.
   - **application/json** will deliver the JSON payload directly as the body of the `POST` request.
   - **application/x-www-form-urlencoded** will send the JSON payload as a form parameter called `payload`.
8. Optionally, under "Secret", type a string to use as a `secret` key. You should choose a random string of text with high entropy. You can use the webhook secret to limit incoming requests to only those originating from GitHub. For more information, see Validating webhook deliveries.
9. Under "Which events would you like to trigger this webhook?", select the types of webhooks you'd like to receive. You should only subscribe to the webhook events that you need.
10. If you chose **Let me select individual events**, select the events that will trigger the webhook.
11. To make the webhook active immediately after adding the configuration, select **Active**.
12. Click **Add webhook**.

After you create a new webhook, GitHub will send you a simple `ping` event to let you know you've set up the webhook correctly. For more information, see Webhook events and payloads.

### Creating a GitHub Marketplace webhook

You can create a webhook to subscribe to events relating to an app that you published in GitHub Marketplace. Only the owner of the app, or an app manager for the app, can create a GitHub Marketplace webhook.

1. Navigate to your GitHub Marketplace listing page.
2. Next to the GitHub Marketplace listing that you want to view webhook deliveries for, click **Manage listing**.
3. In the sidebar, click **Webhook**.
4. Under "Payload URL", type the URL where you'd like to receive payloads.
5. Optionally, select the **Content type** drop-down menu, and click a data format to receive the webhook payload in.
   - **application/json** will deliver the JSON payload directly as the body of the `POST` request.
   - **application/x-www-form-urlencoded** will send the JSON payload as a form parameter called `payload`.
6. Optionally, under "Secret", type a string to use as a `secret` key. You should choose a random string of text with high entropy. You can use the webhook secret to limit incoming requests to only those originating from GitHub. For more information, see Validating webhook deliveries.
7. To make the webhook active immediately after adding the configuration, select **Active**.
8. Click **Create webhook**.

After you create a new webhook, GitHub will send you a simple `ping` event to let you know you've set up the webhook correctly. For more information, see Webhook events and payloads.

### Creating a GitHub Sponsors webhook

You can create a webhook to subscribe to events relating to your sponsorships. Only the owner of the sponsored account can create sponsorship webhooks for that account. For more information about the event that a sponsorship webhook is subscribed to, see the sponsorship webhook event.

1. In the upper-right corner of any page, click your profile picture, then click **Your sponsors**.
2. Next to the account you want to create a webhook for, click **Dashboard**.
3. In the left sidebar, click **Webhooks**.
4. Click **Add webhook**.
5. Under "Payload URL", type the URL where you'd like to receive payloads.
6. Optionally, select the **Content type** drop-down menu, and click a data format to receive the webhook payload in.
   - **application/json** will deliver the JSON payload directly as the body of the `POST` request.
   - **application/x-www-form-urlencoded** will send the JSON payload as a form parameter called `payload`.
7. Optionally, under "Secret", type a string to use as a `secret` key. You should choose a random string of text with high entropy. You can use the webhook secret to limit incoming requests to only those originating from GitHub. For more information, see Validating webhook deliveries.
8. To make the webhook active immediately after adding the configuration, select **Active**.
9. Click **Create webhook**.

### Creating webhooks for a GitHub App

The owner of a GitHub App can subscribe the app to webhook events to receive notifications whenever certain events occur. If the app owner has designated any app managers for a GitHub App, the app managers can also subscribe the app to webhook events. For more information, see Using webhooks with GitHub Apps.

Each GitHub App has one webhook. You can configure the webhook when you register a GitHub App, or you can edit the webhook configuration for an existing GitHub App registration.

For more information about configuring a webhook when you register a GitHub App, see Registering a GitHub App.

To configure a webhook for an existing GitHub App registration:

1. In the upper-right corner of any page on GitHub, click your profile picture.

2. Navigate to your account settings.
   - For an app owned by a personal account, click **Settings**.
   - For an app owned by an organization:
     1. Click **Your organizations**.
     2. To the right of the organization, click **Settings**.

3. In the left sidebar, click **Developer settings**.

4. In the left sidebar, click **GitHub Apps**.

5. Next to the GitHub App that you want to configure the webhook for, click **Edit**.

6. Under "Webhook," select **Active**.

7. Under "Webhook URL", type the URL where you'd like to receive payloads.

8. Optionally, under "Webhook secret", type a string to use as a `secret` key. You should choose a random string of text with high entropy. You can use the webhook secret to limit incoming requests to only those originating from GitHub. For more information, see Validating webhook deliveries.

9. Click **Save changes**.

10. In the sidebar, click **Permissions & events**.

11. The specific webhook events that you can select for your GitHub App registration are determined by the type of permissions you selected for your app. You will first need to select the permissions you would like your app to have, and then you can subscribe your app to webhook events that are related to that set of permissions.

    Under the sections "Repository permissions," "Organization permissions," and "Account permissions," select the permissions that are required for the events your app will subscribe to. For more information, see Choosing permissions for a GitHub App. For more information about things to consider when changing the permissions, see Modifying a GitHub App registration.

12. Under "Subscribe to Events," select the webhook events you would like your GitHub App to receive.

13. Click **Save changes**.

You can also use the REST API to create a webhook for a GitHub App. For more information, see REST API endpoints for GitHub App webhooks.

### Further reading

- About webhooks
- Handling webhook deliveries

---

## Webhook events and payloads

> Source: https://docs.github.com/en/webhooks/webhook-events-and-payloads

### About webhook events and payloads

You can create webhooks that subscribe to the events listed on this page. To limit the number of HTTP requests to your server, you should only subscribe to the specific events that you plan on handling. For more information, see Creating webhooks.

Each webhook event on this page includes a description of the webhook properties for that event. If the event has multiple actions, the properties corresponding to each action are included.

Each event is only available to specific types of webhooks. For example, an organization webhook can subscribe to the `team` event, but a repository webhook cannot. The description of each webhook event lists the availability for that event. For more information, see Types of webhooks.

Payloads are capped at 25 MB. If an event generates a larger payload, GitHub will not deliver a payload for that webhook event. This may happen, for example, if a large number of files are pushed at once or if the payload contains many commits.

### Delivery headers

HTTP POST payloads that are delivered to your webhook's configured URL endpoint will contain several special headers:

- `X-GitHub-Hook-ID`: The unique identifier of the webhook.
- `X-GitHub-Event`: The name of the event that triggered the delivery.
- `X-GitHub-Delivery`: A globally unique identifier (GUID) to identify the event.
- `X-Hub-Signature`: This header is sent if the webhook is configured with a `secret`. This is the HMAC hex digest of the request body, and is generated using the SHA-1 hash function. `X-Hub-Signature` is provided for compatibility with existing integrations. We recommend that you use the more secure `X-Hub-Signature-256` instead.
- `X-Hub-Signature-256`: This header is sent if the webhook is configured with a `secret`. This is the HMAC hex digest of the request body, and is generated using the SHA-256 hash function.
- `User-Agent`: This header will always have the prefix `GitHub-Hookshot/`.
- `X-GitHub-Hook-Installation-Target-Type`: The type of resource where the webhook was created.
- `X-GitHub-Hook-Installation-Target-ID`: The unique identifier of the resource where the webhook was created.

To see what each header might look like in a webhook payload, see Example webhook delivery.

### Webhook payload object common properties

Each webhook payload will have some common properties (regardless of the specific event type), as well as properties specific to that event type.

| Name | Type | Description |
| --- | --- | --- |
| `action` | `string` | **Required.** Most webhook payloads contain an `action` property that contains the specific activity that triggered the event. |
| `enterprise` | `object` | An enterprise on GitHub. Webhook payloads contain the `enterprise` property when the webhook is configured on an enterprise account or an organization that's part of an enterprise account. |
| `installation` | `object` | The GitHub App installation. Webhook payloads contain the `installation` property when the event is configured for and sent to a GitHub App. |
| `organization` | `object` | A GitHub organization. Webhook payloads contain the `organization` property when the webhook is configured for an organization or the event occurs from activity in a repository owned by an organization. |
| `repository` | `object` | The repository on GitHub where the event occurred. Webhook payloads contain the `repository` property when the event occurs from activity in a repository. |
| `sender` | `object` | The GitHub user that triggered the event. This property is included in every webhook payload. |

### Webhook event types covered on this page

(Each event is only available to specific webhook types — repository, organization, GitHub App, business/enterprise, or GitHub Marketplace — and most events list their required permission. See the live page for the full per-event property tables and example payloads.)

```
branch_protection_configuration
branch_protection_rule
check_run
check_suite
code_scanning_alert
commit_comment
create
custom_property
custom_property_values
delete
dependabot_alert
deploy_key
deployment
deployment_protection_rule
deployment_review
deployment_status
discussion
discussion_comment
fork
github_app_authorization
gollum
installation
installation_repositories
installation_target
issue_comment
issue_dependencies
issues
label
marketplace_purchase
member
membership
merge_group
meta
milestone
org_block
organization
package
page_build
personal_access_token_request
ping
project
project_card
project_column
projects_v2
projects_v2_item
projects_v2_status_update
public
pull_request
pull_request_review
pull_request_review_comment
pull_request_review_thread
push
registry_package
release
repository
repository_advisory
repository_dispatch
repository_import
repository_ruleset
repository_vulnerability_alert
secret_scanning_alert
secret_scanning_alert_location
secret_scanning_scan
security_advisory
security_and_analysis
sponsorship
star
status
sub_issues
team
team_add
watch
workflow_dispatch
workflow_job
workflow_run
```

---

## Validating webhook deliveries

> Source: https://docs.github.com/en/webhooks/using-webhooks/validating-webhook-deliveries

You can use a webhook secret to verify that a webhook delivery is from GitHub.

### About validating webhook deliveries

Once your server is configured to receive payloads, it will listen for any delivery that's sent to the endpoint you configured. To ensure that your server only processes webhook deliveries that were sent by GitHub and to ensure that the delivery was not tampered with, you should validate the webhook signature before processing the delivery further. This will help you avoid spending server time to process deliveries that are not from GitHub and will help avoid man-in-the-middle attacks.

To do this, you need to:

1. Create a secret token for a webhook.
2. Store the token securely on your server.
3. Validate incoming webhook payloads against the token, to verify that they are coming from GitHub and were not tampered with.

### Creating a secret token

You can create a new webhook with a secret token, or you can add a secret token to an existing webhook. When creating a secret token, you should choose a random string of text with high entropy.

- *To create a new webhook with a secret token*, see [Creating webhooks](/en/webhooks/using-webhooks/creating-webhooks).
- *To add a secret token to an existing webhook*, edit the webhook's settings. Under "Secret", type a string to use as a `secret` key. For more information, see [Editing webhooks](/en/webhooks/using-webhooks/editing-webhooks).

### Securely storing the secret token

After creating a secret token, you should store it in a secure location that your server can access. Never hardcode a token into an application or push a token to any repository. For more information about how to use authentication credentials securely in your code, see [Keeping your API credentials secure](/en/rest/overview/keeping-your-api-credentials-secure#use-authentication-credentials-securely-in-your-code).

### Validating webhook deliveries

GitHub will use your secret token to create a hash signature that's sent to you with each payload. The hash signature will appear in each delivery as the value of the `X-Hub-Signature-256` header. For more information, see [Webhook events and payloads](/en/webhooks/webhook-events-and-payloads#delivery-headers).

In your code that handles webhook deliveries, you should calculate a hash using your secret token. Then, compare the hash that GitHub sent with the expected hash that you calculated, and ensure that they match. For examples showing how to validate the hashes in various programming languages, see [Examples](#examples).

There are a few important things to keep in mind when validating webhook payloads:

- GitHub uses an HMAC hex digest to compute the hash.
- The hash signature always starts with `sha256=`.
- The hash signature is generated using your webhook's secret token and the payload contents.
- If your language and server implementation specifies a character encoding, ensure that you handle the payload as UTF-8. Webhook payloads can contain unicode characters.
- Never use a plain `==` operator. Instead consider using a method like [`secure_compare`](https://www.rubydoc.info/gems/rack/Rack%2FUtils:secure_compare) or [`crypto.timingSafeEqual`](https://nodejs.org/api/crypto.html#cryptotimingsafeequala-b), which performs a "constant time" string comparison to help mitigate certain timing attacks against regular equality operators, or regular loops in JIT-optimized languages.

#### Testing the webhook payload validation

You can use the following `secret` and `payload` values to verify that your implementation is correct:

- `secret`: `It's a Secret to Everybody`
- `payload`: `Hello, World!`

If your implementation is correct, the signatures that you generate should match the following signature values:

- signature: `757107ea0eb2509fc211221cce984b8a37570b6d7586c22c46f4379c8b043e17`
- X-Hub-Signature-256: `sha256=757107ea0eb2509fc211221cce984b8a37570b6d7586c22c46f4379c8b043e17`

#### Examples

You can use your programming language of choice to implement HMAC verification in your code. Following are some examples showing how an implementation might look in various programming languages.

##### Ruby example

For example, you can define the following `verify_signature` function:

```ruby
def verify_signature(payload_body)
  signature = 'sha256=' + OpenSSL::HMAC.hexdigest(OpenSSL::Digest.new('sha256'), ENV['SECRET_TOKEN'], payload_body)
  return halt 500, "Signatures didn't match!" unless Rack::Utils.secure_compare(signature, request.env['HTTP_X_HUB_SIGNATURE_256'])
end
```

Then you can call it when you receive a webhook payload:

```ruby
post '/payload' do
  request.body.rewind
  payload_body = request.body.read
  verify_signature(payload_body)
  push = JSON.parse(payload_body)
  "I got some JSON: #{push.inspect}"
end
```

##### Python example

For example, you can define the following `verify_signature` function and call it when you receive a webhook payload:

```python
import hashlib
import hmac
def verify_signature(payload_body, secret_token, signature_header):
    """Verify that the payload was sent from GitHub by validating SHA256.

    Raise and return 403 if not authorized.

    Args:
        payload_body: original request body to verify (request.body())
        secret_token: GitHub app webhook token (WEBHOOK_SECRET)
        signature_header: header received from GitHub (x-hub-signature-256)
    """
    if not signature_header:
        raise HTTPException(status_code=403, detail="x-hub-signature-256 header is missing!")
    hash_object = hmac.new(secret_token.encode('utf-8'), msg=payload_body, digestmod=hashlib.sha256)
    expected_signature = "sha256=" + hash_object.hexdigest()
    if not hmac.compare_digest(expected_signature, signature_header):
        raise HTTPException(status_code=403, detail="Request signatures didn't match!")
```

##### JavaScript example

For example, you can define the following `verifySignature` function and call it in any JavaScript environment when you receive a webhook payload:

```javascript
let encoder = new TextEncoder();

async function verifySignature(secret, header, payload) {
    let parts = header.split("=");
    let sigHex = parts[1];

    let algorithm = { name: "HMAC", hash: { name: 'SHA-256' } };

    let keyBytes = encoder.encode(secret);
    let extractable = false;
    let key = await crypto.subtle.importKey(
        "raw",
        keyBytes,
        algorithm,
        extractable,
        [ "sign", "verify" ],
    );

    let sigBytes = hexToBytes(sigHex);
    let dataBytes = encoder.encode(payload);
    let equal = await crypto.subtle.verify(
        algorithm.name,
        key,
        sigBytes,
        dataBytes,
    );

    return equal;
}

function hexToBytes(hex) {
    let len = hex.length / 2;
    let bytes = new Uint8Array(len);

    let index = 0;
    for (let i = 0; i < hex.length; i += 2) {
        let c = hex.slice(i, i + 2);
        let b = parseInt(c, 16);
        bytes[index] = b;
        index += 1;
    }

    return bytes;
}
```

##### TypeScript example

For example, you can define the following `verify_signature` function and call it when you receive a webhook payload:

```javascript
import { Webhooks } from "@octokit/webhooks";

const webhooks = new Webhooks({
  secret: process.env.WEBHOOK_SECRET,
});

const handleWebhook = async (req, res) => {
  const signature = req.headers["x-hub-signature-256"];
  const body = await req.text();

  if (!(await webhooks.verify(body, signature))) {
    res.status(401).send("Unauthorized");
    return;
  }

  // The rest of your logic here
};
```

### Troubleshooting

If you are sure that the payload is from GitHub but the signature verification fails:

- Make sure that you have configured a secret for your webhook. The `X-Hub-Signature-256` header will not be present if you have not configured a secret for your webhook. For more information about configuring a secret for your webhook, see [Editing webhooks](/en/webhooks/using-webhooks/editing-webhooks).
- Make sure you are using the correct header. GitHub recommends that you use the `X-Hub-Signature-256` header, which uses the HMAC-SHA256 algorithm. The `X-Hub-Signature` header uses the HMAC-SHA1 algorithm and is only included for legacy purposes.
- Make sure that you are using the correct algorithm. If you are using the `X-Hub-Signature-256` header, you should use the HMAC-SHA256 algorithm.
- Make sure you are using the correct webhook secret. If you don't know the value of your webhook secret, you can update your webhook's secret. For more information, see [Editing webhooks](/en/webhooks/using-webhooks/editing-webhooks).
- Make sure that the payload and headers are not modified before verification. For example, if you use a proxy or load balancer, make sure that the proxy or load balancer does not modify the payload or headers.
- If your language and server implementation specifies a character encoding, ensure that you handle the payload as UTF-8. Webhook payloads can contain unicode characters.

### Further reading

- [Handling webhook deliveries](/en/webhooks/using-webhooks/handling-webhook-deliveries)
- [Best practices for using webhooks](/en/webhooks/using-webhooks/best-practices-for-using-webhooks)

---

## Handling webhook deliveries

> Source: https://docs.github.com/en/webhooks/using-webhooks/handling-webhook-deliveries

Learn how to write code to listen for and respond to webhook deliveries.

### Introduction

When you create a webhook, you specify a URL and subscribe to event types. When an event that your webhook is subscribed to occurs, GitHub will send an HTTP request with data about the event to the URL that you specified. If your server is set up to listen for webhook deliveries at that URL, it can take action when it receives one.

This article describes how to write code to let your server listen for and respond to webhook deliveries. You will test your code by using your computer or codespace as a local server.

### Setup

In order to test your webhook locally, you can use a webhook proxy URL to forward webhooks from GitHub to your computer or codespace. This article uses smee.io to provide a webhook proxy URL and forward webhooks.

#### Get a webhook proxy URL

1. In your browser, navigate to <https://smee.io/>.
2. Click **Start a new channel**.
3. Copy the full URL under "Webhook Proxy URL". You will use this URL in the following setup steps.

#### Forward webhooks

1. If you don't already have [smee-client](https://www.npmjs.com/package/smee-client) installed, run the following command in your terminal:

   ```shell
   npm install --global smee-client
   ```

2. To receive forwarded webhooks from smee.io, run the following command in your terminal. Replace `WEBHOOK_PROXY_URL` with your webhook proxy URL from earlier.

   ```shell
   smee --url WEBHOOK_PROXY_URL --path /webhook --port 3000
   ```

   You should see output that looks like this, where `WEBHOOK_PROXY_URL` is your webhook proxy URL:

   ```shell
   Forwarding WEBHOOK_PROXY_URL to http://127.0.0.1:3000/webhook
   Connected WEBHOOK_PROXY_URL
   ```

   Note that the path is `/webhook` and the port is `3000`. You will use these values later when you write code to handle webhook deliveries.

3. Keep this running while you test out your webhook. When you want to stop forwarding webhooks, enter <kbd>Ctrl</kbd>+<kbd>C</kbd>.

#### Create a webhook

1. Create a webhook with the following settings. For more information, see [Creating webhooks](/en/webhooks/using-webhooks/creating-webhooks).

   - For the URL, use your webhook proxy URL from earlier.
   - If you have an option to choose the content type, use JSON.

### Write code to handle webhook deliveries

In order to handle webhook deliveries, you need to write code that will:

- Initialize your server to listen for requests to your webhook URL
- Read the HTTP headers and body from the request
- Take the desired action in response to the request

You can use any programming language that you can run on your server.

The following examples print a message when a webhook delivery is received. However, you can modify the code to take another action, such as making a request to the GitHub API or sending a Slack message.

- [Ruby example](#ruby-example)
- [JavaScript example](#javascript-example)

#### Ruby example

This example uses the Ruby gem, Sinatra, to define routes and handle HTTP requests. For more information, see [the Sinatra README](https://github.com/sinatra/sinatra#readme).

##### Ruby example: Install dependencies

To use this example, you must install the sinatra gem in your Ruby project. For example, you can do this with [Bundler](https://bundler.io/):

1. If you don't already have Bundler installed, run the following command in your terminal:

   ```shell
   gem install bundler
   ```

2. If you don't already have a Gemfile for your app, run the following command in your terminal:

   ```shell
   bundle init
   ```

3. If you don't already have a Gemfile.lock for your app, run the following command in your terminal:

   ```shell
   bundle install
   ```

4. Install the Sinatra gem by running the following command in your terminal:

   ```shell
   bundle add sinatra
   ```

##### Ruby example: Write the code

Create a Ruby file with the following contents. Modify the code to handle the event types that your webhook is subscribed to, as well as the `ping` event that GitHub sends when you create a webhook. This example handles the `issues` and `ping` events.

```ruby
# These are the dependencies for this code. You installed the `sinatra` gem earlier. For more information, see [Ruby example: Install dependencies](#ruby-example-install-dependencies). The `json` library is a standard Ruby library, so you don't need to install it.
require 'sinatra'
require 'json'

# The `/webhook` route matches the path that you specified for the smee.io forwarding. For more information, see [Forward webhooks](#forward-webhooks).
#
# Once you deploy your code to a server and update your webhook URL, you should change this to match the path portion of the URL for your webhook.
post '/webhook' do

  # Respond to indicate that the delivery was successfully received.
  # Your server should respond with a 2XX response within 10 seconds of receiving a webhook delivery. If your server takes longer than that to respond, then GitHub terminates the connection and considers the delivery a failure.
  status 202

  # Check the `X-GitHub-Event` header to learn what event type was sent.
  # Sinatra changes `X-GitHub-Event` to `HTTP_X_GITHUB_EVENT`.
  github_event = request.env['HTTP_X_GITHUB_EVENT']

  # You should add logic to handle each event type that your webhook is subscribed to.
  # For example, this code handles the `issues` and `ping` events.
  #
  # If any events have an `action` field, you should also add logic to handle each action that you are interested in.
  # For example, this code handles the `opened` and `closed` actions for the `issue` event.
  #
  # For more information about the data that you can expect for each event type, see [AUTOTITLE](/webhooks/webhook-events-and-payloads).
  if github_event == "issues"
    data = JSON.parse(request.body.read)
    action = data['action']
    if action == "opened"
      puts "An issue was opened with this title: #{data['issue']['title']}"
    elsif action == "closed"
      puts "An issue was closed by #{data['issue']['user']['login']}"
    else
      puts "Unhandled action for the issue event: #{action}"
    end
  elsif github_event == "ping"
    puts "GitHub sent the ping event"
  else
    puts "Unhandled event: #{github_event}"
  end
end
```

##### Ruby example: Test the code

To test your webhook, you can use your computer or codespace to act as a local server. If you have trouble with these steps, see [Troubleshooting](#troubleshooting).

1. Make sure that you are forwarding webhooks. If you are no longer forwarding webhooks, follow the steps in [Forward webhooks](#forward-webhooks) again.

2. In a separate terminal window, run the following command to start a local server on your computer or codespace. Replace `FILE_PATH` with the path to the file where your code from the previous section is stored. Note that `PORT=3000` matches the port that you specified for the webhook forwarding in the previous step.

   ```shell
   PORT=3000 ruby FILE_NAME
   ```

   You should see output that indicates something like "Sinatra has taken the stage on 3000".

3. Trigger your webhook. For example, if you created a repository webhook that is subscribed to the `issues` event, open an issue in your repository. You can also redeliver a previous webhook delivery. For more information, see [Redelivering webhooks](/en/webhooks/testing-and-troubleshooting-webhooks/redelivering-webhooks).

4. Navigate to your webhook proxy URL on smee.io. You should see an event that corresponds to the event that you triggered or redelivered. This indicates that GitHub successfully sent a webhook delivery to the payload URL that you specified.

5. In the terminal window where you ran `smee --url WEBHOOK_PROXY_URL --path /webhook --port 3000`, you should see something like `POST http://127.0.0.1:3000/webhook - 202`. This indicates that smee successfully forwarded your webhook to your local server.

6. In the terminal window where you ran `PORT=3000 ruby FILE_NAME`, you should see a message corresponding to the event that was sent. For example, if you use the example code from above and you redelivered the `ping` event, you should see "GitHub sent the ping event". You may also see some other lines that Sinatra automatically prints.

7. In both terminal windows, enter <kbd>Ctrl</kbd>+<kbd>C</kbd> to stop your local server and stop listening for forwarded webhooks.

Now that you have tested out your code locally, you can make changes to use your webhook in production. For more information, see [Next steps](#next-steps). If you had trouble testing your code, try the steps in [Troubleshooting](#troubleshooting).

#### JavaScript example

This example uses Node.js and the Express library to define routes and handle HTTP requests. For more information, see [expressjs.com](https://expressjs.com).

For an example that uses GitHub's Octokit.js SDK, see [Building a GitHub App that responds to webhook events](/en/apps/creating-github-apps/writing-code-for-a-github-app/building-a-github-app-that-responds-to-webhook-events).

This example requires your computer or codespace to run Node.js version 12 or greater and npm version 6.12.0 or greater. For more information, see [Node.js](https://nodejs.org).

##### JavaScript example: Install dependencies

To use this example, you must install the `express` library in your Node.js project. For example:

```shell
npm install express
```

##### JavaScript example: Write the code

Create a JavaScript file with the following contents. Modify the code to handle the event types that your webhook is subscribed to, as well as the `ping` event that GitHub sends when you create a webhook. This example handles the `issues` and `ping` events.

```javascript
// You installed the `express` library earlier. For more information, see [JavaScript example: Install dependencies](#javascript-example-install-dependencies).
const express = require('express');

// This initializes a new Express application.
const app = express();

// This defines a POST route at the `/webhook` path. This path matches the path that you specified for the smee.io forwarding. For more information, see [Forward webhooks](#forward-webhooks).
//
// Once you deploy your code to a server and update your webhook URL, you should change this to match the path portion of the URL for your webhook.
app.post('/webhook', express.json({type: 'application/json'}), (request, response) => {

  // Respond to indicate that the delivery was successfully received.
  // Your server should respond with a 2XX response within 10 seconds of receiving a webhook delivery. If your server takes longer than that to respond, then GitHub terminates the connection and considers the delivery a failure.
  response.status(202).send('Accepted');

  // Check the `x-github-event` header to learn what event type was sent.
  const githubEvent = request.headers['x-github-event'];

  // You should add logic to handle each event type that your webhook is subscribed to.
  // For example, this code handles the `issues` and `ping` events.
  //
  // If any events have an `action` field, you should also add logic to handle each action that you are interested in.
  // For example, this code handles the `opened` and `closed` actions for the `issue` event.
  //
  // For more information about the data that you can expect for each event type, see [AUTOTITLE](/webhooks/webhook-events-and-payloads).
  if (githubEvent === 'issues') {
    const data = request.body;
    const action = data.action;
    if (action === 'opened') {
      console.log(`An issue was opened with this title: ${data.issue.title}`);
    } else if (action === 'closed') {
      console.log(`An issue was closed by ${data.issue.user.login}`);
    } else {
      console.log(`Unhandled action for the issue event: ${action}`);
    }
  } else if (githubEvent === 'ping') {
    console.log('GitHub sent the ping event');
  } else {
    console.log(`Unhandled event: ${githubEvent}`);
  }
});

// This defines the port where your server should listen.
// 3000 matches the port that you specified for webhook forwarding. For more information, see [Forward webhooks](#forward-webhooks).
//
// Once you deploy your code to a server, you should change this to match the port where your server is listening.
const port = 3000;

// This starts the server and tells it to listen at the specified port.
app.listen(port, () => {
  console.log(`Server is running on port ${port}`);
});
```

##### JavaScript example: Test the code

To test your webhook, you can use your computer or codespace to act as a local server. If you have trouble with these steps, see [Troubleshooting](#troubleshooting).

1. Make sure that you are forwarding webhooks. If you are no longer forwarding webhooks, follow the steps in [Forward webhooks](#forward-webhooks) again.

2. In a separate terminal window, run the following command to start a local server on your computer or codespace. Replace `FILE_PATH` with the path to the file where your code from the previous section is stored.

   ```shell
   node FILE_NAME
   ```

   You should see output that says `Server is running on port 3000`.

3. Trigger your webhook. For example, if you created a repository webhook that is subscribed to the `issues` event, open an issue in your repository. You can also redeliver a previous webhook delivery. For more information, see [Redelivering webhooks](/en/webhooks/testing-and-troubleshooting-webhooks/redelivering-webhooks).

4. Navigate to your webhook proxy URL on smee.io. You should see an event that corresponds to the event that you triggered or redelivered. This indicates that GitHub successfully sent a webhook delivery to the payload URL that you specified.

5. In the terminal window where you ran `smee --url WEBHOOK_PROXY_URL --path /webhook --port 3000`, you should see something like `POST http://127.0.0.1:3000/webhook - 202`. This indicates that smee successfully forwarded your webhook to your local server.

6. In the terminal window where you ran `node FILE_NAME`, you should see a message corresponding to the event that was sent. For example, if you use the example code from above and you redelivered the `ping` event, you should see "GitHub sent the ping event".

7. In both terminal windows, enter <kbd>Ctrl</kbd>+<kbd>C</kbd> to stop your local server and stop listening for forwarded webhooks.

Now that you have tested out your code locally, you can make changes to use your webhook in production. For more information, see [Next steps](#next-steps). If you had trouble testing your code, try the steps in [Troubleshooting](#troubleshooting).

### Troubleshooting

If you don't see the expected results described in the testing steps, try the following:

- Make sure that your webhook is using your webhook proxy URL (Smee.io URL). For more information about your webhook proxy URL, see [Get a webhook proxy URL](#get-a-webhook-proxy-url). For more information about your webhook settings, see [Creating webhooks](/en/webhooks/using-webhooks/creating-webhooks).
- Make sure that your webhook uses the JSON content type, if you have a choice about what content type to use. For more information about your webhook settings, see [Creating webhooks](/en/webhooks/using-webhooks/creating-webhooks).
- Make sure that both the smee client and your local server are running. You will have these processes running in two separate terminal windows.
- Make sure that your server is listening to the same port where smee.io is forwarding webhooks. All of the examples in this article use port 3000.
- Make sure that the path where smee.io is forwarding webhooks matches a route that is defined in your code. All of the examples in this article use the `/webhook` path.
- Check for error messages in the terminal windows where you are running the smee client and your local server.
- Check GitHub to verify that a webhook delivery was triggered. For more information, see [Viewing webhook deliveries](/en/webhooks/testing-and-troubleshooting-webhooks/viewing-webhook-deliveries).
- Check your webhook proxy URL on smee.io. You should see an event that corresponds to the event that you triggered or redelivered. This indicates that GitHub successfully sent a webhook delivery to the payload URL that you specified.

### Next steps

This article demonstrated how to write code to handle webhook deliveries. It also demonstrated how to test your code by using your computer or codespace as a local server and by forwarding webhook deliveries from GitHub to your local server via smee.io. Once you are done testing your code, you might want to modify the code and deploy your code to a server.

#### Modify the code

This article gave basic examples that print a message when a webhook delivery is received. You may want to modify the code to take some other action. For example, you could modify the code to:

- Make a request to the GitHub API
- Send a message on Slack
- Log events
- Update an external project management tool

#### Verify that the delivery is from GitHub

In your code that handles webhook deliveries, you should validate that the delivery is from GitHub before processing the delivery further. For more information, see [Validating webhook deliveries](/en/webhooks/using-webhooks/securing-your-webhooks).

#### Deploy your code to a server

This article demonstrated how to use your computer or codespace as a server while you develop your code. Once the code is ready for production use, you should deploy your code to a dedicated server.

When you do so, you may need to update your code to reflect the host and port where your server is listening.

#### Update the webhook URL

Once you have a server that is set up to receive webhook traffic from GitHub, update the URL in your webhook settings. You may need to update the route that your code handles to match the path portion of the new URL. For example, if your new webhook URL is `https://example.com/github-webhooks`, you should change the route in these examples from `/webhook` to `/github-webhooks`.

You should not use smee.io to forward your webhooks in production.

#### Follow best practices

You should aim to follow best practices with your webhooks. For more information, see [Best practices for using webhooks](/en/webhooks/using-webhooks/best-practices-for-using-webhooks).

### Further reading

- [Building a GitHub App that responds to webhook events](/en/apps/creating-github-apps/writing-code-for-a-github-app/building-a-github-app-that-responds-to-webhook-events)
- [Best practices for using webhooks](/en/webhooks/using-webhooks/best-practices-for-using-webhooks)

---

## Redelivering webhooks

> Source: https://docs.github.com/en/webhooks/testing-and-troubleshooting-webhooks/redelivering-webhooks

You can redeliver webhooks that occurred in the past 3 days. You may want to redeliver a webhook to help you test your application or to recover from server downtime.

GitHub does not automatically redeliver failed deliveries. If your server goes down, you should redeliver missed webhooks once your server is back up.

### Redelivering repository webhooks

Only people with admin access to a repository can redeliver webhooks in that repository.

You can use the GitHub web interface or the REST API to redeliver webhooks for a repository. For more information about using the REST API to redeliver webhooks, see [REST API endpoints for repository webhooks](/en/rest/webhooks/repo-deliveries).

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click **Settings**. If you cannot see the "Settings" tab, select the dropdown menu, then click **Settings**.
3. In the "Code and automation" section of the sidebar, click **Webhooks**.
4. In the list of webhooks, click the URL of the webhook you'd like to redeliver. If you do not have a webhook configured, no webhooks will be listed.
5. Click **Recent deliveries**. All deliveries from the past 3 days will be listed. If this webhook has not been delivered within the past 3 days, no deliveries will be listed.
6. Click the delivery GUID for the delivery that you want to redeliver.
7. Click **Redeliver**.

### Redelivering organization webhooks

Only organization owners can redeliver webhooks in that organization. The steps mirror the repository process, beginning from the organization's settings and locating **Webhooks** in the "Code and automation" section of the sidebar, then selecting the webhook URL, clicking **Recent deliveries**, choosing the delivery GUID, and clicking **Redeliver**.

### Redelivering GitHub App webhooks

The GitHub App owner or designated app managers can redeliver webhooks for a GitHub App.

1. In the upper-right corner of any page on GitHub, click your profile picture.
2. Navigate to your account settings. For an app owned by a personal account, click **Settings**. For an app owned by an organization: Click **Your organizations**. To the right of the organization, click **Settings**.
3. In the left sidebar, click **Developer settings**.
4. In the left sidebar, click **GitHub Apps**.
5. Next to the GitHub App that you want to redeliver a webhook for, click **Edit**.
6. In the sidebar, click **Advanced**.
7. Under "Recent deliveries", all deliveries from the past 3 days will be listed. Click the delivery GUID for the delivery that you want to redeliver.
8. Click **Redeliver**.

### Redelivering GitHub Marketplace webhooks

App owners and managers redeliver Marketplace webhooks by accessing the GitHub Marketplace listing page, managing the listing, selecting the **Webhook** section, locating the delivery GUID under "Recent deliveries", and clicking **Redeliver** for the chosen delivery.

### Redelivering GitHub Sponsors webhooks

Only sponsored account owners can redeliver sponsorship webhooks. From the Sponsors dashboard, access the **Webhooks** section, select the webhook URL, locate the delivery GUID under "Recent deliveries", and click **Redeliver**.

---

## Best practices for using webhooks

> Source: https://docs.github.com/en/webhooks/using-webhooks/best-practices-for-using-webhooks

Follow these best practices to improve security and performance when using webhooks.

### Subscribe to the minimum number of events

You should only subscribe to the webhook events that you need. This will reduce the amount of work your server needs to do. For more information about subscribing to events, see [Creating webhooks](/en/webhooks/creating-webhooks) and [Editing webhooks](/en/webhooks/using-webhooks/editing-webhooks).

### Use a webhook secret

> [!WARNING]
> To avoid accidental exposure of sensitive information, do **not** include sensitive information in your payload URL.
> This includes your own API keys and other authentication credentials. Instead, to validate that webhook deliveries were sent by GitHub and have not been tampered with, use a webhook secret. For more information, see [Validating webhook deliveries](/en/webhooks/using-webhooks/validating-webhook-deliveries).

The webhook secret should be a random string of text with high entropy. You should securely store your webhook secret in a way that your server can access.

### Use HTTPS and SSL verification

You should ensure that your server uses an HTTPS connection. By default, GitHub will verify SSL certificates when delivering webhooks. GitHub recommends that you leave SSL verification enabled.

### Allow GitHub's IP addresses

You can set up an IP allow list for your server, and add the IP addresses that GitHub uses for webhook deliveries. This can block spoofed requests to your server.

You can use the `GET /meta` endpoint to find the current list of GitHub's IP addresses. For more information, see [REST API endpoints for meta data](/en/rest/meta/meta#get-github-meta-information). GitHub occasionally makes changes to its IP addresses, so you should update your IP allow list periodically.

For more information, see [About GitHub's IP addresses](/en/authentication/keeping-your-account-and-data-secure/about-githubs-ip-addresses).

### Respond within 10 seconds

Your server should respond with a 2XX response within 10 seconds of receiving a webhook delivery. If your server takes longer than that to respond, then GitHub terminates the connection and considers the delivery a failure.

In order to respond in a timely manner, you may want to set up a queue to process webhook payloads asynchronously. Your server can respond when it receives the webhook, and then process the payload in the background without blocking future webhook deliveries. For example, you can use services like [Hookdeck](https://hookdeck.com) or libraries like [Resque](https://github.com/resque/resque/) (Ruby), [RQ](http://python-rq.org/) (Python), or [RabbitMQ](http://www.rabbitmq.com/) (Java).

### Check the event type and action before processing the event

There are multiple webhook event types, and many events can have multiple action types. GitHub continues to add new event types and new actions to existing event types. Your application should check the event type and action of a webhook payload before processing the payload. To determine the event type, you can use the `X-GitHub-Event` request header. To determine the action type, you can use the top-level `action` key in the event payload.

### Redeliver missed deliveries

If your server goes down, you should redeliver missed webhooks once your server is back up. For more information, see [Redelivering webhooks](/en/webhooks/testing-and-troubleshooting-webhooks/redelivering-webhooks).

### Use the `X-GitHub-Delivery` header

In a replay attack, a bad actor intercepts a webhook delivery and re-sends the delivery. To protect against replay attacks, you can use the `X-GitHub-Delivery` header to ensure that each delivery is unique per event.

> [!NOTE]
> If you request a redelivery, the `X-GitHub-Delivery` header will be the same as in the original delivery.

### Further reading

- [Best practices for using the REST API](/en/rest/guides/best-practices-for-integrators)
- [Best practices for creating a GitHub App](/en/apps/creating-github-apps/about-creating-github-apps/best-practices-for-creating-a-github-app)
