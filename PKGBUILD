# Maintainer: Tom Gundersen <teg@jklm.no>
# Contributor: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>
# Contributor: Thomas Baechler <thomas@archlinux.org>

pkgname=libfprint
pkgver=0.5.1
pkgrel=1
pkgdesc="Library for fingerprint readers"
arch=(i686 x86_64)
url="http://www.freedesktop.org/wiki/Software/fprint/libfprint"
license=(LGPL)
depends=(libusb nss gdk-pixbuf2)
groups=(fprint)
options=(!libtool !emptydirs)
source=(http://people.freedesktop.org/~hadess/$pkgname-$pkgver.tar.xz)
md5sums=('f52ac662d89fb82a441dacb0bac36c13')

build() {
  cd $pkgname-$pkgver
  ./configure --prefix=/usr --sysconfdir=/etc --disable-static
  make
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir" install
}
