# Maintainer: Christopher Reimer <c.reimer1993@gmail.com>

pkgname=spotify-client
pkgver=0.8.4.103
_revision=.g9cb177b.260-1
pkgrel=3
pkgdesc="Spotify desktop client"
arch=('x86_64' 'i686')
url="http://www.spotify.com"
license=('custom')
depends=('nss' 'gtk2' 'libxss' 'openssl' 'qtwebkit' 'gconf' 'libpng12')
conflicts=('spotify-beta' 'spotify')
install='spotify-client.install'
if [ "${CARCH}" = "x86_64" ]; then
  md5sums=('d85ef9a3e612510b8565834df66eb47e'
           '34aff4d3b03f2c7e413670e02c57b2d8')
  _carch=amd64
elif [ "${CARCH}" = "i686" ]; then
  md5sums=('0d87b47e356b308b56399ceabe8bd6c8'
           '34aff4d3b03f2c7e413670e02c57b2d8')
  _carch=i386
fi
source=("http://repository.spotify.com/pool/non-free/s/spotify/${pkgname}_${pkgver}${_revision}_${_carch}.deb"
        'spotify-bin')

package() {
  cd $srcdir

  tar -xf data.tar.gz -C "${pkgdir}"

  install -Dm775 spotify-bin "${pkgdir}/usr/bin/spotify"

  mkdir -p $pkgdir/usr/share/licenses/$pkgname
  mv $pkgdir/usr/share/doc/$pkgname/copyright \
    "${pkgdir}/usr/share/licenses/${pkgname}"
}

