# ITSC 2026 Tutorial website

Static site for the half-day tutorial **Bridging the Sim-to-Real Gap in Traffic Engineering:
Integrating Traffic Signal Control and Reinforcement Learning**, at IEEE ITSC 2026 in Naples
(Friday 18 September 2026, 14:00–16:00), plus a page for the **Sim2Signal** benchmark.

Built on the LibSignal project site (styleshout template).

## Pages

- `index.html` — Sim2Signal: Sim-to-Real Benchmarks for Traffic Signal Control
- `tutorial.html` — the tutorial: aim, agenda, organizers

## Styling

`css/main.css` and `css/base.css` are the template's, kept close to upstream. Two exceptions:

- **Accent colour.** The template's green was replaced throughout `main.css` with a deep
  academic blue. The mapping was `#39b54a → #2b6cb0` (accent), `#44c455 → #3d82cc` (hover),
  `#309a3f → #1f5089` (pressed), `#2a9038 → #1a4e85` (rule on the accent background),
  `#b2fabc → #cfe3f7` (tint text on the accent background). To recolour again, search those
  five values. The pristine original is in `DaRL-LibSignal.github.io-gh-pages.zip`.
- **`css/site.css`** holds local layout overrides and loads after `main.css`: the wide
  image-less hero (both pages; the overview figure appears only in the Sim2Signal About section), the header and footer wordmarks as real text rather than the baked-in
  `logo.png` (which reads "LibSignal"), the pill-shaped agenda badges (the template's fixed
  circle clipped "10 min"), and the white background + centred heading rule for the agenda
  and organizers sections (the template keys those styles on `#about` alone, so any other
  section id falls back to the dark body background and its headings disappear).

## Local preview

```
python3 -m http.server 8000
```

then open <http://localhost:8000>. Serve it over HTTP rather than opening the file directly —
the parallax hero and scroll animations need a real origin.

## Deploy on GitHub Pages

No build step — it is plain HTML/CSS/JS, so Pages serves the repo as-is. All internal links
are relative, so either hosting style below works without editing the HTML.

**Project site** (simplest): push this folder to a repo, then
Settings → Pages → Build and deployment → Deploy from a branch → `main` → `/ (root)`.
Served at `https://<account>.github.io/<repo>/`.

**Organization site** (what LibSignal uses): name the repo `<org>.github.io` and it is served at
`https://<org>.github.io/` with no path prefix.

`.nojekyll` is present so Pages copies files verbatim instead of running them through Jekyll.

## TODO

- Final Sim2Signal author list (`index.html` footer) — the .tex still has the AAAI placeholder block
- Public code repo URL — `Sim2RealTSCBenchMark` is assumed in both pages
- Paper link once it is public (`index.html` hero button)
- Per-block slide / video / code links in the agenda, added after the session
- Room / track number for the session, once ITSC publishes the programme
