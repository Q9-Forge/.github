# Q9 Forge – Roadmap

Stand: 2026-07-31 (Tag der Repo-Reorganisation).

# Detaillierte Phasenpläne (Andreas, Stand 2026-07-31)

Die Reihenfolge orientiert sich an Abhängigkeiten und stabilen
Zwischenständen, bewusst ohne feste Zeitangaben.

| Symbol | Bedeutung |
|--------|-----------|
| ✅ | ready, maybe with some issues |
| 🔄 | working, now aktiv in development |
| ⏳ | in planing, tomorrow, next month or next century :-) |

## Q9-OS

### Phase 1

- 🔄 Kernel reengeneers, Disassembly — Dez 2026
- ⏳ Kernel-Planung, welche Teilmodule wir brauchen — 2027
- ⏳ Kernel: erste Übersetzung eines vorhandenen Kernels mit Originalcode — 2027
- ⏳ Kernel neu schreiben in C — 2027
- ⏳ Systemmodule bauen — 2027/28
- ⏳ Manager bauen, untersuchen und planen — 2028

## Q9-Flux

### Phase 1

- ✅ Emulator für Motorola 68K (Musashi-Basis), läuft auf Mac/Linux/Windows
- ✅ Port für OS-9/68k als 68030-CPU
- ✅ Telnet-Support in OS-9
- Hardware-Simulationen:
  - ✅ CF-Kartenleser (CompactFlash, RBF/PCF)
  - ✅ UART-Simulator (68681 DUART)
  - ✅ RTC-Simulator (RTC72421)
  - ✅ Timer-/Clock-Simulator (IRQ3)
  - ✅ Virtuelle Netzwerk-Terminal-Simulation (/x1–/x8)
  - ✅ Ethernet-Simulation (QUICC)
  - 🔄 Framebuffer mit Remote-Support (Q9 Frame) — Aug 2026, Details siehe unten

#### Q9 Frame (Framebuffer-über-Netzwerk)

##### Phase 1 – Projektbasis ordnen

- Q9 Forge als übergeordnete Struktur etablieren
- Q9-Flux und Q9 Frame sauber einordnen
- bestehende Projekte und Buildpfade inventarisieren
- gemeinsame Namenskonventionen und Dokumentationsstruktur festlegen
- öffentliche Repository-Struktur vorbereiten

##### Phase 2 – Q9-Flux stabilisieren

- Emulator- und Hardware-Simulationsbereiche klar trennen
- Speicher-, I/O- und Geräteabbild dokumentieren
- bestehende Tests und Buildvarianten vereinheitlichen
- reproduzierbare Builds für die unterstützten Plattformen sicherstellen

##### Phase 3 – Q9 Frame v1

- separates Video-RAM bei `0xFD000000` anbinden
- MC6845-Registermodell ab `0xFFFFA000` integrieren
- monochromen 1-Bit-Framebuffer implementieren
- Bit- und Byte-Layout festlegen und testen
- Dirty-Tracking bei VRAM-Schreibzugriffen umsetzen

##### Phase 4 – Host-Service-Manager

- gemeinsamen nicht-blockierenden Service-Rahmen bereitstellen
- bestehenden Terminal-Service einbinden
- Q9-Frame-TCP-Service ergänzen
- Updatefrequenz, Sendewarteschlangen und Client-Lebenszyklus implementieren

##### Phase 5 – Q9 Frame Netzwerk v1

- `HELLO` und `VIDEO_INFO`
- `FRAME_FULL` und `FRAME_UPDATE`
- Vollbildanforderung und Resynchronisierung
- UDP-Discovery im lokalen Netz
- Protokoll- und Verbindungstests

##### Phase 6 – Test-Clients

- kleiner Desktop-Referenzclient
- Nearest-Neighbor-Skalierung
- Fenster-, Vollbild- und Minimierungsverhalten
- Test mit verschiedenen Updatefrequenzen und langsamen Clients
- später ESP32-Client mit kleinem Display

##### Phase 7 – Öffentliche Veröffentlichung

- README und Quickstart vervollständigen
- Lizenzen und Drittanbieter-Komponenten dokumentieren
- Debugdaten, lokale Pfade und private Konfigurationen entfernen
- CI, Tests und reproduzierbare Builds einrichten
- Versions- und Release-Konvention festlegen
- erster öffentlicher Entwicklungsstand von Q9 Forge

##### Phase 8 – Erweiterungen

- Farbmodi und virtuelle DAC-Modelle
- mehrere gleichzeitige Video-Clients
- optionaler UDP-Transport für Video-Updates
- Tastatur- und Mauskanal
- konfigurierbare Pixel- und Speicherformate
- weitergehende MC6845-Timing- und Cursorfunktionen
- spätere Fenster- und Terminalintegration

### Phase 2

- ⏳ Neues, schnelles virtuelles Hardware-Target für Q9-Flux — 2027
- ⏳ Neues Target-Hardware MC68000 — 2027
- ⏳ Interner 6809-Emulator — 2027
- ⏳ Interne CP/M-68k-Emulation — 2027

### Phase 3

- ⏳ Neues Target x86 32-Bit — 2028
- ⏳ Neues Target Raspberry — 2029

## Q9-QCC

### Phase 1

- ✅ EBNF-Parser, rekursiver Top-Down-Parser (erste Version)
- ✅ Codegenerierung zu Intermediate Code
- ✅ Intermediate Code als Stack-Maschine definiert
- ✅ Backend für 68k aus Intermediate Code

### Phase 2

- ⏳ C-Präprozessor — 2027
- ⏳ 68k-Assembler für Q9 — 2027
- ⏳ Linker für Q9-ROF-Format — 2028

### Phase 3

- ⏳ Weitere Frontends, Rust — 2028
- ⏳ Interpreter für Intermediate Code — 2028

## Vinculum

Hardware: Motorola 68360, Netzwerk, 32 MByte RAM, Dual-CF-Drive, USB-Stick.

### Phase 1

- 🔄 Schematic — 2027
- ⏳ PCB und Bauteile bestellen — 2028
- ⏳ Erster Prototyp mit laufendem Q9 — 2028

---

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
