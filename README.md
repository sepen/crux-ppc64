# CRUX-PPC64

**Bringing CRUX to PowerPC 64-bit (big-endian) systems**

This project provides a root filesystem image and a set of port overlays to run the minimalist CRUX Linux
 distribution on PowerPC 64-bit big-endian (ppc64) hardware.

It is intended for enthusiasts, developers, and users of POWER and PowerPC systems who want a clean, source-based Linux distribution.

--- 

## Overview

CRUX officially targets the x86-64 architecture. \
CRUX-PPC64 extends CRUX to support ppc64 big-endian systems, including a wide range of CPUs from older Apple hardware to enterprise POWER machines.

This project focuses on a portable and consistent userland, built with a unified toolchain targeting:

- 64-bit PowerPC (big-endian)
- ELFv1 ABI compatibility
- Broad CPU support across multiple generations

This release includes:

- A prebuilt root filesystem: \
  `crux-ppc64.rootfs.tar.xz` — a minimal CRUX base system for ppc64
- Architecture-specific port overlays:
  - `core-ppc64` — base system ports adapted for ppc64
  - `opt-ppc64` — optional and userland software ports
  - `xorg-ppc64` — graphical environment ports

These overlays contain adjusted `Pkgfile`'s and build configurations tuned for portable ppc64 systems.

They come preinstalled and preconfigured in the root filesystem image.

---

## Target Architecture

CRUX-PPC64 targets:

- **ppc64 (big-endian)** systems
- Compatible with CPUs such as:
  - PowerPC 970 (PowerMac G5)
  - POWER4 / POWER5 / POWER6 / POWER7

The system is built to be:

- Portable across multiple CPUs
- **ABI-stable (ELFv1)**
- Independent of specific microarchitectural optimizations

This allows a single root filesystem to be reused across different machines, as long as the kernel supports the hardware.

---

## Target Audience

- PowerPC and IBM POWER hardware users
- PowerMac G5 owners
- Retrocomputing enthusiasts
- Developers interested in non-x86 architectures
- Users who prefer minimal, source-based Linux systems

CRUX-PPC64 stays aligned with CRUX principles: **simplicity, transparency, and control**.

---

## Toolchain Notes

The system toolchain is rebuilt for consistency across all components:
- binutils
- glibc
- gcc
- core libraries

All packages are compiled with unified flags targeting:
- 64-bit PowerPC
- Generic CPU baseline
- ELFv1 ABI

This ensures:
- inary compatibility across systems
- Predictable behavior
- Reduced risk of ABI or instruction mismatches

---

## Notes on Compatibility

- This is an unofficial CRUX port
- Not supported by the CRUX core team
- Some upstream software may not support ppc64 anymore
- Fallback to default ports may require manual fixes
- Kernel support is required per machine (G5, POWER, etc.)

Despite this, a large portion of userland software builds cleanly with a modern toolchain.

---

## Philosophy

> “Keep it simple.” — CRUX motto

CRUX-PPC64 follows the same philosophy as upstream CRUX:
- Minimal modifications
- Transparent build system
- No unnecessary abstraction
- Full user control

The goal is not to reinvent CRUX, but to **extend it to another architecture cleanly**.

---

## License

All CRUX base ports retain their original licenses. \
Overlay modifications and project-specific scripts are released under the **GPLv3 License**.

---

## Credits

- [CRUX Linux Team](https://crux.nu/)
- [CRUX-ARM Project](https://crux-arm.nu/) — inspiration for overlay design
- [CRUX-PPC GNU/Linux Project](https://cruxppc.org/) - for all his work over the years
- [cruxppc-ng-3.7](https://github.com/cruxppc/cruxppc-ng-3.7) - CRUX Linux 3.7 ported to PowerPC with a multilib design
- [VoidLinux PPC](https://voidlinux-ppc.org/) - impressive what they've managed to do for this architecture
- Community maintainers and retro-hardware enthusiasts
