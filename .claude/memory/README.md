# Session memory

Claude Code memories, checked into the repo on purpose.

Claude Code's own memory store is keyed on the local directory path, so it is
lost on a repo move or a re-clone. Checking these files in means the context
survives that. `CLAUDE.md` instructs a session to read this directory at start.

## What's here

- `MEMORY.md` — the index. One line per memory file.
- `feedback_*.md` — stated preferences on how a session should work here.

## When to add, update or prune

- **Add** when Adam says "remember X", or when an observation is non-obvious
  enough that a future session would otherwise reinvent it.
- **Update** in place when the underlying fact changes.
- **Prune** what has stopped being true. Git holds the history.

**This repository is public.** Everything here is world-readable. Keep these
files to how work is done in this repo; business detail, other properties and
anything resembling a credential do not belong in them.
