# Template and Author Guide

This guide and template is for authors of [www.majlovesreg.one](https://www.majlovesreg.one). Authoring uses the Markdown (MD) format. Learn more about MD and related technologies here:
- [What is Markdown?](https://www.markdownguide.org/getting-started/)
- [Basic Markdown Syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- Advanced: [MDX](https://docs.astro.build/en/guides/integrations-guide/mdx/)
- Advanced: [Content Management Systems](https://jamstack.org/headless-cms/) and their [Astro integrations](https://docs.astro.build/en/guides/cms/)

## Table of Contents

- [Step 1: Create a GitHub account](#step-1-create-a-github-account)
- [Step 2: Create your author repository](#step-2-create-your-author-repository)
- [Step 3: Create a blog post](#step-3-create-a-blog-post)
- [Step 4: Ask majlovesreg.one admins to connect your repo](#step-4-ask-majlovesregone-admins-to-connect-your-repo)
- [Examples](#examples)
- [Checklist](#checklist)
- [Troubleshooting](#troubleshooting)

## Step 1: Create a GitHub account

If you already have an account, continue to Step 2.

1. Go to [github.com](https://github.com).
2. Click **Sign up**.
3. Follow the steps.
4. Verify your email.

## Step 2: Create your author repository

1. Create new repository from template at [https://github.com/majlovesreg/website-mlr2-authors](https://github.com/majlovesreg/website-mlr2-authors)
2. Click `Use this template` > `Create a new repository`
3. In your new repo, edit [`author-profile.md`](author-profile.md). See [example](#example-author-profilemd)

## Step 3: Create a blog post

1. Create a folder for the post, for example: `yyyy-mm-dd-my-first-post`
2. Inside that folder, create [`index.md`](yyyy-mm-dd-my-first-post/index.md)
3. Add your [frontmatter](https://docs.astro.build/en/guides/markdown-content/) (aka settings) and content. See [example](#example-blog-post-indexmd)
4. Upload the images you want to use in the post to the same folder as [`index.md`](yyyy-mm-dd-my-first-post/index.md)

## Step 4: Ask majlovesreg.one admins to connect your repo

If your repository is **public**: Simply provide your GitHub repository address to majlovesreg.one admins.

If your repository is **private**: You must generate a secure API key so the majlovesreg.one can read your posts. Do not give admin access to your account or repository! Create a "Read-only" Fine-grained token.

1. Go to your GitHub **Settings** -> **Developer settings** -> **Personal access tokens** -> [**Fine-grained tokens**](https://github.com/settings/personal-access-tokens).
2. Click **Generate new token**.
3. Select a memorable **token name** (e.g. `Access for majlovesreg.one`)
4. You may choose to not set an **expiration** date, or set it to a shorter time frame, like 1 year. Just set a reminder to renew it when it is about to expire, and send the new token to majlovesreg.one admins.
5. **Repository access:** Select **Only select repositories**, then choose your author repository.
6. **Permissions:** Under **Repository permissions**, find **Contents** and set it to **Read-only**. (Leave everything else as `No access`).
7. Click **Generate token** at the bottom, and copy the `github_pat_...` string.
8. Securely share this **token** and your **repository link** to majlovesreg.one admins.

## Checklist

- GitHub account created
- Author repository created
- [`author-profile.md`](author-profile.md) updated
- Create a post folder with [`index.md`](yyyy-mm-dd-my-first-post/index.md) inside it
- Changes committed
- Inform site owner of your repository address. If your repo is private, include your generated API token as well

## Troubleshooting

### I pushed changes but site did not update yet

GitHub will check your repository every hour (on the hour). If you have new content in your repo, it will be picked up for publishing. Check at around five minutes after the hour to see new content on the site.

### I need more help

Contact majlovesreg.one admins

## Examples

### Example [`author-profile.md`](author-profile.md)

```md
---
description: "Short one-line bio shown at the top of your author page."
gravatarEmail: "author@example.com"
links:
  - label: "Website"
    url: "https://example.com"
    kind: website
  - label: "Facebook"
    url: "https://www.facebook.com/example"
    kind: social
---
Hello, I am an author. This is my longer bio.
```

### Example blog post [`index.md`](yyyy-mm-dd-my-first-post/index.md)

```md
---
title: "My First Post"
description: "A short summary of this post."
pubDate: 2026-03-28
author:
  - your-author-slug
category: thoughts
tags:
  - personal
heroImage: "./cover.jpg"
draft: false
unlisted: false
---

Hello! This is my first post.

![Cover image](./cover.jpg)
```

Notes:

- `title`, `description`, and `pubDate` are required.
- `author` uses your author slug (not full name). Your personal slug will be created for you by majlovesreg.one admins, ask them about it.
- Keep images in the same post folder and use relative paths like `./cover.jpg`.
