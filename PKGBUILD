# Maintainer: twistedturtle <hindredkin@gmail.com>
# Contributer:

pkgname="wacfig"
pkgver="0.1"
pkgrel="1"
pkgdesc="Provides a CLI utility to easily configure wacom tablets"
url="https://github.com/twistedturtle/ShanWanTwin_2-4Ghz_Linux"
arch=('any')
license=('GPLv3')
depends=('python>=3')
optdepends=()
makedepends=("git")
source=("git+https://github.com/twistedturtle/wacfig.git")
sha256sums=(SKIP)

package() {
  cd "${srcdir}/${_pkgname}"
  install -Dm755 wacfig ${pkgdir}/usr/bin/wacfig
  install -Dm644 wacfig.service ${pkgdir}/usr/lib/systemd/user/wacfig.service
  install -Dm644 95-wacfig.rules ${pkgdir}/etc/udev/rules.d/95-wacfig.rules
}