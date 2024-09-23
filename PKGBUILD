# Based on these AUR
# - https://aur.archlinux.org/packages/circuitjs1-web-bin
# - https://aur.archlinux.org/packages/circuitjs1-electron
# - https://aur.archlinux.org/packages/circuitjs-bin
#
# source code: https://github.com/pfalstad/circuitjs1

pkgname=circuitjs1-bin
pkgver=20201006
pkgrel=1
pkgdesc="Falstad Circuit Simulator."
arch=('any')
url="https://www.falstad.com/circuit/"
license=('GPL2')
depends=(electron)
makedepends=()
checkdepends=()
optdepends=()
provides=(circuitjs1-bin)
conflicts=(circuitjs-bin circuitjs1-web)
options=(!strip)

source=("https://www.falstad.com/circuit/offline/circuitjs1-linux64.tgz"
   circuitjs.png
   circuitjs.desktop
   circuitjs)
sha256sums=('SKIP'
   'c19618d234feccc2c0878d244b2b5125df6e45b24d2bcfff1d8289e2cd69fc50'
   'SKIP'
   'e2abbfcc8ce9bdcb29e6e1387c2c6d6ac56e1543357cda87542edea20a1a48a4')

package() 
{
   cd "${srcdir}"/circuitjs1
   mkdir -p "${pkgdir}/usr/share"
   cp -r resources/app/war "${pkgdir}/usr/share"
   mv "${pkgdir}/usr/share/war" "${pkgdir}/usr/share/circuitjs1"

   cd "${srcdir}"
   mkdir -p "${pkgdir}/usr/bin"
   cp circuitjs "${pkgdir}/usr/bin/circuitjs"
   chmod 775 ${pkgdir}/usr/bin/circuitjs

   #integrate the desktop file
   install -d ${pkgdir}/usr/share/applications/
   install -m644 ${srcdir}/circuitjs.desktop ${pkgdir}/usr/share/applications/circuitjs.desktop

   #integrate icons
   install -D -m644 ${srcdir}/circuitjs.png $pkgdir/usr/share/icons/hicolor/512x512/apps/circuitjs.png
}
