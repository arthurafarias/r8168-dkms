# Maintainer: arthur <arthur at afarias . org>
_pkgbase=r8169
pkgname=r8169-dkms
pkgver=6.032.00
pkgrel=1
pkgdesc="Kernel module for Realtek RTL8169"
arch=('x86_64')
url='https://www.realtek.com/Download/List?cate_id=583'
license=('GPL2')
depends=('dkms')
optdepends=('linux-headers: Build the module for Arch kernel'
            'linux-lts-headers: Build the module for LTS Arch kernel')
conflicts=("${_pkgbase}")
source=("https://github.com/arthurafarias/${_pkgbase}/archive/refs/tags/${pkgver}.tar.gz"
        "dkms.conf")
sha256sums=('28175bcf143b4d0c1af7db83371372865fa72cfcb984eec0e00e5032dc1f4452'
            '936bd24befc34fd6f9d5742f301a0b87bc18340223958fbe2676fc5c061eaa81')
package() {
  sed -e "s/@_PKGBASE@/${_pkgbase}/" \
      -e "s/@PKGVER@/${pkgver}/" \
      -i dkms.conf

  install -d "${pkgdir}"/usr/src/${_pkgbase}-${pkgver}/
  install -Dm644 dkms.conf "${_pkgbase}-${pkgver}"/src/* "${pkgdir}/usr/src/${_pkgbase}-${pkgver}/"
}
