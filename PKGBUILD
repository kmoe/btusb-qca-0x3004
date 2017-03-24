# Maintainer: Katy Moe katy@katy.moe

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
	"btusb.c::https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git/plain/drivers/bluetooth/btusb.c?id=refs/tags/v4.10.4"
	"btintel.h::https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git/plain/drivers/bluetooth/btintel.h?id=refs/tags/v4.10.4"
	"btbcm.h::https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git/plain/drivers/bluetooth/btbcm.h?id=refs/tags/v4.10.4"
	"btrtl.h::https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git/plain/drivers/bluetooth/btrtl.h?id=refs/tags/v4.10.4")
md5sums=('SKIP')
	
_kernver="$(uname -r)"

prepare() {
	echo "preparing"
	\cp --remove-destination $(readlink btusb.c) btusb.c
	patch -p1 < btusb.patch
}

build() {
	make
}

package() {
	#gzip -9 btusb.ko
	#install -Dm644 btusb.ko.gz "$pkgdir/lib/modules/$_kernver/kernel/drivers/bluetooth/btusb.ko.gz"
}

