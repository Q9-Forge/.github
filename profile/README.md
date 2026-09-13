<p align="center">
  <img width="300" height="300" alt="Q9-Forge" src="https://github.com/user-attachments/assets/0f469c58-eebb-429b-91bd-9fc9ef6df503" />
</p>

# Q9-Forge

German version: [README_de.md](README_de.md)

## What is Q9?

Q9 is a new operating-system project with historical roots. It is inspired
by Microware OS-9/68K and OS-9000, with the aim of creating a compatible,
portable and modular system that can run historical OS-9 programs while also
providing a foundation for new software.

The first target is the Motorola 68000 family. The long-term goal is an open
kernel with its own I/O system, I/O managers and support for additional
architectures.

## What is Q9-Forge?

Q9-Forge brings together the projects required to develop and run Q9:

- [Q9-OS](https://github.com/Q9-Forge/Q9-OS) — operating-system kernel and system components.
- [Q9-Flux](https://github.com/Q9-Forge/Q9-Flux) — emulator and hardware models.
- [Q9-QCC](https://github.com/Q9-Forge/Q9-QCC) — compiler toolchain, IR and backends.
- [Q9-Tools](https://github.com/Q9-Forge/Q9-Tools) — system, network and language utilities.
- [Q9-Port](https://github.com/Q9-Forge/Q9-Port) — reserved for future porting work.

The projects are maintained in separate repositories so that each toolchain
or system component can evolve independently.

## Project status

Version numbers indicate the internal development state and are not stable
releases.

| Project | Status | Description |
| --- | --- | --- |
| [Q9-OS](https://github.com/Q9-Forge/Q9-OS) |  | Kernel and system development |
| &nbsp;&nbsp;- [Q9-OS Kernel 68k](https://github.com/Q9-Forge/Q9-OS/tree/main/Q9-KERNEL/68k) | 🔴 0.1 | Kernel development started |
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
| [Q9-Port](https://github.com/Q9-Forge/Q9-Port) |  | Reserved for future porting work |

## Contributing

Supporters and contributors are welcome. Questions, bug reports and proposed
improvements can be opened as [Issues](https://github.com/Q9-Forge) or Pull
Requests in the relevant repository.

The project is under active development; status information and development
versions are indicative and are not stable releases.
