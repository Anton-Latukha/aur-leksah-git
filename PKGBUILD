# Maintainer : Anton  Latukha <Anton.Latukha@aur.archlinux.org>
# Contributor: Damien Flament <damien.flament___at___gmx___dot___com>
# Contributor: Martin Harvan  <martinhrvn___at___gmail___dot___com>
pkgname=leksah-git
pkgver=git
#r1804.d249138-1
pkgrel=1
pkgdesc="Haskell IDE written in Haskell"
arch=('i686' 'x86_64')
url="http://leksah.org"
license=('GPL2')
depends=('ghc>=7.10.3'
    'cabal-install>=1.24'
    'gobject-introspection>=1.50.0'
    'gobject-introspection-runtime>=1.50.0'
    'gtksourceview3>=3.22.2'
    'webkit2gtk>=2.14.5' )
makedepends=('git')
provides=()
conflicts=('leksah')
replaces=()
backup=()
options=('strip')
install=
changelog=()
# leksah::git+https://github.com/leksah/leksah#branch=master
source=()
noextract=()
#md5sums=('SKIP')
validpgpkeys=()

prepare() {
  git clone --recursive --branch master https://github.com/leksah/leksah "${srcdir}"'/'"${pkgname}" || git -C "${srcdir}"'/'"${pkgname}" pull
}

pkgver() {
  cd "${srcdir}"'/'"${pkgname}"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cabal update
  cabal install alex happy
  cabal install haskell-gi
  "${srcdir}"'/'"${pkgname}"/leksah.sh
}

package() {
    echo echo
}

