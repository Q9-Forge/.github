# Q9 Forge

Modulares Mini-OS und Compiler-/Werkzeug-Familie rund um die Q9-Plattform
(CB030/68030-Emulator für echtes Microware OS-9).

## Repos

- [**Q9-Flux**](https://github.com/Q9-Forge/Q9-Flux) — CB030/68030-Hardware-Emulator (Musashi-CPU-Kern), bootet echtes Microware OS-9/68K
- [**Q9-OS**](https://github.com/Q9-Forge/Q9-OS) — Port von echtem Microware OS-9/68K für Q9
- [**Q9-Parsec**](https://github.com/Q9-Forge/Q9-Parsec) — EBNF-Parser-/Scanner-Generator
- [**Q9-QCC**](https://github.com/Q9-Forge/Q9-QCC) — Tiny-C-Compiler (C-Sprachkern, IR, 68000-/ARM64-Backends), baut auf Q9-Parsec auf

Hardware-Zielsystem (KiCad-Daten, später bereinigtes Image) folgt separat als
**Vinculum**.

Archivierte, nicht mehr aktiv weiterverfolgte Vorarbeiten liegen unter dem
persönlichen Account [`foellmy51`](https://github.com/foellmy51) mit
`Q9RESUME-`-Präfix (z.B. `Q9RESUME-Kernel`, `Q9RESUME-Edit`) — mit voller
Historie, falls sie mal wieder aufgegriffen werden.

Siehe [`CONVENTIONS.md`](https://github.com/Q9-Forge/.github/blob/main/CONVENTIONS.md)
für die Projektstruktur-Konvention und
[`ROADMAP.md`](https://github.com/Q9-Forge/.github/blob/main/ROADMAP.md)
für den aktuellen Stand.
