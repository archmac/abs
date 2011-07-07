
pkgname=libarchive
pkgver=2.8.4
pkgrel=7
pkgdesc="library that can create and read several streaming archive formats"
arch=('i386')
url="http://people.freebsd.org/~kientzle/libarchive/"
license=('BSD')
groups=('base')
depends=('zlib' 'bzip2')
options=(!libtool)
source=(http://libarchive.googlecode.com/files/libarchive-$pkgver.tar.gz)
md5sums=('83b237a542f27969a8d68ac217dc3796')

build() {
  cd $srcdir/$pkgname-$pkgver
  ./configure --prefix=/Library/ArchMac
  make
}

package() {
  cd $srcdir/$pkgname-$pkgver
  make DESTDIR=$pkgdir install
}
