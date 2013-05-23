# Maintainer: Benjamin Althues <benjamin@babab.nl>

name=Gitto
pkgname=gitto-git
pkgver=20130523
pkgrel=1
pkgdesc="Keep track of your git repositories"
depends=('guile>=2.0.9')
arch=('any')
url="http://ryuslash.org/projects/gitto.html"
license=("GPL")

_gitroot=git://github.com/ryuslash/gitto.git
_gitname=master

build() {
    cd "$srcdir"

    if [ ! -d $name ]; then
        git clone $_gitroot $name;
        cd $name
    else
        cd $name
        git pull origin $_gitname
    fi

    make
}

package() {
    cd "$srcdir/$name"
    make DESTDIR="$pkgdir" install
}
