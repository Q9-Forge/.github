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

---

# Detaillierte Phasenpläne (Andreas, Stand 2026-07-31)

Die Reihenfolge orientiert sich an Abhängigkeiten und stabilen
Zwischenständen, bewusst ohne feste Zeitangaben.

Legende:
```
v    ready, maybe with some issues
-    working, now aktiv in development
x    in planing, tomorrow, next month or next century :-)
```

## Q9 OS

- Phase 1
    - Kernel reengeneers, Diasassembly                   - Dez 2026
    - Kernel planung, welche Teilmodule brauchen wir     x 2027
    - Kernel erste übersetzung eines vorhandenen         x 2027
      Kernels mit originalen Code
    - Kernel neu schreiben in C-Code                     x 2027
    - Systemmodule bauen                                 x 2027/28
    - Manager bauen, untersuchen und planen              x 2028

## Q9 Flex Emulator

- Phase 1
    - Emulator für Motorola 68K (Mushaki Basis)           v
      running on Mac, Linux, Windows
    - add hard Simulation for real or virtuel Hardware    v
    - add Port for OS-9/68k as 68030 CPU                  v
    - add virtual Network Terminal Simulatoren            v
    - add network Support as Ethernet Simulation          v
    - add telnet support in OS-9                          v
    - add Framebuffer Support  with remote Support        - Aug 2026

- Phase 2
    - add new virtual fast Hardware Target for Q9 Flex    x 2027
    - add new Target Hardware mc68000                     x 2027
    - add intern emulator 6809                            x 2027
    - add intern CP/M-68k Emulation                       x 2027

- Phase 3
    - add new Target x86 32Bit                            x 2028
    - add new Target Raspberry                            x 2029

## Q9 QCC C-Compiler

- Phase 1
    - Ebnf Parser, create recursive top down parser       v   (first Version)
    - Code generation to Intermediat Code                 v
    - Intermidied Code defined as Stack machine           v
    - Backend for 68k from Intermidied Code               v

- Phase 2
    - C Preprozesoor                                      x 2027
    - 68k Assembler for Q9                                x 2027
    - Linker for Q9 ROF Format                            x 2028

- Phase 3
    - other Frontends, Rust                               x 2028
    - Interpreter for Intermdiet Code                     x 2028

## Vinculum

Hardware mit Motorola 68360, Network, 32 MByte RAM, Dual-CF-Drive, USB-Stick.

- Phase 1
    - Schematic                                          - 2027
    - Order PCB and Devices                              x 2028
    - First Prototype with running Q9                    x 2028

## Q9 Frame (Framebuffer-über-Netzwerk, siehe auch Q9-Flex Phase-1-Eintrag oben)

### Phase 1 – Projektbasis ordnen

- Q9 Forge als übergeordnete Struktur etablieren
- Q9 Flex und Q9 Frame sauber einordnen
- bestehende Projekte und Buildpfade inventarisieren
- gemeinsame Namenskonventionen und Dokumentationsstruktur festlegen
- öffentliche Repository-Struktur vorbereiten

### Phase 2 – Q9 Flex stabilisieren

- Emulator- und Hardware-Simulationsbereiche klar trennen
- Speicher-, I/O- und Geräteabbild dokumentieren
- bestehende Tests und Buildvarianten vereinheitlichen
- reproduzierbare Builds für die unterstützten Plattformen sicherstellen

### Phase 3 – Q9 Frame v1

- separates Video-RAM bei `0xFD000000` anbinden
- MC6845-Registermodell ab `0xFFFFA000` integrieren
- monochromen 1-Bit-Framebuffer implementieren
- Bit- und Byte-Layout festlegen und testen
- Dirty-Tracking bei VRAM-Schreibzugriffen umsetzen

### Phase 4 – Host-Service-Manager

- gemeinsamen nicht-blockierenden Service-Rahmen bereitstellen
- bestehenden Terminal-Service einbinden
- Q9-Frame-TCP-Service ergänzen
- Updatefrequenz, Sendewarteschlangen und Client-Lebenszyklus implementieren

### Phase 5 – Q9 Frame Netzwerk v1

- `HELLO` und `VIDEO_INFO`
- `FRAME_FULL` und `FRAME_UPDATE`
- Vollbildanforderung und Resynchronisierung
- UDP-Discovery im lokalen Netz
- Protokoll- und Verbindungstests

### Phase 6 – Test-Clients

- kleiner Desktop-Referenzclient
- Nearest-Neighbor-Skalierung
- Fenster-, Vollbild- und Minimierungsverhalten
- Test mit verschiedenen Updatefrequenzen und langsamen Clients
- später ESP32-Client mit kleinem Display

### Phase 7 – Öffentliche Veröffentlichung

- README und Quickstart vervollständigen
- Lizenzen und Drittanbieter-Komponenten dokumentieren
- Debugdaten, lokale Pfade und private Konfigurationen entfernen
- CI, Tests und reproduzierbare Builds einrichten
- Versions- und Release-Konvention festlegen
- erster öffentlicher Entwicklungsstand von Q9 Forge

### Phase 8 – Erweiterungen

- Farbmodi und virtuelle DAC-Modelle
- mehrere gleichzeitige Video-Clients
- optionaler UDP-Transport für Video-Updates
- Tastatur- und Mauskanal
- konfigurierbare Pixel- und Speicherformate
- weitergehende MC6845-Timing- und Cursorfunktionen
- spätere Fenster- und Terminalintegration
