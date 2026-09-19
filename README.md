# Md. Ashfaq Shahamat Rahi — Portfolio

Personal portfolio site, built as a single static page. Live at:
**https://asrahi-7.github.io/as-rahi**

## Files

| File            | Purpose                                                              |
|-----------------|-----------------------------------------------------------------------|
| `index.html`    | The site. References `portrait.webp` for the profile photo.          |
| `portrait.webp` | Profile photo, background removed, used by `index.html`.             |

Both files must stay in the same folder — `index.html` loads the photo by filename, not by embedding it.

> A second, self-contained version (`as-rahi-portfolio.html`, photo embedded as base64) is kept separately for emailing or sharing as one file. It is not part of the deployed site.

## Stack

No build step, no framework, no dependencies to install.

- Plain HTML5 + CSS (custom properties, grid/flexbox)
- [IBM Plex Sans](https://fonts.google.com/specimen/IBM+Plex+Sans) and [Newsreader](https://fonts.google.com/specimen/Newsreader) via Google Fonts CDN
- A small vanilla-JS `IntersectionObserver` snippet to highlight the current section in the side nav
- One inline SVG line chart (semester GPA) — no charting library

## Running locally

Just open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploying updates (GitHub Pages)

1. Edit `index.html` directly (sections are labelled: Introduction, Projects, Education, Skills, Activities, Certifications, Contact).
2. Commit and push to the `asrahi-7.github.io` repo, `as-rahi` folder (or repo root, depending on how Pages is configured).
3. GitHub Pages rebuilds automatically — changes usually appear within a minute or two.

## Common edits

- **Swap the photo:** replace `portrait.webp` with a new image using the exact same filename. No HTML/CSS changes needed. Keep it roughly square (1:1) for the crop to look right.
- **Add a project:** copy one of the `<div class="mini">` blocks (for a small project) or a `<article class="proj-major">` block (for a featured one) inside `#projects`, and edit the text and links.
- **Update GPA chart:** edit the `<polyline points="...">` and `<circle>` coordinates plus the number labels inside the `<svg>` under `#education`. Coordinates are hand-placed, not generated — a value of `y=94` sits at 3.50, `y=54` at 3.75, `y=14` at 4.00 on the current scale.
- **Update contact info:** the four tiles are in `.contact-grid` near the bottom of the file.

## Notes

- No analytics, tracking, or external JS beyond the two font stylesheets and Font Awesome-free inline SVG icons (all icons are hand-written SVG, no icon font).
- Dark theme only; respects `prefers-reduced-motion` for the entrance animation.
