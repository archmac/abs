
pkgname=nettle
pkgver=2.7
pkgrel=1
pkgdesc="A low-level cryptographic library."
arch=(i386 x86_64)
url="http://www.lysator.liu.se/~nisse/nettle/"
license=(GPL)
depends=('gmp')
source=($url/../archive/$pkgname-$pkgver.tar.gz)
md5sums=(2caa1bd667c35db71becb93c5d89737f)

build() {
    cd $srcdir/$pkgname-$pkgver
    ./configure --prefix=/Library/ArchMac \
        --infodir=/Library/ArchMac/info
    make
}

check() {
    cd $srcdir/$pkgname-$pkgver
    #make -k check
}

package() {
    cd $srcdir/$pkgname-$pkgver
    make DESTDIR=$pkgdir install
}

