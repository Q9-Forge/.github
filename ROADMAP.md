# Q9 Forge – Roadmap

Stand: 2026-07-31 (Tag der Repo-Reorganisation).

## Aktueller Stand je Repo

- **Q9-Flux**: aktiv, funktionsfähiger CB030-Emulator, bootet echtes
  Microware OS-9 (RBF/PCF-Descriptoren, Netzwerk, PMMU). Frisch bereinigt um
  die frühe, aufgegebene "eigenes Mini-OS"-Vision (→ `Q9RESUME-Kernel`).
- **Q9-OS**: gerade erst angelegt, bisher nur das `mbr`-Tool. Rest des
  Microware-OS-9-Ports steht noch aus.
- **Q9-Parsec**: aktiv, ausführlich getestete Regressionssuite
  (`runtests.sh`). Offener Punkt: [#53](https://github.com/Q9-Forge/Q9-Parsec/issues/53)
  — fünf Testgrammatiken ohne automatischen Erzeugungsschritt.
- **Q9-QCC**: frisch aus Q9-Parsec extrahiert. Umfangreicher Tiny-C-Compiler
  mit 68000-/ARM64-Backends, siehe dortiges `docs/TEILPROJEKTE.md` für die
  Sprachkern-Roadmap (Priorität P0: Stringkonstanten, Literale, `typedef`,
  `enum`, `struct`, ...). Braucht noch eine eigenständige Testsuite (bisher
  nur über Q9-Parsecs `runtests.sh` mitgetestet).
- **Vinculum**: noch nicht angelegt, folgt mit KiCad-Daten und später einem
  bereinigten (Microware-freien) Image.

## Nächste Schritte (unsortiert, kein Commitment)

- Q9-Parsec#53 beheben (fünf fehlende Testgrammatik-Generierungsschritte)
- Q9-OS mit weiteren Tools füllen, sobald klar ist, was noch gebraucht wird
- Q9-QCC: eigene Regressionssuite, unabhängig von Q9-Parsecs `runtests.sh`
- Vinculum-Repo anlegen, KiCad-Daten einpflegen
- Q9-Forge-weites GitHub Project (Board) für repo-übergreifende Themen
