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
- [Checklist](#checklist)
- [Troubleshooting](#troubleshooting)
- [Examples](#examples)
- [Advanced use](#advanced)
- [Frontmatter Reference](#frontmatter-reference)

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
5. If you set `draft: true` on your frontmatter, you will be able to preview your post on [next.majlovesreg.one](https://next.majlovesreg.one) before it goes live on the main site [www.majlovesreg.one](https://www.majlovesreg.one)

**Pro tip:** You can first write your content on a proper editor, like Google Docs, then copy it as markdown to be pasted on your `index.md`

## Step 4: Ask majlovesreg.one admins to connect your repo

If your repository is **public**: Simply provide your GitHub repository address to majlovesreg.one admins.

If your repository is **private**: You must generate a secure API key so the majlovesreg.one can read your posts. Do not give admin access to your account or repository! Create a "Read-only" Fine-grained token.

1. Go to your GitHub **Settings** -> **Developer settings** -> **Personal access tokens** -> [**Fine-grained tokens**](https://github.com/settings/personal-access-tokens).
2. Click **Generate new token**.
3. Select a memorable **token name** (e.g. `Access for majlovesreg.one`)
4. You may choose to not set an **expiration** date, or set it to a shorter time frame, like 1 year. Just set a reminder to renew it when it is about to expire, and send the new token to majlovesreg.one admins.
5. **Repository access:** Select **Only select repositories**, then choose your author repository.
6. **Permissions:** Under **Repository permissions**, find **Contents** and set it to **Read-only**. (It will also automatically add `Metadata` read-only permission).
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

GitHub will [try to check](https://github.com/orgs/community/discussions/147369) your repository every hour. If you have new content in your repo, it will be picked up for publishing. Check back in an hour or so. If it is `draft: true`, you will see it at [next.majlovesreg.one](https://next.majlovesreg.one).

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

## Advanced use

### Using MDX (JavaScript in Markdown)

MDX allows you to embed JSX components and JavaScript expressions directly in your markdown content. This is useful for interactive elements, custom layouts, or dynamic content.

> **Note:** MDX files use the `.mdx` extension instead of `.md`. Simply rename your post folder to use `index.mdx` instead of `index.md`.

#### Example: Embedding a Code Block with Syntax Highlighting

```mdx
export const highlight = (text) => `✨ ${text} ✨`;

Here's some highlighted text: {highlight("Look at me!")}
```

#### Example: Using Custom Components

If you want to embed custom HTML or use reusable components, you can use raw HTML or import components:

```mdx
<div class="callout-info my-6 rounded-lg border-l-4 px-4 py-3">
  <strong>Tip:</strong> This is a callout box using Tailwind styling.
</div>
```

Learn more about MDX: [MDX Documentation](https://docs.astro.build/en/guides/integrations-guide/mdx/)

### Advanced Markdown Features

#### Tables

```md
| Feature | Description |
|---------|-------------|
| **Bold** | Use `**text**` |
| *Italic* | Use `*text*` |
| `Code` | Use backticks |
```

#### Using HTML for Complex Layouts

You can embed raw HTML for layouts that standard markdown cannot express:

```md
<div class="grid grid-cols-2 gap-4">
  <div>Column 1</div>
  <div>Column 2</div>
</div>
```

#### Callout Boxes

Use callout boxes to highlight important information:

```html
<div class="callout-warning my-6 rounded-lg border-l-4 px-4 py-3 not-prose">
  <p class="m-0"><strong>Warning:</strong> This is important information.</p>
</div>
```

Available callout types: `callout-info`, `callout-warning`, `callout-success`, `callout-error`.

### Internal Linking

Link to other posts and pages using relative paths:

```md
Read my [previous post](/entropy/my-earlier-post/) for context.

Check out the [about page](/about/) for more information.
```

### Image Optimization

Keep all images in the same folder as your `index.md` (or `index.mdx`) and reference them with relative paths:

```md
![A descriptive caption](./my-image.jpg)
```

The site automatically optimizes images for different screen sizes and formats. Use descriptive alt text for accessibility.

### Responsive Images

For more control, use HTML with Tailwind classes:

```html
<img 
  src="./image.jpg" 
  alt="Responsive image" 
  class="w-full max-w-2xl mx-auto rounded-lg shadow-md"
/>
```

### Multi-Author Posts

You can mark a post as authored by multiple people:

```yaml
---
title: "Collaboration"
author:
  - maj
  - reg
---
```

Both authors will be listed on the post with their respective profile information.

### Using Draft and Unlisted Strategically

- **`draft: true`**: Post is hidden from main site but visible at [next.majlovesreg.one](https://next.majlovesreg.one). Perfect for work-in-progress content.
- **`unlisted: true`**: Post is hidden from listings and search but accessible via direct link. Useful for supplementary content or private shares.
- **`accessGroup: "group-name"`**: Post requires a password to view. Ask admins to configure the password mapping.

### Frontmatter Customization

While the fields above are standard, you can add custom frontmatter fields for personal tracking or tooling:

```yaml
---
title: "My Post"
description: "Short summary"
pubDate: 2026-03-28
customField: "my-value"
---
```

Custom fields won't affect the site but can be useful for personal organization.

## Frontmatter Reference

All blog posts and pages use YAML frontmatter (the metadata section at the top between `---` markers). Here are all available fields:

### Required Fields

- **`title`** (string): The title of your post or page. This appears in the browser tab, search results, and at the top of the page.
- **`description`** (string): A short summary (1-2 sentences). Used in previews and social sharing.
- **`pubDate`** (date): Publication date in `YYYY-MM-DD` format, e.g., `2026-03-28`.

### Optional Common Fields

- **`subtitle`** (string): A secondary headline shown below the title (blog posts only).
- **`ogTitle`** (string): Custom title for social media sharing. Defaults to the title or `title—subtitle`.
- **`ogDescription`** (string): Custom description for social media sharing. Defaults to description.

### Content Organization

- **`category`** (string): Blog category. Posts without a category appear under "entropy". Examples: `thoughts`, `life`, `love`.
- **`slug`** (string): For creating custom post URLs. Example: `slug: about` creates the page at `/<category>/about/`. Cannot contain leading/trailing slashes.
- **`tags`** (array of strings): List of tags for filtering and discovery. Example: `tags: [personal, travel, tech]`.
- **`author`** (string or array): Author slug(s). Matches your author profile. Example: `author: maj` or `author: [maj, reg]`.

### Content Control

- **`draft`** (boolean, default: `false`): When `true`, the post/page only appears on the preview site ([next.majlovesreg.one](https://next.majlovesreg.one)), not the main site. Useful for work-in-progress.
- **`unlisted`** (boolean, default: `false`): Post/page doesn't appear in listings, searches, or social sharing, but remains publicly accessible via direct link. Useful for occasional one-off content.
- **`accessGroup`** (string): Restricts access to posts/pages behind a password. Example: `accessGroup: trip-2026`. Admins configure password mappings.

### Linking & Sharing

- **`autoLinkHeading`** (boolean, default: `true`): When `true`, clickable link icons appear next to subheadings (h2, h3, etc.) on hover, allowing visitors to copy the link to that section.
- **`autoLinkParagraph`** (boolean, default: `true`): When `true`, clickable link icons appear next to paragraphs when clicked, allowing visitors to copy the link to that paragraph.
- **`share`** (array of strings or `false`): Controls which social platforms appear in share buttons. Example: `share: [twitter, facebook, linkedin]`. Set to `false` to hide sharing entirely.

### Media & Metadata

- **`heroImage`** (string): Path to a featured image. Use relative paths from the post folder, e.g., `./cover.jpg`. Appears at the top of the post and in social previews.
- **`originalUrl`** (string): If reposting content, link to the original. Useful for canonicalization.

### Pages-Only Fields

- **`path`** (string): For creating nested URLs. Example: `path: privacy/policy` creates the page at `/privacy/policy/`. Cannot contain leading/trailing slashes. Cannot be used with `slug`.
