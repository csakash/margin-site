# Margin website

Landing page for [Margin](https://github.com/csakash/margin), the floating markdown notepad for macOS. Static HTML, hosted on Cloudflare Pages.

```bash
npx wrangler pages deploy . --project-name margin-notes   # live at https://margin.motiontic.com
```

## Publishing an update

Installed copies of Margin read `appcast.xml` at the site root once a day and download the DMG it points to.

1. In the app repo, run `scripts/release.sh`. It leaves `dist/Margin-<version>.dmg` and `dist/appcast.xml`.
2. Copy the DMG into `download/` and `appcast.xml` into the site root.
3. Update the three download links in `index.html` to the new DMG.
4. Deploy with the command above, then check that `https://margin.motiontic.com/appcast.xml` shows the new version.

Keep the previous DMG in `download/` for one release, so anyone mid-download is not cut off. To stop a bad update, put the previous `appcast.xml` back and redeploy; it takes effect within five minutes.
