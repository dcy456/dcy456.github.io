# Personal homepage — Chengyi Dong

Live at **https://dcy456.github.io/**

Single-file static site. No build step, no dependencies, no framework.
Edit `index.html`, push, done.

## Files

| file | what it is |
|---|---|
| `index.html` | the entire page — content **and** styling |
| `photo.jpg` | profile photo, square, 600×600 |
| `cv.pdf` | not added yet, see below |

## Updating the site

```bash
cd ~/code/dcy456.github.io
git pull                      # only needed if you edited from another machine
# ... edit index.html ...
git add -A
git commit -m "Add WASA paper link"
git push
```

GitHub rebuilds automatically. The change is live in 30–60 seconds.
If you do not see it, hard-reload (`Cmd+Shift+R`) — the browser caches the old page.

### Preview before pushing

```bash
cd ~/code/dcy456.github.io && python3 -m http.server 8000
```

Open http://localhost:8000. Reload after each edit. `Ctrl+C` to stop.

## Common edits

Everything lives in `index.html`. Search for the marker, edit the text around it.

**Add a publication** — copy an existing `<li class="pub">` block and change the
fields. Newest goes first. Own name stays wrapped in `<strong>`:

```html
<li class="pub">
  <span class="title">Paper Title</span>
  <span class="authors"><strong>Chengyi Dong</strong>, Co-Author</span>
  <span class="meta">
    <span class="venue">Venue Name (ABBREV)</span>, 2027.
    <span class="refs">[<a href="https://doi.org/...">DOI</a>]</span>
  </span>
</li>
```

For something accepted but not yet out, add `<span class="badge">To appear</span>`
right after the year instead of a link.

**Add the CV** — name the PDF `cv.pdf`, put it in this folder, then find the block
starting `<!-- TO ADD YOUR CV` and delete the line starting with `<!--` and the
line that is just `-->`, keeping `<a href="cv.pdf">CV</a>` between them.
Google Scholar and DBLP links are commented out the same way.

**Replace the photo** — overwrite `photo.jpg` with another square image. The page
crops it to a circle. Around 600×600 keeps the file small.

**Change a colour** — the `:root` block near the top defines every colour once,
and the `@media (prefers-color-scheme: dark)` block below it redefines them for
dark mode. Change both or the page breaks in one theme.

**Update the date** — the footer says `Last updated: ...`. Bump it when you make
a real change.

## Custom domain

Put a file named `CNAME` in this folder containing just the domain
(e.g. `chengyidong.com`), push, then point an A record at GitHub's four Pages IPs
at your registrar. Settings → Pages shows the verification status.
