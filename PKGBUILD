# $Id$
# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-audioencoder-flac
_commit=71e5204
pkgver=20170517.71e5204
pkgrel=1
pkgdesc="FLAC Audio Encoder add-on for Kodi"
arch=('i686' 'x86_64')
url='https://github.com/xbmc/audioencoder.flac'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-audioencoder')
provides=('kodi-audioencoder-flac')
replaces=('kodi-audioencoder-flac')
depends=('kodi')
makedepends=('git' 'cmake' 'kodi-dev')
source=("$pkgname::git://github.com/xbmc/audioencoder.flac.git#commit=$_commit")
sha256sums=('SKIP')

pkgver() {
	cd "$pkgname"
	git log -1 --date=short --format="%cd.%h" | tr -d '-'
}

build() {
	cd "$pkgname"
	cmake \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_BUILD_TYPE=Release \
		-DBUILD_SHARED_LIBS=1 \
		-DUSE_LTO=1
	make
}

package() {
	cd "$pkgname"
	make DESTDIR="$pkgdir/" install
}

