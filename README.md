#Fedora 44 - Kernel Upgrade, Old Kernel Cleanup, and NVIDIA GTX 750 Ti Driver Installation
Author: Reza
System: Fedora 44
GPU: NVIDIA GeForce GTX 750 Ti
Driver Series: NVIDIA 580xx Legacy
Status: Successful

======================================================================
1) Goal
======================================================================

This document records the steps used to:

1. Upgrade and stabilize the system on kernel 7.1.3
2. Remove the old kernel 6.19.10
3. Install the correct NVIDIA legacy driver for GTX 750 Ti
4. Rebuild kernel modules and initramfs
5. Verify that NVIDIA is working correctly
6. Extend display to dual monitors

======================================================================
2) Initial Problem
======================================================================

The system did not properly recognize the NVIDIA GTX 750 Ti.

Observed issues:
- `nvidia-smi` was not working initially
- Newer NVIDIA driver series 595.x had been installed
- GTX 750 Ti is not supported by NVIDIA 590+ driver series
- No NVIDIA kernel module was loaded
- The monitor was connected through the motherboard/iGPU during setup

Important compatibility note:
- GTX 750 Ti requires the NVIDIA 580xx legacy driver series
- Driver 595.x is incompatible with this card
