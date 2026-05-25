# GitHub Apps

> **Source root:** https://docs.github.com/en/apps
> **Fetched:** 2026-05-26
> **Area:** 01 — Apps

## Table of contents

- [GitHub Apps overview](#github-apps-overview)
- [About creating GitHub Apps](#about-creating-github-apps)
- [Registering a GitHub App](#registering-a-github-app)
- [About authentication with a GitHub App](#about-authentication-with-a-github-app)
- [Generating a JSON Web Token (JWT) for a GitHub App](#generating-a-json-web-token-jwt-for-a-github-app)
- [Authenticating as a GitHub App installation](#authenticating-as-a-github-app-installation)
- [Choosing permissions for a GitHub App](#choosing-permissions-for-a-github-app)
- [Deciding when to build a GitHub App](#deciding-when-to-build-a-github-app)
- [Differences between GitHub Apps and OAuth apps](#differences-between-github-apps-and-oauth-apps)

> **Note on the landing page** (`https://docs.github.com/en/apps`): this URL is a navigation hub / table-of-contents page with no standalone prose body — it links out to the sections reproduced below (Getting started, Creating GitHub Apps, Using GitHub Apps, GitHub Marketplace, OAuth apps, Maintaining GitHub Apps). All substantive content lives on the sub-pages captured in this file.

---

## GitHub Apps overview

> Source: https://docs.github.com/en/apps/overview

You can use GitHub Apps to extend the functionality of GitHub.

### About GitHub Apps

GitHub Apps are tools that extend GitHub's functionality. GitHub Apps can do things on GitHub like open issues, comment on pull requests, and manage projects. They can also do things outside of GitHub based on events that happen on GitHub. For example, a GitHub App can post on Slack when an issue is opened on GitHub.

For more information about how to use GitHub Apps, see "Using GitHub Apps."

For more information about how to build GitHub Apps, see "Creating GitHub Apps."

### GitHub Apps and OAuth apps

GitHub supports two types of apps: GitHub Apps and OAuth apps. In general, GitHub Apps are preferred to OAuth apps because they use fine-grained permissions, give the user more control over which repositories the app can access, and use short-lived tokens. These properties can harden the security of your app by limiting the damage that could be done if your app's credentials were leaked.

For more information about the differences between GitHub Apps and OAuth apps, see "Differences between GitHub Apps and OAuth apps."

---

## About creating GitHub Apps

> Source: https://docs.github.com/en/apps/creating-github-apps/about-creating-github-apps/about-creating-github-apps

GitHub Apps let you build integrations to automate processes and extend GitHub's functionality.

### About GitHub Apps

A GitHub App is a type of integration that you can build to interact with and extend the functionality of GitHub. You can build a GitHub App to provide flexibility and reduce friction in your processes, without needing to sign in a user or create a service account.

Common use cases for GitHub Apps include:

* Automating tasks or background processes
* Supporting "Sign in with GitHub," which allows users to sign in with their GitHub account to provide their identity in your ecosystem
* As a developer tool, allowing users to work with GitHub by signing into your GitHub App, which can then act on their behalf
* Integrating your tool or external service with GitHub

Like OAuth apps, GitHub Apps use OAuth 2.0 and can act on behalf of a user. Unlike OAuth apps, GitHub Apps can also act independently of a user.

GitHub Apps can be installed directly on organizations and personal accounts and granted access to specific repositories. They come with built-in webhooks and narrow, specific permissions.

By default, only organization owners can manage the settings of GitHub Apps in an organization. To allow additional users to change the developer settings of GitHub Apps owned by the organization, an owner can grant them GitHub App manager permissions. GitHub App Managers can't manage third-party applications. For more information about adding and removing GitHub App managers in your organization, see "Roles in an organization."

### Building a GitHub App

In order to build a GitHub App, you first need to register a GitHub App. For more information, see "Registering a GitHub App."

Then, you need to write code to add functionality to your GitHub App. You can use the credentials from your GitHub App registration to make authenticated requests to GitHub's APIs. For more information about writing code for your GitHub App, see "About writing code for a GitHub App." For more information about making authenticated requests, see "About authentication with a GitHub App."

Once you have written the code for your GitHub App, your app needs to run somewhere. If your app is a website or web app, you might host your app on a server like Azure App Service. If your app is a client-side app, it might run on a user's device.

To use your GitHub App, you need to install it on your organization or personal account.

* If your GitHub App is **private**, you can only install it on the account that owns the app.
* If your GitHub App is **public**, other accounts can also install it. Only members of the enterprise can sign in to it.

For more information, see "Installing your own GitHub App" and "Sharing your GitHub App."

### Understanding what type of GitHub App to build

There are multiple ways to design a GitHub App that you will want to consider, based on the functionality you want the app to have.

#### GitHub Apps that act on behalf of a user

If you want your app to take actions on behalf of a user, you should use a user access token for authentication. This type of request is sometimes called "user-to-server," and it means that the app will be limited by the permissions that have been given to the app as well as the user's permission. With this pattern, the user must authorize the app before the app can take action. For more information, see "Authenticating with a GitHub App on behalf of a user."

Some examples of automations you could create with a GitHub App, where the app acts on a user's behalf, include:

* A GitHub App that uses GitHub as an identity provider for your ecosystem.
* A GitHub App that adds a service on top of GitHub that might be useful to a GitHub user. You can share the app with other developers via GitHub Marketplace or by making the app public.

#### GitHub Apps that act on their own behalf

If you want your app to take actions on behalf of itself, rather than a user, you should use an installation access token for authentication. This type of request is sometimes called "server-to-server," and it means that the app will be limited by the permissions that have been given to the app. For more information, see "Authenticating as a GitHub App installation."

Some examples of automations you could create with a GitHub App, where the app acts on its own behalf, include:

* A GitHub App that uses webhooks to react to an event given a certain set of criteria. For example, you could create an automation around the REST API endpoints for reviewing requests for fine-grained personal access token that approves a request given a certain policy.
* A GitHub App that helps repository contributors. For example, the app could post helpful resources after a contributor creates a pull request or makes a comment.
* A GitHub App that generates short-lived tokens to give to other CI/CD tools, or to pull information from a repository.

#### GitHub Apps that respond to webhooks

If you want your app to respond to events on GitHub, your app should subscribe to webhooks. For example, you may want your app to leave a comment when a pull request is opened. For more information, see "Using webhooks with GitHub Apps."

#### GitHub Apps that can take certain actions

When you set up your GitHub App, you can select specific permissions for the app. These permissions determine what the app can do via the GitHub API, what they can do on behalf of a signed in user, and what webhooks the app can receive. For more information, see "Choosing permissions for a GitHub App."

---

## Registering a GitHub App

> Source: https://docs.github.com/en/apps/creating-github-apps/registering-a-github-app/registering-a-github-app

You can register a GitHub App under your personal account or under any organization you own.

### About registering GitHub Apps

You can register a GitHub App in a few different ways.

* Under your **personal account**.
* Under an **organization you own**.
* Under an **organization** that has granted you permission to manage all its apps. See "Adding and removing GitHub App managers in your organization."

A user or organization can register up to 100 GitHub Apps, but there is no limit to how many GitHub Apps can be installed on an account.

### Registering a GitHub App

1. In the upper-right corner of any page on GitHub, click your profile picture.

2. Navigate to your account settings.
   * For an app owned by a personal account, click **Settings**.
   * For an app owned by an organization:
     1. Click **Your organizations**.
     2. To the right of the organization, click **Settings**.

3. In the left sidebar, click **Developer settings**.

4. In the left sidebar, click **GitHub Apps**.

5. Click **New GitHub App**.

6. Under "GitHub App name", enter a name for your app. You should choose a clear and short name. The name cannot be longer than 34 characters. Your app's name (converted to lowercase, with spaces replaced by `-`, and with special characters replaced) will be shown in the user interface when your app takes an action. For example, `My APp Näme` would display as `my-app-name`.

   The name must be unique across GitHub. You cannot use the same name as an existing GitHub account, unless it is your own user or organization name.

7. Optionally, under "Description", type a description of your app. Users will see this description when they install your app.

8. Under "Homepage URL", type the full URL to your app's website. If you don't have a dedicated URL and your app's code is stored in a public repository, you can use that repository URL. Or, you can use the URL of the account that owns the app.

9. Optionally, under "Callback URL", enter the full URL to redirect to after a user authorizes the installation.

   You can enter up to 10 callback URLs. To add additional callback URLs, click **Add callback URL**.

   If your app does not need to act on behalf of a user (does not need to generate a user access token), this field will be ignored. If your app uses device flow instead of web application flow to generate a user access token, this field will be ignored.

   For more information about the callback URL, see "About the user authorization callback URL." For more information about generating a user access token to act on behalf of a user, see "Authenticating with a GitHub App on behalf of a user" and "Generating a user access token for a GitHub App."

10. Optionally, to prevent user access tokens from expiring, deselect **Expire user authorization tokens**. GitHub strongly recommends that you leave this option selected. For more information about refreshing expired tokens and the benefits of user access tokens that expire, see "Refreshing user access tokens." If your app does not need to generate a user access token, this field will be ignored.

11. Optionally, to prompt users to authorize your app when they install it, select **Request user authorization (OAuth) during installation**. If a user authorizes your app, your app can generate a user access token to make API requests on the user's behalf and attribute app activity to the user. For more information, see "Authenticating with a GitHub App on behalf of a user" and "Generating a user access token for a GitHub App."

12. Optionally, if you want to use device flow to generate a user access token, select **Enable Device Flow**. For more information, see "Generating a user access token for a GitHub App."

13. Optionally, under "Setup URL", enter the URL to redirect users to after they install your app. If additional setup is required after installation, you can use this URL to tell users what steps to take after installation. For more information, see "About the setup URL."

    If you selected **Request user authorization (OAuth) during installation** in an earlier step, you will not be able to enter a URL here. Users will instead be redirected to the Callback URL as part of the authorization flow, where you can describe additional setup.

14. Optionally, if you want to redirect users to the setup URL after they update an installation, select **Redirect on update**. An update includes adding or removing a repository for an installation. If "Setup URL" is blank, this will be ignored.

15. Optionally, if you do not want your app to receive webhook events, deselect **Active**. For example, if your app will only be used for authentication or does not need to respond to webhooks, deselect this option. For more information, see "Using webhooks with GitHub Apps."

16. If you selected **Active** in the previous step, under "Webhook URL", enter the URL that GitHub should send webhook events to. For more information, see "Using webhooks with GitHub Apps."

17. Optionally, if you selected **Active** in the previous step, under "Webhook secret", enter a secret token to secure your webhooks. GitHub highly recommends that you set a webhook secret. For more information, see "Using webhooks with GitHub Apps."

18. If you entered a webhook URL, under "SSL verification", select whether to enable SSL verification. GitHub highly recommends that you enable SSL verification.

19. Under "Permissions", choose the permissions that your app needs. For each permission, select the dropdown menu and click **Read-only**, **Read & write**, or **No access**. You should select the minimum permissions necessary for your app. For more information, see "Choosing permissions for a GitHub App."

20. If you selected **Active** in the earlier step to indicate that your app should receive webhook events, under "Subscribe to events", select the webhook events that you want your app to receive. The permissions that you selected in the previous step determine what webhook events are available. For more information about each webhook event, see "Webhook events and payloads."

21. Under "Where can this GitHub App be installed?", select **Only on this account** or **Any account**. For more information on installation options, see "Making a GitHub App public or private."

22. Click **Create GitHub App**.

### Next steps

After registering a GitHub App, you will want to write code to make your GitHub App do something. For examples of how to write code, see:

* "Quickstart for building GitHub Apps"
* "Building a GitHub App that responds to webhook events"
* "Building a 'Login with GitHub' button with a GitHub App"
* "Building a CLI with a GitHub App"
* "Making authenticated API requests with a GitHub App in a GitHub Actions workflow"

You should aim to follow best practices. For more information, see "Best practices for creating a GitHub App."

Once your GitHub App is fully built, you can install your GitHub App and share your GitHub App with others. For more information, see "Installing your own GitHub App" and "Sharing your GitHub App."

You can always make changes to the settings for your GitHub App. For more information, see "Modifying a GitHub App registration."

---

## About authentication with a GitHub App

> Source: https://docs.github.com/en/apps/creating-github-apps/authenticating-with-a-github-app/about-authentication-with-a-github-app

Your GitHub App can authenticate as itself, as an app installation, or on behalf of a user.

### Authentication as a GitHub App

To authenticate as itself, your app will use a JSON Web Token (JWT). Your app should authenticate as itself when it needs to generate an installation access token. An installation access token is required to authenticate as an app installation. Your app should also authenticate as itself when it needs to make API requests to manage resources related to the app. For example, when it needs to list the accounts where it is installed. For more information, see "Authenticating as a GitHub App" and "Generating a JSON Web Token (JWT) for a GitHub App."

### Authentication as an app installation

To authenticate as an installation, your app will use an installation access token. Your app should authenticate as an app installation when you want to attribute app activity to the app. Authenticating as an app installation lets your app access resources that are owned by the user or organization that installed the app. Authenticating as an app installation is ideal for automation workflows that don't involve user input. For more information, see "Authenticating as a GitHub App installation" and "Generating an installation access token for a GitHub App."

### Authentication on behalf of a user

To authenticate on behalf of a user, your app will use a user access token. Your app should authenticate on behalf of a user when you want to attribute app activity to a user. Similar to authenticating as an app installation, your app can access resources that are owned by the user or organization that installed the app. Authenticating on behalf of a user is ideal when you want to ensure that your app only takes actions that could be performed by a specific user. For more information, see "Authenticating with a GitHub App on behalf of a user" and "Generating a user access token for a GitHub App."

---

## Generating a JSON Web Token (JWT) for a GitHub App

> Source: https://docs.github.com/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-json-web-token-jwt-for-a-github-app

Learn how to create a JSON Web Token (JWT) to authenticate to certain REST API endpoints with your GitHub App.

### About JSON Web Tokens (JWTs)

In order to authenticate as an app or generate an installation access token, you must generate a JSON Web Token (JWT). If a REST API endpoint requires a JWT, the documentation for that endpoint will indicate that you must use a JWT to access the endpoint.

Your JWT must be signed using the `RS256` algorithm and must contain the following claims.

| Claim | Meaning | Details |
| ----- | ------- | ------- |
| `iat` | Issued At | The time that the JWT was created. To protect against clock drift, we recommend that you set this 60 seconds in the past and ensure that your server's date and time is set accurately (for example, by using the Network Time Protocol). |
| `exp` | Expires At | The expiration time of the JWT, after which it can't be used to request an installation token. The time must be no more than 10 minutes into the future. |
| `iss` | Issuer | The client ID or application ID of your GitHub App. This value is used to find the right public key to verify the signature of the JWT. You can find your app's IDs on the settings page for your GitHub App. Use of the client ID is recommended. For more information about navigating to the settings page for your GitHub App, see "Modifying a GitHub App registration." |
| `alg` | Message authentication code algorithm | This should be `RS256` since your JWT must be signed using the `RS256` algorithm. |

To use a JWT, pass it in the `Authorization` header of an API request. For example:

```shell
curl --request GET \
--url "https://api.github.com/app" \
--header "Accept: application/vnd.github+json" \
--header "Authorization: Bearer YOUR_JWT" \
--header "X-GitHub-Api-Version: 2026-03-10"
```

In most cases, you can use `Authorization: Bearer` or `Authorization: token` to pass a token. However, if you are passing a JSON web token (JWT), you must use `Authorization: Bearer`.

### Generating a JSON Web Token (JWT)

Most programming languages have a package that can generate a JWT. In all cases, you must have a private key and the ID of your GitHub App. For more information about generating a private key, see "Managing private keys for GitHub Apps." You can find your app's ID with the `GET /app` REST API endpoint. For more information, see "Apps" in the REST API documentation.

> [!NOTE]
> Instead of creating a JWT, you can use GitHub's Octokit SDKs to authenticate as an app. The SDK will take care of generating a JWT for you and will regenerate the JWT once the token expires. For more information, see "Scripting with the REST API and JavaScript."

#### Example: Using Ruby to generate a JWT

> [!NOTE]
> You must run `gem install jwt` to install the `jwt` package in order to use this script.

In the following example, replace `YOUR_PATH_TO_PEM` with the file path where your private key is stored. Replace `YOUR_CLIENT_ID` with the ID of your app. Make sure to enclose the values for `YOUR_PATH_TO_PEM` and `YOUR_CLIENT_ID` in double quotes.

```ruby
require 'openssl'
require 'jwt'  # https://rubygems.org/gems/jwt

# Private key contents
private_pem = File.read("YOUR_PATH_TO_PEM")
private_key = OpenSSL::PKey::RSA.new(private_pem)

# Generate the JWT
payload = {
  # issued at time, 60 seconds in the past to allow for clock drift
  iat: Time.now.to_i - 60,
  # JWT expiration time (10 minute maximum)
  exp: Time.now.to_i + (10 * 60),

# GitHub App's client ID
  iss: "YOUR_CLIENT_ID"
}

jwt = JWT.encode(payload, private_key, "RS256")
puts jwt
```

#### Example: Using Python to generate a JWT

> [!NOTE]
> You must run `pip install PyJWT cryptography` to install the `PyJWT` and the `cryptography` packages in order to use this script.

```python
#!/usr/bin/env python3
import sys
import time

import jwt

# Get PEM file path
if len(sys.argv) > 1:
    pem = sys.argv[1]
else:
    pem = input("Enter path of private PEM file: ")

# Get the Client ID
if len(sys.argv) > 2:
    client_id = sys.argv[2]
else:
    client_id = input("Enter your Client ID: ")

# Open PEM
with open(pem, 'rb') as pem_file:
    signing_key = pem_file.read()

payload = {
    # Issued at time
    'iat': int(time.time()),
    # JWT expiration time (10 minutes maximum)
    'exp': int(time.time()) + 600,

    # GitHub App's client ID
    'iss': client_id

}

# Create JWT
encoded_jwt = jwt.encode(payload, signing_key, algorithm='RS256')

print(f"JWT: {encoded_jwt}")
```

This script will prompt you for the file path where your private key is stored and for the client ID of your app. Alternatively, you can pass those values as inline arguments when you execute the script.

#### Example: Using Bash to generate a JWT

> [!NOTE]
> You must pass your Client ID and the file path where your private key is stored as arguments when running this script.

```bash
#!/usr/bin/env bash

client_id=$1 # Client ID as first argument

pem=$( cat $2 ) # file path of the private key as second argument

now=$(date +%s)
iat=$((${now} - 60)) # Issues 60 seconds in the past
exp=$((${now} + 600)) # Expires 10 minutes in the future

b64enc() { openssl base64 | tr -d '=' | tr '/+' '_-' | tr -d '\n'; }

header_json='{
    "typ":"JWT",
    "alg":"RS256"
}'
# Header encode
header=$( echo -n "${header_json}" | b64enc )

payload_json="{
    \"iat\":${iat},
    \"exp\":${exp},
    \"iss\":\"${client_id}\"
}"
# Payload encode
payload=$( echo -n "${payload_json}" | b64enc )

# Signature
header_payload="${header}"."${payload}"
signature=$(
    openssl dgst -sha256 -sign <(echo -n "${pem}") \
    <(echo -n "${header_payload}") | b64enc
)

# Create JWT
JWT="${header_payload}"."${signature}"
printf '%s\n' "JWT: $JWT"
```

#### Example: Using PowerShell to generate a JWT

In the following example, replace `YOUR_PATH_TO_PEM` with the file path where your private key is stored. Replace `YOUR_CLIENT_ID` with the ID of your app. Make sure to enclose the values for `YOUR_PATH_TO_PEM` in double quotes.

```powershell
#!/usr/bin/env pwsh

$client_id = YOUR_CLIENT_ID

$private_key_path = "YOUR_PATH_TO_PEM"

$header = [Convert]::ToBase64String([System.Text.Encoding]::UTF8.GetBytes((ConvertTo-Json -InputObject @{
  alg = "RS256"
  typ = "JWT"
}))).TrimEnd('=').Replace('+', '-').Replace('/', '_');

$payload = [Convert]::ToBase64String([System.Text.Encoding]::UTF8.GetBytes((ConvertTo-Json -InputObject @{
  iat = [System.DateTimeOffset]::UtcNow.AddSeconds(-10).ToUnixTimeSeconds()
  exp = [System.DateTimeOffset]::UtcNow.AddMinutes(10).ToUnixTimeSeconds()
  iss = $client_id
}))).TrimEnd('=').Replace('+', '-').Replace('/', '_');

$rsa = [System.Security.Cryptography.RSA]::Create()
$rsa.ImportFromPem((Get-Content $private_key_path -Raw))

$signature = [Convert]::ToBase64String($rsa.SignData([System.Text.Encoding]::UTF8.GetBytes("$header.$payload"), [System.Security.Cryptography.HashAlgorithmName]::SHA256, [System.Security.Cryptography.RSASignaturePadding]::Pkcs1)).TrimEnd('=').Replace('+', '-').Replace('/', '_')
$jwt = "$header.$payload.$signature"
Write-Host $jwt
```

---

## Authenticating as a GitHub App installation

> Source: https://docs.github.com/en/apps/creating-github-apps/authenticating-with-a-github-app/authenticating-as-a-github-app-installation

You can make your GitHub App authenticate as an installation in order to make API requests that affect resources owned by the account where the app is installed.

### About authentication as a GitHub App installation

Once your GitHub App is installed on an account, you can make it authenticate as an app installation for API requests. This allows the app to access resources owned by that installation, as long as the app was granted the necessary repository access and permissions. API requests made by an app installation are attributed to the app. For more information about installing GitHub Apps, see "Installing GitHub Apps."

For example, if you want your app to change the `Status` field of an issue on a project owned by an organization called "octo-org," then you would authenticate as the octo-org installation of your app. The timeline of the issue would state that your app updated the status.

To make an API request as an installation, you must first generate an installation access token. Then, you will send the installation access token in the `Authorization` header of your subsequent API requests. You can also use GitHub's Octokit SDKs, which can generate an installation access token for you.

Some REST API endpoints do not accept installation access tokens, and most REST API endpoints require your app to have certain permissions to use an endpoint. To see whether a REST API endpoint accepts installation access tokens and to see what permissions are required, refer to the documentation for the endpoint.

App installations can also use the GraphQL API. Similar to the REST API, the app must have certain permissions to access objects in the GraphQL API. For GraphQL requests, you should test that your app has the required permissions for the GraphQL queries and mutations that you want to make.

You can also use an installation access token to authenticate for HTTP-based Git access. Your app must have the "Contents" repository permission. You can then use the installation access token as the HTTP password. Replace `TOKEN` with the installation access token: `git clone https://x-access-token:TOKEN@github.com/owner/repo.git`.

Requests made with an installation access token are sometimes called "server-to-server" requests.

For more information about authenticating as an app on behalf of a user instead of as an app installation, see "Authenticating with a GitHub App on behalf of a user."

### Using an installation access token to authenticate as an app installation

To authenticate as an installation with an installation access token, first use the REST API to generate an installation access token. Then, use that installation access token in the `Authorization` header of a REST API or GraphQL API request. The installation access token will expire after 1 hour.

#### Generating an installation access token

1. Generate a JSON web token (JWT) for your app. For more information, see "Generating a JSON Web Token (JWT) for a GitHub App."

2. Get the ID of the installation that you want to authenticate as.

   If you are responding to a webhook event, the webhook payload will include the installation ID.

   You can also use the REST API to find the ID for an installation of your app. For example, you can get an installation ID with the `GET /users/{username}/installation`, `GET /repos/{owner}/{repo}/installation`, `GET /orgs/{org}/installation`, or `GET /app/installations` endpoints. For more information, see "REST API endpoints for GitHub Apps."

   You can also find the app ID on the settings page for your app. The app ID is different from the client ID. For more information about navigating to the settings page for your GitHub App, see "Modifying a GitHub App registration."

3. Send a REST API `POST` request to `/app/installations/INSTALLATION_ID/access_tokens`. Include your JSON web token in the `Authorization` header of your request. Replace `INSTALLATION_ID` with the ID of the installation that you want to authenticate as.

   For example, send this curl request. Replace `INSTALLATION_ID` with the ID of the installation and `JWT` with your JSON web token:

   ```shell
   curl --request POST \
   --url "https://api.github.com/app/installations/INSTALLATION_ID/access_tokens" \
   --header "Accept: application/vnd.github+json" \
   --header "Authorization: Bearer JWT" \
   --header "X-GitHub-Api-Version: 2026-03-10"
   ```

   Optionally, you can use the `repositories` or `repository_ids` body parameters to specify individual repositories that the installation access token can access. If you don't use `repositories` or `repository_ids` to grant access to specific repositories, the installation access token will have access to all repositories that the installation was granted access to. The installation access token cannot be granted access to repositories that the installation was not granted access to. You can list up to 500 repositories.

   Optionally, use the `permissions` body parameter to specify the permissions that the installation access token should have. If `permissions` is not specified, the installation access token will have all of the permissions that were granted to the app. The installation access token cannot be granted permissions that the app was not granted.

   The response will include an installation access token, the time that the token expires, the permissions that the token has, and the repositories that the token can access, if applicable. The installation access token will expire after 1 hour.

   For more information about this endpoint, see "REST API endpoints for GitHub Apps."

   > [!NOTE]
   > In most cases, you can use `Authorization: Bearer` or `Authorization: token` to pass a token. However, if you are passing a JSON web token (JWT), you must use `Authorization: Bearer`.

#### Authenticating with an installation access token

To authenticate with an installation access token, include it in the `Authorization` header of an API request. The access token will work with both the GraphQL API and the REST API.

Your app must have the required permissions to use the endpoint. For more information, see "Choosing permissions for a GitHub App."

In the following example, replace `INSTALLATION_ACCESS_TOKEN` with an installation access token:

```shell
curl --request GET \
--url "https://api.github.com/meta" \
--header "Accept: application/vnd.github+json" \
--header "Authorization: Bearer INSTALLATION_ACCESS_TOKEN" \
--header "X-GitHub-Api-Version: 2026-03-10"
```

### Using the Octokit.js SDK to authenticate as an app installation

You can use GitHub's Octokit.js SDK to authenticate as an app installation. One advantage of using the SDK to authenticate is that you do not need to generate a JSON web token (JWT) yourself. Additionally, the SDK will take care of regenerating an installation access token for you so you don't need to worry about the one hour expiration.

> [!NOTE]
> You must install and import `octokit` in order to use the Octokit.js library. The following example uses import statements in accordance with ES6. For more information about different installation and import methods, see the Octokit.js README's Usage section.

#### Using Octokit.js to authenticate with an installation ID

1. Get the ID of your GitHub App. You can find your app's ID on the settings page for your GitHub App. For more information about navigating to the settings page for your GitHub App, see "Modifying a GitHub App registration."

2. Generate a private key. For more information, see "Managing private keys for GitHub Apps."

3. Get the ID of the installation that you want to authenticate as.

   If you are responding to a webhook event, the webhook payload will include the installation ID.

   You can also use the REST API to find the ID for an installation of your app. For example, you can get an installation ID with the `GET /users/{username}/installation`, `GET /repos/{owner}/{repo}/installation`, `GET /orgs/{org}/installation`, or `GET /app/installations` endpoints. For more information, see "REST API endpoints for GitHub Apps."

4. Import `App` from `octokit`. Create a new instance of `App`. In the following example, replace `APP_ID` with a reference to your app's ID. Replace `PRIVATE_KEY` with a reference to your app's private key.

   ```javascript
   import { App } from "octokit";

   const app = new App({
     appId: APP_ID,
     privateKey: PRIVATE_KEY,
   });
   ```

5. Use the `getInstallationOctokit` method to create an authenticated `octokit` instance. In the following example, replace `INSTALLATION_ID` with the ID of the installation of your app that you want to authenticate on behalf of.

   ```javascript
   const octokit = await app.getInstallationOctokit(INSTALLATION_ID);
   ```

6. Use an `octokit` method to make a request to the API.

   Your app must have the required permissions to use the endpoint. For more information, see "Choosing permissions for a GitHub App."

   For example, to make a request to the GraphQL API:

   ```javascript
   await octokit.graphql(`
     query {
       viewer {
         login
       }
     }
     `)
   ```

   For example, to make a request to the REST API:

   ```javascript
   await octokit.request("GET /meta")
   ```

#### Using Octokit.js to authenticate in response to a webhook event

The Octokit.js SDK also passes a pre-authenticated `octokit` instance to webhook event handlers.

1. Get the ID of your GitHub App. You can find your app's ID on the settings page for your GitHub App. For more information about navigating to the settings page for your GitHub App, see "Modifying a GitHub App registration."

2. Generate a private key. For more information, see "Managing private keys for GitHub Apps."

3. Get the webhook secret that you specified in your app's settings. For more information about webhook secrets, see "Using webhooks with GitHub Apps."

4. Import `App` from `octokit`. Create a new instance of `App`. In the following example, replace `APP_ID` with a reference to your app's ID. Replace `PRIVATE_KEY` with a reference to your app's private key. Replace `WEBHOOK_SECRET` with the your app's webhook secret.

   ```javascript
   import { App } from "octokit";

   const app = new App({
     appId: APP_ID,
     privateKey: PRIVATE_KEY,
     webhooks: { WEBHOOK_SECRET },
   });
   ```

5. Use an `app.webhooks.*` method to handle webhook events. For more information, see the Octokit.js README's Webhooks section. For example, to create a comment on an issue when the issue is opened:

   ```javascript
   app.webhooks.on("issues.opened", ({ octokit, payload }) => {
     await octokit.request("POST /repos/{owner}/{repo}/issues/{issue_number}/comments", {
         owner: payload.repository.owner.login,
         repo: payload.repository.name,
         issue_number: payload.issue.number,
         body: `This is a bot post in response to this issue being opened.`,
         headers: {
           "x-github-api-version": "2026-03-10",
         },
       }
     )
   });
   ```

---

## Choosing permissions for a GitHub App

> Source: https://docs.github.com/en/apps/creating-github-apps/registering-a-github-app/choosing-permissions-for-a-github-app

The permissions of a GitHub App determine what the app can do with GitHub's APIs and what webhooks the app can receive.

### About GitHub App permissions

GitHub Apps don't have any permissions by default. When you register a GitHub App, you can select permissions for the app. The permissions that you select determine what the app can do with GitHub's APIs and what webhooks the app can subscribe to. You should select the minimum permissions required for the app.

Although GitHub Apps don't have any permissions by default, they do have implicit permissions to read public resources when acting on behalf of a user. When a user authorizes the app to act on their behalf, the GitHub App can use the resulting user access token to make requests to the REST API and the GraphQL API to read public resources. To learn more about acting on behalf of a user, see "Authenticating with a GitHub App on behalf of a user."

App permissions are classified as repository, organization, or account permissions.

* Repository permissions allow your app to access resources related to repositories that are owned by the account where the app is installed.
* Organization permissions allow your app to access resources related to the organization where the app is installed, if it is installed on an organization account.
* Account permissions allow your app to access resources related to a user if the user has also authorized your app. For more information about user authorization of apps, see "Authenticating with a GitHub App on behalf of a user."

When a user installs an app on their user account or organization, they see and grant the repository and organization permissions that the app requested. They will also see a list of account permissions that the app can request for individual users. When a user authorizes an app to act on their behalf, they will see and grant the account permissions that the app requested.

The success of an API request with a user access token depends on the user's permissions as well as the app's permissions. For example, if the app was granted permission to write the contents of a repository, but the user can only read the contents, then the user access token can only read the contents. The success of an API request with an installation access token only depends on the app's permissions.

For more information about specifying permissions during GitHub App registration, see "Registering a GitHub App."

Some webhooks and API access requires "Administration" permissions. If your app requires "Administration" permissions, consider explaining this requirement on your app's homepage. This will help users understand why your app needs a high level permission.

### About changes to permissions

You can modify the permissions for apps you own or manage at any time. When you do so, the owner of each account where the app was installed will be prompted to approve the new permissions. If the account owner does not approve the new permissions, their installation will continue to use the old permissions.

For more information about modifying permissions, see "Modifying a GitHub App registration."

### Choosing permissions for webhook access

The webhook documentation indicates whether each webhook is available to GitHub Apps. For each webhook that you want to subscribe to, refer to the webhook documentation to see what permissions a GitHub App needs to subscribe to that webhook. For more information, see "Webhook events and payloads."

For example, if you want your app to subscribe to `team` events, your app must have the "Members" organization permission.

On your GitHub App registration page, the available webhook events will change as you change your app's permissions. If you did not select sufficient permissions for your GitHub App to subscribe to an event, the event will not appear as an option on your app registration page.

### Choosing permissions for REST API access

The REST API reference documentation for each endpoint states whether the endpoint works with GitHub Apps and states what permissions are required in order for the app to use the endpoint. Some endpoints may require multiple permissions, and some endpoints may require one of multiple permissions. For an overview of which REST API endpoints a GitHub App can access with each permission, see "Permissions required for GitHub Apps."

For example, to use the `GET /orgs/{org}/dependabot/secrets` endpoint, your app must have at least read-level permission for the "organization dependabot secrets" permission.

If your app makes a REST API request with insufficient permissions, the API will return a `403` response.

To help you choose the correct permissions, you will receive the `X-Accepted-GitHub-Permissions` header in the REST API response. The header will tell you what permissions are required in order to access the endpoint. For more information, see "Troubleshooting the REST API."

### Choosing permissions for GraphQL API access

For GraphQL requests, you should test your app to ensure that it has the required permissions for the GraphQL queries and mutations that you want to make.

If your app makes a GraphQL API query or mutation with insufficient permissions, the API will return a `401` response.

### Choosing permissions for Git access

If you want your app to use an installation or user access token to authenticate for HTTP-based Git access, you should request the "Contents" repository permission. If your app specifically needs to access or edit Actions files in the `.github/workflows` directory, request the "Workflows" repository permission.

You can then use the access token as the HTTP password. Replace `TOKEN` with the access token:

```shell
git clone https://x-access-token:TOKEN@github.com/owner/repo.git
```

---

## Deciding when to build a GitHub App

> Source: https://docs.github.com/en/apps/creating-github-apps/about-creating-github-apps/deciding-when-to-build-a-github-app

When building an integration, you should consider using a GitHub App in the following scenarios, instead of an OAuth app, personal access token, or GitHub Actions.

### Using a GitHub App instead of an OAuth app

In general, GitHub Apps are preferred over OAuth apps.

Both OAuth apps and GitHub Apps use OAuth 2.0.

OAuth apps can only act on behalf of a user while GitHub Apps can either act on behalf of a user or independently of a user.

For more information, see "Differences between GitHub Apps and OAuth apps."

For information on how to migrate an existing OAuth app to a GitHub App, see "Migrating OAuth apps to GitHub Apps."

#### GitHub Apps offer enhanced security

GitHub Apps provide more control over what the app can do. Instead of the broad scopes that OAuth apps use, GitHub Apps use fine-grained permissions. For example, if your app needs to read the contents of a repository, an OAuth app would require the `repo` scope, which would also let the app edit the repository contents and settings. A GitHub App can request read-only access to repository contents, which will not let the app take more privileged actions like editing the repository contents or settings.

GitHub Apps also offer more control over repository access. With a GitHub App, the user or organization owner who installed the app can decide what repositories the app can access. Conversely, an OAuth app can access every repository that the user who authorized the app can access.

GitHub Apps use short lived tokens. If the token is leaked, the token will be valid for a shorter amount of time, which reduces the damage that can be done. Conversely, OAuth app tokens do not expire until the person who authorized the OAuth app revokes the token.

These security features help harden your GitHub App's security by limiting the damage that could be done if your app's credentials were leaked. Additionally, this lets organizations with stricter security policies use your app.

#### GitHub Apps can act independently of or on behalf of a user

GitHub Apps can act independently of a user. This is beneficial for automations that do not require user input.

Similar to OAuth apps, GitHub Apps can still take actions on behalf of a user. Unlike OAuth apps, which don't indicate that the action was performed by the app, GitHub Apps indicate that the action was performed by the app on behalf of the user.

GitHub Apps are not tied to a user account and do not consume a seat. GitHub Apps remain installed even when the person who initially installed the app leaves the organization. This lets your integrations continue to work even if people leave your team.

#### GitHub Apps have scalable rate limits

The rate limit for GitHub Apps using an installation access token scales with the number of repositories and number of organization users. Conversely, OAuth apps have lower rate limits and do not scale. For more information, see "Rate limits for GitHub Apps."

#### GitHub Apps have built in webhooks

GitHub Apps have built-in, centralized webhooks. GitHub Apps can receive webhook events for all repositories and organizations the app can access. Conversely, OAuth apps must configure webhooks individually for each repository and organization.

#### API access differs slightly

In general, GitHub Apps and OAuth apps can make the same API requests. However, there are some differences:

* The REST API to manage check runs and check suites is only available to GitHub Apps.
* Enterprise-level resources such as the enterprise object itself are not available to GitHub Apps. This means that GitHub Apps cannot call endpoints like `GET /enterprise/settings/license`. However, enterprise-owned organization and repository resources are available.
* Some requests may return incomplete data depending on the permissions and repository access that was granted to an GitHub App. For example, if your app makes a request to get all repositories that a user can access, the response will only include the repositories that the app was also granted access to.

For more information about the REST API endpoints that are available to GitHub Apps, see "Endpoints available for GitHub App installation access tokens."

### Choosing between a GitHub App or a personal access token

If you want to access GitHub resources on behalf of a user or in an organization, or you anticipate a long-lived integration, we recommend building a GitHub App.

You can use personal access tokens for API testing or short-lived scripts. Since a personal access token is associated with a user, your automation could break if the user no longer has access to the resources you need. A GitHub App installed on an organization is not dependent on a user. Additionally, unlike a user, a GitHub App does not consume a GitHub seat.

GitHub supports two types of personal access tokens, but recommends that you use fine-grained personal access tokens instead of personal access tokens (classic) whenever possible. For more information about personal access tokens, see "Managing your personal access tokens."

### Choosing between a GitHub App or GitHub Actions

GitHub Apps and GitHub Actions both provide ways to build automation and workflow tools.

*GitHub Actions* provide automation that can perform jobs like continuous integration, deployment tasks, and project management in a repository. They run directly on GitHub-hosted runner machines or self-hosted runners that your administrator sets up. GitHub Actions do not run persistently. GitHub Actions workflows run in response to events that occur in their repository, and only have access to the resources of the repository that they are set up for. However, custom actions can be shared across repositories and organizations, allowing developers to reuse and modify existing actions to meet their needs. GitHub Actions also come with built-in secret management, which you can use to securely interact with third-party services and manage deploy keys safely.

*GitHub Apps* run persistently on a server or compute infrastructure that you provide or run on a user device. They can react to GitHub webhook events as well as events from outside the GitHub ecosystem. They are a good option for operations that span multiple repositories or organizations, or for providing hosted services to other organizations and enterprises. A GitHub App is the best choice when building a tool with functions that occur primarily outside of GitHub or require more execution time or permissions than what a GitHub Actions workflow is allotted.

For more information about comparing GitHub Actions to GitHub Apps, see "GitHub Actions vs GitHub Apps."

You can use a GitHub App to authenticate in a GitHub Actions workflow if the built in `GITHUB_TOKEN` does not have sufficient permissions. For more information, see "Making authenticated API requests with a GitHub App in a GitHub Actions workflow."

---

## Differences between GitHub Apps and OAuth apps

> Source: https://docs.github.com/en/apps/oauth-apps/building-oauth-apps/differences-between-github-apps-and-oauth-apps

In general, GitHub Apps are preferred to OAuth apps because they use fine-grained permissions, give more control over which repositories the app can access, and use short-lived tokens.

### About GitHub Apps and OAuth apps

In general, GitHub Apps are preferred over OAuth apps. GitHub Apps use fine-grained permissions, give the user more control over which repositories the app can access, and use short-lived tokens. These properties can harden the security of your app by limiting the damage that could be done if your app's credentials were leaked.

Similar to OAuth apps, GitHub Apps can still use OAuth 2.0 and generate a type of OAuth token (called a user access token) and take actions on behalf of a user. However, GitHub Apps can also act independently of a user. This is beneficial for automations that do not require user input. The app will continue to work even if the person who installed the app on an organization leaves the organization.

GitHub Apps have built-in, centralized webhooks. GitHub Apps can receive webhook events for all repositories and organizations the app can access. Conversely, OAuth apps must configure webhooks individually for each repository and organization.

The rate limit for GitHub Apps using an installation access token scales with the number of repositories and number of organization users. Conversely, OAuth apps have lower rate limits and do not scale.

There is one case where an OAuth app is preferred over a GitHub App. If your app needs to access enterprise-level resources such as the enterprise object itself, you should use an OAuth app because a GitHub App cannot yet be given permissions against an enterprise. GitHub Apps can still access enterprise-owned organization and repository resources.

For more information about GitHub Apps, see "About creating GitHub Apps."

For more information about migrating an existing OAuth app to a GitHub App, see "Migrating OAuth apps to GitHub Apps."

### Who can install GitHub Apps and authorize OAuth apps?

You can install GitHub Apps in your personal account or organizations you own. If you have admin permissions in a repository, you can install GitHub Apps on organization accounts. If a GitHub App is installed in a repository and requires organization permissions, the organization owner must approve the application.

By default, only organization owners can manage the settings of GitHub Apps in an organization. To allow additional users to change the developer settings of GitHub Apps owned by the organization, an owner can grant them GitHub App manager permissions. GitHub App Managers can't manage third-party applications. For more information about adding and removing GitHub App managers in your organization, see "Roles in an organization."

By contrast, users authorize OAuth apps, which gives the app the ability to act as the authenticated user. For example, you can authorize an OAuth app that finds all notifications for the authenticated user. You can always revoke permissions from an OAuth app.

Organization owners can choose whether to allow outside collaborators to request access for unapproved OAuth apps and GitHub Apps. For more information, see "Limiting OAuth app and GitHub App access requests and installations."

> [!WARNING]
> Revoking all permission from an OAuth app deletes any SSH keys the application generated on behalf of the user, including deploy keys.

| GitHub Apps | OAuth apps |
|---|---|
| You must be an organization owner or have admin permissions in a repository to install a GitHub App on an organization. If a GitHub App is installed in a repository and requires organization permissions, the organization owner must approve the application. | You can authorize an OAuth app to have access to resources. |
| You can install a GitHub App on your personal repository. | You can authorize an OAuth app to have access to resources. |
| You must be an organization owner, personal repository owner, or have admin permissions in a repository to uninstall a GitHub App and remove its access. | You can delete an OAuth access token to remove access. |
| You must be an organization owner or have admin permissions in a repository to request a GitHub App installation. | If an organization application policy is active, any organization member can request to install an OAuth app on an organization. An organization owner must approve or deny the request. |

### What can GitHub Apps and OAuth apps access?

Account owners can use a GitHub App in one account without granting access to another. For example, you can install a third-party build service on your employer's organization, but decide not to grant that build service access to repositories in your personal account. A GitHub App remains installed if the person who set it up leaves the organization.

An *authorized* OAuth app has access to all of the user's or organization owner's accessible resources.

| GitHub Apps | OAuth apps |
|---|---|
| Installing a GitHub App grants the app access to a user or organization account's chosen repositories. | Authorizing an OAuth app grants the app access to the user's accessible resources. For example, repositories they can access. |
| The installation token from a GitHub App loses access to resources if an admin removes repositories from the installation. | An OAuth access token loses access to resources when the user loses access, such as when they lose write access to a repository. |
| Installation access tokens are limited to specified repositories with the permissions chosen by the creator of the app. | An OAuth access token is limited via scopes. |
| GitHub Apps can request separate access to issues and pull requests without accessing the actual contents of the repository. | OAuth apps need to request the `repo` scope to get access to issues, pull requests, or anything owned by the repository. |
| GitHub Apps aren't subject to organization application policies. A GitHub App only has access to the repositories an organization owner has granted. | If an organization application policy is active, only an organization owner can authorize the installation of an OAuth app. If installed, the OAuth app gains access to anything visible to the token the organization owner has within the approved organization. |
| A GitHub App receives a webhook event when an installation is changed or removed. This tells the app creator when they've received more or less access to an organization's resources. | OAuth apps can lose access to an organization or repository at any time based on the granting user's changing access. The OAuth app will not inform you when it loses access to a resource. |

### Token-based identification

> [!NOTE]
> GitHub Apps can also use a user-based token. For more information, see "Authenticating with a GitHub App on behalf of a user."

| GitHub Apps | OAuth apps |
|---|---|
| A GitHub App can request an installation access token by using a private key with a JSON web token format out-of-band. | An OAuth app can exchange a request token for an access token after a redirect via a web request. |
| An installation token identifies the app as the GitHub Apps bot, such as @jenkins-bot. | An access token identifies the app as the user who granted the token to the app, such as @octocat. |
| Installation access tokens expire after a predefined amount of time (currently 1 hour). | OAuth tokens remain active until they're revoked by the customer. |
| GitHub Apps installed on organizations or repositories are subject to rate limits that scale with the number of installations. For more information, see "Rate limits for GitHub Apps." | OAuth tokens use the user's rate limit of 5,000 requests per hour. |
| Rate limit increases can be granted both at the GitHub Apps level (affecting all installations) and at the individual installation level. | Rate limit increases are granted per OAuth app. Every token granted to that OAuth app gets the increased limit. |
| GitHub Apps can authenticate on behalf of the user. The flow to authorize is the same as the OAuth app authorization flow. User access tokens can expire and be renewed with a refresh token. For more information, see "Refreshing user access tokens" and "Authenticating with a GitHub App on behalf of a user." | The OAuth flow used by OAuth apps authorizes an OAuth app on behalf of the user. This is the same flow used to generate a GitHub App user access token. |

### Requesting permission levels for resources

Unlike OAuth apps, GitHub Apps have targeted permissions that allow them to request access only to what they need. For example, a Continuous Integration (CI) GitHub App can request read access to repository content and write access to the status API. Another GitHub App can have no read or write access to code but still have the ability to manage issues, labels, and milestones. OAuth apps can't use granular permissions.

| Access | GitHub Apps (`read` or `write` permissions) | OAuth apps |
|---|---|---|
| **For access to public repositories** | Public repository needs to be chosen during installation. | `public_repo` scope. |
| **For access to repository code/contents** | Repository contents | `repo` scope. |
| **For access to issues, labels, and milestones** | Issues | `repo` scope. |
| **For access to pull requests, labels, and milestones** | Pull requests | `repo` scope. |
| **For access to commit statuses (for CI builds)** | Commit statuses | `repo:status` scope. |
| **For access to deployments and deployment statuses** | Deployments | `repo_deployment` scope. |
| **To receive events via a webhook** | A GitHub App includes a webhook by default. | `write:repo_hook` or `write:org_hook` scope. |

### Repository discovery

| GitHub Apps | OAuth apps |
|---|---|
| GitHub Apps can look at `/installation/repositories` to see repositories the installation can access. | OAuth apps can look at `/user/repos` for a user view or `/orgs/:org/repos` for an organization view of accessible repositories. |
| GitHub Apps receive webhooks when repositories are added or removed from the installation. | OAuth apps create organization webhooks for notifications when a new repository is created within an organization. |

### Webhooks

| GitHub Apps | OAuth apps |
|---|---|
| By default, GitHub Apps have a single webhook that receives the events they are configured to receive for every repository they have access to. | OAuth apps request the webhook scope to create a repository webhook for each repository they need to receive events from. |
| GitHub Apps receive certain organization-level events with the organization member's permission. | OAuth apps request the organization webhook scope to create an organization webhook for each organization they need to receive organization-level events from. |
| Webhooks are automatically disabled when the GitHub App is uninstalled. | Webhooks are not automatically disabled if an OAuth app's access token is deleted, and there is no way to clean them up automatically. You will have to ask users to do this manually. |

### Git access

| GitHub Apps | OAuth apps |
|---|---|
| GitHub Apps ask for repository contents permission and use your installation access token to authenticate via HTTP-based Git. For more information, see "Generating an installation access token for a GitHub App" | OAuth apps ask for `write:public_key` scope and "Create a deploy key" via the API. You can then use that key to perform Git commands. |
| The token is used as the HTTP password. | The token is used as the HTTP username. |

### Machine vs. bot accounts

Machine user accounts are OAuth-based personal accounts that segregate automated systems using GitHub's user system.

Bot accounts are specific to GitHub Apps and are built into every GitHub App.

| GitHub Apps | OAuth apps |
|---|---|
| GitHub App bots do not consume a GitHub Enterprise seat. | A machine user account consumes a GitHub Enterprise seat. |
| Because a GitHub App bot is never granted a password, a customer can't sign into it directly. | A machine user account is granted a username and password to be managed and secured by the customer. |
