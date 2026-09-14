

<p align="center">
  <img width="300" height="300" alt="Q9-Forge" src="https://github.com/user-attachments/assets/0f469c58-eebb-429b-91bd-9fc9ef6df503" />
</p>


# Q9-Forge

## Was ist Q9?

Q9 ist ein neues Betriebssystem mit historischen Wurzeln. In den 1980er-
Jahren war ich ein großer Fan von Microware OS-9/68K und später auch von
OS-9000. Als Student habe ich viel mit diesen Systemen gearbeitet und war
überzeugt, dass sie sich früher oder später durchsetzen würden. Rückblickend
war ich mit dieser Einschätzung etwas zu optimistisch — die meisten Menschen
haben heute vermutlich noch nie von OS-9 gehört.

In einer Zeit von Linux und vielen anderen freien Betriebssystemen möchte ich
die Idee trotzdem noch einmal aufleben lassen. Q9 soll ein kompatibler und
portabler Betriebssystemkern werden, der OS-9 möglichst nahe steht und es
ermöglicht, historische OS-9-Programme auszuführen sowie neue Programme zu
entwickeln. Später soll Q9 um moderne Funktionen erweitert werden.

Der Anfang liegt — wie bei Microware — bei der historischen Motorola-
68000-Prozessorfamilie. Ziel ist ein kompatibler, modularer und portabler
Kernel mit eigenem I/O-System und eigenen I/O-Managern. Bis dahin ist noch
einiges an Arbeit zu leisten.

## Was ist Q9-Forge?

Q9-Forge bündelt die Projekte, die für Entwicklung, Betrieb und Erweiterung
von Q9 benötigt werden:

- [Q9-OS](https://github.com/Q9-Forge/Q9-OS) — Betriebssystemkern und
  OS-Grundlagen sowie das I/O-System.
- [Q9-Flux](https://github.com/Q9-Forge/Q9-Flux) — Emulator und
  Hardware-Visualisierung für 68k, x86 und Gerätekomponenten.
- [Q9-QCC](https://github.com/Q9-Forge/Q9-QCC) — Compiler-Werkzeugkette mit
  Parsergenerator, C-Frontend, IR-Zwischencode, Backends und Interpreter.
- [Q9-Tools](https://github.com/Q9-Forge/Q9-Tools) — System-, Netzwerk- und
  Sprachwerkzeuge für Q9 und OS-9.

Die Projekte sind in eigenständige Repositories aufgeteilt. 
Architekturabhängiger Code wird innerhalb der jeweiligen Projekte getrennt
gehalten; gemeinsame Quellen liegen in eigenen Bereichen.

## Projektübersicht

Die Versionsnummern bezeichnen den internen Entwicklungsstand und sind noch
keine stabilen Releases.

| Projekt | Status | Beschreibung |
| --- | --- | --- |
| [Q9-OS](https://github.com/Q9-Forge/Q9-OS) |  | Grundaufbau und Kernelentwicklung |
| &nbsp;&nbsp;- [Q9-OS Kernel 68k](https://github.com/Q9-Forge/Q9-OS/tree/main/Q9-KERNEL/68k) | 🟡 0.1 | Bootet und läuft |
| &nbsp;&nbsp;- [Q9-OS Kernel x86](https://github.com/Q9-Forge/Q9-OS/tree/main/Q9-KERNEL/x86) | 🔴 | Noch nicht begonnen |
| &nbsp;&nbsp;- [Q9-OS IOMAN 68k](https://github.com/Q9-Forge/Q9-OS/tree/main/Q9-IOMAN/68k) | 🔴 | Noch nicht begonnen |
| &nbsp;&nbsp;- [Q9-OS IOMAN x86](https://github.com/Q9-Forge/Q9-OS/tree/main/Q9-IOMAN/x86) | 🔴 | Noch nicht begonnen |
| [Q9-Flux](https://github.com/Q9-Forge/Q9-Flux) |  | Aktive Emulatorentwicklung |
| &nbsp;&nbsp;- [Q9-Flux 68k](https://github.com/Q9-Forge/Q9-Flux/tree/main/Q9-Flux-68k) | 🟢 0.15 | Funktionsfähiger Entwicklungsstand |
| &nbsp;&nbsp;- [Q9-Flux x86](https://github.com/Q9-Forge/Q9-Flux/tree/main/Q9-Flux-x86) | 🔴 0.1 | Frühe Entwicklung und Analyse |
| [Q9-QCC](https://github.com/Q9-Forge/Q9-QCC) |  | Aktive Compilerentwicklung |
| &nbsp;&nbsp;- [Q9-QCC Frontend-C](https://github.com/Q9-Forge/Q9-QCC/tree/main/Q9-FRONTEND-C) | 🟢 0.15 | In Entwicklung |
| &nbsp;&nbsp;- [Q9-QCC Backend-68k](https://github.com/Q9-Forge/Q9-QCC/tree/main/Q9-BACKEND-68K) | 🟢 0.15 | Funktionsfähiger Entwicklungsstand |
| &nbsp;&nbsp;- [Q9-QCC Backend-x86](https://github.com/Q9-Forge/Q9-QCC/tree/main/Q9-BACKEND-x86) | 🔴 0.1 | Frühe Entwicklung |
| &nbsp;&nbsp;- [Q9-QCC Backend-ARM64](https://github.com/Q9-Forge/Q9-QCC/tree/main/Q9-BACKEND-ARM64) | 🔴 0.1 | Frühe Entwicklung |
| &nbsp;&nbsp;- [Q9-QCC Run](https://github.com/Q9-Forge/Q9-QCC/tree/main/Q9-RUN) | 🟢 0.1 | IR-Interpreter in Entwicklung |
| [Q9-Tools](https://github.com/Q9-Forge/Q9-Tools) | 🟢 0.1  | System-, Netzwerk- und Sprachwerkzeuge |

Die Angaben werden im Laufe der Entwicklung angepasst und sollen vor allem
einen schnellen Überblick über Reifegrad und Schwerpunkt der Projekte geben.

Q9-Forge befindet sich in aktiver Entwicklung. Der Schwerpunkt liegt derzeit
auf dem Q9-Kernel, dem 68k-Emulator und der Vervollständigung der
Q9-QCC-Werkzeugkette.

Weitere Informationen:

- [Projektkonventionen](../CONVENTIONS_de.md)
- [Roadmap](../ROADMAP.md)
- [Roadmap auf Deutsch](../ROADMAP_de.md)

## Hinweis zu KI-/LLM-Anweisungsdateien

Diese Repositories enthalten an mehreren Stellen — allen voran `AGENTS.md`
im Root mancher Repos, aber auch im `docs/`-Verzeichnis sowie vereinzelt
anderswo — Dateien, die gezielt an KI-Coding-Assistenten gerichtet sind:
Arbeitskontext, Konventionen, Anweisungen für die Zusammenarbeit mit
einem LLM. Viele KI-Coding-Werkzeuge (z. B. Claude Code, OpenAI Codex
CLI und ähnliche Agenten) **lesen eine Datei wie `AGENTS.md` automatisch
ein, sobald sie in einem Verzeichnis zu arbeiten beginnen** — bevor ein
Mensch sie für diesen konkreten Einsatzzweck geprüft hat.

Das sind unsere eigenen Arbeitsnotizen, keine neutrale Dokumentation,
und nicht mit Blick auf den Assistenten einer fremden Person geschrieben.
Wer ein KI-Werkzeug auf eines dieser Repositories ansetzt: Bitte den
Inhalt von `AGENTS.md` und ähnlichen Dateien vorher prüfen und bei
Bedarf anpassen oder entfernen, bevor ein Assistent sie automatisch
übernimmt — wie bei jedem Repository, das man einem Agenten öffnet,
sollten Inhalte aus fremden Quellen als Daten behandelt werden, nicht
blind als Instruktion.

## Mitmachen

Supporter und Contributors sind herzlich willkommen. Fragen, Fehlermeldungen,
Ideen und Verbesserungsvorschläge können als [Issue](https://github.com/Q9-Forge/Q9-OS/issues)
eingereicht werden. Wer Code oder Dokumentation beitragen möchte, kann gerne
einen Pull Request erstellen.
