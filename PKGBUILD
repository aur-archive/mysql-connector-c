# Maintainer: David C Rankin <drankinatty at gmail dot com>
# Contributor: Andrea Scarpino <andrea@archlinux.org>
# Contributor: Arjan Gelderblom <arjan.gelderblom@game-creators.nl>
# Contributor: Lars Hupel <hupel@in.tum.de>

pkgname=mysql-connector-c
pkgver=6.1.5
pkgrel=1
pkgdesc="A MySQL database (mariadb) connector for C"
arch=('i686' 'x86_64')
url="http://dev.mysql.com/doc/refman/5.5/en/connector-c.html"
license=('GPL')
depends=('libmariadbclient' 'boost-libs')
makedepends=('cmake' 'boost')

source=(.AURINFO "http://ftp.gwdg.de/pub/misc/mysql/Downloads/Connector-C/${pkgname}-${pkgver}-src.tar.gz")
md5sums=(SKIP '50837220daf43a60890b0af6bfdf5a54')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}-src"
  cmake . -DCMAKE_INSTALL_PREFIX=/usr \
    -DCMAKE_BUILD_TYPE=Release \
    -DMYSQLCPPCONN_BUILD_EXAMPLES=OFF
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}-src"
  make DESTDIR="${pkgdir}" install

}
