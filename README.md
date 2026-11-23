# Margin website

Landing page for [Margin](https://github.com/csakash/margin), the floating markdown notepad for macOS. Static HTML, hosted on Cloudflare Pages.

```bash
npx wrangler pages deploy . --project-name margin-notes
```

The signed DMG lives in `download/`. After a new release, copy it from the app repo's `dist/` and redeploy.
