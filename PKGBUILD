
pkgname=pcre
pkgver=8.32
pkgrel=4
pkgdesc='A library that implements Perl 5-style regular expressions'
arch=(i386 x86_64)
url='http://www.pcre.org/'
license=(BSD)
source=(ftp://ftp.csx.cam.ac.uk/pub/software/programming/pcre/$pkgname-$pkgver.tar.bz2)
md5sums=(62f02a76bb57a40bc66681760ed511d5)

build() {
  cd $srcdir/$pkgname-$pkgver
    ./configure --enable-jit --enable-utf --enable-unicode-properties \
        --prefix=/Library/ArchMac \
        --mandir=/Library/ArchMac/man \
        --docdir=/Library/ArchMac/doc/pcre
  make
}

package() {
    cd $srcdir/$pkgname-$pkgver
    make DESTDIR=$pkgdir install
}

