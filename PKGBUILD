# Contributor: portix <portix@gmx.net>
# Manteiner: botika <aritmeeul@gmail.com>

pkgname=dwb-git
_gitname=dwb
pkgver=2014.09.20.g6a0e483
pkgrel=1
pkgdesc="A webkit web browser with vi-like keyboard shortcuts, latest git-pull" 
url="http://portix.bitbucket.org/dwb"
arch=('i686' 'x86_64')
license=('GPL')
depends=('webkitgtk2' 'desktop-file-utils')
provides=(dwb)
source=("git+https://portix@bitbucket.org/portix/dwb.git")
install=dwb.install
conflicts=('dwb' 'dwb-gtk3-git' 'dwb-gtk3' 'dwb-gtk3-hg' 'dwb-hg')
makedepends=('git' 'json-c')
md5sums=('SKIP')

pkgver() {
    cd "$srcdir"/$_gitname
    git log -1 --format="%cd.g%h" --date=short | sed 's/-/./g'
}
build() {
  cd "$srcdir/$_gitname"
  make 
}
package() {
    cd "${srcdir}/${_gitname}"
    make DESTDIR="${pkgdir}" install \
        BASHCOMPLETION=/usr/share/bash-completion/completions
}
