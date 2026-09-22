# valentin-baron.github.io

Static personal landing page. No framework, no build pipeline: one `index.html`
with inline CSS and a little vanilla JS, plus two GIFs in `assets/`.

## Deploy

1. Create a GitHub repository named exactly `valentin-baron.github.io`.
2. Push this folder to the default branch.
3. Repository, Settings, Pages, Source: *Deploy from a branch*, branch `main`, folder `/ (root)`.
4. Live at <https://valentin-baron.github.io/> within a minute or two.

`.nojekyll` disables Jekyll processing, which this page does not need.

## Editing

`index.html` is what GitHub Pages serves. `.build/` holds the working copy the
page is assembled from. It is not committed (see `.gitignore`) and can be
deleted without affecting the deployment:

- `.build/page.html` is the page body (title, styles, markup, script) without the
  `<!doctype>`/`<head>` wrapper.
- `.build/preview.html` is the same file with the GIFs inlined as data URIs, for
  previewing the page as a single self-contained file.

Project cards are hand-written on purpose: no GitHub API call, no rate limit, no
loading flicker. Update them when a project changes.

## Design

- Palette: [Everforest](https://github.com/sainnhe/everforest/blob/master/palette.md)
  by sainnhe (MIT), medium contrast, light and dark sets.
- Content sits on paper sheets. Above 900px they stack into a deck: `shuffle`
  sends the top sheet to the back, the index in the sidebar brings any sheet to
  the front, and clicking a sheet raises it. Below 900px the deck collapses into
  a normal scrolling document, which is also what happens without JavaScript.
- Sheets carry a static SVG grain texture. Nothing animates on scroll; the only
  motion is the shuffle, and `prefers-reduced-motion` turns it into an instant swap.
- The cat outline on the "Currently" sheet is the `cat` icon from
  [Lucide](https://lucide.dev/) (ISC licence), inlined as SVG.
- Theme follows the OS by default; the toggle cycles auto, light, dark and stores
  the choice in `localStorage`.
