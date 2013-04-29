
pkgname=graphviz
pkgver=2.30.1
pkgrel=2
pkgdesc="Tools for a graph description language"
arch=(i386 x86_64)
license=(CPL)
url="http://www.graphviz.org/"
source=($url/pub/$pkgname/stable/SOURCES/$pkgname-$pkgver.tar.gz)
install=graphviz.install
md5sums=(8130785a8f1fb8a57f6b839b617e85fa)

build() {
    cd $srcdir/$pkgname-$pkgver
    ./configure --prefix=/Library/ArchMac \
        --mandir=/Library/ArchMac/man --disable-tcl
    make
}

package() {
    cd $srcdir/$pkgname-$pkgver
    make DESTDIR="$pkgdir" install

    # configure --docdir doesn't work
    cd $pkgdir/Library/ArchMac
    mkdir doc
    mv share/graphviz/doc doc/graphviz
}

