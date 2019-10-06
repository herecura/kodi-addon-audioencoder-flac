# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-audioencoder-flac
epoch=1
pkgver=2.0.2
_codename=Leia
pkgrel=1
pkgdesc="FLAC Audio Encoder add-on for Kodi"
arch=('x86_64')
url='https://github.com/xbmc/audioencoder.flac'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-audioencoder')
provides=('kodi-audioencoder-flac')
replaces=('kodi-audioencoder-flac')
depends=('kodi')
makedepends=('cmake' 'kodi-dev')
source=("$pkgname-$pkgver.tar.gz::https://github.com/xbmc/audioencoder.flac/archive/$pkgver-$_codename.tar.gz")
sha512sums=('5e5ac3e66b193727e5d2d85c5416275adda642502526bf2525864135119f831b0332a50fca9dbb0042cb0a8165fa93de12d49f1e9cd467eb3280f31e3ee99486')

build() {
    cd "audioencoder.flac-$pkgver-$_codename"
    cmake \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_SHARED_LIBS=1 \
        -DUSE_LTO=1 \
        .
    make
}

package() {
	cd "audioencoder.flac-$pkgver-$_codename"
	make DESTDIR="$pkgdir/" install
}

