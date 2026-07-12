# AGENTS.md — Algorix boilerplate

This repo publishes Algorix's canonical [`AGENTS.template.md`](./AGENTS.template.md):
the baseline agentic-AI collaboration convention we drop into every repository —
application code, infrastructure, docs, data, anything.

> **Two AGENTS files, different jobs:**
> - [`AGENTS.template.md`](./AGENTS.template.md) — the artifact you copy into other
>   repos (renaming it to `AGENTS.md` there).
> - [`AGENTS.md`](./AGENTS.md) — guidance for working in *this* boilerplate repo.
>
> They're separate so that agents working here never write this repo's own notes
> into the template everyone else vendors.

## What the template is

[`AGENTS.template.md`](./AGENTS.template.md) is a standalone working agreement for
AI agents. Its baseline sections (§1–§6) are **defaults, not dogma**: agents
observe the repo's own practices first and fall back to these defaults only when
the repo shows none. §5 is a **safety floor** that always applies. The template
reserves a **repo-local context** section (§7) that agents grow over time into
that repo's memory, driven by concrete events (a command first succeeds, a wrong
command gets corrected, the user states a durable rule). It's written to be:

- **Portable** — no external dependencies, works in any repo type.
- **Self-evolving** — the agent extends the local copy's §7 as it works, so
  knowledge persists across machines, sessions, and agents. Each repo evolves
  *its own copy*; the file does not phone home to this one.

## How to use it

From within your target repo, install the template as `AGENTS.md` — without
clobbering an existing one:

```sh
# Refuse to overwrite an existing AGENTS.md (which may hold a grown §7)
test ! -e AGENTS.md || { echo "AGENTS.md already exists; not overwriting." >&2; exit 1; }

# Latest baseline:
curl -fsSL https://raw.githubusercontent.com/algorix-hq/AGENTS.md/main/AGENTS.template.md -o AGENTS.md

# …or pin a reproducible version (recommended for teams):
# curl -fsSL https://raw.githubusercontent.com/algorix-hq/AGENTS.md/v1.1.0/AGENTS.template.md -o AGENTS.md
```

Or paste it in as boilerplate when you `init` a new repo. Once it's in your repo,
it belongs to that repo — commit it, and let agents grow its §7 as they work.

### Make sure your agent actually reads it

`AGENTS.md` is recognized natively by many tools (Codex, Amp, Jules, opencode,
and others), but discovery varies — some tools need a one-line pointer from their
own config. If yours does, add one so the file is read on entry:

- **Cursor** → in `.cursorrules` (or `.cursor/rules/*`): `Read AGENTS.md fully before doing anything.`
- **Claude Code** → in `CLAUDE.md`: `See AGENTS.md for the working agreement; follow it.`
- **GitHub Copilot** → in `.github/copilot-instructions.md`: `Follow AGENTS.md.`
- **Windsurf** → in `.windsurfrules`: `Read AGENTS.md before acting.`

Keep the pointer to one line — the real content stays in `AGENTS.md` so there's a
single source to maintain.

### Per-developer language override (optional)

The template doesn't hard-code a conversation language. If an individual developer
wants a specific language without imposing it on everyone, they create a
git-ignored `.agents.local.md` in the repo root. See the Appendix of
[`AGENTS.template.md`](./AGENTS.template.md) for the exact rules.

## Updating the convention

This repo is the reference copy; baseline improvements land here first and bump the
`algorix-agents-baseline: vX.Y.Z` marker at the top of the template.

There is **no automatic update path** once a repo has vendored the file and grown
its §7 — §7 is now that repo's own memory. The template is built for a clean manual
update: everything between the `BEGIN/END ALGORIX AGENTS BASELINE` markers is the
replaceable baseline (§1–§6 plus intro, instruction hierarchy, and Appendix), and
everything between `BEGIN/END REPO-LOCAL CONTEXT` is the repo's own §7.

**To adopt a newer baseline:** replace the baseline block only, and leave the
repo-local block untouched. Compare version markers to see what changed.

If you re-sync often and even that is a chore, you can instead **split the two
concerns** — keep the baseline in `AGENTS.md` and move the repo-local memory to its
own file (e.g. `.agents/notes.md`) referenced from `AGENTS.md`. That makes the
baseline freely replaceable at the cost of the single-file simplicity. It's a
tradeoff; pick based on how often you re-sync.
