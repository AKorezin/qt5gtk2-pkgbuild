pkgname=qt5gtk2
pkgver=r7.443361b
pkgrel=2
pkgdesc='GTK+2.0 integration plugins for Qt5'
url='https://bitbucket.org/trialuser02/qt5gtk2'
arch=('i686' 'x86_64')
license=('GPL3')

# make dependancies
depends=('qt5-base>=5.7')

# source download from git repo & prepare
source=(git+https://bitbucket.org/trialuser02/qt5gtk2.git)
sha256sums=('SKIP')
install=qt5gtk2.install
prepare() {
	  cd "${srcdir}"
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
	  cd "${srcdir}/${pkgname}"
		make INSTALL_ROOT="${pkgdir}" DESTDIR="${pkgdir}" install
} 
