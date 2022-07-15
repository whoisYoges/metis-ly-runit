# Maintainer: whoisYoges <helloyogesh@tuta.io>
pkgname=metis-ly-runit
pkgver=0.1
pkgrel=1
pkgdesc="runit service for metis-ly"
arch=('any')
url="https://github.com/whoisYoges/metis-ly-runit"
license=('MIT')
makedepends=('git')
depends=('metis-ly')
provides=("${pkgname}")
options=(!strip !emptydirs)
source=(${pkgname}::"git+${url}")
sha256sums=('SKIP')

package() {
	install -Dm754 "${srcdir}/$pkgname/metis-ly/run" "${pkgdir}/etc/runit/sv/run"
	install -Dm754 "${srcdir}/$pkgname/metis-ly/conf" "${pkgdir}/etc/runit/sv/conf"
	install -Dm754 "${srcdir}/$pkgname/metis-ly/finish" "${pkgdir}/etc/runit/sv/finish"
	install -Dm644 "${srcdir}/$pkgname/metis-ly/ly" "${pkgdir}/etc/pam.d/ly"
}

pkgver() {
  cd "${srcdir}/$pkgname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}
