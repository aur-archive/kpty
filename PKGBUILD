# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kpty
pkgver=4.99.0
pkgrel=1
pkgdesc='KPty'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/kpty'
license=('LGPL')
depends=('kcoreaddons' 'ki18n' 'libutempter')
makedepends=('extra-cmake-modules')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('bdcbe32badc7d83ff882db9fad8ed577')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
