# swift-comet

Source for [meherbejaoui.com](https://www.meherbejaoui.com), built with [Hugo](https://gohugo.io) and the [Hugo Blox](https://hugoblox.com) blog template.

## Stack

- [Hugo](https://gohugo.io) (extended) — static site generator, version pinned in `hugoblox.yaml`
- [Hugo Blox Kit](https://github.com/HugoBlox/kit) modules (`go.mod`) — theme, layouts, blocks
- [Tailwind CSS v4](https://tailwindcss.com/) — styling
- [Pagefind](https://pagefind.app/) — static search index
- pnpm — package management

## Local development

```bash
pnpm install
pnpm run dev
```

This starts a Hugo dev server (`hugo server --disableFastRender`) with live reload.

## Building

```bash
pnpm run build
```

Runs `hugo --minify` and generates the Pagefind search index into `public/`.

## Content structure

- `content/blog/<slug>/index.md` — blog posts, as Hugo page bundles (images/data files live alongside `index.md` in the same folder)
- `content/authors/` — author profile data (rendering disabled; see `data/authors/`)
- `content/projects.md`, `content/uses.md`-style single pages — standalone pages linked from the nav (`config/_default/menus.yaml`)
- `data/authors/me.yaml` — site owner's bio, links, education, etc.
- `config/_default/` — site config (`hugo.yaml`, `params.yaml`, `menus.yaml`, `module.yaml`)

## Deployment

Pushes to `main` trigger `.github/workflows/deploy.yml`, which builds the site and publishes it to GitHub Pages. The workflow also runs on a 6-hour schedule so that content with a future `date` (or an expired `expiryDate`) goes live automatically, since Hugo excludes such content from production builds by default.
