# GitHub Pages preview (fork only)

This branch deploys the website to GitHub Pages. `master` stays unchanged.

## URL

https://acrogenesis.github.io/herdr/

Docs: https://acrogenesis.github.io/herdr/docs/

## One-time setup

1. Open **Settings → Pages** on your fork.
2. Set **Source** to **GitHub Actions**.

## Deploy

Push to `website-deploy`:

```bash
git push origin website-deploy
```

Or run the workflow manually from the **Actions** tab.

## Refresh from master

```bash
git checkout website-deploy
git merge master
git push origin website-deploy
```

## Local preview with GitHub Pages paths

```bash
cd website
GITHUB_PAGES=true GITHUB_PAGES_OWNER=acrogenesis GITHUB_PAGES_REPO=herdr bun run build
GITHUB_PAGES=true GITHUB_PAGES_OWNER=acrogenesis GITHUB_PAGES_REPO=herdr bun run preview
```