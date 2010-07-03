# Maintainer: Thomas Baechler <thomas@archlinux.org>

pkgname=libfprint
pkgver=0.0.6
pkgrel=7
pkgdesc="Library for fingerprint scanner support in applications"
arch=('i686' 'x86_64')
url="http://reactivated.net/fprint/wiki/Main_Page"
license=('LGPL')
depends=('libusb' 'imagemagick' 'openssl' 'glib2')
groups=('fprint')
options=(!libtool)
install=fprint.install
source=(http://downloads.sourceforge.net/sourceforge/fprint/$pkgname-$pkgver.tar.bz2
        50-fprint.rules)
md5sums=('4f47b46021b186488b60aaa97f90fe43' '2c4021484509498fb17bdbe0b6d85ebf')
sha1sums=('430af91efbefeb2b98fe30215fb33051e4f8efc5' '86e7274711226685dabf7d28f4b93dae85ffb29b')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./configure --prefix=/usr #--enable-debug-log
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir" install
  install -D -m644 "$srcdir/50-fprint.rules" "$pkgdir/lib/udev/rules.d/70-fprint.rules"
}
