
pkgname=nodejs
pkgver=0.10.15
pkgrel=1
pkgdesc='Evented I/O for V8 javascript'
arch=(i386 x86_64)
url='http://nodejs.org/'
license=(MIT)
options=(!emptydirs !strip)
source=("$url/dist/v${pkgver}/node-v${pkgver}.tar.gz")
md5sums=(59f295b0a30dc8dbdb46407c2d9b2923)

build() {
  cd node-v$pkgver

  ./configure \
    --prefix=/Library/ArchMac \
    --without-snapshot
#    --with-arm-float-abi=$EABI \
#    --shared-v8 \
#    --shared-v8-libpath=/usr/lib \
#    --shared-v8-includes=/usr/include 
#    --shared-openssl \

  make 
}

check() {
  cd node-v$pkgver

  make test || true
}

package() {
  cd node-v$pkgver

  make DESTDIR=$pkgdir install

  # install docs as per user request
  #install -d ${pkgdir}/usr/share/doc/nodejs
  #cp -r doc/api/{*.html,assets} \
    #${pkgdir}/usr/share/doc/nodejs

  # compress man pages
  #find "$pkgdir"/usr/lib/node_modules/npm/man -type f | xargs gzip -9

  #install -D -m644 LICENSE \
    #${pkgdir}/usr/share/licenses/nodejs/LICENSE
}

