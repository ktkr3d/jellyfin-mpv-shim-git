# Maintainer: Anonymous
pkgname=jellyfin-mpv-shim-git
_pkgname=jellyfin-mpv-shim
pkgver=v3.1.0.r31.437ac000 # makepkg実行時に自動更新されます
pkgrel=1
pkgdesc="Cast media from Jellyfin to MPV (Git version)"
arch=('any')
url="https://github.com/jellyfin/jellyfin-mpv-shim"
license=('GPL-3.0-or-later')
depends=(
  'mpv'
  'python'
  'python-jellyfin-apiclient'
  'python-jinja'
  'python-mpv'
  'python-mpv-jsonipc'
  'python-pypresence'
  'python-websocket-client'
)
makedepends=(
  'git'
  'python-build'
  'python-installer'
  'python-setuptools'
  'python-wheel'
)
provides=("${_pkgname}")
conflicts=("${_pkgname}")
source=("git+${url}.git")
sha256sums=('SKIP')

pkgver() {
  cd "${_pkgname}"
  git describe --long --tags 2>/dev/null | sed 's/\([^-]*-\)g/r\1/;s/-/./g' ||
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd "${_pkgname}"
  python -m build --wheel --no-isolation
}

package() {
  cd "${_pkgname}"
  python -m installer --destdir="${pkgdir}" dist/*.whl
  
  install -Dm644 "jellyfin_mpv_shim/integration/com.github.iwalton3.jellyfin-mpv-shim.desktop" "${pkgdir}/usr/share/applications/jellyfin-mpv-shim.desktop"
  
  for size in 16 32 48 64 128 256; do
    install -Dm644 "jellyfin_mpv_shim/integration/jellyfin-${size}.png" "${pkgdir}/usr/share/icons/hicolor/${size}x${size}/apps/jellyfin-mpv-shim.png"
  done
}

