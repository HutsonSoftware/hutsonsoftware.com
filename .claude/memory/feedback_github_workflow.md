---
name: feedback-github-workflow
description: "For all changes in this repo, create a branch and open a PR; never commit directly to main. Adam reviews and merges the PR himself."
metadata:
  node_type: memory
  type: feedback
---

For every change in this repo, work on a branch and open a PR against `main`.
Never commit directly to `main`. Adam reviews the PR and handles the
approve/merge himself — do not merge or self-approve.

**Why:** Adam wants a human-in-the-loop review gate before anything lands on
`main`, and the identical workflow in every repository so there is no per-repo
rule to remember. Here it also gates what becomes public: `main` deploys
straight to the live site.

**How to apply:**
- Before starting work, `git checkout -b <descriptive-branch-name>` off `main`.
- Commit and push to that branch.
- Open the PR with `gh pr create` or the GitHub MCP `create_pull_request` tool.
  Write a title and body that let Adam review without re-deriving context, and
  keep both free of anything that should not be public.
- Stop once the PR is open. Do not merge, do not self-approve, do not push to
  `main` directly.
- No exception for trivial changes. A typo or copy tweak takes a PR too.
