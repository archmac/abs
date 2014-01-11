
pkgname=glib2
pkgver=2.38.0
pkgrel=1
pkgdesc="Common C routines used by GTK+ and other libs"
url="http://www.gtk.org/"
arch=(i386 x86_64)
license=(LGPL)
depends=(pcre libffi gettext)
makedepends=(pkg-config xz)
options=(!libtool !docs)
source=(http://ftp.gnome.org/pub/GNOME/sources/glib/${pkgver%.*}/glib-$pkgver.tar.xz)
md5sums=(c50d2805a76763e9b4cc4385d4ea215d)

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

