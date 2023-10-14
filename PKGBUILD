# Maintainer: Guilherme Monteiro de Oliveira <gmonteiro.oliveira@outlook.com>
pkgname=dmenu-git
pkgver=r615.dfd2086
pkgrel=1
epoch=
pkgdesc="A build of dmenu, patched with border, center, fuzzyhighlight-caseinsensitive, fuzzymatch, grid, lineheight, numbers, xyw"
arch=('x86_64')
url="https://github.com/monteiroliveira/dmenu.git"
license=('MIT')
groups=()
depends=()
makedepends=('git')
checkdepends=()
optdepends=()
provides=('dmenu')
conflicts=('dmenu')
replaces=()
backup=()
options=()
install=
changelog=
source=("$pkgname::git+$url")
noextract=()
md5sums=('SKIP')
validpgpkeys=()

pkgver() {
    cd "$pkgname"
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd "$pkgname"
	make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
	cd "$pkgname"
	make PREFIX=/usr DESTDIR="$pkgdir" install
	install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname"
	install -Dm644 README.org "$pkgdir/usr/share/doc/$pkgname"
}
