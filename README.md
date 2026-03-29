# AUTHOR GUIDE

This guide is for authors of [www.majlovesreg.one](https://www.majlovesreg.one)

## Table of Contents

- [Step 1: Create a GitHub account](#step-1-create-a-github-account)
- [Step 2: Create your author repository](#step-2-create-your-author-repository)
- [Step 3: Create a blog post](#step-3-create-a-blog-post)
- [Step 4: Save (commit) your changes](#step-4-save-commit-your-changes)
- [Step 5: Ask a maintainer to connect your repo](#step-5-ask-a-maintainer-to-connect-your-repo)
- [Examples](#examples)
- [Troubleshooting](#troubleshooting)
- [Done Checklist](#done-checklist)

## Step 1: Create a GitHub account

If you already have an account, continue to Step 2.

1. Go to [github.com](https://github.com).
2. Click **Sign up**.
3. Follow the steps.
4. Verify your email.

## Step 2: Create your author repository

1. Create new repository from template at [https://github.com/majlovesreg/website-mlr2-authors](https://github.com/majlovesreg/website-mlr2-authors)
2. Click `Use this template` > `Create a new repository`
3. In your new repo, edit `author-profile.md`. See [examples](#example-author-profilemd)

## Step 3: Create a blog post

1. Create a folder for the post, for example: `2026-03-28-my-first-post`
2. Inside that folder, create `index.md`.
3. Add your frontmatter and content. See [example](#example-blog-post-indexmd)

## Step 4: Save (commit) your changes

On GitHub web editor:

1. Click the pencil icon to edit.
2. Make your changes.
3. Scroll down.
4. Add a short commit message.
5. Click **Commit changes**.

## Step 5: Ask majlovesreg.one to connect your repo

Provide your GitHub repository address to majlovesreg.one

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
  - your-slug
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
- `author` uses author slugs (not full names).
- Keep images in the same post folder and use relative paths like `./cover.jpg`.

## Done Checklist

- GitHub account created
- Author repository created
- `author-profile.md` updated
- Create a post folder with `index.md` inside it
- Changes committed
- Inform site owner of your repo address

## Troubleshooting

### I pushed changes but site did not update yet

GitHub will check your repository every hour (on the hour). If you have new content in your repo, it will be picked up for publishing. Check at around five minutes after the hour to see new content on the site.