# Pocket Relay website

Static marketing and support site for Pocket Relay, an iPhone and iPad app for following and steering the coding agent on your own computer.

## What is here

- `index.html`: home page
- `support/`, `privacy/`, `terms/`: one folder per page, each with its own `index.html`
- `404.html`, `robots.txt`, `sitemap.xml`
- `assets/`: the one stylesheet (`styles.css`), icons, screenshots and the Open Graph image
- `.nojekyll`: tells GitHub Pages to serve the files as they are

Plain HTML and CSS. No framework, no build step, no external requests. The animated character ("Float") is inline SVG driven by CSS in `assets/styles.css`.

## Publishing

The site is published with GitHub Pages from the root of the `main` branch, as a project site at `https://bpollak.github.io/pocket-relay-site/`. In the repository settings choose Pages, then "Deploy from a branch", branch `main`, folder `/ (root)`.

All internal links are relative, so the site works from any folder.

## If the address changes

The base URL `https://bpollak.github.io/pocket-relay-site/` appears in one marked block in the `<head>` of each HTML file, and in `robots.txt` and `sitemap.xml`. Replace it everywhere with one command:

```sh
grep -rl 'bpollak.github.io/pocket-relay-site' . | xargs sed -i '' 's#https://bpollak.github.io/pocket-relay-site/#https://NEW-ADDRESS/#g'
```

`404.html` also has a `SITE_PATH` value (`/pocket-relay-site/`) near the top; set it to the new folder, or `/` for a custom domain.

## Before public release

- Add contact details where the pages say "Contact details will be added before public release." (search for `CONTACT_EMAIL_TBD`).
- Confirm the terms of use (search for `REVIEW:`).
- Replace the "Coming soon to the App Store" pill with the App Store link.
