
pkgname=gnupg
pkgver=1.4.12
pkgrel=5
pkgdesc="The OpenPGP part of the GNU Privacy Guard (GnuPG)"
arch=(i386 x86_64)
license=(GPL3)
depends=(bzip2 curl libedit zlib)
source=(ftp://ftp.gnupg.org/gcrypt/gnupg/gnupg-$pkgver.tar.bz2)
url='http://www.gnupg.org/'
md5sums=(ce3742e5c7912559cab7894ad8ba7f6b)

build() {
    cd $srcdir/$pkgname-$pkgver
    ./configure --prefix=/Library/ArchMac \
                --mandir=/Library/ArchMac/man \
                --infodir=/Library/ArchMac/info
    make
}

package() {
    cd $srcdir/$pkgname-$pkgver
    make DESTDIR=$pkgdir install
}

