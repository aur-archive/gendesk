# Maintainer: Alexander R�dseth <rodseth@gmail.com>

pkgname=gendesk
pkgver=0.1
pkgrel=2
pkgdesc="Utility to generate .desktop files and download icons"
arch=('x86_64' 'i686')
url="http://roboticoverlords.org/gendesk/"
license=('MIT')
depends=('go')
conflicts=('go-hg')
source=("http://roboticoverlords.org/$pkgname/$pkgname-$pkgver.tar.gz")
sha256sums=('8cfe7fd99535bcb91f61047b41495d71223c05d70bcf63a2a2e52f264bb65c9a')
options=(!strip)
if [ "$CARCH" = "x86_64" ]; then
  num=6
else
  num=8
fi

build() {
  cd "$srcdir/$pkgname-$pkgver"

  "${num}g" "$pkgname.go"
  "${num}l" -o "$pkgname" "$pkgname.$num"
}

package() {
  cd "$srcdir/$pkgname-$pkgver"

  install -Dm755 "$pkgname" "$pkgdir/usr/bin/$pkgname"
}

# vim:set ts=2 sw=2 et:
