# Maintainer: Katy Moe katy@katy.moe

_kernver="$(uname -r)"
_kernver_base="$(echo $_kernver | cut -d- -f1)"
pkgname=btusb-qca-0x3004
_pkgname=btusb
pkgver=0.8
pkgrel=1
pkgdesc="patch btusb so it works on QCA devices with id 0x3004"
arch=('i686' 'x86_64')
license=('GPL')
depends=('linux-headers')
source=("Makefile"
	"btusb.patch"
	"btusb-qca-0x3004.install"
	"btusb.c::https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git/plain/drivers/bluetooth/btusb.c?id=refs/tags/v4.10.4"
	"btintel.h::https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git/plain/drivers/bluetooth/btintel.h?id=refs/tags/v4.10.4"
	"btbcm.h::https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git/plain/drivers/bluetooth/btbcm.h?id=refs/tags/v4.10.4"
	"btrtl.h::https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git/plain/drivers/bluetooth/btrtl.h?id=refs/tags/v4.10.4")
md5sums=('SKIP')
install="btusb-qca-0x3004.install"
	

prepare() {
	echo $_kernver_base
	\cp --remove-destination $(readlink btusb.c) btusb.c
	patch -p1 < btusb.patch
}

build() {
	make
}

package() {
	install -Dm644 btusb.ko "$pkgdir/usr/lib/modules/$_kernver/updates/btusb.ko"
}


