

<p align="center">
  <img width="300" height="300" alt="Q9-Forge" src="https://github.com/user-attachments/assets/0f469c58-eebb-429b-91bd-9fc9ef6df503" />
</p>


# Q9-Forge

Was ist Q9 ? 
Q9 ist ein neues Betriessystem mit historischen Wurzeln. In den 80er war ich großer Fan vom Microware OS-9/68k Betriebssystem 
und später auch von OS-9000. Als Student habe ich viel mit dem System gearbeitet und war überzeugt früher oder später wird es sich 
durchsetzen :-) Ich war natürlich etwas zu optimistisch mit meine Annahme, wie wir natürlich wissen ist das nie passiert, die wenigsten 
werden davon je von OS-9 gehört haben.
Heute, in der Zeit von Linux und vielen anderen freien Betriessystemen, will ich es aber noch einmal aufleben lassen. Ich will versuchen 
einen kompatibles und portables Betriebssystem Kernel zu bauen das OS-9 sehr nahe steht, und es möglich macht, historische OS-9 Programme 
auszuführen und auch neu zu erstellen. Zukünftig soll das System dann auch erweitert werden um es wieder an die modernen Zeiten 
anzupassen.
Ich starte mit der historischen 68000 Motorola CPU Famile (wie bei Microware auch). Mein Ziel ist ein kompatiblerm modularer und partabler 
Kernel. Zusätzlich zum Kernel gehört noch das I/O System und diverse I/O Manager. Das ist noch ein wenig Arbeit ...

- [Q9-OS](https://github.com/Q9-Forge/Q9-OS) 




Was ist Q9-Forge ?   
Q9-Forge ist eine Site rund um das Betriebssystem Q9. 

1. Als erste wäre da ein Emulator Flux. Dieser ist sehr hilreich bei der Entwicklung des Kernels und des Compilers. Sicher auch bei der 
späteren Entwicklung von Anwendungen. Er ist von Musachi Emulator abgeleitet und hat ein modulares System um neue Hardware Simulationen 
hinzuzufügen.
- [Q9-Flux](https://github.com/Q9-Forge/Q9-Flux) — Emulator- und
  Hardware-Visualisierungsprojekt mit Bereichen für 68k, x86 und Geräte.

  
2. Weiter haben wir einen C-Compiler QCC. Damit ist es Möglich OS-9/68k kompatible Module zu erzeugen. Weiterhin ist er Bootstrap fähig, d.h.
er kann sich selber übersetzen. Somit lässt er sich als Coss- oder Nativcompiler übersetzen. Er arbeitet mit einem IE Zwischencode so das
er getrennte Front- Back-ends hat. So sind wir flexibel um weitere Architekturen hinzuzufügen.
- [Q9-QCC](https://github.com/Q9-Forge/Q9-QCC) — Compiler-Werkzeugkette mit
  Treiber, C-Frontend, Q9-Zwischencode, Interpreter und Backends.


3. Als drittes haben wir noch die Tools. Wie bei OS-9 haben wir auch in unserer Site eine reihe von Tools. Die sind oft UNIX/Linus ähnlich
und ermöglichen es das System zu kontrollieren und zu steuern.  


4. Dann haben wir noch Q9-Port. Dies ist eine Sammlung von Treibern und Descriptoren für dirverse Geräte und Schnittstelle. Es gibt schon diverse 
UARTS (serielle Schnittstellen), Framebuffer, Compact Flash und anderes.
- [Q9-Port](https://github.com/Q9-Forge/Q9-Port) — vorgesehenes Repository
  für spätere Portierungsarbeiten; derzeit noch nicht aktiv.



Aug Basis des 
 r-   ist eine modulare Entwicklungsumgebung für die Q9-Plattform. Das
Projekt verbindet einen eigenen Kernel, Emulatoren und eine portable
Compiler-Werkzeugkette für historische und zukünftige Zielarchitekturen.

## Repositories



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
