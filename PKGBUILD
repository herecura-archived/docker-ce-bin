# Maintainer: BlackIkeEagle

pkgname=docker-ce-bin
_rpmfile=docker-engine-17.03.0.ce-1.fc25.x86_64.rpm
pkgver=17.03.0
pkgrel=2
pkgdesc='Pack, ship and run any application as a lightweight container, using official binaries'
arch=('x86_64')
url='https://www.docker.com/'
license=('Apache')
provides=('docker')
conflicts=('docker' 'docker-git')
replaces=('docker-bin')
depends=('bridge-utils' 'iproute2' 'device-mapper' 'sqlite' 'systemd' 'libseccomp' 'libtool')
optdepends=('btrfs-progs: btrfs backend support'
            'lxc: lxc backend support')
# don't strip binaries! A sha1 is used to check binary consistency.
options=('!strip')
source=(
  "https://yum.dockerproject.org/repo/main/fedora/25/Packages/$_rpmfile"
  "docker.sysusers")
sha512sums=('470a91944fe7a6c571642b994b29a626e4309191e69254bba9700485c40159077e2559347265e27fab2969a483e0be9feeaae93debc3c6f07f14ae70e20fb3de'
            '5791272636736b70509ae5ddd29ba94caba52ba7cc90190e20b867d926a47f1fd062fe8c00cb5585e4def39814bfc7a2d5d191fed46b26847b0206f65647309d')

package() {
  cp -a {etc,usr} "$pkgdir"
  mv "$pkgdir/usr/share/doc/"{docker-engine,docker}
}

# vim:set ts=2 sw=2 et:
