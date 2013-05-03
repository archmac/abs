
pkgname=nu-git
pkgver=20130422
pkgrel=1
pkgdesc='A lisp for the Objective-C runtime'
arch=(i386 x86_64)
license=(Apache)
url='http://programming.nu'
provides=(nu)
conflicts=(nu)
install=$pkgname.install
md5sums=()
_gitroot=https://github.com/timburks/nu.git
_gitname="$pkgname"

build() {
    cd $srcdir
    msg "Connecting to GIT server...."

    if [[ -d $_gitname ]]; then
        cd $_gitname && git pull origin
        msg "The local files are updated."
    else
        git clone $_gitroot $_gitname
    fi

    msg "GIT checkout done or server timeout"
    msg "Starting build..."

    rm -rf $srcdir/$_gitname-build
    git clone $srcdir/$_gitname $srcdir/$_gitname-build
    cd $srcdir/$_gitname-build

    make
    ./mininush tools/nuke
}

package() {
    cd $srcdir/$_gitname-build

    mkdir -p $pkgdir/Library/ArchMac/bin
    cp -a nush tools/* $pkgdir/Library/ArchMac/bin
    chmod 755 $pkgdir/Library/ArchMac/bin/*

    mkdir -p $pkgdir/Library/ArchMac/frameworks
    cp -a Nu.framework $pkgdir/Library/ArchMac/frameworks

    mkdir -p $pkgdir/Library/ArchMac/share
    cp -a share/nu $pkgdir/Library/ArchMac/share
}

check() {
    cd $srcdir/$_gitname-build
    ./mininush tools/nuke test
}

