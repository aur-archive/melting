# Contributor: Brandon Invergo <brandon@invergo.net>
# Contributor: Anton Bazhenov <anton.bazhenov at gmail>
# Contributor: Abhishek Dasgupta <abhidg@gmail.com>

pkgname=melting
pkgver=5.1.1
pkgrel=1
pkgdesc="A software for computing enthalpy, entropy and melting temperature of nucleic acid duplex"
arch=('any')
url="http://www.ebi.ac.uk/compneur-srv/melting/"
license=('GPL')
depends=('java-runtime')
source=("http://downloads.sourceforge.net/${pkgname}/MELTING${pkgver}.tar.gz"
        "${pkgname}.sh")
md5sums=('9b389a84055b0cce4d04adb3cfac7425'
         '91849851495657a0152fc3e79fb0b9a7')

package() {
  cd "${srcdir}/MELTING${pkgver}"

  # Install a launcher
  install -Dm755 ../${pkgname}.sh "${pkgdir}/usr/bin/${pkgname}"

  # Install data files
  mkdir -p "${pkgdir}/usr/share/${pkgname}"
  cp -r Data executable/melting5.jar "${pkgdir}/usr/share/${pkgname}"

  # Install documentation and a man page
  mkdir -p "${pkgdir}/usr/share/doc/${pkgname}"
  install -m644 doc/*.pdf "${pkgdir}/usr/share/doc/${pkgname}"
  install -Dm644 doc/${pkgname}.1 "${pkgdir}/usr/share/man/man1/${pkgname}.1"
}
