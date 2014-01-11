
pkgname=cmake
pkgver=2.8.10.2
pkgrel=1
pkgdesc='A cross-platform open-source make system'
arch=(i386 x86_64)
license=(custom)
url="http://www.cmake.org"
depends=(curl)
source=("${url}/files/v2.8/${pkgname}-${pkgver}.tar.gz")
md5sums=('097278785da7182ec0aea8769d06860c')

build() {
    cd $srcdir/$pkgname-$pkgver

    ./bootstrap --prefix=/Library/ArchMac \
                --mandir=/man \
                --docdir=/doc/cmake \
                --system-libs

  make
}

package() {
  cd $srcdir/$pkgname-$pkgver
  make DESTDIR=$pkgdir install

  #vimpath="$pkgdir/Library/ArchMac/share/vim/vimfiles"
  #install -Dm644 Docs/cmake-indent.vim ${vimpath}/indent/cmake-indent.vim
  #install -Dm644 Docs/cmake-syntax.vim ${vimpath}/syntax/cmake-syntax.vim
  #install -Dm644 Docs/cmake-mode.el ${pkgdir}/usr/share/emacs/site-lisp/cmake-mode.el

  #install -Dm644 Copyright.txt ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
}

