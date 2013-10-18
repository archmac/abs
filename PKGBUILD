
pkgname=s3cmd
pkgver=1.0.1
pkgrel=1
pkgdesc="command line tool for uploading, retrieving, managing data in Amazon S3"
arch=('i386' 'x86_64')
url="http://s3tools.org/s3cmd"
license=('GPL')
depends=('python')
source=(http://downloads.sourceforge.net/project/s3tools/$pkgname/$pkgver/$pkgname-$pkgver.tar.gz)
md5sums=('dc62becc03a3e6100843611ebe2707c2')

build() {
    cd $srcdir/$pkgname-$pkgver
    python setup.py build
}

package() {
    cd $srcdir/$pkgname-$pkgver
    python setup.py install --root=$pkgdir --prefix=/Library/ArchMac
}
