
# Srijan Barua Portfolio — Blog Navigation Update

This package updates the existing plain-HTML portfolio without introducing a new theme or framework.

## Changes

- Added **Blog** to the homepage navigation.
- Updated the Blog link on About, Projects and Certifications pages to `blog/index.html`.
- Added a Blog landing page using the existing `css/style.css`, Archivo and Source Serif 4 fonts, colour variables, sidebar navigation and responsive rules.
- Added six article starter pages in the existing portfolio.
- Added a homepage preview for the first three articles.
- Added CSS for blog listing, article metadata, tags, article navigation and draft notices.
- Added `PUBLISHING.md` with publishing instructions.

## Local preview

Open `index.html` in a browser, or run a local static server from this directory:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Publish

Copy the contents of this package into the root of your existing GitHub Pages repository, review the changes, commit and push.

**No Jekyll build is required for these HTML pages.** The existing Markdown files remain in place and are not deleted.

## Before publishing article drafts

- Remove employer/customer names, internal URLs, IPs, hostnames, namespaces, identifiers, logs, screenshots and secrets.
- Get employer approval where needed.
- Verify the accuracy of claims and label prototypes, personal labs and proposed architectures.
- Replace draft status notices when articles are ready.
