
pkgname=gnupg
pkgver=1.4.12
pkgrel=1
pkgdesc="The OpenPGP part of the GNU Privacy Guard (GnuPG)"
arch=('i386' 'x86_64')
license=('GPL3')
depends=('zlib' 'bzip2' 'libedit' 'curl')
source=(ftp://ftp.gnupg.org/gcrypt/gnupg/gnupg-$pkgver.tar.bz2)
url="http://www.gnupg.org/"
md5sums=('ce3742e5c7912559cab7894ad8ba7f6b')

build() {
	cd ${srcdir}/${pkgname}-${pkgver}
	./configure --prefix=/Library/ArchMac
	make || return 1
}

package() {
	cd ${srcdir}/${pkgname}-${pkgver}
	make DESTDIR=${pkgdir} install || return 1

	# remove gettext alias file because it interferes with
	# other packages
	rm ${pkgdir}/Library/ArchMac/lib/charset.alias
}

