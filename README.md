# SystemD Stub Package for Arch Linux
## Description
This is a minimal pacman package that pretends to provide `systemd`, `systemd-libs` and `libsystemd.so=0-64` functionality and creates the symlink `/usr/lib/libsystemd.so.0` which points to `/usr/lib/libelogind.so.0` to solve dependency issues and prevent some packages like `seatd` from crashing when trying to use a distribution shipping `makepkg` and SystemD, without SystemD.
## Installation
```
git clone https://github.com/Secondarian/archlinux-sysremd-stub
cd archlinux-systemd-stub
makepkg -si
```
## Use Case
I personally use this so that I can have the x86_64-v3-optimised ALHP and CachyOS repos above the Artix repos in `/etc/pacman.conf` without switching to SystemD and I don't know of any other practical use case.
## Note
This has only been tested by me on my fairly minimal system, issues may arise on more bloated environments like systems with full desktop environments because these may have some more SystemD dependencies.
## Tip
If pacman asks you to replace you standalone `udev` package with `systemd` on every single update, uncomment `IgnorePkg` in `/etc/pacman.conf` and add `systemd` to it.
