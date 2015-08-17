# Maintainer: Gavin Lloyd <gavinhungry@gmail.com>
# Contributor: xav <xav at ethertricks dot net>
# Contributor: julian <pidanc_j at epita dot fr>

pkgname=openssl_tpm_engine
pkgver=0.4.2
pkgrel=3
pkgdesc="OpenSSL engine which interfaces with the TSS API"
arch=('i686' 'x86_64')
url="http://sourceforge.net/projects/trousers"
license=('GPL')
depends=('openssl' 'trousers')
source=(http://downloads.sourceforge.net/sourceforge/trousers/${pkgname}-${pkgver}.tar.gz)
md5sums=('5bc8d66399e517dde25ff55ce4c6560f')


build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  ./configure --prefix=/usr --with-openssl=/usr
  make
}

package() {
  cd ${srcdir}/${pkgname}-${pkgver}
  make DESTDIR=${pkgdir} install
  mv ${pkgdir}/usr/lib/openssl/engines/ ${pkgdir}/usr/lib/engines/
  rm -rf ${pkgdir}/usr/lib/openssl
}
