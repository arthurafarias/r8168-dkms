# Maintainer: arthur <arthur at afarias . org>
_pkgbase=r8168
pkgname=r8168-dkms
pkgver=8.055.00
pkgrel=1
pkgdesc="Kernel module for Realtek RTL8168"
arch=('x86_64')
url='https://www.realtek.com/Download/List?cate_id=584'
license=('GPL2')
depends=('dkms')
optdepends=('linux-headers: Build the module for Arch kernel'
            'linux-lts-headers: Build the module for LTS Arch kernel')
conflicts=("${_pkgbase}")
source=("https://github.com/arthurafarias/${_pkgbase}/archive/refs/tags/${pkgver}.tar.gz"
        "dkms.conf")
sha256sums=('SKIP'
            'SKIP')
package() {
  sed -e "s/@_PKGBASE@/${_pkgbase}/" \
      -e "s/@PKGVER@/${pkgver}/" \
      -i dkms.conf

  install -d "${pkgdir}"/usr/src/${_pkgbase}-${pkgver}/
  install -Dm644 dkms.conf "${_pkgbase}-${pkgver}"/src/* "${pkgdir}/usr/src/${_pkgbase}-${pkgver}/"
}
