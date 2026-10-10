# jellyfin-mpv-shim-git

This repository contains the `PKGBUILD` to build and install the latest development version (Git master branch) of `jellyfin-mpv-shim` for Arch Linux.

## Installation

To install this package, clone this repository and use the `makepkg` command. This will automatically download the latest source code from GitHub, resolve the internal build process, and install the package on your system.

```bash
# 1. Clone this repository
git clone https://github.com/ktkr3d/jellyfin-mpv-shim-git.git

# 2. Move into the directory
cd jellyfin-mpv-shim-git

# 3. Build and install the package (resolves dependencies automatically via pacman)
makepkg -si
```

## Prerequisites

Before running `makepkg -si`, make sure you have the required AUR dependency packages installed on your system.

If any dependencies are missing from the official repositories, you will need to install them beforehand using your preferred AUR helper (e.g., `yay` or `paru`):

```bash
# Example: Installing required AUR dependencies if missing
yay -S python-mpv-jsonipc
```
