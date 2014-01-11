
pkgname=tarsnap
pkgver=1.0.35
pkgrel=1
pkgdesc='An online encrypted snapshotted backup service'
arch=(i386 x86_64)
url='https://www.tarsnap.com/'
license=(custom)
depends=(bzip2 openssl)
source=("$url/download/$pkgname-autoconf-$pkgver.tgz")
md5sums=(74daeff5479ec6f101a903f4047b526f)

build() {
  cd $srcdir/$pkgname-autoconf-$pkgver
  ./configure --prefix=/Library/ArchMac
  make
}

package() {
    cd $srcdir/$pkgname-autoconf-$pkgver
    make DESTDIR=$pkgdir install
    # install -D -m644 COPYING "$pkgdir/usr/share/licenses/$pkgname/COPYING"    
}
