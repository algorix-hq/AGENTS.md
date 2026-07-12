# AGENTS.md — Algorix boilerplate

This repo holds Algorix's default [`AGENTS.md`](./AGENTS.md): the baseline
agentic-AI collaboration convention we drop into every repository — application
code, infrastructure, docs, data, anything.

## What it is

[`AGENTS.md`](./AGENTS.md) is a standalone working agreement for AI agents. It
sets our shared conventions for communication, verification, commits/pushes, and
safety, and it reserves a **repo-local context** section (§7) that agents grow
over time into that repo's memory. It's written to be:

- **Portable** — self-contained, no external dependencies, works in any repo.
- **Self-evolving** — the agent extends the local `AGENTS.md`'s §7 as it learns,
  so knowledge persists across machines, sessions, and agents. Each repo evolves
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

This repo is the reference copy. Improvements to the shared conventions (§1–6)
land here first. Repos that already vendored `AGENTS.md` can re-pull the updated
sections when they want — but their §7 (repo-local memory) always stays theirs.
