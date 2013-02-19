
pkgname=nu
pkgver=2
pkgrel=3
pkgdesc='Nu'
arch=('i386' 'x86_64')
license=('Apache')
url='http://programming.nu'
source=(https://github.com/timburks/nu/archive/master.tar.gz)
md5sums=('4e58583c8c96b7671263fbdbd5362def')

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

    mkdir -p $pkgdir/Library/Frameworks
    ln -s ../ArchMac/frameworks/Nu.framework $pkgdir/Library/Frameworks/Nu.framework

    mkdir -p $pkgdir/Library/ArchMac/share
    cp -a share/* $pkgdir/Library/ArchMac/share
}

check() {
    cd $srcdir/nu-master
    ./mininush tools/nuke test
}
