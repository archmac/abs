
pkgname=rdup
pkgver=1.1.14
pkgrel=1
pkgdesc="Generates a file list suitable for making backups."
url="http://miek.nl/projects/rdup"
license=(GPL3)
depends=(glib2 pcre nettle)
arch=(i386 x86_64)
source=($url/$pkgname-$pkgver.tar.bz2)
md5sums=('aaaaf0518304e3a23aee3594d72e7afc')

build() {
    cd $srcdir/$pkgname-$pkgver
    ./configure --prefix=/Library/ArchMac \
        --mandir=/Library/ArchMac/man
    echo '#define HAVE_DIRFD 1' >> config.h
    make
}

package() {
    cd $srcdir/$pkgname-$pkgver
    make DESTDIR=$pkgdir install
}

