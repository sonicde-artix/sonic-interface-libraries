# Maintainer: callmetango
# Contributor: artist <artist@artixlinux.org>

pkgname=sonic-interface-libraries
pkgver=6.6.5
_dirver=$(echo $pkgver | cut -d. -f1-3)
pkgrel=4
pkgdesc='Sonic-DE library and runtime components'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-interface-libraries'
license=(LGPL-2.0-or-later)
depends=(glibc
         kcolorscheme
         kconfig
         kguiaddons
         ki18n
         kiconthemes
         knotifications
         kpackage
         ksvg
         kwidgetsaddons
         libgcc
         libglvnd
         libx11
         libxcb
         qt6-5compat
         qt6-base
         qt6-declarative
         sonic-activities
         sonic-frameworks-core-addons
         sonic-frameworks-io
         sonic-frameworks-keybind
         sonic-frameworks-quick-ui
         sonic-frameworks-windowsystem)
makedepends=(extra-cmake-modules
  plasma-wayland-protocols
             kdoctools)
conflicts=(libplasma plasma-framework)
provides=(libplasma)
replaces=(libplasma plasma-framework)
groups=(sonicde)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('caa8267d5043409a2dc0eb6c421f6ad1b7b5c6315d6f5e8bb0e0d43bc0046dd2')

build() {
  cmake -B build  -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
