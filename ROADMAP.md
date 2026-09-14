# Q9 Forge – Roadmap

Status: 2026-07-31 (day of the repo reorganization).

Legend:

| Symbol | Meaning |
|--------|-----------|
| ✅ | ready, maybe with some issues |
| 🔄 | working, now actively in development |
| ⏳ | in planning, tomorrow, next month or next century :-) |



## Q9-OS – Operating System

Lightweight multitasking, multiuser, realtime operating system. Can run
Microware OS-9/68k modules. Runs on minimal systems with no mass storage,
straight from ROM, up to larger graphics-capable systems with mass
storage. Modular kernel, IO system with the layers Manager – Driver –
Descriptors. TCP stack.

First target: Motorola 68K
Possible next targets: x86 32-bit, ARM64 (Raspberry), RISC-V

### Phase 1

- ✅ Kernel planning, infrastructure, module splitting — 07/26
- ✅ Kernel: first translation to C, runnable for the first time, system calls still missing — 09/26
- ⏳ Kernel complete in C — Q4 2026


### Phase 2

- ⏳ Build system modules — 2027/28
- ⏳ Build, research and implement all managers — 2028

### Phase 3

- ⏳ Further targets (x86 32-bit, ARM64, RISC-V, ...) — 2030 and later



## Q9-Flux – Emulator for Q9-OS (also runs other systems)

For the Motorola 68K target system, runs on Mac (Apple Silicon), Linux,
Windows and later also WASM. System for hardware devices, freely
configurable board, free memory mapping.

### Phase 1

- ✅ Emulator for Motorola 68K (Musashi base), runs on Mac/Linux/Windows — 06/26
- ✅ Original OS-9 boot image can be used, freely configurable — 06/26
- ✅ Ethernet support, 3 modes: NAT, VMnet, Bridge — 07/26
- ✅ Telnet support in OS-9 — 07/26
- 🔄 ? FTP support, issue (FTP still uses the old TCP socket path)
- 🔄 ? NFS support, issue
- 🔄 ? Samba support, issue
- ✅ Linux Bash support V1.10.12 — 07/26
- Hardware simulations:
  - ✅ CF card reader (CompactFlash) — 03/24
    - ✅ Basic functions
    - ✅ Partition support via MBR record — 07/26
    - 🔄 RBF/PCF support — Nov 2026
    - 🔄 Master/slave support — Oct 2026
  - ✅ UART simulator (68681 DUART) — Q1/24
  - ✅ RTC simulator (RTC72421) — Q1/24
  - ✅ Timer/clock simulator (IRQ3) — Q1/24
  - ✅ Virtual network terminal simulation (/x1–/x8) — 07/26
  - ✅ Ethernet simulation (QUICC) — 07/26
  - 🔄 MC6845 framebuffer simulation with remote connection (Q9 Frame) — 08/2026
  - ✅ Companion project Q9 Frame displays the framebuffer in a window (for Mac) — 08/26

### Phase 2

- Virtual simulations, speed-optimized:
  - ⏳ Mass storage, virtual, optimized
  - ⏳ UART simulator, virtual, optimized
  - ⏳ RTC simulator, virtual, optimized
  - ⏳ Timer/clock, virtual, optimized
- ⏳ Board configurator: assembling simulations for a board — Q1 2027
- ⏳ New target hardware MC68000 — 2027
- ⏳ Hardware simulation for various boards (CB030, MC68000, Vinculum, more) — 2028

### Phase 3

- ⏳ New target x86 32-bit — 2028
- ⏳ New target Raspberry — 2029



## Q9 Frame – Program for displaying the Q9-Flux framebuffer over the network

- ✅ Transmission: video modes, reg info (6845), CLUT data, framebuffer (dirty area) — 08/26
- ✅ Full support for the MC6845 register model, dynamic resolution, switchable on the run — 08/26
- ✅ Video modes and DAC models, from monochrome 1-bit up to 24-bit full-color mode, switchable on the run — 08/26
- ✅ UDP HELLO protocol for automatically finding the server — 08/26
- ✅ Screenshot — 08/26
- ⏳ Host service manager: shared, non-blocking service framework for the terminal and Q9-Frame TCP service,
      incl. update frequency, send queues, and client lifecycle — 2027
- ⏳ Multiple clients at once
- ⏳ Optional UDP transport
- ⏳ Mouse and keyboard back-channel (cursor and mouse pointer)
- ⏳ Connection manager
- ⏳ Nearest-neighbor scaling in the reference client
- ⏳ Later window and terminal integration
- ⏳ Client on ESP32 with small LCD display



## Q9-Parsec – Parser Generator

Parser generator. Produces C-code templates for recursive descent. Takes
an EBNF language definition as input. Produces templates for building
parsers and code generation. Q9-QCC also uses such a template.

- ✅ EBNF parser, recursive top-down parser (first version) — 2008
- ✅ Produces a parser table for building a stack machine — 2008
- ✅ Produces code for recursive descent from the parser table — 06/2026
- ⏳ Ability to interactively add further actions, and
  semi-automated support for parser and code generation — 2027



## Q9-QCC

C compiler for Q9/OS-9/68K. The first attempts ran into major problems
with memory consumption in the compilation system – 16 MB is barely
enough to compile with, which could be an issue on a real 68K system.
First bootstrap compiled successfully, but still needs to be optimized.

### Phase 1

- ✅ Generate lexer, syntax check from Q9-Parsec output — 08/2026
- ✅ Define and document IR code — 08/2026
- ✅ Frontend produces IR intermediate code — 08/2026
- ✅ Backend for 68k from intermediate code, OS-9-compatible — 08/2026
- 🔄 Backend for ARM64 (Apple Silicon) — 08/2026

### Phase 2

- ✅ C preprocessor, ISO C89/C99/C11-compatible — 09/26
- ✅ Assembler for 68k, OS-9 format, ROF format output — 09/26
- ✅ Linker for ROF format, OS-9/Q9 module output — 09/26
- ⏳ Further backends, x86 32-bit, ARM64, RISC-V

### Phase 3

- ✅ QCC invocation manager, invokes QCC modules to compile — 09/26
- ⏳ Optimizations in the IR intermediate code — 2027
- ✅ Optimizations in the assembler code — 09/26

### Phase 4

- ⏳ Further frontends: Rust, Go, Modula-2, Oberon — 2029
- ✅ Interpreter for intermediate code — 09/26
- ⏳ Further backends, Raspberry



## Vinculum

Custom hardware: CPU Motorola 68360, Ethernet, 32 MB RAM, dual CF drive, USB stick.

### Phase 1

- 🔄 Schematic — 2027
- ⏳ Order PCB and components — 2028
- ⏳ First prototype with running Q9 — 2028
