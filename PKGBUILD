
pkgname=lua
pkgver=5.1.4
pkgrel=1
pkgdesc="A powerful light-weight programming language designed for extending applications." 
arch=('i386')
license=(MIT)
url="http://www.lua.org/"
depends=('libedit')
source=("$url/ftp/$pkgname-$pkgver.tar.gz")
md5sums=('d0870f2de55d59c1c8419f36e8fac150')

build() { 
    cd $startdir/src/$pkgname-$pkgver 
    make macosx
}

package() {
    cd $startdir/src/$pkgname-$pkgver
    make INSTALL_TOP=$pkgdir/Library/ArchMac install
#   install -m 644 etc/lua.pc $startdir/pkg/opt/arch/lib/pkgconfig/lua.pc
#   install -D -m644 COPYRIGHT $pkgdir/Library/ArchMac/share/licenses/$pkgname/COPYRIGHT
}
