# tatiana-cruz.github.io

Personal academic website of Tatiana Paula da Cruz — Ph.D. Candidate, Department
of Political Science, University of Wisconsin–Madison.

Live at <https://tatianapaulacruz.com/>.

## How it works

A [Hugo](https://gohugo.io/) static site with custom layouts and no theme
dependency. Pushing to `main` triggers `.github/workflows/deploy.yml`, which
builds the site and publishes it to GitHub Pages.

## Layout

Five pages: Bio (`/`), Research, Teaching, CV, Contact.

| Path | What it holds |
|---|---|
| `content/_index.md` | Bio prose (the homepage) |
| `content/*.md` | Stub pages that select a layout |
| `data/papers.yaml` | Working papers and articles |
| `data/gallery.yaml` | The Cataguases gallery |
| `data/*.yaml` | Teaching, awards, talks, education |
| `hugo.yaml` | Name, title, tagline, contact details, menu |
| `layouts/_default/*.html` | One template per page type |
| `assets/css/style.css` | All styling |
| `static/files/` | CV and paper PDFs |
| `static/images/` | Portrait; `cataguases/` holds the gallery |

## Editing

See [UPDATING.md](UPDATING.md) — written for editing directly on GitHub, no local
setup required.

## Local preview

```bash
hugo server
```

Requires Hugo extended (`brew install hugo`).

## Credits

Gallery photographs of Cataguases, via Wikimedia Commons:

- Ponte Metálica: Paulo César Rodrigues, [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
- Town view: Pauloc33, [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)
- Fazendinha: Sérgio Mourão, [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)

The Santuário de Santa Rita de Cássia photograph is the owner's own.
