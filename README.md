# Grade 7 Integrated Science course site

Static site of student-facing resources for Grade 7 Integrated Science.
No build step, no dependencies. Every page is plain HTML and opens correctly by double-clicking it.

This site is currently a scaffold: the structure and styling are finished, and the six unit pages
are waiting for content.

## Publishing this to GitHub Pages

Do this once. After that, updating the site is just editing a file and pushing.

1. Go to github.com and create a new repository named `g7-integrated-science`. Set it to **Public**
   (GitHub Pages on free accounts requires public). Do not add a README, since this folder has one.
2. Upload this entire folder. With no command line: on the new empty repo page, click
   **uploading an existing file**, then drag the *contents* of this folder in. Commit.
3. In the repo, go to **Settings → Pages**. Source: **Deploy from a branch**, branch **main**,
   folder **/ (root)**. Save.
4. Wait about a minute and reload that screen. It will show your live URL:
   `https://YOUR-USERNAME.github.io/g7-integrated-science/`

Link that URL from your Canvas modules.

## Filling in the units

Each unit page is a placeholder. To name a unit:

1. Open `unit-1/index.html`. Change the `<h1>` and the `<p class="lede">` line.
2. Open `index.html` at the site root and update that unit's card: the `.title` and `.desc` lines.

To add a resource to a unit, drop the HTML file into that unit folder, then copy an
`<a class="resource">` block from the AP Psychology site's `unit-0/index.html` as a model, or ask
Claude to wire it up.

## A note on shared course documents

Your G7 course documents that were written by the team need whole-team approval before changes.
Anything you post here should be material you created yourself, or material the team has agreed to
publish. This site is public to anyone holding the link.

## Search visibility

Every page carries `<meta name="robots" content="noindex, nofollow">`, which is what keeps these
pages out of Google. The `robots.txt` file is included but is ignored on a project site like this
one, since search engines only read `robots.txt` at a domain root. The meta tag is what matters.

## Look and feel

The site uses one visual direction throughout: rounded cards, a teal gradient masthead,
pill-shaped navigation, and Fredoka for headings with Inter for body text. It is meant to
feel like something a Grade 7 student would expect to be able to tap.

Fonts are served from `assets/fonts/` rather than from Google Fonts. That is deliberate: a
school network that blocks external hosts would otherwise strip the typography off every
page. Nothing on this site loads from a CDN.

## Structure

```
index.html            course home, unit cards
assets/site.css       styling for the home and unit landing pages
assets/fonts/         self-hosted woff2 files (Fredoka, Inter, Font Awesome solid)
assets/img/           images and figures
unit-1/ ... unit-6/   unit landing pages
unit-1/*.html         resource pages, each self-contained with its styles inlined
.nojekyll             tells GitHub Pages to serve files as-is
```

Resource pages carry their own copy of the stylesheet so they still work when handed out
as a single file or uploaded to Canvas. The one thing that does not survive that trip is
the fonts, since they live in `assets/fonts/`; the pages fall back to system fonts and stay
perfectly readable.

`unit-1/atomworks-lab.html` keeps the dark look it was generated with. Its Tailwind CSS,
icons, and fonts are all compiled or vendored into the page, so it does not depend on any
CDN either.
