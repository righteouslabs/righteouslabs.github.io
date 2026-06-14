# righteous.ai

Marketing website for **Righteous AI**, served at
**[https://www.righteous.ai](https://www.righteous.ai)** via GitHub Pages.

Built with [Astro](https://astro.build) — a lightweight static-site framework.
No client-side framework, no heavy build, just HTML/CSS output.

## Quick start

```bash
# with devbox (matches the tooling in rrmistry.github.io)
devbox shell
devbox run npm-install
devbox run dev          # http://localhost:4321

# or plain npm
npm install
npm run dev
```

| Command           | Action                                   |
| ----------------- | ---------------------------------------- |
| `npm run dev`     | Local dev server at `localhost:4321`     |
| `npm run build`   | Build the static site to `./dist/`       |
| `npm run preview` | Preview the production build locally     |

## tmux workflow

```bash
devbox run tmux        # start the tmuxinator session
devbox run tmux:stop   # stop it
```

## Editing content

| What                | Where                                                    |
| ------------------- | -------------------------------------------------------- |
| Home / About / Contact | `src/pages/*.astro`                                   |
| Site-wide layout    | `src/layouts/Base.astro`, `src/components/`              |
| Look & feel         | `src/styles/global.css` (edit the CSS variables at top)  |
| Blog posts          | Add a Markdown file to `src/content/blog/`               |

### Adding a blog post

Create `src/content/blog/my-post.md`:

```markdown
---
title: "My post title"
description: "One-line summary for the blog list and SEO."
pubDate: 2026-06-14
author: "Rohit Mistry"
---

Your **Markdown** content here.
```

The URL is derived from the filename: `my-post.md` → `/blog/my-post/`.

## Contact form

The site is static, so the contact form needs an external endpoint to actually
send mail. Open `src/pages/contact.astro` and either:

1. Paste a [Formspree](https://formspree.io) endpoint into `FORM_ENDPOINT`, or
2. Rely on the email button (always works).

## Deployment

Every push to `main` triggers `.github/workflows/deploy.yml`, which builds the
Astro site and deploys it to GitHub Pages. The custom domain is pinned by
`public/CNAME` (`www.righteous.ai`).
