
pkgname=chromium-bsu
pkgver=0.9.16.1
pkgrel=1
pkgdesc="A fast paced top scrolling shooter"
arch=('x86_64')
url="http://chromium-bsu.sourceforge.net/"
license=('custom:artistic')
depends=('freeglut' 'glu' 'sdl_image' 'openal' 'freealut' 'ftgl' 'fontconfig')
install=chromium-bsu.install
source=("http://downloads.sourceforge.net/project/chromium-bsu/Chromium%20B.S.U.%20source%20code/chromium-bsu-${pkgver}.tar.gz"
        "https://github.com/Gabrielgtx/chromium-bsu-pack/archive/master.zip")
md5sums=('acc28b2b46567e4a2946031005155a43'
         'SKIP')

build(){
  cd "${srcdir}/${pkgname}-${pkgver}"
  ./configure --prefix=/usr
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" install
  #add Alien Texture Pack 
  cp -R "${srcdir}"/chromium-bsu-pack-master/png "${pkgdir}"/usr/share/${pkgname}
  install -Dm644 COPYING "${pkgdir}"/usr/share/licenses/chromium-bsu/LICENSE
}
