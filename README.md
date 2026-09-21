# Personal homepage — Chengyi Dong

Single-file static site. No build step, no dependencies.

## Files
- `index.html` — the whole page
- `photo.jpg` — profile photo (600×600, square)
- `cv.pdf` — not added yet, see below

## Adding your CV later
1. Export your CV as PDF and name it exactly `cv.pdf`
2. Put it in this folder, next to `index.html`
3. Open `index.html`, find the block that starts with `<!-- TO ADD YOUR CV`
4. Delete the line starting with `<!--` and the line that is just `-->`,
   keeping only `<a href="cv.pdf">CV</a>` between them
5. Commit and push:

       git add cv.pdf index.html
       git commit -m "Add CV"
       git push

The same commented block pattern is there for Google Scholar and DBLP.

## Deploy to GitHub Pages
1. Create a **public** repo named `dcy456.github.io`
2. Push these files to the `main` branch
3. Settings → Pages → Source: "Deploy from a branch" → `main` / `/ (root)`
4. Live in ~1 minute at `https://dcy456.github.io`

## Preview locally
    python3 -m http.server 8000
Then open http://localhost:8000
