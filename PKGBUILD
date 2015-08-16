# Maintainer: kfgz <kfgz at interia dot pl>
# Contributor: yannsen <ynnsen at gmail dot com>

pkgname=libguytools
pkgver=2.0.2
pkgrel=2
pkgdesc="A small programming toolbox."
arch=('i686' 'x86_64')
url="http://guymager.sourceforge.net/"
license=('GPL')
depends=('qt4')
source=(${pkgname}-${pkgver}.tar.gz::http://sourceforge.net/projects/${pkgname}/files/${pkgname}/LatestSource/tools-${pkgver}.tar.gz/download)
md5sums=('3ff2d362b31ce97f99d5d895ce8ca965')

build() {
  cd "${srcdir}"/tools-${pkgver}
  ./create_version_file.sh
  qmake-qt4 toolsstatic.pro
  make
  qmake-qt4 tools.pro
  make
}

package() {
  install -d "${pkgdir}"/usr/lib/
  cp -R "${srcdir}"/tools-${pkgver}/lib/ "${pkgdir}"/usr/
  install -d "${pkgdir}"/usr/include/libguytools2
  cp -R "${srcdir}"/tools-${pkgver}/include/* "${pkgdir}"/usr/include/libguytools2
}
