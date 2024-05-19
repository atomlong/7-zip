# Maintainer: Oleksandr Natalenko <oleksandr@natalenko.name>

pkgname=7-zip
pkgver=24.05
pkgrel=2
pkgdesc="File archiver with a high compression ratio"
url=https://7-zip.org
license=(BSD-2-Clause BSD-3-Clause LGPL-2.1-or-later LicenseRef-LGPL-2.1-or-later-with-unRAR-restriction LicenseRef-unRAR)
arch=(x86_64)
makedepends=(uasm meson)
# Alternative sources:
# * https://7-zip.org/a/7z2405-src.tar.xz
# * https://downloads.sourceforge.net/project/sevenzip/7-Zip/24.05/7z2405-src.tar.xz
source=(https://github.com/ip7z/7zip/releases/download/24.05/7z2405-src.tar.xz
		meson.build
		BSD-2-Clause.txt
		BSD-3-Clause.txt)
sha256sums=('63f341cf80b8d287c6e945519b3da0fa75553c85572a471b7fa6e68f9a90b790'
            'f9d1535f7c7fa22be0daa6dd7ce0de5e148a37578120e56cfbb6dfe7158c34d5'
            '017b5ee48f680e82cba79141c7895a1f02b856df2512225f5c427fe36765ef0b'
            '3cf06aba3588c41c514f6946bb2d757b413ff6491647d474800f55edca75dcb4')

build() {
	arch-meson . build

	meson compile -C build
}

package() {
	meson install -C build --destdir "${pkgdir}"
}

