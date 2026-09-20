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

## Structure

```
index.html            course home, unit cards
assets/site.css       all styling for the site
unit-1/ ... unit-6/   unit landing pages
.nojekyll             tells GitHub Pages to serve files as-is
```
