# Q9 Forge – Projektstruktur-Konvention

## Organisation vs. Repository

Q9-Forge ist eine GitHub-Organisation (kein Repo selbst) und hält mehrere
unabhängige Repos, je mit eigener, ungemischter Git-Historie:

- **Q9-Flux** — CB030/68030-Hardware-Emulator
- **Q9-OS** — Port von echtem Microware OS-9/68K
- **Q9-Parsec** — EBNF-Parser-/Scanner-Generator
- **Q9-QCC** — QCC-Compiler (baut auf Q9-Parsec auf)
- **Vinculum** — Hardware-Zielsystem (KiCad, Image); kein `Q9-`-Präfix, da
  Hardware nicht denselben Namensdruck hat wie Software

## Namenskonvention

`Q9-<Name>`, Bindestrich, erster Buchstabe groß (`Q9-Flux`, nicht `q9-flux`
oder `Q9Flux`). Ausnahme: eigenständige Hardware-Projekte wie `Vinculum`
brauchen den Präfix nicht.

## Struktur innerhalb eines Repos

- `src/` — Quellcode.
  - **1 Modul** → Dateien direkt in `src/`
  - **>1 Modul** → je Modul ein Unterverzeichnis in `src/`
  - Im Zweifel: flach bleiben. Ein Modulverzeichnis lässt sich später leicht
    nachziehen; verwaiste leere Modulverzeichnisse stören mehr als spätes
    Aufteilen.
- `docs/` — Dokumentation. `README.md` im Repo-Root ist Pflicht.
- `test/`/`tests/` — Tests, spiegelt `src/` (modulweise oder flach,
  konsistent mit `src/`).
- `tools/` — eigenständige Hilfsprogramme, nicht Teil des Hauptbuilds.

Kein starres `include/`-Verzeichnis vorgeschrieben — bisher hat sich in der
Praxis gezeigt, dass Header neben ihrer `.c`-Datei in `src/` liegen bleiben
können, solange nichts repo-übergreifend eingebunden werden muss.

## Veraltete/aufgegebene Arbeit

Wird nicht im entsprechenden Q9-Forge-Repo liegen gelassen (verwässert die
Repo-Identität, siehe Q9-Flux' frühe "Mini-OS"-Phase). Stattdessen: mit
vollständiger Git-Historie in ein Repo unter dem persönlichen Account
`foellmy51` extrahieren, Präfix `Q9RESUME-` (z.B. `Q9RESUME-Kernel`,
`Q9RESUME-Edit`).

## Cross-Repo-Abhängigkeiten

Wenn ein Repo auf Werkzeuge/Code eines anderen Q9-Forge-Repos angewiesen ist
(z.B. Q9-QCC braucht Q9-Parsecs `ebnf`-Tool, um seinen eigenen Parser zu
erzeugen), wird das im README des abhängigen Repos dokumentiert
(Checkout-Anleitung, Build-Reihenfolge) — kein automatisches Git-Submodule
ohne expliziten Anlass.

## Dokumentationssprache

Original-Dokumentation/`.md`-Dateien werden auf **Englisch** verfasst.
Dazu jeweils eine deutsche Übersetzung mit Suffix `_de` im Dateinamen
(z.B. `ARBEITSPLAN.md` engl. Original + `ARBEITSPLAN_de.md`). Gilt
repo-übergreifend für alle Q9-Forge-Projekte, abweichend von der
pauschalen "Deutsch"-Regel in `C:\projects\PROJECT.md`.

## Issues

Repo-spezifische Bugs/Aufgaben als Issue im jeweiligen Repo. Cross-Repo-
Themen (Roadmap-übergreifend) hier in `.github` oder als Issue in diesem
Repo.
