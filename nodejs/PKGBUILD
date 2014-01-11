
pkgname=nodejs
pkgver=0.10.20
pkgrel=1
pkgdesc='Evented I/O for V8 javascript'
arch=(i386 x86_64)
url='http://nodejs.org/'
license=(MIT)
source=("$url/dist/v${pkgver}/node-v${pkgver}.tar.gz")
md5sums=(784e7d7a8e29dfec88ddb2e72a895407)

build() {
  cd $srcdir/node-v$pkgver
  ./configure --prefix=/Library/ArchMac
  make 
}

check() {
  cd $srcdir/node-v$pkgver
  ulimit -n 1024
  make test
}

package() {
  cd $srcdir/node-v$pkgver
  make DESTDIR=$pkgdir install

  # install api docs
  install -m755 -d $pkgdir/Library/ArchMac/doc/nodejs
  cp -R doc/api/{*.html,assets} $pkgdir/Library/ArchMac/doc/nodejs

  # install license
  install -m755 -d $pkgdir/Library/ArchMac/share/licenses/nodejs
  install -m644 LICENSE $pkgdir/Library/ArchMac/share/licenses/nodejs/LICENSE

  # workaround for missing --mandir
  mv $pkgdir/Library/ArchMac/share/man $pkgdir/Library/ArchMac/man
}

