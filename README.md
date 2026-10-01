# Exponential — Internal Business Plan

A single static page: `index.html` + `assets/`. No build step, no dependencies.

## Run locally

```sh
python3 -m http.server 8000   # then open http://localhost:8000
```

## Deploy to Vercel

- **Dashboard:** import the folder/repo, set Framework Preset to **Other**, and leave
  Build Command and Output Directory empty. `vercel.json` already sets these.
- **CLI:** `npx vercel` (preview) or `npx vercel --prod`.

`vercel.json` serves the folder as-is, caches `assets/` for a year (the file names
are content hashes), and adds basic security headers. `.vercelignore` keeps the
design-tool files below out of the deployment.

## Navigation

The header is sticky. Each link points to a section `id`, and the inline script
at the bottom of `index.html` highlights the section currently under the header.
Smooth scrolling and the header offset are handled in CSS (`scroll-behavior`,
`scroll-padding-top: var(--hdr)`). To add a section, give it an `id` and add a
matching `<a href="#id">` to `.xp-nav`.

## Design source (not deployed)

`Main.dc.html`, `support.js` and `vendor/` are the original design-tool export and
its React runtime. They are kept for reference only; `index.html` is the static
build of that design.
