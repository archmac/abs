
pkgname=libxml2
pkgver=2.7.8
pkgrel=1
pkgdesc="XML parsing library, version 2"
arch=(i386 x86_64)
license=(custom)
makedepends=()
url='http://www.xmlsoft.org/'
source=(ftp://ftp.xmlsoft.org/${pkgname}/${pkgname}-${pkgver}.tar.gz)
md5sums=(8127a65e8c3b08856093099b52599c86)

build() {
    cd $srcdir/$pkgname-$pkgver
    ./configure --prefix=/Library/ArchMac \
        --docdir=/Library/ArchMac/doc/libxml2 \
        --mandir=/Library/ArchMac/man \
        --with-threads --with-history \
        --without-docbook --enable-shared
    make
}

package() {
    cd $srcdir/$pkgname-$pkgver
    make DESTDIR=$pkgdir install
    rm -rf $pkgdir/Library/ArchMac/share/{doc,gtk-doc}
    #install -Dm644 COPYING "${pkgdir}/share/licenses/${pkgname}/COPYING"
}

