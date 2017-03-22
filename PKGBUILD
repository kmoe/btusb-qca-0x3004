# Maintainer: Katy Moe katy@katy.moe

pkgname=btusb-dkms
pkgver=0.8
pkgrel=1
pkgdesc="patch btusb so it works on QCA devices with id 0x3004"
arch=('i686' 'x86_64')
license=('GPL')
depends=('dkms')
source=("dkms.conf"
        "patches/btusb.patch")

package() {
	install -Dm644 dkms.conf "${pkgdir}"/usr/src/${_pkgbase}-${pkgver}/dkms.conf
	install -Dm644 patches/btusb.patch "${pkgdir}"/usr/src/${_pkgbase}-${pkgver}/patches/btusb.patch
}
