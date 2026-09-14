# Q9 Forge – Project Structure Conventions

*German version: [CONVENTIONS_de.md](CONVENTIONS_de.md)*

## Organization vs. repository

Q9-Forge is a GitHub organization (not a repo itself) and holds several
independent repos, each with its own, unmixed git history:

- **Q9-Flux** — CB030/68030 hardware emulator
- **Q9-OS** — independent, OS-9/68K-compatible operating-system kernel
- **Q9-Parsec** — EBNF parser/scanner generator
- **Q9-QCC** — QCC compiler (built on Q9-Parsec)
- **Vinculum** — hardware target system (KiCad, image); no `Q9-` prefix,
  since hardware doesn't carry the same naming pressure as software

## Naming convention

`Q9-<Name>`, hyphenated, first letter capitalized (`Q9-Flux`, not
`q9-flux` or `Q9Flux`). Exception: standalone hardware projects like
`Vinculum` don't need the prefix.

## Structure within a repo

- `src/` — source code.
  - **1 module** → files directly in `src/`
  - **>1 module** → one subdirectory per module in `src/`
  - When in doubt: stay flat. A module directory can easily be added
    later; orphaned empty module directories are more disruptive than
    splitting things up later.
- `docs/` — documentation. `README.md` at the repo root is mandatory.
- `test/`/`tests/` — tests, mirroring `src/` (per module or flat,
  consistent with `src/`).
- `tools/` — standalone helper programs, not part of the main build.

No rigid `include/` directory is mandated — in practice, headers can stay
next to their `.c` file in `src/` as long as nothing needs to be included
across repos.

## Obsolete/abandoned work

Is not left lying around in the corresponding Q9-Forge repo (it dilutes
the repo's identity, see Q9-Flux's early "Mini-OS" phase). Instead:
extract it with full git history into a repo under the personal account
`foellmy51`, prefix `Q9RESUME-` (e.g. `Q9RESUME-Kernel`,
`Q9RESUME-Edit`).

## Cross-repo dependencies

When a repo depends on tools/code from another Q9-Forge repo (e.g.
Q9-QCC needs Q9-Parsec's `ebnf` tool to generate its own parser), this is
documented in the dependent repo's README (checkout instructions, build
order) — no automatic git submodule without an explicit reason.

## Documentation language

Original documentation/`.md` files are written in **English**. Each gets
a German translation with the `_de` suffix in the filename (e.g.
`ARBEITSPLAN.md` English original + `ARBEITSPLAN_de.md`). This applies
across all Q9-Forge projects, as an exception to the blanket "German"
rule in `C:\projects\PROJECT.md`.

## Issues

Repo-specific bugs/tasks as an issue in the respective repo. Cross-repo
topics (spanning the roadmap) go here in `.github`, or as an issue in
this repo.
