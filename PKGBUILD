# Maintainer: spider-mario <spidermario@free.fr>
# Contributor: Daniel Ehlers <danielehlers@mindeye.net>

pkgname=coin-utils
pkgver=2.9.9
pkgrel=1
pkgdesc="CoinUtils (Coin-or Utilities) is an open-source collection of classes and functions that are generally useful to more than one COIN-OR project."
arch=('i686' 'x86_64')
url="https://projects.coin-or.org/CoinUtils"
license=('EPL')
groups=('coin-or')
depends=('gcc-libs')
source=(http://www.coin-or.org/download/source/CoinUtils/CoinUtils-$pkgver.tgz)
sha512sums=('3d26fc9910c167afe30a4101bdd63ebbb90b1d7f7411f6a59358f61218a56f25f999498e4f50d9654b5bcd2b011c09b4c81ed66145565eac1f48b957dd40a2b3')

build() {
  cd CoinUtils-$pkgver
  ./configure --prefix=/usr -C
  make
}

check() {
  cd CoinUtils-$pkgver
  make test
}

package() {
  cd CoinUtils-$pkgver
  PKG_CONFIG_LIBDIR="$pkgdir"/usr/lib/pkgconfig/ \
  make DESTDIR="$pkgdir"/ install
}
