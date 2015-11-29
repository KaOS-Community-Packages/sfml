pkgname=sfml
_pkgname=SFML
pkgver=2.3.2
pkgrel=1
pkgdesc="Simple and Fast Multimedia Library"
url="https://github.com/SFML/SFML"
arch=('x86_64')
license=('zlib')
depends=('libsndfile' 'libxrandr' 'libjpeg' 'openal' 'glew' 'freetype2')
makedepends=('mesa' 'cmake')
source=("https://github.com/SFML/SFML/archive/${pkgver}.tar.gz")
md5sums=('22d11f8e7e0cbf96d792400b0dcd2391')

build() {
  cd ${srcdir}/${_pkgname}-${pkgver}

  mkdir build && cd build
  cmake .. \
      -DCMAKE_INSTALL_PREFIX=/usr \
      -DSFML_BUILD_EXAMPLES=0 \
      -DSFML_INSTALL_PKGCONFIG_FILES=1
  make
}

package() {
  cd ${srcdir}/${_pkgname}-${pkgver}/build
  make DESTDIR=${pkgdir} install

}
