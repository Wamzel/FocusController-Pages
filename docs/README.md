# Support site for Focus for grandMA3

Static site hosted on GitHub Pages. Used as the App Store support URL and privacy policy URL.

## Files

| File | Purpose |
|---|---|
| `index.html` | Support / landing page (App Store "Support URL") |
| `privacy.html` | Privacy policy (App Store "Privacy Policy URL") |
| `terms.html` | Terms of Use / EULA (App Store "License Agreement URL") |
| `style.css` | Shared dark-mode-first styling (auto-switches to light in light mode) |
| `icon.svg` | Hero icon used in headers |
| `favicon.svg` | Browser tab icon |

## Local preview

Open `index.html` directly in a browser — no build step. Everything is static HTML + CSS, no JS, no Jekyll.

```sh
open docs/index.html
```

Edit, save, refresh.

## Deploy on GitHub Pages

One-time setup:

1. Commit and push the entire `docs/` folder to your GitHub repo's `main` branch.
2. Repo → **Settings** → **Pages**.
3. Under **Build and deployment**, set:
   - **Source**: Deploy from a branch
   - **Branch**: `main` · `/docs` folder
4. Save. GitHub prints the live URL (typically `https://<your-username>.github.io/<repo-name>/`).
5. Wait ~1 minute. Visit the URL to confirm.

The URLs you paste into App Store Connect are then:

- Support URL: `https://<user>.github.io/<repo>/`
- Privacy Policy URL: `https://<user>.github.io/<repo>/privacy.html`
- License Agreement / EULA URL (optional but recommended): `https://<user>.github.io/<repo>/terms.html`

## Custom domain (optional)

If you want it at e.g. `focus.t-minusdesign.com`:

1. Add a `CNAME` file inside `docs/` containing one line: `focus.t-minusdesign.com`.
2. In your DNS, add a CNAME record pointing that subdomain to `<user>.github.io`.
3. Repo → Settings → Pages → Custom domain → enter the same value. Check **Enforce HTTPS** once the cert provisions (usually ~15 min).

## When to update

- Change the contact email anywhere → edit both `index.html` and `privacy.html`.
- Ship a new feature that interacts differently with privacy → update `privacy.html`'s "Last updated" date and the relevant section before submitting the App Store update.
- Users reporting the same issue often → add a `<details>` block to the FAQ in `index.html`.
