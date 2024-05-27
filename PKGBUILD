# Maintainer: Oleksandr Natalenko <oleksandr@natalenko.name>

pkgname=7-zip
pkgver=24.06
pkgrel=1
pkgdesc="File archiver with a high compression ratio"
url=https://7-zip.org
license=(BSD-2-Clause BSD-3-Clause LGPL-2.1-or-later LicenseRef-LGPL-2.1-or-later-with-unRAR-restriction LicenseRef-unRAR)
arch=(x86_64)
depends=(gcc-libs glibc)
makedepends=(meson uasm)
# Alternative sources:
# * https://7-zip.org/a/7z2406-src.tar.xz
# * https://downloads.sourceforge.net/project/sevenzip/7-Zip/24.06/7z2406-src.tar.xz
source=(https://github.com/ip7z/7zip/releases/download/24.06/7z2406-src.tar.xz
		meson.build
		BSD-2-Clause.txt
		BSD-3-Clause.txt)
sha256sums=('2aa1660c773525b2ed84d6cd7ff0680c786ec0893b87e4db44654dcb7f5ac8b5'
            '657f3c6b825b55c8f308e32ca8fe632bdef0176eab3e5bd65c77d02bc7b94161'
            '017b5ee48f680e82cba79141c7895a1f02b856df2512225f5c427fe36765ef0b'
            '3cf06aba3588c41c514f6946bb2d757b413ff6491647d474800f55edca75dcb4')

build() {
	arch-meson . build

	meson compile -C build
}

package() {
	meson install -C build --destdir "${pkgdir}"
}
