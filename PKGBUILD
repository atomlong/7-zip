# Maintainer: Oleksandr Natalenko <oleksandr@natalenko.name>

pkgname=7-zip
pkgver=24.06
pkgrel=4
pkgdesc="File archiver with a high compression ratio"
url=https://7-zip.org
license=(BSD-2-Clause BSD-3-Clause LGPL-2.1-or-later LicenseRef-LGPL-2.1-or-later-with-unRAR-restriction LicenseRef-unRAR)
arch=(x86_64)
depends=(gcc-libs glibc)
makedepends=(meson uasm)
# Alternative sources:
# * https://7-zip.org/a/7z${pkgver//\./}-src.tar.xz
# * https://downloads.sourceforge.net/project/sevenzip/7-Zip/${pkgver}/7z${pkgver//\./}-src.tar.xz
source=(https://github.com/ip7z/7zip/releases/download/${pkgver}/7z${pkgver//\./}-src.tar.xz
		meson.build.template
		BSD-2-Clause.txt
		BSD-3-Clause.txt)
sha256sums=('2aa1660c773525b2ed84d6cd7ff0680c786ec0893b87e4db44654dcb7f5ac8b5'
            '73c785bcdb161296048ec56e0ba2f28b6052890eea01405b6a1e837782d28d65'
            '017b5ee48f680e82cba79141c7895a1f02b856df2512225f5c427fe36765ef0b'
            '3cf06aba3588c41c514f6946bb2d757b413ff6491647d474800f55edca75dcb4')

prepare() {
	cp meson.build.template meson.build

	meson rewrite kwargs set project / version ${pkgver}
}

build() {
	arch-meson . build

	meson compile -C build
}

package() {
	meson install -C build --destdir "${pkgdir}"
}
