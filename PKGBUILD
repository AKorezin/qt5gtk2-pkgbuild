pkgname=qt5gtk2
pkgver=r7.443361b
pkgrel=5
pkgdesc='GTK+2.0 integration plugins for Qt5'
url='https://bitbucket.org/trialuser02/qt5gtk2'
arch=('i686' 'x86_64')
license=('GPL2')

# make dependancies
depends=('qt5-base>=5.7')

# source download from git repo & prepare
source=(git+https://bitbucket.org/trialuser02/qt5gtk2.git
        qt5gtk2.sh)
sha256sums=('SKIP'
            'd8b980446b0f1fd990e58f7ed156a9953a9a84073a2bf711ee375a7bef700f60')
install=qt5gtk2.install
pkgver() {
	  cd "${srcdir}/${pkgname}"
		printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

# start building
build() {
	  cd "${srcdir}/${pkgname}"
		qmake
		make
}

# prepare package
package() {
		install -m755 -d "${pkgdir}/etc/X11/xinit/xinitrc.d"
		install -m755 "${srcdir}/qt5gtk2.sh" \
			"${pkgdir}/etc/X11/xinit/xinitrc.d/qt5gtk2.sh"
		cd "${srcdir}/${pkgname}"
		make INSTALL_ROOT="${pkgdir}" DESTDIR="${pkgdir}" install
} 
