
pkgname=libffi
pkgver=3.0.13
pkgrel=3
pkgdesc="A portable, high level programming interface to various calling conventions"
arch=('i386' 'x86_64')
url="http://sourceware.org/libffi/"
license=('MIT')
options=(!libtool !docs)
source=(ftp://sourceware.org/pub/libffi/libffi-${pkgver}.tar.gz)
md5sums=('45f3b6dbc9ee7c7dfbbbc5feba571529')

build() {
    cd $srcdir/$pkgname-$pkgver
    ./configure --prefix=/Library/ArchMac --disable-static
    make
}

package() {
    cd $srcdir/$pkgname-$pkgver
    make DESTDIR=$pkgdir install
    rm ${pkgdir}/Library/ArchMac/share/info/dir
}

