# latchkeysoftware.com

Static site for Latchkey Software LLC. Plain HTML and one stylesheet — no build step,
no dependencies. Edit the HTML directly and push.

```
index.html          Home
tasteful/           Product page for Tasteful
support/            Support + FAQ  (App Store support URL)
privacy/            Tasteful privacy policy  (App Store privacy URL)
terms/              Terms of service
styles.css          The whole design system
favicon.svg         The mark
CNAME               Custom domain for GitHub Pages
```

## Deploying to GitHub Pages

1. `git init && git add . && git commit -m "Initial site"`
2. Create a repo on GitHub and push to it.
3. Repo → Settings → Pages → Source: **Deploy from a branch**, branch `main`, folder `/ (root)`.
4. Under Custom domain, enter `latchkeysoftware.com`. The `CNAME` file already holds it.
5. GitHub shows the DNS records to add. Add its four **A records** for the apex in the
   Squarespace domain panel's DNS tab, **alongside** the existing records — do not remove
   or edit the MX records, which carry your Google Workspace mail.
6. Add a `CNAME` record for `www` pointing at `<username>.github.io` so both work.
7. Tick **Enforce HTTPS** once the certificate provisions (usually minutes, up to 24h).

Screenshot the existing DNS records before you touch anything.

## Before submitting to the App Store

- `https://latchkeysoftware.com/privacy` and `/support` must load in a private window
  with a valid certificate.
- Update the Terms effective date if you publish on a different day than the one set.

## Notes

- The header lockup is drawn in HTML/SVG using JetBrains Mono, which is the actual
  wordmark face — so it scales cleanly and needs no image asset. Swap in a PNG if
  you'd rather use the exported artwork.
- Single-theme dark by design. Every colour is painted explicitly; there is no
  light-mode variant.
- Palette and type tokens live at the top of `styles.css`.
