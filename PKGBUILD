# Maintainer: archtux <antonio dot arias99999 at gmail dot com>

pkgname=groovewalrus
pkgver=0.382
pkgrel=3
pkgdesc="Music Player with GrooveShark and Last.fm support"
arch=('any')
url="http://groove-walrus.turnip-town.net"
license=('GPL2')
depends=('mplayer' 'python2-pymedia' 'wxpython2.8')
conflicts=('groovewalrus-svn')
source=(http://turnip-town.googlecode.com/files/${pkgname}-${pkgver}_all.deb)
md5sums=('f2a1897d8f5839926033079dd39adf3f')

package() {

   # Extract .deb package
   bsdtar xf $pkgname*
   bsdtar xf data.tar.gz -C $pkgdir

   # Make Groovewalrus work with wxpython2.8
   cd $pkgdir
   find . -iname '*.py' -exec sed -i -e "s|^import wx|import wxversion\nwxversion.select('2.8')\nimport wx|" '{}' +

   # Python2 fix
   cd ./usr
   sed -i 's_python_python2_' bin/groovewalrus share/applications/groovewalrus.desktop
}