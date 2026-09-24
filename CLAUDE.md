# koray-erkan.com

Personal site: documentation-engineering work and job search. Blog at `/blog`.

## Stack

- **Hugo** (extended, pinned to **0.166.0** in three places: `.github/workflows/build.yml`,
  the Cloudflare build variable `HUGO_VERSION`, and the local winget install). Bump all together.
- **No theme.** Layouts are hand-written in `layouts/` (`baseof`, `home`, `list`, `single`,
  `404`, `_partials/header`); styles in `static/css/site.css`. Keep it dependency-free.
- **Cloudflare Workers** (not Pages), project `koray-erkan`, configured by `wrangler.jsonc`.
  Serves `public/` as static assets. Keep `"previews": {}` — without it PR previews fail.

## Workflow

- `main` is protected: every change goes through a PR that passes the `build` check
  (`hugo --gc --minify --panicOnWarning` — any Hugo warning fails the build).
- Each PR gets a Cloudflare preview at `https://<branch>-koray-erkan.koray-erkan.workers.dev`.
- Merging to `main` deploys to https://koray-erkan.com.
- **The owner merges PRs**, not Claude.
- Cloudflare build logs are only visible in the dashboard; ask the owner to paste them.

## Content

- Posts: `content/blog/<slug>.md`, TOML front matter (`+++`), start as `draft = true`.
- Contact email: `contact@koray-erkan.com` (set in `hugo.toml` → `params.email`).
- Line endings are LF (`.gitattributes`); keep them so.

## Conventions

- Public repo — never commit secrets, tokens, or private job-search details.
- Before pushing, build locally with `--panicOnWarning` to catch deprecations early.
