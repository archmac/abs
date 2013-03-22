
pkgname=bitlbee
pkgver=3.2
pkgrel=4
pkgdesc='Brings instant messaging (XMPP, MSN, Yahoo!, AIM, ICQ, Twitter) to IRC'
url='http://www.bitlbee.org/'
license=('GPL')
arch=('i386' 'x86_64')
depends=('openssl' 'glib2')
source=("http://get.bitlbee.org/src/${pkgname}-${pkgver}.tar.gz")
sha1sums=('21e17f082c776566429603b1e8c966983a75ac9e')

build() {
    cd $srcdir/$pkgname-$pkgver

    ./configure \
        --prefix=/Library/ArchMac \
        --etcdir=/Library/ArchMac/etc/bitlbee \
        --sbindir=/Library/ArchMac/bin \
        --ssl=openssl \
        --strip=0

    make
}

package() {
    cd $srcdir/$pkgname-$pkgver
    make DESTDIR=$pkgdir install{,-etc,-dev}
    install -d -m700 $pkgdir/var/lib/bitlbee
}

