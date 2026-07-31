# Q9 Forge – Roadmap

Stand: 2026-07-31 (Tag der Repo-Reorganisation).

# Detaillierte Phasenpläne (Andreas, Stand 2026-07-31)

Die Reihenfolge orientiert sich an Abhängigkeiten und stabilen
Zwischenständen, bewusst nur mit ungefähren Zeitangaben.

Legende:

| Symbol | Bedeutung |
|--------|-----------|
| ✅ | ready, maybe with some issues |
| 🔄 | working, now aktiv in development |
| ⏳ | in planing, tomorrow, next month or next century :-) |

## Q9-OS – Operating System

Leichtes multitasking-, multiuser-, realtime-Operating-System. Es kann
Microware-OS-9/68k-Module ausführen. Läuft auf Minimalsystemen ohne
Massenspeicher, nur aus dem ROM, bis hin zu grafikfähigen größeren Systemen
mit Massenspeicher. Modularer Kernel, IO-System mit den Schichten Manager –
Driver – Descriptoren. TCP-Stack.

Erstes Target: Motorola 68K
Mögliche nächste Targets: Raspberry, x86 32-Bit, ESP32

### Phase 1

- 🔄 Kernel Reverse Engineering, Disassembly — Dez 2026
- ⏳ Kernel-Planung, welche Teilmodule wir brauchen — 2027
- ⏳ Kernel: erste Übersetzung eines vorhandenen Kernels mit Originalcode — 2027
- ⏳ Kernel neu schreiben in C — 2027

### Phase 2

- ⏳ Systemmodule bauen — 2027/28
- ⏳ Manager bauen, untersuchen und planen — 2028
- ⏳ Kernelsupport für CP/M-68k — 2028
- ⏳ Kernelsupport für OS-9/6809 — 2029
- ⏳ Kernelsupport für CP/M-80 — 2030 :-)

### Phase 3

- ⏳ Weitere Targets (Raspberry, x86, ...) — 2030 und später

## Q9-Flux – Emulator für Q9-OS (läuft auch mit anderen Systemen)

Für das Motorola-68K-Zielsystem, läuft auf Mac (Apple Silicon), Linux,
Windows und später auch WASM. System für Hardware-Devices, Board frei
konfigurierbar, freies Memory-Mapping.

### Phase 1

- ✅ Emulator für Motorola 68K (Musashi-Basis), läuft auf Mac/Linux/Windows
- ✅ Original-Bootimage kann verwendet werden, frei einstellbar
- ✅ Ethernet-Support, 3 Modi: NAT, VMnet, Bridge
- ✅ Telnet-Support in OS-9
- 🔄 FTP-Support, Issue (FTP nutzt noch den alten TCP-Socket-Pfad)
- 🔄 NFS-Support, Issue
- 🔄 Samba-Support, Issue
- ✅ Linux-Bash-Support V1.10.12
- Hardware-Simulationen:
  - ✅ CF-Kartenleser (CompactFlash)
    - ✅ Grundfunktionen
    - ✅ Partition-Support über MBR-Record
    - 🔄 RBF-/PCF-Support — Nov 2026
    - 🔄 Master-/Slave-Support — Okt 2026
  - ✅ UART-Simulator (68681 DUART)
  - ✅ RTC-Simulator (RTC72421)
  - ✅ Timer-/Clock-Simulator (IRQ3)
  - ✅ Virtuelle Netzwerk-Terminal-Simulation (/x1–/x8)
  - ✅ Ethernet-Simulation (QUICC)
  - 🔄 MC6845-Framebuffer-Simulation mit Remote-Verbindung (Q9 Frame) — Aug 2026
    Gegenstück-Projekt Q9 Frame stellt den Framebuffer in einem Fenster dar (für Mac)

### Phase 2

- Virtuelle Simulationen, geschwindigkeitsoptimiert:
  - ⏳ Massenspeicher, virtuell, optimiert
  - ⏳ UART-Simulator, virtuell, optimiert
  - ⏳ RTC-Simulator, virtuell, optimiert
  - ⏳ Timer/Clock, virtuell, optimiert
- ⏳ Board-Konfigurator: Zusammenstellung der Simulationen für ein Board — Q1 2027
- ⏳ Neues Target-Hardware MC68000 — 2027
- ⏳ Interner 6809-Emulator — 2027
- ⏳ Interne CP/M-68k-Emulation — 2027
- ⏳ Hardware-Simulation für verschiedene Boards (CB030, MC68000, Vinculum, weitere) — 2028

### Phase 3

- ⏳ Neues Target x86 32-Bit — 2028
- ⏳ Neues Target Raspberry — 2029

## Q9 Frame – Programm zum Darstellen des Q9-Flux-Framebuffers über Netzwerk

- ✅ Übertragung: Videomodi, Reg-Info (6845), CLUT-Daten, Framebuffer (Dirty Area)
- ✅ Volle Unterstützung des MC6845-Registermodells, dynamische Auflösung, on the run umstellbar
- ✅ Videomodi und DAC-Modelle, von monochromem 1-Bit bis 24-Bit-Vollfarbmodus, on the run umschaltbar
- ✅ UDP-HELLO-Protokoll zum automatischen Finden des Servers
- ✅ Screenshot
- ⏳ Host-Service-Manager: gemeinsamer, nicht-blockierender Service-Rahmen für Terminal- und Q9-Frame-TCP-Service, inkl. Update-Frequenz, Sendewarteschlangen und Client-Lebenszyklus
- ⏳ Mehrere Clients gleichzeitig
- ⏳ Optionaler UDP-Transport
- ⏳ Maus- und Tastatur-Rückkanal (Cursor und Mauszeiger)
- ⏳ Verbindungsmanager
- ⏳ Nearest-Neighbor-Skalierung im Referenzclient
- ⏳ spätere Fenster- und Terminalintegration
- ⏳ Client auf ESP32 mit kleinem LCD-Display

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
- Q9-Flux: Emulator- und Hardware-Simulationsbereiche im Code klar trennen,
  dokumentieren, Tests/Buildvarianten vereinheitlichen, reproduzierbare
  Builds für alle Plattformen sicherstellen
- Q9 Frame: README/Quickstart, Lizenzen und Drittanbieter-Komponenten
  dokumentieren, Debugdaten/lokale Pfade entfernen, CI einrichten,
  Versions-/Release-Konvention festlegen — Vorbereitung für einen ersten
  öffentlichen Entwicklungsstand von Q9 Forge
