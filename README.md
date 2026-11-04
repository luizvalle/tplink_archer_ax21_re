# TP-Link Archer AX21 RE

<img src="images/archer_ax21.png" alt="TP-Link Archer AX21 router" width="400">

Exploring a TP-Link Archer AX21 to practice reverse engineering and learn how
embedded Linux devices work.

## What I have done so far

- **Hardware and UART:** identified the UART pins using a multimeter, soldered
  header pins, and connected through a USB-to-UART adapter using minicom at
  115200 baud.
- **Filesystem acquisition:** brought up a direct Ethernet connection and dumped
  the 50 MiB rootfs partition using netcat. Extracted its UBI/UBIFS filesystem
  with UBI Reader for offline inspection.
- **Binary reverse engineering:** used Ghidra to analyze the ARM BusyBox binary,
  traced its custom UART root-password derivation, and verified root login.
- **Web authentication:** inspected the firmware's Lua modules and modified Lua
  bytecode, then recovered the web password using its existing Lua API.
- **SSH and persistence:** investigated vendor-specific Dropbear behavior and
  configured RSA-key-only root access. Added a startup hook backed by persistent
  storage and verified access after reboot.
- **Network exploration:** used iproute2 and Nmap to inspect addressing and
  services, and curl to query HTTP and UPnP descriptions.

Notes and experiments: [work log](docs/work_logs.md).
