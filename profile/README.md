<p align="center">
  <img width="300" height="300" alt="Q9-Forge" src="https://github.com/user-attachments/assets/0f469c58-eebb-429b-91bd-9fc9ef6df503" />
</p>

# Q9-Forge

German version: [README_de.md](README_de.md)

## What is Q9?

Q9 is a new operating system with historical roots. Back in the 1980s, I
was a big fan of Microware OS-9/68K and later also OS-9000. As a student
I worked a lot with these systems and was convinced they would catch on
sooner or later. In hindsight, I was a bit too optimistic about that —
most people today have probably never heard of OS-9.

In an age of Linux and many other free operating systems, I'd still like
to bring the idea back to life. Q9 is meant to become a compatible,
portable operating-system kernel that stays as close to OS-9 as possible,
letting it run historical OS-9 programs while also making it possible to
develop new ones. Later, Q9 is meant to be extended with modern features.

The starting point — as with Microware — is the historical Motorola
68000 processor family. The goal is a compatible, modular and portable
kernel with its own I/O system and its own I/O managers. There's still
quite a bit of work ahead until then.

## What is Q9-Forge?

Q9-Forge brings together the projects needed to develop, run and extend
Q9:

- [Q9-OS](https://github.com/Q9-Forge/Q9-OS) — operating-system kernel
  and OS foundations, plus the I/O system.
- [Q9-Flux](https://github.com/Q9-Forge/Q9-Flux) — emulator and hardware
  visualization for 68k, x86 and device components.
- [Q9-QCC](https://github.com/Q9-Forge/Q9-QCC) — compiler toolchain with
  parser generator, C frontend, IR intermediate code, backends and
  interpreter.
- [Q9-Tools](https://github.com/Q9-Forge/Q9-Tools) — system, network and
  language utilities for Q9 and OS-9.

The projects are split into independent repositories. Architecture-
dependent code is kept separate within each project; shared sources live
in their own areas.

## Project status

Version numbers indicate the internal development state and are not
stable releases.

| Project | Status | Description |
| --- | --- | --- |
| [Q9-OS](https://github.com/Q9-Forge/Q9-OS) |  | Foundations and kernel development |
| &nbsp;&nbsp;- [Q9-OS Kernel 68k](https://github.com/Q9-Forge/Q9-OS/tree/main/Q9-KERNEL/68k) | 🟡 0.1 | Boots and runs |
| &nbsp;&nbsp;- [Q9-OS Kernel x86](https://github.com/Q9-Forge/Q9-OS/tree/main/Q9-KERNEL/x86) | 🔴 | Not started |
| &nbsp;&nbsp;- [Q9-OS IOMAN 68k](https://github.com/Q9-Forge/Q9-OS/tree/main/Q9-IOMAN/68k) | 🔴 | Not started |
| &nbsp;&nbsp;- [Q9-OS IOMAN x86](https://github.com/Q9-Forge/Q9-OS/tree/main/Q9-IOMAN/x86) | 🔴 | Not started |
| [Q9-Flux](https://github.com/Q9-Forge/Q9-Flux) |  | Active emulator development |
| &nbsp;&nbsp;- [Q9-Flux 68k](https://github.com/Q9-Forge/Q9-Flux/tree/main/Q9-Flux-68k) | 🟢 0.15 | Working development version |
| &nbsp;&nbsp;- [Q9-Flux x86](https://github.com/Q9-Forge/Q9-Flux/tree/main/Q9-Flux-x86) | 🔴 0.1 | Early development and analysis |
| [Q9-QCC](https://github.com/Q9-Forge/Q9-QCC) |  | Active compiler development |
| &nbsp;&nbsp;- [Q9-QCC C frontend](https://github.com/Q9-Forge/Q9-QCC/tree/main/Q9-FRONTEND-C) | 🟢 0.15 | In development |
| &nbsp;&nbsp;- [Q9-QCC 68k backend](https://github.com/Q9-Forge/Q9-QCC/tree/main/Q9-BACKEND-68K) | 🟢 0.15 | Working development version |
| &nbsp;&nbsp;- [Q9-QCC x86 backend](https://github.com/Q9-Forge/Q9-QCC/tree/main/Q9-BACKEND-x86) | 🔴 0.1 | Early development |
| &nbsp;&nbsp;- [Q9-QCC ARM64 backend](https://github.com/Q9-Forge/Q9-QCC/tree/main/Q9-BACKEND-ARM64) | 🔴 0.1 | Early development |
| &nbsp;&nbsp;- [Q9-QCC Run](https://github.com/Q9-Forge/Q9-QCC/tree/main/Q9-RUN) | 🟢 0.1 | IR interpreter in development |
| [Q9-Tools](https://github.com/Q9-Forge/Q9-Tools) | 🟢 0.1 | System, network and language utilities |

These indicators are adjusted as development progresses and are mainly
meant to give a quick overview of each project's maturity and focus.

Q9-Forge is under active development. The current focus is on the Q9
kernel, the 68k emulator, and rounding out the Q9-QCC toolchain.

More information:

- [Project conventions](../CONVENTIONS.md)
- [Roadmap](../ROADMAP.md)
- [Roadmap in German](../ROADMAP_de.md)

## AI-assisted development

A substantial part of the code in these repositories was written with
AI assistance (Claude Code). This is visible per commit via the
`Co-Authored-By: Claude Sonnet 5` trailer in the commit history.

## Note on AI/LLM files

We've tried to remove `AGENTS.md` and `PROJECT.md` from every public
repository (see each repo's `.gitignore`). Even so: `docs/` directories,
and occasionally other locations, may still contain further files with
instructions or data directed at AI assistants — for example working
journals or planning notes from collaborating with an LLM.

Before handing such a file to an AI to act on, please review its
content first and adjust or remove anything you don't want followed.

## Contributing

Supporters and contributors are welcome. Questions, bug reports, ideas
and proposed improvements can be filed as an
[Issue](https://github.com/Q9-Forge/Q9-OS/issues). If you'd like to
contribute code or documentation, feel free to open a Pull Request.
