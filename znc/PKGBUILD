
pkgname=znc
pkgver=1.0
pkgrel=1
pkgdesc='An IRC bouncer with modules & scripts support'
url='http://znc.in/'
license=('GPL2')
arch=('i386' 'x86_64')
#makedepends=('swig' 'tcl' 'python' 'perl' 'cyrus-sasl')
optdepends=('tcl: modtcl module'
            'python: modpython module'
            'perl: modperl module'
            'cyrus-sasl: saslauth module')
options=(!libtool)
source=(http://znc.in/releases/znc-$pkgver.tar.gz)
md5sums=('23807ca830c27392cccb6774f542df6e')

build() {
    cd $srcdir/$pkgname-$pkgver
    #./autogen.sh
    ./configure --prefix=/Library/ArchMac
        #--enable-cyrus \
        #--enable-tcl \
        #--enable-perl \
        #--enable-python
    make
}

package() {
    cd $srcdir/$pkgname-$pkgver
    make DESTDIR=$pkgdir install
}

