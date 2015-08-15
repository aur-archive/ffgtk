# Contributor: Bernhard Walle <bernhard.walle@gmx.de>
# Maintainer: Bjoern Franke <bjo@nord-west.org>
# AUR Category: office
pkgname=ffgtk
pkgver=0.8.5
pkgrel=5
pkgdesc="FRITZ!Box Fax-Software and Call-Monitor"
url="http://www.tabos.org/ffgtk"
license="GPL"
depends=('cups' 'libcapi20' 'spandsp' 'libao' 'libsndfile' 'speex')
makedepends=('libcapi20' 'spandsp' 'intltool' 'libao' 'libsndfile' 'speex')
conflicts=('ffgtk-svn')
arch=(i686 x86_64)
source=(http://www.tabos.org/ffgtk/download/${pkgname}-${pkgver}.tar.gz)
md5sums=('346e193e7c10024cea595e7b6579427c')
install="ffgtk.install"

build() {

  cd ${srcdir}/${pkgname}-${pkgver}
  ./autogen.sh
  export LIBS=-lgmodule-2.0;./configure --prefix=/usr --sysconfdir=/etc --with-gnome-keyring=no --with-pulseaudio=no --disable-Werror
  make
}

package() {
  cd ${srcdir}/${pkgname}-${pkgver}
  make DESTDIR=${pkgdir} install


}
