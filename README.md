# LENA website

Website of the LENA research project, built with
[Zola](https://www.getzola.org/) and the
[researchproject](https://github.com/KonradHoeffner/zola-theme-researchproject)
theme.

This is a first draft. The page structure and theme are in place; project
content, contact details and the legal imprint still need to be filled in.

## Local development

The theme is included as a git submodule:

```sh
git submodule update --init --recursive
zola serve
```

The site is served at <http://127.0.0.1:1111>. To build the static site:

```sh
zola build
```

The output is written to `public/`.

## Structure

- `zola.toml` — title, URL, tagline, colour and other site settings
- `content/` — one Markdown file per page; sidebar order is controlled by `weight`
- `static/logo.svg` — project logo
- `static/publications.bib` — publication data and download

## Deployment

The workflow in `.github/workflows/build.yml` builds the site and deploys it to
GitHub Pages. Set **Pages → Source** to **GitHub Actions** in the repository
settings.

The site is served at <https://lenaproject.github.io/>. This requires the
repository to be named `lenaproject.github.io`, because GitHub only serves an
organisation Pages site at the domain root from that repository name. A custom
domain can be added later by setting `base_url` in `zola.toml` and adding a
`static/CNAME` file.
