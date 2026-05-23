# Maintainer: artist for Artix Linux

pkgname=sonic-interface-libraries
pkgver=6.6.5
_dirver=$(echo $pkgver | cut -d. -f1-3)
pkgrel=4
_commit="e43e11f184067b0c285c68a5baed179c2eacbeb8"
pkgdesc='Sonic-DE library and runtime components'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-interface-libraries'
license=(LGPL-2.0-or-later)
depends=(glibc
         sonic-activities
         kcolorscheme
         kconfig
         sonic-frameworks-core-addons
         kguiaddons
         ki18n
         kiconthemes
         sonic-frameworks-quick-ui
         sonic-frameworks-io
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
         sonic-frameworks-keybind
         sonic-frameworks-windowsystem)
makedepends=(extra-cmake-modules
  plasma-wayland-protocols
             kdoctools)
conflicts=(libplasma plasma-framework)
provides=(libplasma)
replaces=(libplasma plasma-framework)
groups=(sonicde)
makedepends+=(git)
source=("$pkgname-$pkgver::git+$url.git#commit=$_commit")

build() {
  cmake -B build  -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}

sha256sums=('caa8267d5043409a2dc0eb6c421f6ad1b7b5c6315d6f5e8bb0e0d43bc0046dd2')

