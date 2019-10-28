# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-audioencoder-flac
epoch=1
pkgver=2.0.3
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
sha512sums=('036c4368b09e540f67ad7654ec567d22fd52dcc8690bc22717de33180e6f8c03b0f6a1ecb8bd7a63dd99e65fa4318ef0f256b503fcb295ec0fb03ff38aee0322')

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

