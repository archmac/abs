
pkgname=virtualenv
pkgver=1.4.8
pkgrel=1
pkgdesc="Virtual Python Environment builder"
arch=('i386')
url="http://pypi.python.org/pypi/virtualenv"
license=('MIT')
depends=('python')
source=("http://pypi.python.org/packages/source/v/$pkgname/$pkgname-$pkgver.tar.gz")
md5sums=('74ded4025a56e538c1c8df6b9825a8b8')

build() {
    cd "$srcdir/$pkgname-$pkgver"
    python setup.py build
}

package() {
    cd "$srcdir/$pkgname-$pkgver"
    python setup.py install --root=$pkgdir --prefix=/Library/ArchMac
    # install -D -m644 "$srcdir/$pkgname-$pkgver/docs/license.txt" \
    #    "$pkgdir/usr/share/licenses/virtualenv/license.txt"
}
