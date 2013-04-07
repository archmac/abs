
pkgname=gettext
pkgver=0.18.2.1
pkgrel=4
pkgdesc='GNU internationalization library'
arch=(i386 x86_64)
url='http://www.gnu.org/software/gettext/'
license=(GPL)
depends=(bash glib2)
optdepends=('cvs: for autopoint tool')
options=(!docs)
source=(ftp://ftp.gnu.org/pub/gnu/gettext/${pkgname}-${pkgver}.tar.gz)
md5sums=('034c8103b14654ebd300fadac44d6f14')

build() {
    cd $srcdir/$pkgname-$pkgver
    ./configure --prefix=/Library/ArchMac \
                --infodir=/Library/ArchMac/info
    make
}

package() {
    cd $srcdir/$pkgname-$pkgver
    make DESTDIR=$pkgdir install

    rm ${pkgdir}/Library/ArchMac/share/locale/locale.alias
}

