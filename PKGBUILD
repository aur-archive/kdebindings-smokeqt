# $Id: PKGBUILD 226412 2014-11-19 16:43:53Z fyan $
# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kdebindings-smokeqt
pkgver=4.14.3
pkgrel=1
pkgdesc="Language independent library for Qt bindings"
url="https://projects.kde.org/projects/kde/kdebindings/smoke/smokeqt"
arch=('i686' 'x86_64')
license=('GPL' 'LGPL' 'FDL')
groups=('kdebindings')
depends=('kdebindings-smokegen' 'qimageblitz' 'qscintilla')
makedepends=('cmake' 'automoc4' 'mesa')
conflicts=('kdebindings-smoke')
source=("http://download.kde.org/stable/${pkgver}/src/smokeqt-${pkgver}.tar.xz")
sha1sums=('f4a1379b255e7506b154d5b5f9c451a1ba26084b')

prepare() {
  mkdir build
}

build() {
  cd build
  cmake ../smokeqt-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DKDE4_BUILD_TESTS=OFF \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DWITH_Qwt5=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
