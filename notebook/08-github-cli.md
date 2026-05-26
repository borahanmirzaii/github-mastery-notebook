# GitHub CLI (gh)

> **Source root:** https://docs.github.com/en/github-cli
> **Fetched:** 2026-05-26
> **Area:** 08 — GitHub CLI

## Table of contents

- [GitHub CLI documentation (landing)](#github-cli-documentation-landing)
- [About GitHub CLI](#about-github-cli)
- [GitHub CLI quickstart](#github-cli-quickstart)
- [Creating GitHub CLI extensions](#creating-github-cli-extensions)
- [Using GitHub CLI extensions](#using-github-cli-extensions)
- [GitHub CLI manual](#github-cli-manual)
- [gh api](#gh-api)
- [gh help formatting](#gh-help-formatting)
- [gh help environment](#gh-help-environment)

---

## GitHub CLI documentation (landing)
> Source: https://docs.github.com/en/github-cli

GitHub CLI is an open source tool for using GitHub from your computer's command line. When you're working from the command line, you can use the GitHub CLI to save time and avoid switching context.

[Overview](/github-cli/github-cli/about-github-cli)[Quickstart](/github-cli/github-cli/quickstart)

### Recommended

[### About GitHub CLI
GitHub CLI is a command-line tool that brings pull requests, issues, GitHub Actions, and other GitHub features to your terminal, so you can do all your work in one place.](/en/free-pro-team@latest/github-cli/github-cli/about-github-cli)[### GitHub CLI quickstart
Start using GitHub CLI to work with GitHub in the command line.](/en/free-pro-team@latest/github-cli/github-cli/quickstart)[### GitHub CLI reference
You can view all of the GitHub CLI commands in your terminal. The same information is available in the GitHub CLI manual.](/en/free-pro-team@latest/github-cli/github-cli/github-cli-reference)

### Articles
All categories

[Learn the basics
#### About GitHub CLI
GitHub CLI is a command-line tool that brings pull requests, issues, GitHub Actions, and other GitHub features to your terminal, so you can do all your work in one place.](/en/github-cli/github-cli/about-github-cli)[Use and extend the CLI
#### Creating GitHub CLI extensions
Learn how to share new GitHub CLI commands with other users by creating custom extensions for GitHub CLI.](/en/github-cli/github-cli/creating-github-cli-extensions)[Learn the basics
#### GitHub CLI quickstart
Start using GitHub CLI to work with GitHub in the command line.](/en/github-cli/github-cli/quickstart)[Use and extend the CLI
#### GitHub CLI reference
You can view all of the GitHub CLI commands in your terminal. The same information is available in the GitHub CLI manual.](/en/github-cli/github-cli/github-cli-reference)[Learn the basics
#### GitHub CLI telemetry
GitHub CLI sends pseudonymous telemetry to help improve the product. Learn what data is collected and how to opt out.](/en/github-cli/github-cli/github-cli-telemetry)[Use and extend the CLI
#### Using GitHub CLI extensions
Learn how to use custom extensions written by other GitHub CLI users.](/en/github-cli/github-cli/using-github-cli-extensions)[Use and extend the CLI
#### Using the GitHub CLI across GitHub platforms
Learn how to run commands when you are authenticated to accounts on different GitHub platforms.](/en/github-cli/github-cli/using-multiple-accounts)

---

## About GitHub CLI
> Source: https://docs.github.com/en/github-cli/github-cli/about-github-cli

GitHub CLI is an open source tool for using GitHub from your computer's command line. When you're working from the command line, you can use the GitHub CLI to save time and avoid switching context.

GitHub CLI includes GitHub features such as:

- View, create, clone, and fork repositories

- Create, close, edit, and view issues and pull requests

- Review, diff, and merge pull requests

- Run, view, and list workflows

- Create, list, view, and delete releases

- Create, edit, list, view, and delete gists

- List, create, delete, and connect to a codespace

- Retrieve information from the GitHub API

For more information about what you can do with GitHub CLI, see the [GitHub CLI manual](https://cli.github.com/manual).

#### What's the difference between GitHub CLI and Git on the command line?

The Git command line interface (`git`) allows you to work with a local or remote Git repository. The remote repository may be hosted on GitHub or it may be hosted by another service.

GitHub CLI (`gh`) is specifically for working with GitHub. It allows you to use the command line to interact with GitHub in all sorts of ways, as illustrated by the previous list. If you tend to work on the command line, you may prefer using GitHub CLI instead of using GitHub in a browser. GitHub CLI also makes it easier for you to create scripts to automate GitHub operations.

### Installing GitHub CLI

For installation instructions for GitHub CLI, see the [GitHub CLI repository](https://github.com/cli/cli#installation).

### Sharing feedback

If you have feedback or feature requests, you can open an issue in the [`cli/cli` repository](https://github.com/cli/cli).

---

## GitHub CLI quickstart
> Source: https://docs.github.com/en/github-cli/github-cli/quickstart

### About GitHub CLI

GitHub CLI is an open source tool for using GitHub from your computer's command line. When you're working from the command line, you can use the GitHub CLI to save time and avoid switching context.

### Prerequisites

- Install GitHub CLI on macOS, Windows, or Linux. For more information, see [Installation](https://github.com/cli/cli?ref_product=cli&ref_type=engagement&ref_style=text#installation) in the GitHub CLI repository.

- To authenticate to GitHub, run the following command from your terminal.

```
gh auth login
```

- Select where you want to authenticate to: If you access GitHub at GitHub.com, select **GitHub.com**.

- If you access GitHub at a different domain, select **Other**, then enter your hostname (for example: `octocorp.ghe.com`).

- Follow the rest of the on-screen prompts. GitHub CLI automatically stores your Git credentials for you when you choose HTTPS as your preferred protocol for Git operations and answer "yes" to the prompt asking if you would like to authenticate to Git with your GitHub credentials. This can be useful as it allows you to use Git commands like `git push` and `git pull` without needing to set up a separate credential manager or use SSH.

### Some useful commands

> [!NOTE]
> When you use some commands for the first time - for example, `gh codespace SUBCOMMAND` - you'll be prompted to add extra scopes to your authentication token. Follow the onscreen instructions.

#### Viewing your status

Enter `gh status` to see details of your current work on GitHub across all the repositories you're subscribed to.

#### Viewing a repository

Enter `gh repo view OWNER/REPO` to see the repository description and `README.md` for the repository. Enter `gh repo view OWNER/REPO --web` to view the repository in your default browser.

If you run the `repo` subcommand from within the directory of a local Git repository that has a remote on GitHub you can omit `OWNER/REPO`.

#### Cloning a repository

Enter `gh repo clone OWNER/REPO`. For example, `gh repo clone octo-org/octo-repo` clones the `octo-org/octo-repo` repository to the directory from which you ran this command on your local computer.

#### Creating a repository

Enter `gh repo create` and follow the on-screen instructions. You can create a new, empty repository on GitHub and then, optionally, clone it locally. Alternatively, you can push an existing local repository to GitHub, and optionally set it as the remote for your local repository. For information on setting a local directory as a Git repository, see [Adding locally hosted code to GitHub](/en/migrations/importing-source-code/using-the-command-line-to-import-source-code/adding-locally-hosted-code-to-github#initializing-a-git-repository).

#### Working with issues

Enter `gh issue list --repo OWNER/REPO` to list the most recently created issues that are currently open for the specified repository. If you run the `issue` subcommand from within the directory of a local Git repository that has a remote on GitHub you can omit `--repo OWNER/REPO`. For example, enter `gh issue list --assignee "@me"` to list issues assigned to you in this repository, or `gh issue list --author monalisa` to list issues created by the user "monalisa."

You can also create a new issue, see [Creating an issue](/en/issues/tracking-your-work-with-issues/creating-an-issue#creating-an-issue-with-github-cli), or search for an issue, see [Filtering and searching issues and pull requests](/en/issues/tracking-your-work-with-issues/filtering-and-searching-issues-and-pull-requests?tool=cli#searching-for-issues-and-pull-requests).

#### Working with pull requests

Enter `gh pr list --repo OWNER/REPO` to list the most recently created pull requests that are currently open for the specified repository. If you run the `pr` subcommand from within the directory of a local Git repository that has a remote on GitHub you can omit `--repo OWNER/REPO`. For example, enter `gh pr list --author "@me"` to list open pull requests that you created in this repository.

Enter `gh pr list --label LABEL-NAME` to list open pull requests with a specific label. Enter `gh search prs --review-requested=@me --state=open` to list pull requests that you've been asked to review.

To create a pull request, enter `gh pr create` and follow the on-screen instructions. For more information, see [Creating a pull request](/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request?tool=cli#creating-the-pull-request).

#### Working with codespaces

To create a new codespace, enter `gh codespace create` and follow the on-screen instructions.

To display your existing codespaces, enter `gh codespace list`. To open a codespace in the web version of VS Code enter `gh codespace code -w` and choose a codespace.

In all of these commands you can substitute `cs` for `codespace`.

### Getting help

Enter `gh` for a reminder of the top-level GitHub CLI commands that you can use. For example, `issue`, `pr`, `repo`, and so on.

For each command, and each subsidiary subcommand, you can append the `--help` flag to find out how it's used. For example, `gh issue --help` or `gh issue create --help`.

### Customizing GitHub CLI

You can change configuration settings and add aliases or extensions, to make GitHub CLI work the way that suits you best.

- Enter `gh config set SUBCOMMANDS` to configure GitHub CLI's settings, replacing `SUBCOMMANDS` with the setting you want to adjust. For example, you can specify the text editor that's used when a GitHub CLI command requires you to edit text - such as when you add the body text for a new issue you're creating. To set your preferred text editor to Visual Studio Code enter `gh config set editor "code -w"`. The `-w` (or `--wait`) flag in this example causes the command to wait for the file to be closed in Visual Studio Code before proceeding with the next step in your terminal. For more information, see [`gh config set`](https://cli.github.com/manual/gh_config_set).

- Define aliases for commands that you commonly run. For example, if you run `gh alias set prd "pr create --draft"`, you will then be able to run `gh prd` to quickly open a draft pull request. For more information, see [`gh alias`](https://cli.github.com/manual/gh_alias).

- Create or add custom commands with GitHub CLI extensions. For more information, see [Using GitHub CLI extensions](/en/github-cli/github-cli/using-github-cli-extensions) and [Creating GitHub CLI extensions](/en/github-cli/github-cli/creating-github-cli-extensions).

### Using GitHub CLI with multiple accounts

If you have multiple accounts on the same GitHub platform, such as GitHub.com, you can authenticate to each one and switch between them using the `gh auth switch` command. See [gh auth switch](https://cli.github.com/manual/gh_auth_switch) in the GitHub CLI manual.

If you need to use the GitHub CLI across multiple GitHub platforms, such as a personal account on GitHub.com and a managed user account on GHE.com, see [Using the GitHub CLI across GitHub platforms](/en/github-cli/github-cli/using-multiple-accounts).

### Further reading

- [GitHub CLI reference](/en/github-cli/github-cli/github-cli-reference)

- [GitHub CLI online manual](https://cli.github.com/manual/gh)

---

## Creating GitHub CLI extensions
> Source: https://docs.github.com/en/github-cli/github-cli/creating-github-cli-extensions

### About GitHub CLI extensions

GitHub CLI extensions are custom GitHub CLI commands that anyone can create and use. For more information about how to use GitHub CLI extensions, see [Using GitHub CLI extensions](/en/github-cli/github-cli/using-github-cli-extensions).

You need a repository for each extension that you create. The repository name must start with `gh-`. The rest of the repository name is the name of the extension. The repository must have an executable file at its root with the same name as the repository or a set of precompiled binary executables attached to a release.

> [!NOTE]
> When relying on an executable script, we recommend using a bash script because bash is a widely available interpreter. You may use non-bash scripts, but the user must have the necessary interpreter installed in order to use the extension. If you would prefer to not rely on users having interpreters installed, consider a precompiled extension.

### Creating an interpreted extension with gh extension create

> [!NOTE]
> Running `gh extension create` with no arguments will start an interactive wizard.

You can use the `gh extension create` command to create a project for your extension, including a bash script that contains some starter code.

- Set up a new extension by using the `gh extension create` subcommand. Replace `EXTENSION-NAME` with the name of your extension.

```
gh extension create EXTENSION-NAME
```

- Follow the printed instructions to finalize and optionally publish your extension.

### Creating a precompiled extension in Go with gh extension create

You can use the `--precompiled=go` argument to create a Go-based project for your extension, including Go scaffolding, workflow scaffolding, and starter code.

- Set up a new extension by using the `gh extension create` subcommand. Replace `EXTENSION-NAME` with the name of your extension and specify `--precompiled=go`.

```
gh extension create --precompiled=go EXTENSION-NAME
```

- Follow the printed instructions to finalize and optionally publish your extension.

### Creating a non-Go precompiled extension with gh extension create

You can use the `--precompiled=other` argument to create a project for your non-Go precompiled extension, including workflow scaffolding.

- Set up a new extension by using the `gh extension create` subcommand. Replace `EXTENSION-NAME` with the name of your extension and specify `--precompiled=other`.

```
gh extension create --precompiled=other EXTENSION-NAME
```

- Add some initial code for your extension in your compiled language of choice.

- Fill in `script/build.sh` with code to build your extension to ensure that your extension can be built automatically.

- Follow the printed instructions to finalize and optionally publish your extension.

### Creating an interpreted extension manually

- Create a local directory called `gh-EXTENSION-NAME` for your extension. Replace `EXTENSION-NAME` with the name of your extension. For example, `gh-whoami`.

- In the directory that you created, add an executable file with the same name as the directory.
> [!NOTE] Make sure that your file is executable. On Unix, you can execute `chmod +x file_name` in the command line to make `file_name` executable. On Windows, you can run `git init -b main`, `git add file_name`, then `git update-index --chmod=+x file_name`.

- Write your script in the executable file. For example:

```
#!/usr/bin/env bash
set -e
exec gh api user --jq '"You are @\(.login) (\(.name))."'
```

- From your directory, install the extension as a local extension.

```
gh extension install .
```

- Verify that your extension works. Replace `EXTENSION-NAME` with the name of your extension. For example, `whoami`.

```
gh EXTENSION-NAME
```

- From your directory, create a repository to publish your extension. Replace `EXTENSION-NAME` with the name of your extension.

```
git init -b main
git add . && git commit -m "initial commit"
gh repo create gh-EXTENSION-NAME --source=. --public --push
```

- Optionally, to help other users discover your extension, add the repository topic `gh-extension`. This will make the extension appear on the [`gh-extension` topic page](https://github.com/topics/gh-extension). For more information about how to add a repository topic, see [Classifying your repository with topics](/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/classifying-your-repository-with-topics).

### Tips for writing interpreted GitHub CLI extensions

#### Handling arguments and flags

All command line arguments following a `gh my-extension-name` command will be passed to the extension script. In a bash script, you can reference arguments with `$1`, `$2`, etc. You can use arguments to take user input or to modify the behavior of the script.

For example, this script handles multiple flags. When the script is called with the `-h` or `--help` flag, the script prints help text instead of continuing execution. When the script is called with the `--name` flag, the script sets the next value after the flag to `name_arg`. When the script is called with the `--verbose` flag, the script prints a different greeting.

```
#!/usr/bin/env bash
set -e

verbose=""
name_arg=""
while [ $# -gt 0 ]; do
  case "$1" in
  --verbose)
    verbose=1
    ;;
  --name)
    name_arg="$2"
    shift
    ;;
  -h|--help)
    echo "Add help text here."
    exit 0
    ;;
  esac
  shift
done

if [ -z "$name_arg" ]
then
  echo "You haven't told us your name."
elif [ -z "$verbose" ]
then
  echo "Hi $name_arg"
else
  echo "Hello and welcome, $name_arg"
fi
```

#### Calling core commands in non-interactive mode

Some GitHub CLI core commands will prompt the user for input. When scripting with those commands, a prompt is often undesirable. To avoid prompting, supply the necessary information explicitly via arguments.

For example, to create an issue programmatically, specify the title and body:

```
gh issue create --title "My Title" --body "Issue description"
```

#### Fetching data programmatically

Many core commands support the `--json` flag for fetching data programmatically. For example, to return a JSON object listing the number, title, and mergeability status of pull requests:

```
gh pr list --json number,title,mergeStateStatus
```

If there is not a core command to fetch specific data from GitHub, you can use the [`gh api`](https://cli.github.com/manual/gh_api) command to access the GitHub API. For example, to fetch information about the current user:

```
gh api user
```

All commands that output JSON data also have options to filter that data into something more immediately usable by scripts. For example, to get the current user's name:

```
gh api user --jq '.name'
```

For more information, see [`gh help formatting`](https://cli.github.com/manual/gh_help_formatting).

### Creating a precompiled extension manually

- Create a local directory called `gh-EXTENSION-NAME` for your extension. Replace `EXTENSION-NAME` with the name of your extension. For example, `gh-whoami`.

- In the directory you created, add some source code. For example:

```
package main
import (
  "github.com/cli/go-gh"
  "fmt"
)

func main() {
  args := []string{"api", "user", "--jq", `"You are @\(.login) (\(.name))"` }
  stdOut, _, err := gh.Exec(args...)
  if err != nil {
    fmt.Println(err)
    return
  }
  fmt.Println(stdOut.String())
}
```

- From your directory, install the extension as a local extension.

```
gh extension install .
```

- Build your code. For example, with Go, replacing `YOUR-USERNAME` with your GitHub username:

```
go mod init github.com/YOUR-USERNAME/gh-whoami
go mod tidy
go build
```

- Verify that your extension works. Replace `EXTENSION-NAME` with the name of your extension. For example, `whoami`.

```
gh EXTENSION-NAME
```

- From your directory, create a repository to publish your extension. Replace `EXTENSION-NAME` with the name of your extension.
> [!NOTE] Be careful not to commit the binary produced by your compilation step to version control.

```
 git init -b main
echo "gh-EXTENSION-NAME" >> .gitignore
git add main.go go.* .gitignore && git commit -m 'Initial commit'
gh repo create "gh-EXTENSION-NAME"
```

- Create a release to share your precompiled extension with others. Compile for each platform you want to support, attaching each binary to a release as an asset. Binary executables attached to releases must follow a naming convention and have a suffix of OS-ARCHITECTURE[EXTENSION]. For example, an extension named `whoami` compiled for Windows 64bit would have the name `gh-whoami-windows-amd64.exe` while the same extension compiled for Linux 32bit would have the name `gh-whoami-linux-386`. To see an exhaustive list of OS and architecture combinations recognized by `gh`, see [this source code](https://github.com/cli/cli/blob/14f704fd0da58cc01413ee4ba16f13f27e33d15e/pkg/cmd/extension/manager.go#L696).
> [!NOTE] For your extension to run properly on Windows, its asset file must have a `.exe` extension. No extension is needed for other operating systems.
 Releases can be created from the command line. For example:

```
git tag v1.0.0
git push origin v1.0.0
GOOS=windows GOARCH=amd64 go build -o gh-EXTENSION-NAME-windows-amd64.exe
GOOS=linux GOARCH=amd64 go build -o gh-EXTENSION-NAME-linux-amd64
GOOS=darwin GOARCH=amd64 go build -o gh-EXTENSION-NAME-darwin-amd64
gh release create v1.0.0 ./*amd64*
```

- Optionally, to help other users discover your extension, add the repository topic `gh-extension`. This will make the extension appear on the [`gh-extension` topic page](https://github.com/topics/gh-extension). For more information about how to add a repository topic, see [Classifying your repository with topics](/en/github/administering-a-repository/managing-repository-settings/classifying-your-repository-with-topics).

### Tips for writing precompiled GitHub CLI extensions

#### Automating releases

Consider adding the [gh-extension-precompile](https://github.com/cli/gh-extension-precompile) action to a workflow in your project. This action will automatically produce cross-compiled Go binaries for your extension and supplies build scaffolding for non-Go precompiled extensions.

#### Using GitHub CLI features from Go-based extensions

Consider using [go-gh](https://github.com/cli/go-gh), a Go library that exposes pieces of `gh` functionality for use in extensions.

### Next steps

To see more examples of GitHub CLI extensions, look at [repositories with the `gh-extension` topic](https://github.com/topics/gh-extension).

---

## Using GitHub CLI extensions
> Source: https://docs.github.com/en/github-cli/github-cli/using-github-cli-extensions

### About GitHub CLI extensions

> [!NOTE]
> Extensions outside of GitHub and GitHub CLI are not certified by GitHub and are governed by separate terms of service, privacy policy, and support documentation. To mitigate risk when using third-party extensions, audit the source code of the extension before installing or updating the extension.

GitHub CLI extensions are custom GitHub CLI commands that anyone can create and use. For more information about how to create GitHub CLI extensions, see [Creating GitHub CLI extensions](/en/github-cli/github-cli/creating-github-cli-extensions).

Extensions are locally installed and are scoped to the user. Therefore, if you access GitHub CLI from a different machine or another user accesses GitHub CLI from the same machine, the extension will not be available.

### Finding extensions

You can find extensions by browsing [repositories with the `gh-extension` topic](https://github.com/topics/gh-extension).

### Installing extensions

To install an extension, use the `extensions install` subcommand. Replace the `repo` parameter with the repository of the extension. You can use the full URL, such as `https://github.com/octocat/gh-whoami`, or just the owner and repository, such as `octocat/gh-whoami`.

If the owner and repository are used, `gh` will install the extension using the hostname to which `gh` is currently authenticated. The full URL format is useful when installing extensions from a different host. For example, users on GitHub Enterprise Server should use the full repository URL to install extensions from GitHub.com or any other host.

To install an extension in development from the current directory, use `.` as the value for the `repo` parameter.

```
gh extension install REPO
```

If you already have an extension by the same name installed, the command will fail. For example, if you have installed `octocat/gh-whoami`, you must uninstall it before installing `hubot/gh-whoami`.

### Running an extension

When you have installed an extension, you run the extension as you would run a native GitHub CLI command, using `gh EXTENSION-NAME`. The `EXTENSION-NAME` is the name of the repository that contains the extension, minus the `gh-` prefix.

For example, if you installed the extension from the `octocat/gh-whoami` repository, you would run the extension with the following command.

```
gh whoami
```

You can usually find specific information about how to use an extension in the README of the repository that contains the extension.

### Viewing installed extensions

To view all installed extensions, use the `extensions list` subcommand. The output will also tell you which extensions have updates available.

```
gh extension list
```

### Updating extensions

To update an extension, use the `extensions upgrade` subcommand. Replace the `extension` parameter with the name of the extension.

```
gh extension upgrade EXTENSION
```

To update all installed extensions, use the `--all` flag.

```
gh extension upgrade --all
```

### Uninstalling extensions

To uninstall an extension, use the `extensions remove` subcommand. Replace the `extension` parameter with the name of the extension.

```
gh extension remove EXTENSION
```

---

## GitHub CLI manual
> Source: https://cli.github.com/manual/

GitHub CLI, or `gh`, is a command-line interface to GitHub for use in your terminal or your scripts.

-
    [Available commands](./gh)

-
    [Usage examples](./examples)

-
    [Community extensions](https://github.com/topics/gh-extension)

### Installation

You can find installation instructions on our [README](https://github.com/cli/cli#installation).

### Configuration

-
    Run [`gh auth login`](./gh_auth_login) to authenticate with your GitHub account. Alternatively, `gh` will respect the `GITHUB_TOKEN` [environment variable](./gh_help_environment).

-
    To set your preferred editor, use `gh config set editor <editor>`. Read more about [`gh config`](./gh_config) and [environment variables](./gh_help_environment).

-
    Declare your aliases for often-used commands with [`gh alias set`](./gh_alias_set).

### GitHub Enterprise

GitHub CLI supports GitHub Enterprise Server 2.20 and above. To authenticate with a GitHub instance, run:

```
gh auth login --hostname
```

To define this host as a default for all GitHub CLI commands, set the GH_HOST environment variable:

```
export GH_HOST=
```

Finally, to authenticate commands in scripting mode or automation, set the GH_ENTERPRISE_TOKEN:

```
export GH_ENTERPRISE_TOKEN=
```

### Support

-
    Ask usage questions and send us feedback in [Discussions](https://github.com/cli/cli/discussions)

-
    Report bugs or search for existing feature requests in our [issue tracker](https://github.com/cli/cli/issues)

---

## gh api
> Source: https://cli.github.com/manual/gh_api

```
gh api  [flags]
```

Makes an authenticated HTTP request to the GitHub API and prints the response.

The endpoint argument should either be a path of a GitHub API v3 endpoint, or
`graphql` to access the GitHub API v4.

Placeholder values `{owner}`, `{repo}`, and `{branch}` in the endpoint
argument will get replaced with values from the repository of the current
directory or the repository specified in the `GH_REPO` environment variable.
Note that in some shells, for example PowerShell, you may need to enclose
any value that contains `{...}` in quotes to prevent the shell from
applying special meaning to curly braces.

The `-p/--preview` flag enables opting into previews, which are feature-flagged,
experimental API endpoints or behaviors. The API expects opt-in via the `Accept`
header with format `application/vnd.github.<preview-name>-preview+json` and this
command facilitates that via `--preview <preview-name>`. To send a request for
the corsair and scarlet witch previews, you could use `-p corsair,scarlet-witch`
or `--preview corsair --preview scarlet-witch`.

The default HTTP request method is `GET` normally and `POST` if any parameters
were added. Override the method with `--method`.

Pass one or more `-f/--raw-field` values in `key=value` format to add static string
parameters to the request payload. To add non-string or placeholder-determined values, see
`-F/--field` below. Note that adding request parameters will automatically switch the
request method to `POST`. To send the parameters as a `GET` query string instead, use
`--method GET`.

The `-F/--field` flag has magic type conversion based on the format of the value:

- literal values `true`, `false`, `null`, and integer numbers get converted to
appropriate JSON types;

- placeholder values `{owner}`, `{repo}`, and `{branch}` get populated with values
from the repository of the current directory;

- if the value starts with `@`, the rest of the value is interpreted as a
filename to read the value from. Pass `-` to read from standard input.

For GraphQL requests, all fields other than `query` and `operationName` are
interpreted as GraphQL variables.

To pass nested parameters in the request payload, use `key[subkey]=value` syntax when
declaring fields. To pass nested values as arrays, declare multiple fields with the
syntax `key[]=value1`, `key[]=value2`. To pass an empty array, use `key[]` without a
value.

To pass pre-constructed JSON or payloads in other formats, a request body may be read
from file specified by `--input`. Use `-` to read from standard input. When passing the
request body this way, any parameters specified via field flags are added to the query
string of the endpoint URL.

In `--paginate` mode, all pages of results will sequentially be requested until
there are no more pages of results. For GraphQL requests, this requires that the
original query accepts an `$endCursor: String` variable and that it fetches the
`pageInfo{ hasNextPage, endCursor }` set of fields from a collection. Each page is a separate
JSON array or object. Pass `--slurp` to wrap all pages of JSON arrays or objects
into an outer JSON array.

#### Options

- `--cache <duration>`
	: Cache the response, e.g. "3600s", "60m", "1h"

- `-F`, `--field <key=value>`
	: Add a typed parameter in key=value format (use "@<path>" or "@-" to read value from file or stdin)

- `-H`, `--header <key:value>`
	: Add a HTTP request header in key:value format

- `--hostname <string>`
	: The GitHub hostname for the request (default "github.com")

- `-i`, `--include`
	: Include HTTP response status line and headers in the output

- `--input <file>`
	: The file to use as body for the HTTP request (use "-" to read from standard input)

- `-q`, `--jq <string>`
	: Query to select values from the response using jq syntax

- `-X`, `--method <string> (default "GET")`
	: The HTTP method for the request

- `--paginate`
	: Make additional HTTP requests to fetch all pages of results

- `-p`, `--preview <strings>`
	: Opt into GitHub API previews (names should omit '-preview')

- `-f`, `--raw-field <key=value>`
	: Add a string parameter in key=value format

- `--silent`
	: Do not print the response body

- `--slurp`
	: Use with "--paginate" to return an array of all pages of either JSON arrays or objects

- `-t`, `--template <string>`
	: Format JSON output using a Go template; see "gh help formatting"

- `--verbose`
	: Include full HTTP request and response in the output

#### Examples

```
# List releases in the current repository
$ gh api repos/{owner}/{repo}/releases

# Post an issue comment
$ gh api repos/{owner}/{repo}/issues/123/comments -f body='Hi from CLI'

# Post nested parameter read from a file
$ gh api gists -F 'files[myfile.txt][content]=@myfile.txt'

# Add parameters to a GET request
$ gh api -X GET search/issues -f q='repo:cli/cli is:open remote'

# Use a JSON file as request body
$ gh api repos/{owner}/{repo}/rulesets --input file.json

# Set a custom HTTP header
$ gh api -H 'Accept: application/vnd.github.v3.raw+json' ...

# Opt into GitHub API previews
$ gh api --preview baptiste,nebula ...

# Print only specific fields from the response
$ gh api repos/{owner}/{repo}/issues --jq '.[].title'

# Use a template for the output
$ gh api repos/{owner}/{repo}/issues --template \
  '{{range .}}{{.title}} ({{.labels | pluck "name" | join ", " | color "yellow"}}){{"\n"}}{{end}}'

# Update allowed values of the "environment" custom property in a deeply nested array
$ gh api -X PATCH /orgs/{org}/properties/schema \
   -F 'properties[][property_name]=environment' \
   -F 'properties[][default_value]=production' \
   -F 'properties[][allowed_values][]=staging' \
   -F 'properties[][allowed_values][]=production'

# List releases with GraphQL
$ gh api graphql -F owner='{owner}' -F name='{repo}' -f query='
  query($name: String!, $owner: String!) {
    repository(owner: $owner, name: $name) {
      releases(last: 3) {
        nodes { tagName }
      }
    }
  }
'

# List all repositories for a user
$ gh api graphql --paginate -f query='
  query($endCursor: String) {
    viewer {
      repositories(first: 100, after: $endCursor) {
        nodes { nameWithOwner }
        pageInfo {
          hasNextPage
          endCursor
        }
      }
    }
  }
'

# Get the percentage of forks for the current user
$ gh api graphql --paginate --slurp -f query='
  query($endCursor: String) {
    viewer {
      repositories(first: 100, after: $endCursor) {
        nodes { isFork }
        pageInfo {
          hasNextPage
          endCursor
        }
      }
    }
  }
' | jq 'def count(e): reduce e as $_ (0;.+1);
[.[].data.viewer.repositories.nodes[]] as $r | count(select($r[].isFork))/count($r[])'
```

#### See also

- [gh](./gh)

---

## gh help formatting
> Source: https://cli.github.com/manual/gh_help_formatting

By default, the result of `gh` commands are output in line-based plain text format.
Some commands support passing the `--json` flag, which converts the output to JSON format.
Once in JSON, the output can be further formatted according to a required formatting string by
adding either the `--jq` or `--template` flag. This is useful for selecting a subset of data,
creating new data structures, displaying the data in a different format, or as input to another
command line script.

The `--json` flag requires a comma separated list of fields to fetch. To view the possible JSON
field names for a command omit the string argument to the `--json` flag when you run the command.
Note that you must pass the `--json` flag and field names to use the `--jq` or `--template` flags.

The `--jq` flag requires a string argument in jq query syntax, and will only print
those JSON values which match the query. jq queries can be used to select elements from an
array, fields from an object, create a new array, and more. The `jq` utility does not need
to be installed on the system to use this formatting directive. When connected to a terminal,
the output is automatically pretty-printed. To learn about jq query syntax, see:
[https://jqlang.github.io/jq/manual/](https://jqlang.github.io/jq/manual/)

The `--template` flag requires a string argument in Go template syntax, and will only print
those JSON values which match the query.

In addition to the Go template functions in the standard library, the following functions can be used
with this formatting directive:

- `autocolor`: like `color`, but only emits color to terminals

- `color <style> <input>`: colorize input using [https://github.com/mgutz/ansi](https://github.com/mgutz/ansi)

- `join <sep> <list>`: joins values in the list using a separator

- `pluck <field> <list>`: collects values of a field from all items in the input

- `tablerow <fields>...`: aligns fields in output vertically as a table

- `tablerender`: renders fields added by tablerow in place

- `timeago <time>`: renders a timestamp as relative to now

- `timefmt <format> <time>`: formats a timestamp using Go's `Time.Format` function

- `truncate <length> <input>`: ensures input fits within length

- `hyperlink <url> <text>`: renders a terminal hyperlink

The following Sprig template library functions can also be used with this formatting directive:

- `contains <arg> <string>`: checks if `string` contains `arg`

- `hasPrefix <prefix> <string>`: checks if `string` starts with `prefix`

- `hasSuffix <suffix> <string>`: checks if `string` ends with `suffix`

- `regexMatch <regex> <string>`: checks if `string` has any matches for `regex`

For more information about the Sprig library, see [https://masterminds.github.io/sprig/](https://masterminds.github.io/sprig/).

To learn more about Go templates, see: [https://golang.org/pkg/text/template/](https://golang.org/pkg/text/template/).

#### Examples

```
# Default output format
$ gh pr list
Showing 23 of 23 open pull requests in cli/cli

#123  A helpful contribution          contribution-branch              about 1 day ago
#124  Improve the docs                docs-branch                      about 2 days ago
#125  An exciting new feature         feature-branch                   about 2 days ago

# Adding the --json flag with a list of field names
$ gh pr list --json number,title,author
[
  {
    "author": {
      "login": "monalisa"
    },
    "number": 123,
    "title": "A helpful contribution"
  },
  {
    "author": {
      "login": "codercat"
    },
    "number": 124,
    "title": "Improve the docs"
  },
  {
    "author": {
      "login": "cli-maintainer"
    },
    "number": 125,
    "title": "An exciting new feature"
  }
]

# Adding the --jq flag and selecting fields from the array
$ gh pr list --json author --jq '.[].author.login'
monalisa
codercat
cli-maintainer

# --jq can be used to implement more complex filtering and output changes
$ gh issue list --json number,title,labels --jq \
  'map(select((.labels | length) > 0))    # must have labels
  | map(.labels = (.labels | map(.name))) # show only the label names
  | .[:3]                                 # select the first 3 results'
  [
    {
      "labels": [
        "enhancement",
        "needs triage"
      ],
      "number": 123,
      "title": "A helpful contribution"
    },
    {
      "labels": [
        "help wanted",
        "docs",
        "good first issue"
      ],
      "number": 125,
      "title": "Improve the docs"
    },
    {
      "labels": [
        "enhancement",
      ],
      "number": 7221,
      "title": "An exciting new feature"
    }
  ]

# Using the --template flag with the hyperlink helper
$ gh issue list --json title,url --template '{{range .}}{{hyperlink .url .title}}{{"\n"}}{{end}}'

# Adding the --template flag and modifying the display format
$ gh pr list --json number,title,headRefName,updatedAt --template \
	'{{range .}}{{tablerow (printf "#%v" .number | autocolor "green") .title .headRefName (timeago .updatedAt)}}{{end}}'

#123  A helpful contribution      contribution-branch       about 1 day ago
#124  Improve the docs            docs-branch               about 2 days ago
#125  An exciting new feature     feature-branch            about 2 days ago

# A more complex example with the --template flag which formats a pull request using multiple tables with headers
$ gh pr view 3519 --json number,title,body,reviews,assignees --template \
'{{printf "#%v" .number}} {{.title}}

{{.body}}

{{tablerow "ASSIGNEE" "NAME"}}{{range .assignees}}{{tablerow .login .name}}{{end}}{{tablerender}}
{{tablerow "REVIEWER" "STATE" "COMMENT"}}{{range .reviews}}{{tablerow .author.login .state .body}}{{end}}
'

#3519 Add table and helper template functions

Resolves #3488

ASSIGNEE  NAME
mislav    Mislav Marohnić

REVIEWER  STATE              COMMENT
mislav    COMMENTED          This is going along great! Thanks for working on this ❤️
```

#### See also

- [gh](./gh)

---

## gh help environment
> Source: https://cli.github.com/manual/gh_help_environment

`GH_TOKEN`, `GITHUB_TOKEN` (in order of precedence): an authentication token that will be used when
a command targets either `github.com` or a subdomain of `ghe.com`. Setting this avoids being prompted to
authenticate and takes precedence over previously stored credentials.

`GH_ENTERPRISE_TOKEN`, `GITHUB_ENTERPRISE_TOKEN` (in order of precedence): an authentication
token that will be used when a command targets a GitHub Enterprise Server host.

`GH_HOST`: specify the GitHub hostname for commands where a hostname has not been provided, or
cannot be inferred from the context of a local Git repository. If this host was previously
authenticated with, the stored credentials will be used. Otherwise, setting `GH_TOKEN` or
`GH_ENTERPRISE_TOKEN` is required, depending on the targeted host.

`GH_REPO`: specify the GitHub repository in the `[HOST/]OWNER/REPO` format for commands
that otherwise operate on a local repository.

`GH_EDITOR`, `GIT_EDITOR`, `VISUAL`, `EDITOR` (in order of precedence): the editor tool to use
for authoring text.

`GH_BROWSER`, `BROWSER` (in order of precedence): the web browser to use for opening links.

`GH_DEBUG`: set to a truthy value to enable verbose output on standard error. Set to `api`
to additionally log details of HTTP traffic.

`DEBUG` (deprecated): set to `1`, `true`, or `yes` to enable verbose output on standard
error.

`GH_PAGER`, `PAGER` (in order of precedence): a terminal paging program to send standard output
to, e.g. `less`.

`GLAMOUR_STYLE`: the style to use for rendering Markdown. See
[https://github.com/charmbracelet/glamour#styles](https://github.com/charmbracelet/glamour#styles)

`NO_COLOR`: set to any value to avoid printing ANSI escape sequences for color output.

`CLICOLOR`: set to `0` to disable printing ANSI colors in output.

`CLICOLOR_FORCE`: set to a value other than `0` to keep ANSI colors in output
even when the output is piped.

`GH_COLOR_LABELS`: set to any value to display labels using their RGB hex color codes in terminals that
support truecolor.

`GH_ACCESSIBLE_COLORS` (preview): set to a truthy value to use customizable, 4-bit accessible colors.

`GH_FORCE_TTY`: set to any value to force terminal-style output even when the output is
redirected. When the value is a number, it is interpreted as the number of columns
available in the viewport. When the value is a percentage, it will be applied against
the number of columns available in the current viewport.

`GH_NO_UPDATE_NOTIFIER`: set to any value to disable GitHub CLI update notifications.
When any command is executed, gh checks for new versions once every 24 hours.
If a newer version was found, an upgrade notice is displayed on standard error.

`GH_NO_EXTENSION_UPDATE_NOTIFIER`: set to any value to disable GitHub CLI extension update notifications.
When an extension is executed, gh checks for new versions for the executed extension once every 24 hours.
If a newer version was found, an upgrade notice is displayed on standard error.

`GH_CONFIG_DIR`: the directory where gh will store configuration files. If not specified,
the default value will be one of the following paths (in order of precedence):

- `$XDG_CONFIG_HOME/gh` (if `$XDG_CONFIG_HOME` is set),

- `$AppData/GitHub CLI` (on Windows if `$AppData` is set), or

- `$HOME/.config/gh`.

`GH_PROMPT_DISABLED`: set to any value to disable interactive prompting in the terminal.

`GH_PATH`: set the path to the gh executable, useful for when gh can not properly determine
its own path such as in the cygwin terminal.

`GH_MDWIDTH`: default maximum width for markdown render wrapping.  The max width of lines
wrapped on the terminal will be taken as the lesser of the terminal width, this value, or 120 if
not specified.  This value is used, for example, with `pr view` subcommand.

`GH_ACCESSIBLE_PROMPTER` (preview): set to a truthy value to enable prompts that are
more compatible with speech synthesis and braille screen readers.

`GH_TELEMETRY`: set to `log` to print telemetry data to standard error instead of sending it.
Set to `false` or `0` to disable telemetry. Takes precedence over `DO_NOT_TRACK`.

`DO_NOT_TRACK`: set to `true` or `1` to disable telemetry. Ignored when
`GH_TELEMETRY` is set, which takes precedence.

`GH_SPINNER_DISABLED`: set to a truthy value to replace the spinner animation with
a textual progress indicator.

#### See also

- [gh](./gh)
