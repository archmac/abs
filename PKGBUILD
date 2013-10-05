
pkgname=glib2
pkgver=2.34.3
pkgrel=3
pkgdesc="Common C routines used by GTK+ and other libs"
url="http://www.gtk.org/"
arch=(i386 x86_64)
license=(LGPL)
depends=(pcre libffi)
makedepends=(pkg-config xz)
options=(!libtool !docs)
source=(http://ftp.gnome.org/pub/GNOME/sources/glib/${pkgver%.*}/glib-$pkgver.tar.xz)
sha256sums=(855fcbf87cb93065b488358e351774d8a39177281023bae58c286f41612658a7)

build() {
    cd $srcdir/glib-$pkgver
    ./configure --prefix=/Library/ArchMac \
        --with-pcre=system \
        --disable-fam
  make
}

package() {
    cd $srcdir/glib-$pkgver
    make DESTDIR=$pkgdir install
    mv $pkgdir/Library/ArchMac/share/bash-completion/completions/* \
        $pkgdir/Library/ArchMac/share/bash-completion
}

