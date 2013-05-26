
pkgname=xz
pkgver=5.0.4
pkgrel=3
pkgdesc='Library and command line tools for XZ and LZMA compressed files'
arch=('i386' 'x86_64')
url='http://tukaani.org/xz/'
license=('GPL' 'LGPL' 'custom')
options=(!libtool)
source=("http://tukaani.org/${pkgname}/${pkgname}-${pkgver}.tar.gz")
md5sums=('df3df690aef18384e1e031be7ec3a964')

build() {
    cd $srcdir/$pkgname-$pkgver
    ./configure --disable-rpath --enable-werror \
        --prefix=/Library/ArchMac \
        --mandir=/Library/ArchMac/man \
        --docdir=/Library/ArchMac/doc/$pkgname
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

