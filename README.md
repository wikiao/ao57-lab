# ao57-lab

Production mirror for **ao-57.ru**.

Architecture:

```
ChatGPT Sites (editor + publish)
        ↓
published source URL
        ↓ every 15 min
GitHub Actions mirror
        ↓
GitHub Pages
        ↓
ao-57.ru
```

## Important

The file `.site-source-url` is the upstream ChatGPT Sites URL that GitHub mirrors.

**Before moving ao-57.ru to GitHub Pages, the upstream must be changed from the apex domain to a separate source hostname (for example `sites.ao-57.ru`) that continues to point to ChatGPT Sites.** Otherwise the mirror would start reading its own GitHub Pages output.

The workflow is `.github/workflows/mirror-pages.yml`.

Current migration status: staging. Do not switch the apex DNS until the GitHub Pages copy has been verified.
