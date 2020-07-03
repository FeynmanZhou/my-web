---
author: Feynman
title: GitHub Invalid Authentication
date: 2020-05-31T12:00:06+09:00
description: How to Resolve GitHub Invalid Authentication
draft: false
hideToc: false
enableToc: true
enableTocContent: true
tocPosition: inner
tags:
- shortcode
series:
-
categories:
-
image: images/feature3/code-file.png
---

![](https://pek3b.qingstor.com/kubesphere-docs/png/20200531225922.png)

## Authentication issue

After I enabled the Two-factor Authentication in GitHub, I can't push the local commits to GitHub repository, and  encountered the issue as follows:

{{< box >}}
git push origin master
Password for 'https://git@github.com':
remote: Invalid username or password.
fatal: Authentication failed for 'https://git@github.com/eurydyce/MDANSE.git/'
{{< /box >}}

## How do I Resolve it

Why this issue happened after Two-factor Authentication has been enabled? I got the answer from [GitHub Documentation](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line).

Here, I just take notes for the solution. GitHub requires users to create a personal access token to replace the password when performing Git operations over HTTPS with Git on the CLI.

A personal access token is required to authenticate to GitHub in the following situations:

- When you're using [two-factor authentication](two-factor authentication)
- To access protected content in an organization that uses SAML single sign-on (SSO). Tokens used with organizations that use SAML SSO must be authorized.

## Create a Token

1. Log in to GitHub, in the upper-right corner of any page, click your profile photo, then click Settings.

2. In the left sidebar, click **Developer settings**.

3. In the left sidebar, click **Personal access tokens**.

4. Click **Generate new token**.

5. Name it, then select the scopes, or permissions, you'd like to grant this token. To use your token to access repositories from the command line, select repo.

![](https://pek3b.qingstor.com/kubesphere-docs/png/20200531222847.png)

6. Click **Generate token**.

7. Copy the token. Then you can enter it instead of your password when performing Git operations over HTTPS.

```
$ git clone https://github.com/username/repo.git
Username: your_username
Password: your_token    # Replace your initial password)
```

It works!

> Tip: Personal access tokens can only be used for HTTPS Git operations. If your repository uses an SSH remote URL, you will need to [switch the remote from SSH to HTTPS](switch the remote from SSH to HTTPS).

## Reference

- [Stackoverflow - GitHub: invalid username or password](https://stackoverflow.com/questions/29297154/github-invalid-username-or-password)
- [Creating a personal access token for the command line](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line)
