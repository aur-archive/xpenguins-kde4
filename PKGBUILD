# Maintainer: Jan <jan@next-game.de>

pkgname=xpenguins-kde4
pkgver=20121230
pkgrel=1
pkgdesc="xpenguins with KDE4 Support"
depends=('imlib')
provides=('xpenguins')
conflicts=('xpenguins')
source=()
license=('GPL2')
arch=('i686' 'x86_64')
url="http://gitorious.org/~amalon/xpenguins/amalons-xpenguins"
md5sums=()

_gitroot='git://gitorious.org/~amalon/xpenguins'
_gitname='xpenguins'

build() {
  msg "Connecting to gitorious.org GIT server...."

  if [ -d $_gitname ]; then
    cd $_gitname && time git pull --depth 1 origin
    msg "The local files are updated."
  else
    git clone --depth 1 $_gitroot
  fi
  msg "GIT checkout done. Preparing sources..."

cd $startdir/src/xpenguins
autoreconf
./configure --prefix=/usr
make || return 1
make prefix=$startdir/pkg/usr install
}
