# hutsonsoftware.com

Static site for Hutson Software, LLC. Hugo source and published output live in
this one repo — GitHub Actions builds on every push to `main` and deploys to
GitHub Pages. There is no theme submodule and no local build step to remember.

## Local preview

```sh
hugo server -D    # http://localhost:1313
```

## Deploy

Push to `main`. That's it — `.github/workflows/hugo.yml` builds and publishes.

## Layout

```
content/          Markdown pages (about, contact, projects/)
layouts/          Custom templates — no external theme
assets/css/       Styles; fingerprinted at build time
static/CNAME      Custom domain for Pages
```

## Domain

`hutsonsoftware.com` is registered at GoDaddy. DNS points the apex at GitHub
Pages' four A records, with `www` as a CNAME to `hutsonsoftware.github.io`.
