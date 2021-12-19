# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Your Name <youremail@domain.com>
pkgname=dwm-spikeyamk
pkgver=6.2
pkgrel=1
pkgdesc="Suckless' Dynamic Window Manager customized by spikeyamk"
arch=(x86_64)
url="https://www.github.com/spikeyamk/dwm-spikeyamk.git"
license=('MIT')
groups=()
depends=('libx11' 'libxinerama' 'libxft' 'freetype2' 'st' 'dmenu' 'ttf-hack' 'ttf-joypixels' 'rofi')
makedepends=()
checkdepends=()
optdepends=()
provides=(dwm-spikeyamk)
conflicts=(dwm)
replaces=(dwm)
backup=()
options=()
install=
changelog=
source=("git+$url")
noextract=()
md5sums=('SKIP')
validpgpkeys=()

build() {
	cd "$pkgname"
	make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11 FREETYPEINC=/usr/include/freetype2
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  install -Dm644 README "$pkgdir/usr/share/doc/$pkgname/README"
  install -Dm644 "$srcdir/dwm.desktop" "$pkgdir/usr/share/xsessions/dwm.desktop"
}
