# GitHub Pages

> **Source root:** https://docs.github.com/en/pages
> **Fetched:** 2026-05-26
> **Area:** 06 — Pages

## Table of contents

- [GitHub Pages documentation (landing)](#github-pages-documentation-landing)
- [What is GitHub Pages?](#what-is-github-pages)
- [Creating a GitHub Pages site](#creating-a-github-pages-site)
- [Configuring a publishing source for your GitHub Pages site](#configuring-a-publishing-source-for-your-github-pages-site)
- [Using custom workflows with GitHub Pages](#using-custom-workflows-with-github-pages)
- [About custom domains and GitHub Pages](#about-custom-domains-and-github-pages)
- [About GitHub Pages and Jekyll](#about-github-pages-and-jekyll)

---

## GitHub Pages documentation (landing)

> Source: https://docs.github.com/en/pages

GitHub Pages turns any GitHub repository into a live website—no separate hosting required.

- [Quickstart](https://docs.github.com/pages/quickstart)
- [Overview](https://docs.github.com/pages/getting-started-with-github-pages/what-is-github-pages)

**Articles**

- **[About custom domains and GitHub Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages)** — _Learn about GitHub Pages_
  GitHub Pages supports using custom domains, or changing the root of your site's URL from the default, like octocat.github.io, to any domain you own.
- **[About GitHub Pages and Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll)** — _Learn about GitHub Pages_
  Jekyll is a static site generator with built-in support for GitHub Pages.
- **[About Jekyll build errors for GitHub Pages sites](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-jekyll-build-errors-for-github-pages-sites)** — _Set up a GitHub Pages site_
  If Jekyll encounters an error building your GitHub Pages site locally or on GitHub, you'll receive an error message with more information.
- **[Adding a theme to your GitHub Pages site using Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll)** — _Set up a GitHub Pages site_
  You can personalize your Jekyll site by adding and customizing a theme.
- **[Adding content to your GitHub Pages site using Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-content-to-your-github-pages-site-using-jekyll)** — _Managing a GitHub Pages site_
  You can add a new page or post to your Jekyll site on GitHub Pages.
- **[Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)** — _Set up a GitHub Pages site_
  You can configure your GitHub Pages site to publish when changes are pushed to a specific branch, or you can write a GitHub Actions workflow to publish your site.
- **[Creating a custom 404 page for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-custom-404-page-for-your-github-pages-site)** — _Set up a GitHub Pages site_
  You can display a custom 404 error page when people try to access nonexistent pages on your site.
- **[Creating a GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)** — _Set up a GitHub Pages site_
  You can create a GitHub Pages site in a new or existing repository.
- **[Creating a GitHub Pages site with Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll)** — _Set up a GitHub Pages site_
  You can use Jekyll to create a GitHub Pages site in a new or existing repository.

_(The landing page lists additional articles across paginated results; the cards above are those rendered in the initial server response.)_

---

## What is GitHub Pages?

> Source: https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages

You can use GitHub Pages to host a website about yourself, your organization, or your project directly from a repository on GitHub.

**Who can use this feature?**

GitHub Pages is available in public repositories with GitHub Free and GitHub Free for organizations, and in public and private repositories with GitHub Pro, GitHub Team, GitHub Enterprise Cloud, and GitHub Enterprise Server. For more information, see [GitHub's plans](https://docs.github.com/en/get-started/learning-about-github/githubs-plans).

## About GitHub Pages

GitHub Pages is a static site hosting service that takes HTML, CSS, and JavaScript files straight from a repository on GitHub, optionally runs the files through a build process, and publishes a website. You can see examples of GitHub Pages sites in the [GitHub Pages examples collection](https://github.com/collections/github-pages-examples).

## Types of GitHub Pages sites

There are two types of GitHub Pages sites. Sites associated with a user or organization account, and sites for a specific project.

| Property | User and organization sites | Project sites |
|----|----|----|
| Source files | Must be stored in a repository named `<owner>.github.io`, where `<owner>` is the personal or organization account name | Stored in a folder within the repository that contains the project's code |
| Limits | Maximum of one pages site per account | Maximum of one pages site per repository |
| Default site location | `http(s)://<owner>.github.io` | `http(s)://<owner>.github.io/<repositoryname>` |

### Hosting on your own custom domain

You can host your site on GitHub's `github.io` domain or your own custom domain. See [Configuring a custom domain for your GitHub Pages site](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

## Data collection

When a GitHub Pages site is visited, the visitor's IP address is logged and stored for security purposes, regardless of whether the visitor has signed into GitHub or not. For more information about GitHub's security practices, see [GitHub Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-privacy-statement).

## Further reading

- [GitHub Pages](https://github.com/skills/github-pages) on GitHub Skills
- [REST API endpoints for repositories](https://docs.github.com/en/rest/repos#pages)
- [Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [About custom domains and GitHub Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages#using-a-custom-domain-across-multiple-repositories)

---

## Creating a GitHub Pages site

> Source: https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site

You can create a GitHub Pages site in a new or existing repository.

**Who can use this feature?**

GitHub Pages is available in public repositories with GitHub Free and GitHub Free for organizations, and in public and private repositories with GitHub Pro, GitHub Team, GitHub Enterprise Cloud, and GitHub Enterprise Server. For more information, see [GitHub's plans](https://docs.github.com/en/get-started/learning-about-github/githubs-plans).

## Creating a repository for your site

You can either create a repository or choose an existing repository for your site.

If you want to create a GitHub Pages site for a repository where not all of the files in the repository are related to the site, you will be able to configure a publishing source for your site. For example, you can have a dedicated branch and folder to hold your site source files, or you can use a custom GitHub Actions workflow to build and deploy your site source files.

If the account that owns the repository uses GitHub Free or GitHub Free for organizations, the repository must be public.

If you want to create a site in an existing repository, skip to the [Creating your site](#creating-your-site) section.

1.  In the upper-right corner of any page, select (Create something new), then click **New repository**.

    ![Screenshot of a GitHub dropdown menu showing options to create new items. The menu item "New repository" is outlined in dark orange.](https://docs.github.com/assets/cb-29762/images/help/repository/repo-create-global-nav-update.png)

2.  Use the **Owner** dropdown menu to select the account you want to own the repository. ![Screenshot of the owner menu for a new GitHub repository. The menu shows two options, octocat and github.](https://docs.github.com/assets/cb-80933/images/help/repository/create-repository-owner.png)

3.  Type a name for your repository and an optional description. If you're creating a user or organization site, your repository must be named `<user>.github.io` or `<organization>.github.io`. If your user or organization name contains uppercase letters, you must lowercase the letters. For more information, see [What is GitHub Pages?](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages#types-of-github-pages-sites). ![Screenshot of GitHub Pages settings in a repository. The repository name field contains the text "octocat.github.io" and is outlined in dark orange.](https://docs.github.com/assets/cb-48480/images/help/pages/create-repository-name-pages.png)

4.  Choose a repository visibility. For more information, see [About repositories](https://docs.github.com/en/repositories/creating-and-managing-repositories/about-repositories#about-repository-visibility).

5.  Toggle **Add README** to **On**.

6.  Click **Create repository**.

## Creating your site

Before you can create your site, you must have a repository for your site on GitHub. If you're not creating your site in an existing repository, see [Creating a repository for your site](#creating-a-repository-for-your-site).

> [!WARNING]
> GitHub Pages sites are publicly available on the internet, even if the repository for the site is private (if your plan or organization allows it). If you have sensitive data in your site's repository, you may want to remove the data before publishing. For more information, see [About repositories](https://docs.github.com/en/repositories/creating-and-managing-repositories/about-repositories#about-repository-visibility).

1.  On GitHub, navigate to your site's repository.

2.  Decide which publishing source you want to use. See [Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

3.  Create the entry file for your site. GitHub Pages will look for an `index.html`, `index.md`, or `README.md` file as the entry file for your site.

    If your publishing source is a branch and folder, the entry file must be at the top level of the source folder on the source branch. For example, if your publishing source is the `/docs` folder on the `main` branch, your entry file must be located in the `/docs` folder on a branch called `main`.

    If your publishing source is a GitHub Actions workflow, the artifact that you deploy must include the entry file at the top level of the artifact. Instead of adding the entry file to your repository, you may choose to have your GitHub Actions workflow generate your entry file when the workflow runs.

4.  Configure your publishing source. See [Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

5.  Your GitHub Pages site is built and deployed with a GitHub Actions workflow. For more information, see [Viewing workflow run history](https://docs.github.com/en/actions/monitoring-and-troubleshooting-workflows/viewing-workflow-run-history).

    > [!NOTE]
    > GitHub Actions is free for public repositories. Usage charges apply for private and internal repositories that go beyond the monthly allotment of free minutes. For more information, see [Billing and usage](https://docs.github.com/en/actions/learn-github-actions/usage-limits-billing-and-administration).

## Viewing your published site

1.  Under your repository name, click **(gear) Settings**. If you cannot see the "Settings" tab, select the **(More)** dropdown menu, then click **Settings**.

    ![Screenshot of a repository header showing the tabs. The "Settings" tab is highlighted by a dark orange outline.](https://docs.github.com/assets/cb-28260/images/help/repository/repo-actions-settings.png)

2.  In the "Code and automation" section of the sidebar, click **(browser) Pages**.

3.  To see your published site, under "GitHub Pages," click **(link-external) Visit site**.

> [!NOTE]
> It can take up to 10 minutes for changes to your site to publish after you push the changes to GitHub. If you don't see your GitHub Pages site changes reflected in your browser after an hour, see [About Jekyll build errors for GitHub Pages sites](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-jekyll-build-errors-for-github-pages-sites).
>
> - If you are publishing from a branch and your site has not published automatically, make sure someone with admin permissions and a verified email address has pushed to the publishing source.
> - Commits pushed by a GitHub Actions workflow that uses the `GITHUB_TOKEN` do not trigger a GitHub Pages build.

## Static site generators

GitHub Pages publishes any static files that you push to your repository. You can create your own static files or use a static site generator to build your site for you. You can also customize your own build process locally or on another server.

If you use a custom build process or a static site generator other than Jekyll, you can write a GitHub Actions workflow to build and publish your site. GitHub provides workflow templates for several static site generators. For more information, see [Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

If you publish your site from a source branch, GitHub Pages will use Jekyll to build your site by default. If you want to use a static site generator other than Jekyll, we recommend that you write a GitHub Actions to build and publish your site instead. Otherwise, disable the Jekyll build process by creating an empty file called `.nojekyll` in the root of your publishing source, then follow your static site generator's instructions to build your site locally.

> [!NOTE]
> GitHub Pages does not support server-side languages such as PHP, Ruby, or Python.

## MIME types on GitHub Pages

A MIME type is a header that a server sends to a browser, providing information about the nature and format of the files the browser requested. GitHub Pages supports more than 750 MIME types across thousands of file extensions. The list of supported MIME types is generated from the [mime-db project](https://github.com/jshttp/mime-db).

While you can't specify custom MIME types on a per-file or per-repository basis, you can add or modify MIME types for use on GitHub Pages. For more information, see [the mime-db contributing guidelines](https://github.com/jshttp/mime-db#adding-custom-media-types).

## Next steps

You can add more pages to your site by creating more new files. Each file will be available on your site in the same directory structure as your publishing source. For example, if the publishing source for your project site is the `gh-pages` branch, and you create a new file called `/about/contact-us.md` on the `gh-pages` branch, the file will be available at `https://<user>.github.io/<repository>/about/contact-us.html`.

You can also add a theme to customize your site’s look and feel. For more information, see [Adding a theme to your GitHub Pages site using Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll).

## Further reading

- [About GitHub Pages and Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll).
- [Troubleshooting Jekyll build errors for GitHub Pages sites](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/troubleshooting-jekyll-build-errors-for-github-pages-sites)
- [Creating and deleting branches within your repository](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository)
- [Creating new files](https://docs.github.com/en/repositories/working-with-files/managing-files/creating-new-files)
- [Troubleshooting 404 errors for GitHub Pages sites](https://docs.github.com/en/pages/getting-started-with-github-pages/troubleshooting-404-errors-for-github-pages-sites)

---

## Configuring a publishing source for your GitHub Pages site

> Source: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

You can configure your GitHub Pages site to publish when changes are pushed to a specific branch, or you can write a GitHub Actions workflow to publish your site.

**Who can use this feature?**

GitHub Pages is available in public repositories with GitHub Free and GitHub Free for organizations, and in public and private repositories with GitHub Pro, GitHub Team, GitHub Enterprise Cloud, and GitHub Enterprise Server. For more information, see [GitHub's plans](https://docs.github.com/en/get-started/learning-about-github/githubs-plans).

## About publishing sources

You can publish your site when changes are pushed to a specific branch, or you can write a GitHub Actions workflow to publish your site.

If you do not need any control over the build process for your site, we recommend that you publish your site when changes are pushed to a specific branch. You can specify which branch and folder to use as your publishing source. The source branch can be any branch in your repository, and the source folder can either be the root of the repository (`/`) on the source branch or a `/docs` folder on the source branch. Whenever changes are pushed to the source branch, the changes in the source folder will be published to your GitHub Pages site.

If you want to use a build process other than Jekyll or you do not want a dedicated branch to hold your compiled static files, we recommend that you write a GitHub Actions workflow to publish your site. GitHub provides workflow templates for common publishing scenarios to help you write your workflow.

> [!WARNING]
> GitHub Pages sites are publicly available on the internet, even if the repository for the site is private (if your plan or organization allows it). If you have sensitive data in your site's repository, you may want to remove the data before publishing. For more information, see [About repositories](https://docs.github.com/en/repositories/creating-and-managing-repositories/about-repositories#about-repository-visibility).

## Publishing from a branch

1.  Make sure the branch you want to use as your publishing source already exists in your repository.

2.  On GitHub, navigate to your site's repository.

3.  Under your repository name, click **(gear) Settings**. If you cannot see the "Settings" tab, select the **(More)** dropdown menu, then click **Settings**.

    ![Screenshot of a repository header showing the tabs. The "Settings" tab is highlighted by a dark orange outline.](https://docs.github.com/assets/cb-28260/images/help/repository/repo-actions-settings.png)

4.  In the "Code and automation" section of the sidebar, click **(browser) Pages**.

5.  Under "Build and deployment", under "Source", select **Deploy from a branch**.

6.  Under "Build and deployment", use the branch dropdown menu and select a publishing source. ![Screenshot of Pages settings in a GitHub repository. A menu to select a branch for a publishing source, labeled "None," is outlined in dark orange.](https://docs.github.com/assets/cb-47265/images/help/pages/publishing-source-drop-down.png)

7.  Optionally, use the folder dropdown menu to select a folder for your publishing source. ![Screenshot of Pages settings in a GitHub repository. A menu to select a folder for a publishing source, labeled "/(root)," is outlined in dark orange.](https://docs.github.com/assets/cb-24510/images/help/pages/publishing-source-folder-drop-down.png)

8.  Click **Save**.

### Troubleshooting publishing from a branch

> [!NOTE]
> If your repository contains symbolic links, you will need to publish your site using a GitHub Actions workflow. For more information about GitHub Actions, see [GitHub Actions documentation](https://docs.github.com/en/actions).

> [!NOTE]
> - If you are publishing from a branch and your site has not published automatically, make sure someone with admin permissions and a verified email address has pushed to the publishing source.
> - Commits pushed by a GitHub Actions workflow that uses the `GITHUB_TOKEN` do not trigger a GitHub Pages build.

If you choose the `docs` folder on any branch as your publishing source, then later remove the `/docs` folder from that branch in your repository, your site won't build and you'll get a page build error message for a missing `/docs` folder. For more information, see [Troubleshooting Jekyll build errors for GitHub Pages sites](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/troubleshooting-jekyll-build-errors-for-github-pages-sites#missing-docs-folder).

Your GitHub Pages site will always be deployed with a GitHub Actions workflow run, even if you've configured your GitHub Pages site to be built using a different CI tool. Most external CI workflows "deploy" to GitHub Pages by committing the build output to the `gh-pages` branch of the repository, and typically include a `.nojekyll` file. When this happens, the GitHub Actions workflow will detect the state that the branch does not need a build step, and will execute only the steps necessary to deploy the site to GitHub Pages servers.

To find potential errors with either the build or deployment, you can check the workflow run for your GitHub Pages site by reviewing your repository's workflow runs. For more information, see [Viewing workflow run history](https://docs.github.com/en/actions/monitoring-and-troubleshooting-workflows/viewing-workflow-run-history). For more information about how to re-run the workflow in case of an error, see [Re-running workflows and jobs](https://docs.github.com/en/actions/managing-workflow-runs/re-running-workflows-and-jobs).

## Publishing with a custom GitHub Actions workflow

To configure your site to publish with GitHub Actions:

1.  On GitHub, navigate to your site's repository.

2.  Under your repository name, click **(gear) Settings**. If you cannot see the "Settings" tab, select the **(More)** dropdown menu, then click **Settings**.

    ![Screenshot of a repository header showing the tabs. The "Settings" tab is highlighted by a dark orange outline.](https://docs.github.com/assets/cb-28260/images/help/repository/repo-actions-settings.png)

3.  In the "Code and automation" section of the sidebar, click **(browser) Pages**.

4.  Under "Build and deployment", under "Source", select **GitHub Actions**.

5.  GitHub will suggest several workflow templates. If you already have a workflow to publish your site, you can skip this step. Otherwise, choose one of the options to create a GitHub Actions workflow. For more information about creating your custom workflow, see [Creating a custom GitHub Actions workflow to publish your site](#creating-a-custom-github-actions-workflow-to-publish-your-site).

    GitHub Pages does not associate a specific workflow to the GitHub Pages settings. However, the GitHub Pages settings will link to the workflow run that most recently deployed your site.

### Creating a custom GitHub Actions workflow to publish your site

For more information about GitHub Actions, see [GitHub Actions documentation](https://docs.github.com/en/actions).

When you configure your site to publish with GitHub Actions, GitHub will suggest workflow templates for common publishing scenarios. The general flow of a workflow is to:

1.  Trigger whenever there is a push to the default branch of the repository or whenever the workflow is run manually from the Actions tab.
2.  Use the [`actions/checkout`](https://github.com/actions/checkout) action to check out the repository contents.
3.  If required by your site, build any static site files.
4.  Use the [`actions/upload-pages-artifact`](https://github.com/actions/upload-pages-artifact) action to upload the static files as an artifact.
5.  If the workflow was triggered by a push to the default branch, use the [`actions/deploy-pages`](https://github.com/actions/deploy-pages) action to deploy the artifact. This step is skipped if the workflow was triggered by a pull request.

The workflow templates use a deployment environment called `github-pages`. If your repository does not already include an environment called `github-pages`, the environment will be created automatically. We recommend that you add a deployment protection rule so that only the default branch can deploy to this environment. For more information, see [Managing environments for deployment](https://docs.github.com/en/actions/deployment/targeting-different-environments/using-environments-for-deployment).

> [!NOTE]
> A `CNAME` file in your repository file does not automatically add or remove a custom domain. Instead, you must configure the custom domain through your repository settings or through the API. For more information, see [Managing a custom domain for your GitHub Pages site](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-a-subdomain) and [REST API endpoints for GitHub Pages](https://docs.github.com/en/rest/pages#update-information-about-a-github-pages-site).

### Troubleshooting publishing with a custom GitHub Actions workflow

For information about how to troubleshoot your GitHub Actions workflow, see [Monitor workflows](https://docs.github.com/en/actions/monitoring-and-troubleshooting-workflows/about-monitoring-and-troubleshooting).

---

## Using custom workflows with GitHub Pages

> Source: https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages

You can take advantage of using GitHub Actions and GitHub Pages by creating a workflow file or choosing from the predefined workflows.

**Who can use this feature?**

GitHub Pages is available in public repositories with GitHub Free and GitHub Free for organizations, and in public and private repositories with GitHub Pro, GitHub Team, GitHub Enterprise Cloud, and GitHub Enterprise Server. For more information, see [GitHub's plans](https://docs.github.com/en/get-started/learning-about-github/githubs-plans).

## About custom workflows

Custom workflows allow GitHub Pages sites to be built via the use of GitHub Actions. You can still select the branch you would like to use via the workflow file, but you are able to do much more with the use of custom workflows. To start using custom workflows you must first enable them for your current repository. For more information, see [Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow).

## Configuring the configure-pages action

GitHub Actions enables the use of GitHub Pages through the `configure-pages` action, which also lets you gather different metadata about a website. For more information, see the [`configure-pages`](https://github.com/marketplace/actions/configure-github-pages) action.

To use the action place this snippet under your `jobs` in the desired workflow.

```yaml
- name: Configure GitHub Pages
  uses: actions/configure-pages@v5
```

This action helps support deployment from any static site generator to GitHub Pages. To make this process less repetitive you can use workflow templates for some of the most widely used static site generators. For more information, see [Using workflow templates](https://docs.github.com/en/actions/learn-github-actions/using-starter-workflows).

## Configuring the upload-pages-artifact action

The `upload-pages-artifact` actions enables you to package and upload artifacts. The GitHub Pages artifact should be a compressed `gzip` archive containing a single `tar` file. The `tar` file must be under 10GB in size and should not contain any symbolic or hard links. For more information, see the [`upload-pages-artifact`](https://github.com/marketplace/actions/upload-github-pages-artifact) action.

To use the action in your current workflow place this snippet under `jobs`.

```yaml
- name: Upload GitHub Pages artifact
  uses: actions/upload-pages-artifact@v4
```

## Deploying GitHub Pages artifacts

The `deploy-pages` action handles the necessary setup for deploying artifacts. To ensure proper functionality, the following requirements should be met:

- The job must have a minimum of `pages: write` and `id-token: write` permissions.
- The `needs` parameter must be set to the `id` of the build step. Not setting this parameter may result in an independent deployment that continuously searches for an artifact that hasn't been created.
- An `environment` must be established to enforce branch/deployment protection rules. The default environment is `github-pages`.
- To specify the URL of the page as an output, utilize the `url:` field.

For more information, see the [`deploy-pages`](https://github.com/marketplace/actions/deploy-github-pages-site) action.

```yaml
# ...

jobs:
  deploy:
    permissions:
      contents: read
      pages: write
      id-token: write
    runs-on: ubuntu-latest
    needs: jekyll-build
    environment:
      name: github-pages
      url: ${{steps.deployment.outputs.page_url}}
    steps:
      - name: Deploy artifact
        id: deployment
        uses: actions/deploy-pages@v4
# ...
```

## Linking separate build and deploy jobs

You can link your `build` and `deploy` jobs in a single workflow file, eliminating the need to create two separate files to get the same result. To get started on your workflow file, under `jobs` you can define a `build` and `deploy` job to execute your jobs.

```yaml
# ...

jobs:
  # Build job
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v6
      - name: Setup Pages
        id: pages
        uses: actions/configure-pages@v5
      - name: Build with Jekyll
        uses: actions/jekyll-build-pages@v1
        with:
          source: ./
          destination: ./_site
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v4

  # Deployment job
  deploy:
    environment:
      name: github-pages
      url: ${{steps.deployment.outputs.page_url}}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
# ...
```

In certain cases, you might choose to combine everything into a single job, especially if there is no need for a build process. Consequently, you would solely focus on the deployment step.

```yaml
# ...

jobs:
  # Single deploy job no building
  deploy:
    environment:
      name: github-pages
      url: ${{steps.deployment.outputs.page_url}}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v6
      - name: Setup Pages
        uses: actions/configure-pages@v5
      - name: Upload Artifact
        uses: actions/upload-pages-artifact@v4
        with:
          # upload entire directory
          path: '.'
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4

# ...
```

You can define your jobs to be run on different runners, sequentially, or in parallel. For more information, see [Choosing what your workflow does](https://docs.github.com/en/actions/using-jobs).

---

## About custom domains and GitHub Pages

> Source: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages

GitHub Pages supports using custom domains, or changing the root of your site's URL from the default, like `octocat.github.io`, to any domain you own.

**Who can use this feature?**

GitHub Pages is available in public repositories with GitHub Free and GitHub Free for organizations, and in public and private repositories with GitHub Pro, GitHub Team, GitHub Enterprise Cloud, and GitHub Enterprise Server. For more information, see [GitHub's plans](https://docs.github.com/en/get-started/learning-about-github/githubs-plans).

## Supported custom domains

> [!TIP]
> We recommend verifying your custom domain prior to adding it to your repository, in order to improve security and avoid takeover attacks. For more information, see [Verifying your custom domain for GitHub Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages).

GitHub Pages works with two types of domains: subdomains and apex domains. For a list of unsupported custom domains, see [Troubleshooting custom domains and GitHub Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/troubleshooting-custom-domains-and-github-pages#custom-domain-names-that-are-unsupported).

| Supported custom domain type | Example            |
|------------------------------|--------------------|
| `www` subdomain              | `www.example.com`  |
| Custom subdomain             | `blog.example.com` |
| Apex domain                  | `example.com`      |

You can set up either or both of apex and `www` subdomain configurations for your site. For more information on apex domains, see [Using an apex domain for your GitHub Pages site](#using-an-apex-domain-for-your-github-pages-site).

We recommend always using a `www` subdomain, even if you also use an apex domain. When you create a new site with an apex domain, we automatically attempt to secure the `www` subdomain for use when serving your site's content, but you need to make the DNS changes to use the `www` subdomain. If you configure a `www` subdomain, we automatically attempt to secure the associated apex domain. For more information, see [Managing a custom domain for your GitHub Pages site](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).

## Using a custom domain across multiple repositories

If you set a custom domain for a user or organization site, by default, the same custom domain will be used for all project sites owned by the same account. For more information about site types, see [What is GitHub Pages?](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages#types-of-github-pages-sites).

For example, if the custom domain for your user site is `www.octocat.com`, and you have a project site with no custom domain configured that is published from a repository called `octo-project`, the GitHub Pages site for that repository will be available at `www.octocat.com/octo-project`.

You can override the default custom domain by adding a custom domain to the individual repository.

> [!NOTE]
> The URLs for project sites that are privately published are not affected by the custom domain for your user or organization site. For more information about privately published sites, see [Changing the visibility of your GitHub Pages site](https://docs.github.com/en/enterprise-cloud@latest/pages/getting-started-with-github-pages/changing-the-visibility-of-your-github-pages-site) in the GitHub Enterprise Cloud documentation.

To remove the default custom domain, you must remove the custom domain from your user or organization site.

## Using a subdomain for your GitHub Pages site

A subdomain is the part of a URL before the root domain. You can configure your subdomain as `www` or as a distinct section of your site, like `blog.example.com`.

Subdomains are configured with a `CNAME` record through your DNS provider. For more information, see [Managing a custom domain for your GitHub Pages site](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-a-subdomain).

### www subdomains

A `www` subdomain is the most commonly used type of subdomain. For example, `www.example.com` includes a `www` subdomain.

`www` subdomains are the most stable type of custom domain because `www` subdomains are not affected by changes to the IP addresses of GitHub's servers.

### Custom subdomains

A custom subdomain is a type of subdomain that doesn't use the standard `www` variant. Custom subdomains are mostly used when you want two distinct sections of your site. For example, you can create a site called `blog.example.com` and customize that section independently from `www.example.com`.

## Using an apex domain for your GitHub Pages site

An apex domain is a custom domain that does not contain a subdomain, such as `example.com`. Apex domains are also known as base, bare, naked, root apex, or zone apex domains.

An apex domain is configured with an `A`, `ALIAS`, or `ANAME` record through your DNS provider. For more information, see [Managing a custom domain for your GitHub Pages site](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain).

If you are using an apex domain as your custom domain, we recommend also setting up a `www` subdomain. If you configure the correct records for each domain type through your DNS provider, GitHub Pages will automatically create redirects between the domains. For example, if you configure `www.example.com` as the custom domain for your site, and you have GitHub Pages DNS records set up for the apex and `www` domains, then `example.com` will redirect to `www.example.com`. If you instead configure `example.com` as the custom domain, then `www.example.com` will redirect to `example.com`. Automatic redirects also apply to other subdomains, as `www.blog.example.com` will redirect to `blog.example.com` or vice versa. It is not possible to configure a domain that starts with `www.www.`. For more information, see [Managing a custom domain for your GitHub Pages site](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-a-subdomain).

## Securing the custom domain for your GitHub Pages site

If your GitHub Pages site is disabled but has a custom domain set up, it is at risk of a domain takeover. Having a custom domain configured with your DNS provider while your site is disabled could result in someone else hosting a site on one of your subdomains.

Verifying your custom domain prevents other GitHub users from using your domain with their repositories. If your domain is not verified, and your GitHub Pages site is disabled, you should immediately update or remove your DNS records with your DNS provider. For more information, see [Verifying your custom domain for GitHub Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages) and [Managing a custom domain for your GitHub Pages site](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).

There are a couple of reasons your site might be automatically disabled.

- If you downgrade from GitHub Pro to GitHub Free, any GitHub Pages sites that are currently published from private repositories in your account will be unpublished. For more information, see [Downgrading your account's plan](https://docs.github.com/en/billing/managing-the-plan-for-your-github-account/downgrading-your-accounts-plan).
- If you transfer a private repository to a personal account that is using GitHub Free, the repository will lose access to the GitHub Pages feature, and the currently published GitHub Pages site will be unpublished. For more information, see [Transferring a repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/transferring-a-repository).

## Further reading

- [Troubleshooting custom domains and GitHub Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/troubleshooting-custom-domains-and-github-pages)

---

## About GitHub Pages and Jekyll

> Source: https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll

Jekyll is a static site generator with built-in support for GitHub Pages.

**Who can use this feature?**

GitHub Pages is available in public repositories with GitHub Free and GitHub Free for organizations, and in public and private repositories with GitHub Pro, GitHub Team, GitHub Enterprise Cloud, and GitHub Enterprise Server. For more information, see [GitHub's plans](https://docs.github.com/en/get-started/learning-about-github/githubs-plans).

> [!NOTE]
> While the `github-pages` gem remains supported for some workflows, GitHub Actions is now the recommended approach for deploying and automating GitHub Pages sites.

## About Jekyll

Jekyll is a static site generator with built-in support for GitHub Pages and a simplified build process. Jekyll takes Markdown and HTML files and creates a complete static website based on your choice of layouts. Jekyll supports Markdown and Liquid, a templating language that loads dynamic content on your site. For more information, see [Jekyll](https://jekyllrb.com/).

Jekyll is not officially supported for Windows. For more information, see [Jekyll on Windows](https://jekyllrb.com/docs/windows/#installation) in the Jekyll documentation.

We recommend using Jekyll with GitHub Pages. If you prefer, you can use other static site generators or customize your own build process locally or on another server. For more information, see [Creating a GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site#static-site-generators).

## Configuring Jekyll in your GitHub Pages site

You can configure most Jekyll settings, such as your site's theme and plugins, by editing your `_config.yml` file. For more information, see [Configuration](https://jekyllrb.com/docs/configuration/) in the Jekyll documentation.

Some configuration settings cannot be changed for GitHub Pages sites.

```yaml
lsi: false
safe: true
source: [your repo's top level directory]
incremental: false
highlighter: rouge
gist:
  noscript: false
kramdown:
  math_engine: mathjax
  syntax_highlighter: rouge
```

By default, Jekyll doesn't build files or folders that:

- Are located in a folder called `/node_modules` or `/vendor`
- Start with `_`, `.`, or `#`
- End with `~`
- Are excluded by the `exclude` setting in your configuration file

If you want Jekyll to process any of these files, you can use the `include` setting in your configuration file.

## Front matter

To set variables and metadata, such as a title and layout, for a page or post on your site, you can add YAML front matter to the top of any Markdown or HTML file. For more information, see [Front Matter](https://jekyllrb.com/docs/front-matter/) in the Jekyll documentation.

You can add `site.github` to a post or page to add any repository references metadata to your site. For more information, see [Using `site.github`](https://jekyll.github.io/github-metadata/site.github/) in the Jekyll Metadata documentation.

## Themes

You can add a Jekyll theme to your GitHub Pages site to customize the look and feel of your site. For more information, see [Themes](https://jekyllrb.com/docs/themes/) in the Jekyll documentation.

You can add a supported theme to your site on GitHub. For more information, see [Supported themes](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll#supported-themes) on the GitHub Pages site and [Adding a theme to your GitHub Pages site using Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll).

To use any other open source Jekyll theme hosted on GitHub, you can add the theme manually. For more information, see [themes hosted on GitHub](https://github.com/topics/jekyll-theme) and [Adding a theme to your GitHub Pages site using Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll).

You can override any of your theme's defaults by editing the theme's files. For more information, see your theme's documentation and [Overriding your theme's defaults](https://jekyllrb.com/docs/themes/#overriding-theme-defaults) in the Jekyll documentation.

## Plugins

You can download or create Jekyll plugins to extend the functionality of Jekyll for your site. For example, the [jemoji](https://github.com/jekyll/jemoji) plugin lets you use GitHub-flavored emoji in any page on your site the same way you would on GitHub. For more information, see [Plugins](https://jekyllrb.com/docs/plugins/) in the Jekyll documentation.

GitHub Pages uses plugins that are enabled by default and cannot be disabled:

- [`jekyll-coffeescript`](https://github.com/jekyll/jekyll-coffeescript)
- [`jekyll-default-layout`](https://github.com/benbalter/jekyll-default-layout)
- [`jekyll-gist`](https://github.com/jekyll/jekyll-gist)
- [`jekyll-github-metadata`](https://github.com/jekyll/github-metadata)
- [`jekyll-optional-front-matter`](https://github.com/benbalter/jekyll-optional-front-matter)
- [`jekyll-paginate`](https://github.com/jekyll/jekyll-paginate)
- [`jekyll-readme-index`](https://github.com/benbalter/jekyll-readme-index)
- [`jekyll-titles-from-headings`](https://github.com/benbalter/jekyll-titles-from-headings)
- [`jekyll-relative-links`](https://github.com/benbalter/jekyll-relative-links)

You can enable additional plugins by adding the plugin's gem to the `plugins` setting in your `_config.yml` file. For more information, see [Configuration](https://jekyllrb.com/docs/configuration/) in the Jekyll documentation.

For a list of supported plugins, see [Dependency versions](https://pages.github.com/versions.json) on the GitHub Pages site. For usage information for a specific plugin, see the plugin's documentation.

> [!TIP]
> You can make sure you're using the latest version of all plugins by keeping the GitHub Pages gem updated. For more information, see [Testing your GitHub Pages site locally with Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll#updating-the-github-pages-gem) and [Dependency versions](https://pages.github.com/versions.json) on the GitHub Pages site.

GitHub Pages cannot build sites using unsupported plugins. If you want to use unsupported plugins, generate your site locally and then push your site's static files to GitHub.

## Syntax highlighting

To make your site easier to read, code snippets are highlighted on GitHub Pages sites the same way they're highlighted on GitHub. For more information about syntax highlighting, see [Creating and highlighting code blocks](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-and-highlighting-code-blocks).

By default, code blocks on your site will be highlighted by Jekyll. Jekyll uses the [Rouge](https://github.com/rouge-ruby/rouge) highlighter (which is compatible with [Pygments](https://pygments.org/)). If you specify Pygments in your `_config.yml` file, Rouge will be used as the fallback instead. Jekyll cannot use any other syntax highlighter, and you'll get a page build warning if you specify another syntax highlighter in your `_config.yml` file. For more information, see [About Jekyll build errors for GitHub Pages sites](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-jekyll-build-errors-for-github-pages-sites).

> [!NOTE]
> Rouge only recognizes lower-case language identifiers for fenced code blocks. For a list of supported languages, see [Languages](https://rouge-ruby.github.io/docs/file.Languages.html).

If you want to use another highlighter, such as [highlight.js](https://github.com/highlightjs/highlight.js), you must disable Jekyll's syntax highlighting by updating your project's `_config.yml` file.

```yaml
kramdown:
  syntax_highlighter_opts:
    disable : true
```

If your theme doesn't include CSS for syntax highlighting, you can generate GitHub's syntax highlighting CSS and add it to your project's `style.css` file.

```shell
rougify style github > style.css
```

## Building your site locally

If you are publishing from a branch, changes to your site are published automatically when the changes are merged into your site's publishing source. If you are publishing from a custom GitHub Actions workflow, changes are published whenever your workflow is triggered (typically by a push to the default branch). If you want to preview your changes first, you can make the changes locally instead of on GitHub. Then, test your site locally. For more information, see [Testing your GitHub Pages site locally with Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll).

---
