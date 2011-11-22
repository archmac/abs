
pkgname=tarsnap
pkgver=1.0.29
pkgrel=1
pkgdesc='An online encrypted snapshotted backup service'
arch=('i386')
url='http://www.tarsnap.com/'
license=('custom')
depends=('bzip2' 'openssl')
source=("https://www.tarsnap.com/download/$pkgname-autoconf-$pkgver.tgz")
md5sums=('0e5ef12a92fb651b51159b1ad52317f6')

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
