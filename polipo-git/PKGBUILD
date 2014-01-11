
pkgname=polipo-git
pkgver=20130401
pkgrel=2
pkgdesc="A caching web proxy"
arch=('i386' 'x86_64')
url="http://www.pps.jussieu.fr/~jch/software/polipo/"
license=('custom')
provides=('polipo')
conflicts=('polipo' 'polipo-darcs')
md5sums=()
_gitroot=https://github.com/jech/polipo.git
_gitname="$pkgname"

build() {
    cd "$srcdir"
    msg "Connecting to GIT server...."

    if [[ -d "$_gitname" ]]; then
        cd "$_gitname" && git pull origin
        msg "The local files are updated."
    else
        git clone "$_gitroot" "$_gitname"
    fi

    msg "GIT checkout done or server timeout"
    msg "Starting build..."

    rm -rf "$srcdir/$_gitname-build"
    git clone "$srcdir/$_gitname" "$srcdir/$_gitname-build"
    cd "$srcdir/$_gitname-build"

    make PREFIX="$pkgdir/Library/ArchMac" \
         MANDIR="$pkgdir/Library/ArchMac/share/man" \
         INFODIR="$pkgdir/Library/ArchMac/share/info" \
         LOCAL_ROOT="$pkgdir/Library/ArchMac/share/polipo/www" \
         DISK_CACHE_ROOT="$pkgdir/Library/ArchMac/var/cache/polipo" \
         all
}

package() {
    cd "$srcdir/$_gitname-build"
    make PREFIX="$pkgdir/Library/ArchMac" \
         MANDIR="$pkgdir/Library/ArchMac/share/man" \
         INFODIR="$pkgdir/Library/ArchMac/share/info" \
         LOCAL_ROOT="$pkgdir/Library/ArchMac/share/polipo/www" \
         DISK_CACHE_ROOT="$pkgdir/Library/ArchMac/var/cache/polipo" \
         install

    # install config files
    mkdir -p -m755 $pkgdir/Library/ArchMac/etc/polipo
    install -m644 config.sample forbidden.sample $pkgdir/Library/ArchMac/etc/polipo

    # install license
    mkdir -p -m755 $pkgdir/Library/ArchMac/usr/share/licenses/polipo/
    install -m644 COPYING $pkgdir/Library/ArchMac/usr/share/licenses/polipo/LICENSE
}

