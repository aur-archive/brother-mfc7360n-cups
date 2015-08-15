# Maintainer: Martin Wimpress <code@flexion.org>

pkgname=brother-mfc7360n-cups
pkgver=2.0.4
pkgrel=2
_pkgrel=2
pkgdesc="Brother MFC-7360N CUPS driver"
url="http://solutions.brother.com/linux/en_us/download_prn.html#MFC-7360N"
license=('custom:Brother' 'GPL')
depends=('cups' 'brother-mfc7360n-lpr')
makedepends=('rpmextract')
install="brother-mfc7360n-cups.install"
arch=('i686' 'x86_64')
source=("http://www.brother.com/pub/bsc/linux/dlf/cupswrapperMFC7360N-${pkgver}-${_pkgrel}.i386.rpm")
md5sums=('2871ab07e085c41609593522c3045f32')

if [ "${CARCH}" == "x86_64" ]; then
    depends+=('lib32-libcups')
fi

prepare() {
    cd "${srcdir}"
    for RPM in *.rpm; do
        rpmextract.sh "${RPM}"
    done
}

package() {
    cp -R "${srcdir}/usr" "${pkgdir}"
}
