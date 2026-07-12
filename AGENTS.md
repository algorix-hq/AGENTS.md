# AGENTS.md

Working guidance for agents operating **in this repository** (the Algorix
`AGENTS.md` boilerplate repo itself).

> **This file is not the template.** The distributable artifacts are
> [`AGENTS.template.md`](./AGENTS.template.md) (public, vendor-neutral) and
> [`AGENTS.algorix.md`](./AGENTS.algorix.md) (Algorix internal variant). Do **not**
> copy repo-specific notes about this project into either — that would ship this
> repo's knowledge to everyone who vendors it. Keep the two straight:
> - Edits to **conventions we distribute** → the two template files.
> - Edits/notes about **maintaining this repo** → this file.

## What this repo is
A single-purpose repo that publishes the canonical AGENTS baseline in two forms —
[`AGENTS.template.md`](./AGENTS.template.md) (public, vendor-neutral) and
[`AGENTS.algorix.md`](./AGENTS.algorix.md) (Algorix internal, adds §0 org
conventions) — plus a [`README.md`](./README.md) explaining how to use them. There
is no build, no test suite, and no application code.

## Conventions for working here
- **Communication:** match the user's language (docs and discussion here are
  typically Korean); keep the templates' own text in English for portability.
- **Keep the two templates in sync:** the baseline (§1–§6, Appendix) must stay
  identical between `AGENTS.template.md` and `AGENTS.algorix.md`. When you change
  baseline content, edit **both** and bump the version marker in both. The only
  intended differences: `AGENTS.algorix.md` uses `ALGORIX`-named markers, an
  `algorix-agents-baseline:` version tag, and adds §0 (org conventions).
- **Editing a template:** preserve the markers (`BEGIN/END [ALGORIX] AGENTS
  BASELINE`, `BEGIN/END REPO-LOCAL CONTEXT`) and bump the
  `[algorix-]agents-baseline: vX.Y.Z` version marker when you change baseline
  content, so downstream repos can tell what they have.
- **Verification:** no automated checks exist. "Verify" here means proofreading
  the Markdown, confirming the two templates' baselines match, and sanity-checking
  that all markers and version tags are intact and consistent.
- **Commits:** Conventional Commits (`docs: …`, `fix: …`). Commit only when asked;
  never push or change remote state without an explicit request.

## Boundaries
- ✅ Always: edit `AGENTS.template.md`, `AGENTS.algorix.md`, `README.md`, this file.
- ⚠️ Ask first: renaming files, changing the install command in the README,
  restructuring the baseline/repo-local split.
- 🚫 Never: commit secrets; push or publish without an explicit request.
