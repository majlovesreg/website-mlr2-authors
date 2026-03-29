# TEMPLATE AND AUTHOR GUIDE

This guide and template is for authors of [www.majlovesreg.one](https://www.majlovesreg.one).

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
3. In your new repo, edit `author-profile.md`. See [example](#example-author-profilemd)

## Step 3: Create a blog post

1. Create a folder for the post, for example: `yyyy-mm-dd-my-first-post`
2. Inside that folder, create `index.md`
3. Ask majlovesreg.one admins for your author slug
4. Add your frontmatter and content. See [example](#example-blog-post-indexmd)

## Step 4: Ask majlovesreg.one admins to connect your repo

**If your repository is public:**
Simply provide your GitHub repository address to majlovesreg.one admins.

**If your repository is private:**
You must generate a secure API key so the main site can securely read your posts. DO NOT give admin access to your account or repository! Create a "Read-only" Fine-grained token.

1. Go to your GitHub **Settings** -> **Developer settings** -> **Personal access tokens** -> **Fine-grained tokens**.
2. Click **Generate new token**.
3. **Token name:** `website-mlr2-sync`
4. **Expiration:** Set to 1 year (you will need to renew it when it expires).
5. **Repository access:** Select **Only select repositories**, then choose your author repository.
6. **Permissions:** Under **Repository permissions**, find **Contents** and set it to **Read-only**. (Leave everything else as `No access`).
7. Click **Generate token** at the bottom, and copy the `github_pat_...` string.
8. Securely share this token **AND** your repository link with the majlovesreg.one admins.

## Examples

### Example `author-profile.md`

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

### Example blog post `index.md`

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
- `author` uses your author slug (not full name). Ask majlovesreg.one admins for your author slug
- Keep images in the same post folder and use relative paths like `./cover.jpg`.

## Checklist

- GitHub account created
- Author repository created
- `author-profile.md` updated
- Create a post folder with `index.md` inside it
- Changes committed
- Inform site owner of your repo address

## Troubleshooting

### I pushed changes but site did not update yet

GitHub will check your repository every hour (on the hour). If you have new content in your repo, it will be picked up for publishing. Check at around five minutes after the hour to see new content on the site.

### I need more help

Contact majlovesreg.one admins