pkgname=qactus
pkgver=0.7.0
pkgrel=1
pkgdesc="A Qt-based Opensuse Build System notifier"
arch=('x86_64')
url="http://qt-apps.org/content/show.php?content=169054"
license=('GPL')
depends=('qt5-base' 'qtkeychain')
makedepends=('rpmextract')
source=("http://download.opensuse.org/repositories/openSUSE:/Factory/standard/src/${pkgname}-${pkgver}-${pkgrel}.2.src.rpm")
sha512sums=('07204f8efbdf9e56ca58643a3232670b5e86fbd4dce405d439115eeb9797466932504035ec4c593caa39419f33c011c75d334b851ecb23d7950f8c03cd8be1ad')

build() {
 cd "${srcdir}"
 rpmextract.sh ${pkgname}-${pkgver}-1.2.src.rpm
 tar xvjf ${pkgname}-${pkgver}.tar.bz2
 cd ${pkgname}
 qmake-qt5 qactus.pro PREFIX="${pkgdir}/usr" .
}

package() {
 cd "${srcdir}/${pkgname}"
 make DESTDIR="${pkgdir}" install
}
