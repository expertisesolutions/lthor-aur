# Maintainer: Felipe Magno de Almeida <felipe.m.almeida__at__gmail.com>

pkgbase=lthor
pkgname=lthor
pkgver=20160615
pkgrel=1
pkgdesc="Firmware uploader for Tizen Development devices"
arch=('i686' 'x86_64')
license=('GPL')
makedepends=('cmake')
source=('git://git.tizen.org/tools/lthor.git' 'udev-rules.patch')
sha256sums=('SKIP' 'b5b977266a61d5c38840ea534e2b91deb4a8ce10e72b86912e6fb2f82391ea2b')

build() {
  cd $srcdir/lthor
  patch -p1 -i $srcdir/udev-rules.patch
  cmake -DCMAKE_INSTALL_PREFIX:PATH=/usr .
  make ${MAKEFLAGS}
}

package() {
  cd $srcdir/lthor
  DESTDIR=$pkgdir make install
#  install -m644 -D LICENSE $pkgdir/usr/share/licenses/$pkgname/LICENSE
}
