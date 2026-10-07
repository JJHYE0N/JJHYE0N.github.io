# Jaehyeon Jeong — Quant / Finance Portfolio

Quarto portfolio for POSTECH Computer Science, quantitative finance, investing, and technology.

Repository: https://github.com/JJHYE0N/JJHYE0N.github.io

Site: https://jjhye0n.github.io/

## Local preview

Install [Quarto](https://quarto.org/docs/get-started/), version 1.10.19 (the version used in CI), then:

```sh
quarto preview
```

`quarto render` builds the site into `_site/`. Generated HTML is ignored by Git.

## Structure

```text
_quarto.yml                    Site navigation, metadata, HTML defaults
index.qmd                      Home
about.qmd                      About
resume.qmd                     Resume landing page
research/index.qmd             Automatic research listing
research/posts/<slug>/index.qmd Research notes
investments/index.qmd          Automatic investment listing
investments/posts/<slug>/index.qmd  Memos and PE / VC cases
projects/index.qmd             Automatic project listing
projects/posts/<slug>/index.qmd Engineering write-ups
assets/styles.css              Shared responsive styling
assets/favicon.svg             JJ monogram
templates/                     Four reusable authoring templates
.github/workflows/publish.yml   Build and GitHub Pages deployment
```

## Add a new piece

1. Copy a template into the appropriate `posts/<slug>/index.qmd` folder.
2. Fill in title, description, categories, and the analysis. Add a date when publishing.
3. Keep `draft: true` until the piece is ready. Remove it or set it to `false` to publish.
4. Commit and push to `main`; the relevant listing updates automatically and Pages deploys.

Example:

```sh
mkdir -p research/posts/my-study
cp templates/quant-research.qmd research/posts/my-study/index.qmd
```

The initial public entries are explicitly labeled **Planned**. Replace them with completed work or remove them as the portfolio develops. Do not present planned results as completed work.

## Resume and contact details

Add a verified PDF as `assets/resume.pdf`, then add `[Download resume](assets/resume.pdf)` to `resume.qmd`. Add confirmed GitHub / LinkedIn / contact links to the navbar in `_quarto.yml` when available.

## GitHub Pages setup

Create an empty public repository and connect it to this checkout. In **Settings → Pages → Build and deployment**, choose **GitHub Actions**. Push `main`; the included workflow renders and deploys the site. No personal access token is stored in this repository.

For a project repository, the URL is `https://<username>.github.io/<repository>/`. For a repository named `<username>.github.io`, the URL is `https://<username>.github.io/`.

Once the final URL is known, set `website.site-url` in `_quarto.yml`. The site uses Quarto-managed relative navigation so both root and project paths work.

## Analysis code

The initial site has no executable analysis or Python package dependency. If you add executable Python / R cells, configure the corresponding runtime and pinned dependencies in the build workflow, or render locally and commit Quarto's `_freeze/` outputs. `execute.freeze: auto` caches results but is not a substitute for the required analysis environment.

## Documentation

- [Quarto GitHub Pages](https://quarto.org/docs/publishing/github-pages.html)
- [Quarto document listings](https://quarto.org/docs/websites/website-listings.html)
- [GitHub Pages custom workflows](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages)
