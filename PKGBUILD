# Maintainer: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>
# Contributor: Tom Gundersen <teg@jklm.no>
# Contributor: Thomas Baechler <thomas@archlinux.org>

pkgname=libfprint
pkgver=0.8.1
pkgrel=1
pkgdesc="Library for fingerprint readers"
arch=(x86_64)
url="https://www.freedesktop.org/wiki/Software/fprint/libfprint"
license=(LGPL)
depends=(libusb nss pixman glib2)
makedepends=(git meson gtk-doc)
groups=(fprint)
_commit=6f6127cbb640a8549eb971aa73d6fe8543d3c40b  # tags/V_0_8_1^0
source=("git+https://gitlab.freedesktop.org/libfprint/libfprint.git#commit=$_commit")
sha256sums=('SKIP')

pkgver() {
  cd $pkgname
  git describe --tags | sed 's/^V_//;s/_/./g;s/-/+/g'
}

prepare() {
  cd $pkgname
  # Fixup missing tag
  git tag -f V_0_8_1 6f6127cbb640a8549eb971aa73d6fe8543d3c40b
}

build() {
  arch-meson $pkgname build -D x11-examples=false
  ninja -C build
}

check() {
  cd build
  meson test
}

package() {
  DESTDIR="$pkgdir" ninja -C build install
}
