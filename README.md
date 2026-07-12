# AGENTS.md — Algorix boilerplate

This repo holds Algorix's default [`AGENTS.md`](./AGENTS.md): the baseline
agentic-AI collaboration convention we drop into every repository — application
code, infrastructure, docs, data, anything.

## What it is

[`AGENTS.md`](./AGENTS.md) is a standalone working agreement for AI agents. Its
baseline sections (§1–§6) are **defaults, not dogma**: agents observe the repo's
own practices first and fall back to these defaults only when the repo shows none.
It reserves a **repo-local context** section (§7) that agents grow over time into
that repo's memory, driven by concrete events (a command first succeeds, a wrong
command gets corrected, the user corrects an approach). It's written to be:

- **Portable** — no external dependencies, works in any repo type (code, infra,
  docs, data).
- **Self-evolving** — the agent extends the local `AGENTS.md`'s §7 as it works, so
  knowledge persists across machines, sessions, and agents. Each repo evolves
  *its own copy*; the file does not phone home to this one.

## How to use it

Copy [`AGENTS.md`](./AGENTS.md) into the root of your repository:

```sh
# From within your target repo
curl -fsSL https://raw.githubusercontent.com/algorix-hq/AGENTS.md/main/AGENTS.md -o AGENTS.md
```

Or paste it in as boilerplate when you `init` a new repo. Once it's in your repo,
it belongs to that repo — commit it, and let agents grow its §7 as they work.

### Per-developer language override (optional)

`AGENTS.md` doesn't hard-code a conversation language. If an individual developer
wants a specific language without imposing it on everyone, they create a
git-ignored `.agents.local.md` in the repo root. See §1 of
[`AGENTS.md`](./AGENTS.md) for the exact rules.

## Updating the convention

This repo is the reference copy. Improvements to the baseline sections (§1–§6)
land here first.

There is **no automatic update path** once a repo has vendored `AGENTS.md` and
grown its §7 — §7 is now that repo's own memory. To adopt an improved baseline,
**manually replace §1–§6 in the target repo and leave its §7 untouched.**

If a repo re-syncs the baseline often and the manual merge becomes a chore,
consider **splitting the two concerns**: keep the baseline in `AGENTS.md` and move
the repo-local memory to its own file (e.g. `.agents/notes.md`), with `AGENTS.md`
pointing at it. That makes the baseline freely replaceable and removes the merge
problem entirely — at the cost of the "one self-contained file" simplicity. It's a
tradeoff; pick based on how often you re-sync.
