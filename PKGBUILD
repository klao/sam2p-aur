# Contributor: Jonathan Liu <net147@hotmail.com>
# Maintainer: Stefan Husmann <stefan-husmann@t-online.de>
# Contributor: menta

pkgname=sam2p
pkgver=0.49.4
pkgrel=4
pkgdesc="A bitmap-to-eps-or-pdf-converter that produces very small files"
arch=('i686' 'x86_64')
url="http://www.inf.bme.hu/~pts"
license=('GPL2')
depends=('gcc-libs')
makedepends=('tar')
optdepends=('ghostscript: PS, EPS, PDF support'
	    'libjpeg: JPEG support'
	    'tif22pnm: for tiff support'
	    'png22pnm: for png support')
# 'netpbm: PNG support'
source=("https://github.com/pts/sam2p/releases/download/v$pkgver/$pkgname-$pkgver.tar.gz")
sha256sums=('5bc5b5a526bc798315da23b02564d6a1bfea51b364b8b03f76695a833f6d2bed')

build() {
  cd $pkgname-$pkgver
  CXX="g++ --std=c++98" ./configure --prefix=/usr --enable-lzw --enable-gif
  make all
}

package() {
  cd $pkgname-$pkgver
  install -Dm755 sam2p $pkgdir/usr/bin/sam2p
  install -Dm755 sam2p_pdf_scale.pl $pkgdir/usr/bin/sam2p_pdf_scale
  install -Dm644 README "$pkgdir"/usr/share/sam2p/docs/README
}
