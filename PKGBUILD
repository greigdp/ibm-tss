# Maintainer: robertfoster

pkgname=ibm-tss
pkgver=1119
pkgrel=1
pkgdesc="A user space TSS for TPM 2.0 by IBM"
arch=(i686 x86_64)
url="https://sourceforge.net/projects/ibmtpm20tss/"
license=('BSD')
depends=('openssl')
source=("https://downloads.sourceforge.net/project/ibmtpm20tss/ibmtss$pkgver.tar.gz")

build() {
	cd $srcdir/utils
	make -f makefile
}

package() {
	cd $srcdir/utils
	mkdir -p $pkgdir/usr/bin

	for f in *; do
	if [[ -x $f && -f $f ]]; then
		cp -p $f $pkgdir/usr/bin/tss_$f
	fi;
	done
	cd $pkgdir/usr
	mkdir lib
	cp $srcdir/utils/libtss.so  $pkgdir/usr/lib/
}

md5sums=('9b696c9d7470326f67f8d5bc9063d3d3')
