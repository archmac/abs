
pkgname=gmp
pkgver=5.1.1
pkgrel=2
pkgdesc="A free library for arbitrary precision arithmetic"
arch=(i386 x86_64)
url="http://gmplib.org/"
makedepends=(xz)
license=(LGPL3)
source=(ftp://ftp.gmplib.org/pub/gmp-$pkgver/gmp-$pkgver.tar.xz)
md5sums=(485b1296e6287fa381e6015b19767989)

build() {
    cd $srcdir/$pkgname-$pkgver
    ./configure --prefix=/Library/ArchMac \
        --infodir=/Library/ArchMac/info
    make
}

check() {
    cd $srcdir/$pkgname-$pkgver
    make -k check
}

package() {
    cd $srcdir/$pkgname-$pkgver
    make DESTDIR=$pkgdir install
}

