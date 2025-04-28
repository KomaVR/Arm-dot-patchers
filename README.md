[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

# ARM Patch Tools

> A curated collection of fully free, no-trial tools for applying and managing binary patches (`.patch`, delta, or OTA-style) targeting ARM/AArch32 and AArch64 binaries and firmware.

---

## Table of Contents

1. [Overview](#overview)  
2. [Tools](#tools)  
   - [Radare2 (r2)](#radare2-r2)  
   - [Ghidra](#ghidra)  
   - [bsdiff / bspatch](#bsdiff--bspatch)  
   - [xdelta3](#xdelta3)  
   - [Android’s `applypatch` (AOSP)](#androids-applypatch-aosp)  
   - [IMG Patch Tools (erfanoabdi)](#img-patch-tools-erfanoabdi)  
3. [Installation & Usage](#installation--usage)  
4. [Contributing](#contributing)  
5. [License](#license)  

---

## Overview

Applying binary patches to ARM executables and firmware is essential for software distribution, reverse engineering, firmware updates, and security testing. This repository aggregates the best fully free and open-source tools—without any trial limitations—that support ARM architectures:

- **Instruction-level & byte-level patching**  
- **Delta-based firmware updates**  
- **OTA-style patch application**

Each tool entry includes description, key features, supported platforms, pros & cons, and links to official repositories.

---

## Tools

### Radare2 (r2)

A modular, command-line reverse-engineering framework and hex editor.  
- **Features**  
  - Disassembly & re-assembly (ARM/AArch32/AArch64)  
  - Interactive hex editing & scripting via r2pipe (JavaScript, Python)  
  - Debugging, emulation, plugin support (diffing, unpacking, etc.)  
- **Platforms**  
  Windows, Linux, macOS, Android, BSD variants  
- **Pros**  
  Fully open-source (LGPL), highly scriptable, extensive architecture support  
- **Cons**  
  Steep CLI learning curve; non-intuitive for beginners  
- **Repo**  
  https://github.com/radareorg/radare2

---

### Ghidra

A Java-based software reverse-engineering suite with a polished GUI.  
- **Features**  
  - Advanced disassembler & decompiler for ARM/AArch32/AArch64  
  - Interactive CodeBrowser for instruction/data patching  
  - Scripting via Java or Python; project database management  
- **Platforms**  
  Cross-platform: Windows, macOS, Linux  
- **Pros**  
  Rich analysis features; permissive Apache 2.0 license; widely adopted  
- **Cons**  
  Large memory footprint; requires Java; moderate learning curve  
- **Repo**  
  https://github.com/NationalSecurityAgency/ghidra

---

### bsdiff / bspatch

High-performance binary diff & patch utilities (BSD license).  
- **Features**  
  - Generates compact binary diffs (suffix-sorting algorithm)  
  - Applies diffs to recreate target binaries  
- **Platforms**  
  Linux, macOS, Windows (MinGW/Cygwin)  
- **Pros**  
  Produces very small patches for executables; used in Android OTA, Chrome, FreeBSD  
- **Cons**  
  Patch creation can be memory-intensive; requires exact “old” version  
- **Repo**  
  https://github.com/mendsley/bsdiff

---

### xdelta3

A VCDIFF-based delta encoding tool with optional compression (GPL v2).  
- **Features**  
  - Creates & applies binary deltas; supports LZMA, gzip, bzip2  
  - Handles large files efficiently  
- **Platforms**  
  Linux, macOS, Windows  
- **Pros**  
  Standard VCDIFF format; mature/stable codebase  
- **Cons**  
  Larger patches than bsdiff for executables; copyleft license  
- **Repo**  
  https://github.com/xorgy/xdelta3

---

### Android’s `applypatch` (AOSP)

OTA patch application utility built into Android recovery (Apache 2.0).  
- **Features**  
  - Applies OTA-style `.p` patches to partitions or files  
  - Verifies integrity via hash checks  
- **Platforms**  
  Android recovery environment (requires AOSP build)  
- **Pros**  
  Official mechanism for Android firmware updates  
- **Cons**  
  Not standalone; complex usage via updater-script  
- **Source**  
  Included in AOSP under `platform_system_core`

---

### IMG Patch Tools (erfanoabdi)

Desktop utilities for applying Android OTA patches on PC (GPL 3.0).  
- **Features**  
  - `BlockImageUpdate` for sparse image transfers  
  - `ApplyPatchfn` for generic `.p` patch files  
- **Platforms**  
  Linux, macOS (Windows untested)  
- **Pros**  
  Apply OTA patches without device; open-source  
- **Cons**  
  Specialized to OTA format; requires build dependencies  
- **Repo**  
  https://github.com/erfanoabdi/imgpatchtools

---

## Installation & Usage

Each tool is distributed via its GitHub repository. Generally:

1. **Clone the repo**  
   ```bash
   git clone https://github.com/<owner>/<repo>.git
   cd <repo>
