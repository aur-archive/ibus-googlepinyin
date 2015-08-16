# Author: Jiahua Huang <jhuangjiahua@gmail.com>
# Maintainer: Yangtse <yangtsesu@gmail.com> 

pkgname=ibus-googlepinyin
pkgver=0.1.2
pkgrel=2
pkgdesc="IBus Wrapper for libgooglepinyin"
arch=('any')
url="http://code.google.com/p/libgooglepinyin"
license=('APACHE')
optdepends=(
    'opencc: for simplified chinese translation to tranditional chinese'
)
depends=('libgooglepinyin' 'ibus')
makedepends=('cmake')
conflicts=('ibus-googlepinyin-hg')
source=(http://libgooglepinyin.googlecode.com/files/${pkgname}-${pkgver}.tar.bz2)

build(){
  cd "${srcdir}"

  msg "Starting make..."

  rm -rf "${srcdir}/build"
  cp -rf "${srcdir}/${pkgname}" "$srcdir/build"
  cd "$srcdir/build"

  find . -type f -name '*.py' | xargs sed -i 's|/usr/bin/python|/usr/bin/python2|g'
  cmake -DCMAKE_INSTALL_PREFIX=/usr .
  make DESTDIR=${pkgdir} install
}

md5sums=('f9af459849c29934e8d59fc7f23a9318')
