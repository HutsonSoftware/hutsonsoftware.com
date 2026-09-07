# CLAUDE.md

Guidance for Claude Code (claude.ai/code) when working in this repository.

## Read session memory too

Alongside this file, read every `.md` file under `.claude/memory/` at session
start. Those files carry stated working preferences and are checked into the
repo deliberately: Claude Code's own memory store is keyed on the local
directory path, so it is lost on a repo move or a re-clone.

**Start with the GitHub workflow one.** Every change here goes on a branch and
through a pull request. Nothing is committed straight to `main`.

## What this is

The static corporate site for Hutson Software, LLC, served at
`hutsonsoftware.com`.

Hugo with custom layouts and no external theme. GitHub Actions builds on every
push to `main` and deploys to GitHub Pages, so nothing needs installing locally
to publish. `.github/workflows/hugo.yml` is the build.

```
content/          Markdown pages (about, contact, products/)
layouts/          Custom templates, no external theme
assets/css/       Styles; fingerprinted at build time
design/           Mark and icon sources; not published
static/CNAME      Custom domain for Pages
```

Local preview: `hugo server -D`, then http://localhost:1313.

## This repository is public

Everything committed here is world-readable, permanently, including commit
messages and PR titles and bodies.

- **No business detail.** Not mailboxes, vendor accounts, infrastructure,
  billing, client names or internal decisions.
- **No secrets of any kind**, including anything that merely looks like a
  credential.
- **Do not reference other properties, products or engagements**, in either
  direction — not in page content, code comments, commit messages or PR text.
  Where an explanation needs context from elsewhere, describe the mechanism
  without naming the source.

Anything that fails those tests belongs in the private notes for this site, not
in this repo.

## Content conventions

- The mark is an H knocked out of a solid tile. `design/icon.svg` is the single
  source for the favicon set, the SVG favicon and the social card. Regenerate
  from it rather than editing outputs by hand.
- `safari-pinned-tab.svg` is deliberately the bare H: Safari mask icons are
  silhouettes, so a filled tile renders as a black square.
- The published contact address is `contact@hutsonsoftware.com`. Personal
  addresses never appear on the site.
