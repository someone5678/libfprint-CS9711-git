# Maintainer: Tom Gundersen <teg@jklm.no>
# Contributor: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>
# Contributor: Thomas Baechler <thomas@archlinux.org>

pkgname=libfprint
pkgver=0.4.0
pkgrel=3
pkgdesc="Library for fingerprint readers"
arch=(i686 x86_64)
url="http://www.freedesktop.org/wiki/Software/fprint/libfprint"
license=(LGPL)
depends=(libusb nss gdk-pixbuf2)
groups=(fprint)
options=(!libtool !emptydirs)
_snap=$pkgname-dfff16f3e32519ad071bdb1233c75bfe3ffa5557
source=(http://cgit.freedesktop.org/libfprint/$pkgname/snapshot/$_snap.tar.bz2)

build() {
  cd "$srcdir/$_snap"
  sed -i '\|^./configure|,+1d' autogen.sh
  ./autogen.sh
  ./configure --prefix=/usr --sysconfdir=/etc --disable-static
  make
}

package() {
  cd "$srcdir/$_snap"
  make DESTDIR="$pkgdir" install
}
md5sums=('aa2fb6b90cf8c53aebd1f0e656dd70c1')
