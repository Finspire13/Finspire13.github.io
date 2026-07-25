# Repository Guidelines

## Project Structure & Module Organization

This repository is a static, one-page academic website published directly by
GitHub Pages. `index.html` contains the page content, metadata, and publication
entries. Styling lives in `assets/css/site.css`. Store profile and publication
images under `assets/images/`, icons under `assets/images/icons/`, and local
papers under `assets/papers/`. `about.html` and `about/index.html` preserve old
URLs through redirects. Keep `.nojekyll`, `robots.txt`, `sitemap.xml`, and
`assets/site.webmanifest` at their current locations.

## Build, Test, and Development Commands

There is no build or dependency-installation step.

```sh
python3 -m http.server 8000
```

Serves the repository locally at `http://localhost:8000/`.

```sh
ruby -rnokogiri -e 'd=Nokogiri::HTML5.parse(File.read("index.html")); abort(d.errors.join("\n")) unless d.errors.empty?'
```

Checks that `index.html` parses as HTML5 when Nokogiri is available.

```sh
pdfinfo assets/papers/example.pdf
```

Verifies a local PDF before linking it.

## Coding Style & Naming Conventions

Use two-space indentation in HTML, CSS, JSON, and XML. Prefer semantic HTML,
descriptive link text, and concise CSS classes. Every content image must have
useful `alt`, `width`, and `height` attributes. Publication thumbnails are
500×260 PNG files. Name new assets with lowercase kebab-case, for example
`assets/images/publications/paper-title-icml-2026.png`. Reuse CSS variables from
`:root` and keep styling in `site.css`; avoid inline styles.

## Testing Guidelines

There is no automated test suite. Preview changes at desktop and mobile widths,
check keyboard focus, and confirm every local image, PDF, manifest icon, and
redirect resolves without a 404. After structural edits, search for stale paths
with `rg 'images/|stylesheet\.css|output/pdf' index.html`.

## Commit & Pull Request Guidelines

History uses short update messages; prefer clearer imperative subjects such as
`Add ICML 2026 publications` or `Fix mobile thumbnail sizing`. Keep each commit
focused. Pull requests should summarize the user-visible effect, list validation
performed, link relevant issues, and include before/after screenshots for visual
changes.

## Repository-Specific Notes

Keep the site dependency-free and compatible with direct GitHub Pages hosting.
Do not reintroduce Jekyll, analytics, external scripts, or generated theme files
without an explicit requirement.
