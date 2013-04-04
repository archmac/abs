
pkgname=qemu
pkgver=1.2.1
pkgrel=1
pkgdesc="A generic and open source processor emulator which achieves a good emulation speed by using dynamic translation."
arch=('i686' 'x86_64')
license=('GPL2' 'LGPL2.1')
url="http://wiki.qemu.org/Index.html"
makedepends=('pkg-config')
source=(http://wiki.qemu.org/download/${pkgname}-${pkgver}.tar.bz2)
options=(!strip !libtool)
md5sums=('189bc5b87281a72f8c72a0f7ebaa6d00')

build()
{
  cd $srcdir/$pkgname-$pkgver

  ./configure --prefix=/Library/ArchMac \
              --audio-drv-list=coreaudio \
              --audio-card-list=ac97 \
              --enable-cocoa
  make
}

package() {
  cd $srcdir/$pkgname-$pkgver
  make DESTDIR=$pkgdir install
}

