# SEAIS 2026 — Symposium Website

Website of the **Special Symposium on Software Engineering and AI (SEAIS)**,
June 30 – July 2, 2026, Hasso Plattner Institute (HPI), Potsdam, Germany.

Hosted by the [Chair for Software Engineering and AI](https://hpi.de/en/research/research-groups/software-engineering-and-ai/) at HPI.

## Structure

A static page, no build step, no runtime data fetch, no dependencies beyond
fonts loaded from the Google Fonts CDN (Inter, IBM Plex Mono).

```
index.html              Entire site (markup + embedded CSS + embedded speaker data)
assets/
  hero-hpi.jpg          Header photo (Photo: HPI)
  campus-map.jpg        Annotated campus map with routes to the SEAIS entrance
  speakers/             Local speaker portraits used by the inline speaker data
```

## Editing

All content lives in `index.html`:

- **Program** — `<section id="program">`. Each row is a `div.slot`;
  `slot kn` marks keynotes/panels (red), `span.room` renders the room tag.
- **Speakers** — edit the inline `SPEAKERS` array in the final `<script>` block.
  Use local image paths such as `assets/speakers/reem-ayad.jpg`. Leave `image`
  empty for the default avatar.
- **Venue** — `<section id="venue">`. The Google Maps iframe is pinned to
  coordinates `52.392667, 13.124833` (entrance at Haus L); the
  "Open in Google Maps" link uses the shared location link.
- **Colors/typography** — CSS custom properties at the top of the
  `<style>` block (palette derived from the HPI corporate design).

The page is responsive (down to ~360 px) and includes a print stylesheet,
so the program can be printed directly from the browser.

## Deployment (GitHub Pages)

1. Push `index.html` and `assets/` to the `main` branch root.
2. Repository Settings → Pages → Source: "Deploy from a branch",
   branch `main`, folder `/ (root)`.
3. The site is served at `https://<org-or-user>.github.io/<repo>/`.

Any other static host (institute web space, Netlify, etc.) works the same
way — copy `index.html` and `assets/` to the document root.

## Image credits

Photos and map material: Hasso Plattner Institute (HPI). Not licensed for reuse outside this site.

Speaker portraits: source pages of the respective speakers or their institutions at the date of the event.
