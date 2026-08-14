# hutsonsoftware.com

Static site for Hutson Software, LLC. Hugo source and published output live in
this one repo. GitHub Actions builds on every push to `main` and deploys to
GitHub Pages. There is no theme submodule and no local build step to remember.

## Local preview

```sh
hugo server -D    # http://localhost:1313
```

## Deploy

Push to `main`. That's it. `.github/workflows/hugo.yml` builds and publishes.

## Layout

```
content/          Markdown pages (about, contact, projects/)
layouts/          Custom templates, no external theme
assets/css/       Styles; fingerprinted at build time
static/CNAME      Custom domain for Pages
```

## Contact address

The site publishes no email address on purpose. To add one: add
`hutsonsoftware.com` as a secondary domain in the existing Google Workspace,
create a role address such as `contact@hutsonsoftware.com` there, then set
`params.email` in `hugo.toml`. The footer link returns on its own.

Never publish a personal address, and never publish the working mailbox behind
the Track My Job aliases. Role addresses only.

Notes like this belong here rather than in `content/`. HTML comments in content
are passed through to the built pages and republished in full in `index.xml`.

## Domain

`hutsonsoftware.com` is registered at GoDaddy. DNS points the apex at GitHub
Pages' four A records, with `www` as a CNAME to `hutsonsoftware.github.io`.
