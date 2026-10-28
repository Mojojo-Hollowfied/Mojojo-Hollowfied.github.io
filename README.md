# Nebula Files website

Static website for **Nebula Files**, the Android file manager developed by Mojojo
(contact: mojojotwom@gmail.com). Plain hand-written HTML and CSS: no build step,
no frameworks, no external CDNs. The Orbitron font is self-hosted.

## Pages

| File | Purpose |
| --- | --- |
| `index.html` | Home page: what the app does, APK download, install steps, features, how Google Drive is used |
| `privacy.html` | Privacy policy (incl. Google API Services User Data Policy / Limited Use statement) |
| `terms.html` | Terms of service (incl. format/wipe data-loss disclaimer) |
| `404.html` | Not-found page served by GitHub Pages |

## Deploy on GitHub Pages

1. Push the contents of this folder to a repository (repo root or a `/docs` folder).
2. Settings → Pages → *Deploy from a branch* → pick the branch and folder.
3. `.nojekyll` is included so GitHub serves the files as-is.

All links are relative, so the site works at a domain root (`https://user.github.io/`,
custom domain) and in a subfolder (`https://user.github.io/nebula-files/`).

`404.html` pins its links with a `<base>` computed in a small inline script: on
`*.github.io` it assumes a project site (`/<repo>/`), elsewhere `/`. If you deploy
it as a **user site** (`user.github.io` repo), change the script to always use `/`.

## Updating the APK

1. Put the new APK in `downloads/` (e.g. `downloads/NebulaFiles-v2.6.apk`).
2. Update the Download button `href`, the version and size in `index.html`, and the
   file name in install step 2.
3. Delete the old APK so the repository stays small.

GitHub rejects files over 100 MB and warns above 50 MB; the v2.5 APK is about 56 MB,
which pushes fine (with a warning). If a future build passes 100 MB, attach it to a
GitHub Release instead and point the button at the release asset.

## Social previews

`og:image` is a relative path (`assets/og-image.jpg`). Some link-preview crawlers
require an absolute URL: once the final address is known, change it to
`https://<your-site>/assets/og-image.jpg` in each page.

## Google OAuth verification

- Home page URL: `index.html` (describes the app, not just a sign-in page)
- Privacy policy URL: `privacy.html`
- Terms of service URL: `terms.html`
