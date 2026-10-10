# jellyfin-mpv-shim-git

This repository contains the `PKGBUILD` to build and install the latest development version (Git master branch) of `jellyfin-mpv-shim` for Arch Linux.

## Installation

### 1. Manual Build

Clone this repository and use the `makepkg` command to build and install the package.

```bash
git clone https://github.com/ktkr3d/jellyfin-mpv-shim-git.git
cd jellyfin-mpv-shim-git
makepkg -si
```

### 2. Using AUR Helpers (yay / paru)

You can also install it directly by passing the GitHub repository URL to your preferred AUR helper.

```bash
# Using yay
yay -S git+https://github.com/ktkr3d/jellyfin-mpv-shim-git.git

# Using paru
paru -S git+https://github.com/ktkr3d/jellyfin-mpv-shim-git.git
```

## Prerequisites

Before building, make sure you have the required AUR dependency packages (such as `python-mpv-jsonipc`) installed on your system.
