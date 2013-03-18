
pkgname=gettext
pkgver=0.18.2.1
pkgrel=2
pkgdesc="GNU internationalization library"
arch=('i386' 'x86_64')
url="http://www.gnu.org/software/gettext/"
license=('GPL')
#depends=('gcc-libs' 'acl' 'sh' 'glib2')
optdepends=('cvs: for autopoint tool')
options=(!libtool !docs)
#install=gettext.install
source=(ftp://ftp.gnu.org/pub/gnu/gettext/${pkgname}-${pkgver}.tar.gz)
md5sums=('034c8103b14654ebd300fadac44d6f14')
         #'e4658c307333395a12f8d0b4d95fbb0f')

build() {
    cd $srcdir/$pkgname-$pkgver
    ./configure --prefix=/Library/ArchMac
    make
}

package() {
    cd $srcdir/$pkgname-$pkgver
    make DESTDIR=$pkgdir install

    rm ${pkgdir}/Library/ArchMac/share/info/dir
    rm ${pkgdir}/Library/ArchMac/share/locale/locale.alias
}

