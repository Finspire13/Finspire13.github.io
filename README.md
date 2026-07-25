# Daochang Liu — Academic Website

Source for [finspire13.github.io](https://finspire13.github.io/), a static
one-page academic website hosted with GitHub Pages.

## Structure

- `index.html` — page content and metadata
- `assets/css/site.css` — all site styling
- `assets/images/` — profile, publication, and icon images
- `assets/papers/` — locally hosted publication PDFs
- `about.html` and `about/index.html` — compatibility redirects for old URLs

There is no build step. The `.nojekyll` marker tells GitHub Pages to publish
the files directly.

For a local preview, run:

```sh
python3 -m http.server 8000
```

Then open `http://localhost:8000/`.

The visual design is adapted from
[Jon Barron's academic website](https://github.com/jonbarron/jonbarron.github.io).
The earlier Jekyll migration approach was informed by
[Leonid Keselman's fork](https://github.com/leonidk/leonidk.github.io).
