
pkgname=tarsnap
pkgver=1.0.33
pkgrel=1
pkgdesc='An online encrypted snapshotted backup service'
arch=('i386' 'x86_64')
url='http://www.tarsnap.com/'
license=('custom')
depends=('bzip2' 'openssl')
source=("https://www.tarsnap.com/download/$pkgname-autoconf-$pkgver.tgz")
md5sums=('a6267972d834198716b9fe09680e47e2')

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
