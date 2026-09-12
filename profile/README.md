# Q9-Forge


<img width="300" height="300" alt="image" src="https://github.com/user-attachments/assets/0f469c58-eebb-429b-91bd-9fc9ef6df503" />


Q9-Forge ist eine modulare Entwicklungsumgebung für die Q9-Plattform. Das
Projekt verbindet einen eigenen Kernel, Emulatoren und eine portable
Compiler-Werkzeugkette für historische und zukünftige Zielarchitekturen.

## Repositories

- [Q9-OS](https://github.com/Q9-Forge/Q9-OS) — eigener Kernel und die
  Betriebssystem-Grundlagen für Q9; zunächst für 68k, später für weitere
  Architekturen.
- [Q9-Flux](https://github.com/Q9-Forge/Q9-Flux) — Emulator- und
  Hardware-Visualisierungsprojekt mit Bereichen für 68k, x86 und Geräte.
- [Q9-QCC](https://github.com/Q9-Forge/Q9-QCC) — Compiler-Werkzeugkette mit
  Treiber, C-Frontend, Q9-Zwischencode, Interpreter und Backends.
- [Q9-Port](https://github.com/Q9-Forge/Q9-Port) — vorgesehenes Repository
  für spätere Portierungsarbeiten; derzeit noch nicht aktiv.

## Projektstruktur

Die Projekte sind in eigenständige Repositories aufgeteilt. Dadurch bleiben
Kernel, Emulator, Compiler und Portierungsarbeiten unabhängig versionierbar.
Architekturabhängiger Code wird innerhalb der Projekte getrennt gehalten;
gemeinsame Quellen liegen in einem eigenen Bereich.

## Status

Q9-Forge befindet sich in aktiver Entwicklung. Der Schwerpunkt liegt derzeit
auf dem Q9-Kernel, dem 68k-Emulator und der Vervollständigung der
Q9-QCC-Werkzeugkette.

Weitere Informationen:

- [Projektkonventionen](../CONVENTIONS.md)
- [Roadmap](../ROADMAP.md)
- [Roadmap auf Deutsch](../ROADMAP_de.md)
