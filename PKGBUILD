pkgname=secureboot
pkgver=0.3
pkgrel=1
pkgdesc="Install keys and hooks necessary for Secure Boot"
arch=(any)
license=(GPL3)
depends=('util-linux' 'efitools' 'coreutils' 'bash' 'python2' 'openssl')
source=('sb-keygen' '99-sbsign-kernel.hook' '109-sbsign-systemd.hook')
sha256sums=('SKIP' 'SKIP' 'SKIP')

install=secureboot.install

package() {
    install -Dm755 sb-keygen $pkgdir/usr/bin/sb-keygen
    # install -Dm644 sbgenkeys.service $pkgdir/usr/lib/systemd/system/sbgenkeys.service

    # hooks
    install -Dm644 99-sbsign-kernel.hook ${pkgdir}/etc/pacman.d/hooks/99-sbsign-kernel.hook
    install -Dm644 109-sbsign-systemd.hook ${pkgdir}/etc/pacman.d/hooks/109-sbsign-systemd.hook
}

