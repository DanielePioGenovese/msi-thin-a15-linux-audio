# MSI Thin A15 B7VF - Linux Internal Microphone Quirk

This repository contains a kernel patch to enable the internal digital microphone on **MSI Thin A15 B7VF** laptops (AMD Yellow Carp / Rembrandt platform).

##  STATUS: SUBMITTED UPSTREAM
- **Target Subsystem:** ALSA / ASoC (AMD yc)
- **Submission Date:** March 20, 2026
- **Link to Discussion:** Pending

## The Issue
On the MSI Thin A15 B7VF, the internal microphone is not detected by default because it requires a specific entry in the kernel's ACPI/DMI quirk table. Without this patch, the system fails to initialize the digital mic on the AMD Audio processor.

## Patch Content
The patch adds the following DMI match to `sound/soc/amd/yc/acp6x-mach.c`:
- **Vendor:** Micro-Star International Co., Ltd.
- **Product Name:** Thin A15 B7VF
- **Board Name:** MS-16R8

## How to Apply
If you are compiling your own kernel (version 6.x+):
1. Clone the Linux source tree.
2. Download the `.patch` file from this repo.
3. Run: `patch -p1 < 0001-ASoC-amd-yc-Add-MSI-Thin-A15-B7VF-to-quirk-table.patch`
4. Recompile and install your kernel.

## Author
**Daniele Pio Genovese** *Linux Kernel Contributor*