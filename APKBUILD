pkgname=firmware-xiaomi-rosy
pkgver=1
pkgrel=0
_commit="1868de4c9469fdf3c031553233bc1cccdda9b1df"
pkgdesc="Firmware files for Xiaomi Redmi 5"
url="https://postmarketos.org"
arch="aarch64"
license="proprietary"
depends="wcnss-wlan adsp-audio"
source="rosy-fw-$_commit.tar.gz::https://github.com/hiprivsid/postmarketos-vendor-xiaomi-rosy/archive/$_commit.tar.gz"
options="!strip !check !archcheck !spdx !tracedeps pmb:cross-native"

_fwdir="/lib/firmware/postmarketos"

package() {
	cd "$srcdir/postmarketos-vendor-xiaomi-rosy-$_commit"

	# ADSP firmware
	install -Dm0644 adsp/adsp.* -t "$pkgdir/$_fwdir"

	# Fingerprint firmware
	install -Dm0644 fingerprint/goodix_firmware.bin -t "$pkgdir/$_fwdir"

	# GPU and video acceleration firmwares
	install -Dm0644 gpu/a530* -t "$pkgdir/$_fwdir/../qcom"
	install -Dm0644 gpu/a506_zap.* -t "$pkgdir/$_fwdir"
        install -Dm0644 venus/venus.* -t "$pkgdir/$_fwdir"

	# Modem firmware
	install -Dm0644 modem/mba.mbn -t "$pkgdir/$_fwdir"
	install -Dm0644 modem/modem.* -t "$pkgdir/$_fwdir"

	# Wifi/BT firmware
	install -Dm0644 wcnss/wcnss.* -t "$pkgdir/$_fwdir"
}

sha512sums=""
