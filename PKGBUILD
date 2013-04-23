
pkgname=nu
pkgver=2
pkgrel=5
pkgdesc='Nu'
arch=('i386' 'x86_64')
license=('Apache')
url='http://programming.nu'
install=nu.install
source=(https://github.com/timburks/nu/archive/master.tar.gz)
md5sums=('18c3c4082d88d727c3d05d95194b5f56')

build() {
    cd $srcdir/nu-master
    make
    ./mininush tools/nuke
}

package() {
    cd $srcdir/nu-master
    
    mkdir -p $pkgdir/Library/ArchMac/bin
    cp -a nush tools/* $pkgdir/Library/ArchMac/bin
    chmod 755 $pkgdir/Library/ArchMac/bin/*

    mkdir -p $pkgdir/Library/ArchMac/frameworks
    cp -a Nu.framework $pkgdir/Library/ArchMac/frameworks

    mkdir -p $pkgdir/Library/ArchMac/share
    cp -a share/* $pkgdir/Library/ArchMac/share
}

check() {
    cd $srcdir/nu-master
    ./mininush tools/nuke test
}
