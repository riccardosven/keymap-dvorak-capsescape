# Maintainer: Riccardo Sven Risuleo <riccardosven@gmail.com>

pkgname=keymap-dvorak-capsescape
pkgver=1.0.0
pkgrel=1
pkgdesc="A dvorak keymap with capslock remapped to escape (capslock available
as shift+capslock)"
arch=('any')
makedepends=('kbd')
url="https://github.com/riccardosven"
license=('GPL')
install=keymap-dvorak-capsescape.install

prepare() {
  cd "$srcdir"
  cp -dpr --no-preserve=ownership \
    /usr/share/kbd/keymaps/i386/dvorak/dvorak.map.gz dvorak.map.gz
  gunzip dvorak.map.gz
}

build() {
  cd "$srcdir"
  sed \
    -i \
    -e '1i #dvorak-capsescape' \
    -e 's/\(keycode\s*58\s*=\s*\).*/\1Escape Caps_Lock/' \
    dvorak.map
  mv dvorak.map dvorak-capsescape.map
  gzip dvorak-capsescape.map
}

package() {
  cd "$srcdir"
  install -Dm 644 dvorak-capsescape.map.gz \
          -t "$pkgdir/usr/share/kbd/keymaps/i386/dvorak/"
}
