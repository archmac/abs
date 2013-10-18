
pkgname=rbenv
pkgver=0.4.0
pkgrel=2
pkgdesc="Simple Ruby version manager"
arch=(any)
url="https://github.com/sstephenson/rbenv"
license=(MIT)
optdepends=(ruby-build)
source=("$pkgname-$pkgver.tgz::https://github.com/sstephenson/rbenv/tarball/v${pkgver}")
md5sums=('c1cf110b256cdab1c44e41020b57b489')

build() {
    cd $srcdir
    tar -x --strip-components 1 -zf "v$pkgver"
}

package() {
  cd $srcdir

  mkdir -p $pkgdir/Library/ArchMac/{bin,doc/$pkgname,libexec/$pkgname,share/bash-completion}

  install -m 644 ./README.md $pkgdir/Library/ArchMac/doc/$pkgname
  install -m 644 ./completions/rbenv.bash $pkgdir/Library/ArchMac/share/bash-completion/rbenv
  install -m 755 ./libexec/* $pkgdir/Library/ArchMac/libexec/rbenv

  ln -s /Library/ArchMac/libexec/rbenv/rbenv $pkgdir/Library/ArchMac/bin
}

