# hutsonsoftware.com

Static site for Hutson Software, LLC.

Hugo with custom layouts, no theme. GitHub Actions builds on every push to
`main` and deploys to GitHub Pages, so nothing needs to be installed locally to
publish.

## Local preview

```sh
hugo server -D    # http://localhost:1313
```

## Deploy

Push to `main`. `.github/workflows/hugo.yml` builds and publishes.

## Layout

```
content/          Markdown pages (about, contact, products/)
layouts/          Custom templates, no external theme
assets/css/       Styles; fingerprinted at build time
static/CNAME      Custom domain for Pages
```
