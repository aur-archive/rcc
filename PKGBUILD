# Maintainer: Andre Bartke

_gccver=4.4.6
_rtemsver=4.10

pkgname=rcc
pkgver=1.2.18
pkgrel=1
pkgdesc="Cross-compilation system of RTEMS C/C++ applications for LEON processors."
arch=('i686' 'x86_64')
url="http://www.gaisler.com/index.php/products/operating-systems/rtems"
license=('GPL')
options=('!strip')
source=("http://gaisler.com/anonftp/rcc/bin/linux/sparc-rtems-${_rtemsver}-gcc-${_gccver}-${pkgver}-linux.tar.bz2")

package() {
	mkdir -p $pkgdir/opt
	cp -r $srcdir/rtems-$_rtemsver $pkgdir/opt

	msg "Creating /usr/bin symlinks..."
	mkdir -p $pkgdir/usr/bin
	for bin in $pkgdir/opt/rtems-$_rtemsver/bin/sparc-rtems-*; do
		bbin=`basename "$bin"`;
		ln -s "/opt/rtems-${_rtemsver}/bin/${bbin}" "${pkgdir}/usr/bin/${bbin}";
	done
}

md5sums=('b8494345f6b3fd4aaf30e44f93650989')

# vim: set noet ci pi sts=0 sw=4 ts=4:
