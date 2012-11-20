# Maintainer: Tom Gundersen <teg@jklm.no>
# Contributor: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>
# Contributor: Thomas Baechler <thomas@archlinux.org>

pkgname=libfprint
pkgver=0.4.0
pkgrel=4
pkgdesc="Library for fingerprint readers"
arch=(i686 x86_64)
url="http://www.freedesktop.org/wiki/Software/fprint/libfprint"
license=(LGPL)
depends=(libusb nss gdk-pixbuf2)
groups=(fprint)
options=(!libtool !emptydirs)
_snap=$pkgname-b2a53a459cc4294dec049d8d7f1b92ebb704f983
source=(http://cgit.freedesktop.org/libfprint/$pkgname/snapshot/$_snap.tar.bz2)

build() {
  cd "$srcdir/$_snap"
  NOCONFIGURE=1 ./autogen.sh
  ./configure --prefix=/usr --sysconfdir=/etc --disable-static
  make
}

package() {
  cd "$srcdir/$_snap"
  make DESTDIR="$pkgdir" install
}
md5sums=('2695b689910146b753111d48d8a6cb1c')
