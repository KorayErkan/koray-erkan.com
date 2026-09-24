# koray-erkan.com

Source for [koray-erkan.com](https://koray-erkan.com), built with [Hugo](https://gohugo.io) and
hosted on Cloudflare Workers (project `koray-erkan`; fallback URL
https://koray-erkan.koray-erkan.workers.dev).

## Everyday use

| Task | Command |
|------|---------|
| Preview locally (drafts included) | `hugo server -D` → open http://localhost:1313 |
| New blog post | `hugo new content blog/my-post.md` |
| Publish a post | set `draft = false`, open a PR, merge |

## How changes go live

1. Work on a branch; open a pull request.
2. GitHub runs the **Build** check; Cloudflare posts a preview link.
3. Merge to `main` → the live site updates.

`main` is protected: changes arrive only through pull requests that pass the Build check.
