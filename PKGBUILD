
pkgname=pkg-config
pkgver=0.28
pkgrel=2
pkgdesc='A system for managing library compile/link flags'
arch=(i386 x86_64)
url='http://pkgconfig.freedesktop.org/wiki/'
license=(GPL)
source=(http://pkgconfig.freedesktop.org/releases/$pkgname-$pkgver.tar.gz)
md5sums=(aa3c86e67551adc3ac865160e34a2a0d)

build() {
  cd $srcdir/$pkgname-$pkgver
  ./configure --prefix=/Library/ArchMac --with-internal-glib
  make
}

check() {
  cd $srcdir/$pkgname-$pkgver
  make check
}

package() {
  cd $srcdir/$pkgname-$pkgver
  make DESTDIR=$pkgdir install
}

