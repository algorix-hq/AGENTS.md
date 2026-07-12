# AGENTS.md

Working guidance for agents operating **in this repository** (the Algorix
`AGENTS.md` boilerplate repo itself).

> **This file is not the template.** The distributable artifact is
> [`AGENTS.template.md`](./AGENTS.template.md). Do **not** copy repo-specific notes
> about this project into the template — that would ship this repo's knowledge to
> everyone who vendors it. Keep the two straight:
> - Edits to **conventions we distribute** → [`AGENTS.template.md`](./AGENTS.template.md)
> - Edits/notes about **maintaining this repo** → this file.

## What this repo is
A single-purpose repo that publishes Algorix's canonical
[`AGENTS.template.md`](./AGENTS.template.md) plus a [`README.md`](./README.md)
explaining how to use it. There is no build, no test suite, and no application
code.

## Conventions for working here
- **Communication:** match the user's language (docs and discussion here are
  typically Korean); keep the template's own text in English for portability.
- **Editing the template:** preserve the baseline markers
  (`BEGIN/END ALGORIX AGENTS BASELINE`, `BEGIN/END REPO-LOCAL CONTEXT`) and bump
  the `algorix-agents-baseline: vX.Y.Z` version marker when you change baseline
  content, so downstream repos can tell what they have.
- **Verification:** no automated checks exist. "Verify" here means proofreading
  the Markdown and sanity-checking that the two markers and the version marker are
  intact and consistent.
- **Commits:** Conventional Commits (`docs: …`, `fix: …`). Commit only when asked;
  never push or change remote state without an explicit request.

## Boundaries
- ✅ Always: edit `AGENTS.template.md`, `README.md`, this file.
- ⚠️ Ask first: renaming files, changing the install command in the README,
  restructuring the baseline/repo-local split.
- 🚫 Never: commit secrets; push or publish without an explicit request.
