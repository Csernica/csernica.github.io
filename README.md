# Tim Csernica — personal website

A single-page site built as a Claude Design canvas. It is a self-contained static
bundle: the runtime (`support.js`) loads React and Babel from a CDN at page load and
renders the canvas. No build server is required — any static host works.

This repo is kept **isolated** from the parent faculty-application workspace so that
private, school-specific notes are never published by accident.

## Source of truth

- **`Csernica Site.dc.html`** is the editable source (open it in the Claude Design canvas).
- **`index.html`** is a *copy* of that file and is what gets served. After editing the
  source, regenerate the entry point:

  ```bash
  cp "Csernica Site.dc.html" index.html
  ```

  The site title, description, and favicon live in the literal `<head>` of the source
  file (above `support.js`) so search engines see them without running JavaScript —
  preserve them if the canvas editor rewrites the head.

## Deploying (GitHub Pages)

- `.nojekyll` is required: it stops GitHub Pages' Jekyll from ignoring the `_ds/` folder
  (Jekyll drops `_`-prefixed directories, which would break the stylesheet).
- Push to a GitHub repo, then enable Pages on the default branch, root folder.

## Assets

`figures/`, `Photos/`, and `Csernica_CV.pdf` are referenced by relative path. Working
files (`source/`, `uploads/`, the source `.docx`, unused figures) are git-ignored.
