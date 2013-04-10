
pkgname=qemu
pkgver=1.2.1
pkgrel=2
pkgdesc='A generic and open source processor emulator which achieves a good emulation speed by using dynamic translation.'
arch=(i386 x86_64)
license=(GPL2 LGPL2.1)
url='http://wiki.qemu.org/Index.html'
depends=(gettext glib2)
makedepends=(pkg-config)
source=(http://wiki.qemu.org/download/$pkgname-$pkgver.tar.bz2)
options=(!strip)
md5sums=(189bc5b87281a72f8c72a0f7ebaa6d00)

build()
{
  cd $srcdir/$pkgname-$pkgver

  ./configure --prefix=/Library/ArchMac \
              --mandir=/Library/ArchMac/man \
              --audio-drv-list=coreaudio \
              --audio-card-list=ac97 \
              --enable-cocoa
  make
}

package() {
  cd $srcdir/$pkgname-$pkgver
  make DESTDIR=$pkgdir install
}

