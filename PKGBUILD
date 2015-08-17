# Maintainer: Jason St. John <jstjohn .. purdue . edu>
# Contributor: Sebastian Köhler <sebkoehler@whoami.org.uk>

_perlmod=Sys-Info-Driver-Linux
_modnamespace=Sys
pkgname=perl-sys-info-driver-linux
pkgver=0.7903
pkgrel=4
pkgdesc="Sys::Info::Driver::Linux - Linux driver for Sys::Info"
arch=('i686' 'x86_64')
url="http://search.cpan.org/dist/${_perlmod}"
license=('GPL' 'PerlArtistic')
depends=('perl-config-general' 'perl-sys-info-base>=0.7803' 'perl-test-sys-info>=0.20' 'perl-unix-processors' 'net-tools')
options=('!emptydirs')
source=("http://cpan.org/modules/by-module/${_modnamespace}/${_perlmod}-${pkgver}.tar.gz")
sha512sums=('2956f97e1780e2bb247b73c65467fced1fe16188c45120682f86881d9998dfe59f86a47a645693427c50e2c65b2f9cfed56e25721947a5bf13533eaf3f33a551')

build() {
	cd "${_perlmod}-${pkgver}"

	# Install module in vendor directories.
	PERL_MM_USE_DEFAULT=1 perl Makefile.PL INSTALLDIRS=vendor
	make
}

check() {
	cd "${_perlmod}-${pkgver}"
	make test
}

package() {
	cd "${_perlmod}-${pkgver}"
	make install DESTDIR="${pkgdir}"
}
