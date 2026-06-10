# GitHub Pages preview (fork only)

This branch deploys the website to GitHub Pages. `master` stays unchanged.

## URL

https://acrogenesis.com/herdr/

Docs: https://acrogenesis.com/herdr/docs/

(`acrogenesis.github.io/herdr/` redirects to the custom domain above.)

## One-time setup

1. Open **Settings → Pages** on your fork.
2. Set **Source** to **GitHub Actions**.
3. Open **Settings → Environments → github-pages**.
4. Under **Deployment branches**, allow the `website-deploy` branch.

If either step is skipped, the workflow builds successfully but the deploy job fails with a 404 or environment protection error.

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