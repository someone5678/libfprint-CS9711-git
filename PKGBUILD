# Maintainer: Tom Gundersen <teg@jklm.no>
# Contributor: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>
# Contributor: Thomas Baechler <thomas@archlinux.org>

pkgname=libfprint
pkgver=0.6.0
pkgrel=1
pkgdesc="Library for fingerprint readers"
arch=(i686 x86_64)
url="http://www.freedesktop.org/wiki/Software/fprint/libfprint"
license=(LGPL)
depends=(libusb nss pixman)
groups=(fprint)
options=(!emptydirs)
source=(http://people.freedesktop.org/~hadess/$pkgname-$pkgver.tar.xz)
md5sums=('1e66f6e786348b46075368cc682450a8')

build() {
  cd $pkgname-$pkgver
  ./configure --prefix=/usr --sysconfdir=/etc --disable-static
  make
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir" install
}
