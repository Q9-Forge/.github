# Q9 Forge

A modular mini-OS and a family of compiler/tooling projects built around
the Q9 platform (a CB030/68030 emulator for genuine Microware OS-9).

## Repos

- [**Q9-Flux**](https://github.com/Q9-Forge/Q9-Flux) — CB030/68030 hardware emulator (Musashi CPU core), boots real Microware OS-9/68K
- [**Q9-OS**](https://github.com/Q9-Forge/Q9-OS) — port of genuine Microware OS-9/68K for Q9
- [**Q9-Parsec**](https://github.com/Q9-Forge/Q9-Parsec) — EBNF parser/scanner generator
- [**Q9-QCC**](https://github.com/Q9-Forge/Q9-QCC) — QCC compiler (C language core, IR, 68000/ARM64 backends), builds on Q9-Parsec

A hardware target system (KiCad data, later a cleaned-up image) will
follow separately as **Vinculum**.

Archived work that is no longer actively pursued lives under the personal
account [`foellmy51`](https://github.com/foellmy51) with a `Q9RESUME-`
prefix (e.g. `Q9RESUME-Kernel`, `Q9RESUME-Edit`) — full history preserved,
in case it gets picked up again someday.

See [`CONVENTIONS.md`](https://github.com/Q9-Forge/.github/blob/main/CONVENTIONS.md)
for the project structure convention and
[`ROADMAP.md`](https://github.com/Q9-Forge/.github/blob/main/ROADMAP.md)
([German: `ROADMAP_de.md`](https://github.com/Q9-Forge/.github/blob/main/ROADMAP_de.md))
for the current status.
