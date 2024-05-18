# Maintainer: Oleksandr Natalenko <oleksandr@natalenko.name>

pkgname=7-zip
pkgver=24.05
pkgrel=1
pkgdesc="File archiver with a high compression ratio"
url=https://7-zip.org
license=(BSD-2-Clause BSD-3-Clause LGPL-2.1-or-later LicenseRef-unRAR)
arch=(x86_64)
makedepends=(uasm meson)
source=(${url}/a/7z2405-src.tar.xz
		meson.build)
sha256sums=('63f341cf80b8d287c6e945519b3da0fa75553c85572a471b7fa6e68f9a90b790'
            'd1a583e7252f1e4d61c6f1cacd920dd4d74918744d0ad048a5281cc2228edcef')

build() {
	arch-meson . build

	meson compile -C build
}

package() {
	meson install -C build --destdir "${pkgdir}"
}

