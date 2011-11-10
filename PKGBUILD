# Maintainer: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>
# Contributor: Thomas Baechler <thomas@archlinux.org>

pkgname=libfprint
pkgver=0.4.0
pkgrel=1
pkgdesc="Library for fingerprint readers"
arch=(i686 x86_64)
url="http://www.freedesktop.org/wiki/Software/fprint/libfprint"
license=(LGPL)
depends=(libusb nss gdk-pixbuf2)
groups=(fprint)
options=(!libtool !emptydirs)
_snap=$pkgname-48ec64f68330452b011d14be67653f1d48fb1405
source=(http://cgit.freedesktop.org/libfprint/$pkgname/snapshot/$_snap.tar.bz2)
md5sums=('858a0f0d7abd21ac494f9bec904dc156')

build() {
  cd "$srcdir/$_snap"
  ./autogen.sh --prefix=/usr --sysconfdir=/etc --disable-static \
    --disable-examples-build --disable-x11-examples-build
  make
}

package() {
  cd "$srcdir/$_snap"
  make DESTDIR="$pkgdir" install

  mkdir -p "$pkgdir/lib/udev/rules.d"
  mv "$pkgdir"/etc/udev/rules.d/* "$pkgdir/lib/udev/rules.d/"
}
