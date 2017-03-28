# Maintainer: BlackIkeEagle

pkgname=docker-ce-bin
_rpmfile=docker-engine-17.03.1.ce-1.fc25.x86_64.rpm
pkgver=17.03.1
pkgrel=1
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
sha512sums=('cbf4fef05d1c84e3e2332534912fedb176747bfb7832cbe3264be82fb10e12e06a0aa455b0324a532c97ff2080adc190a35d2defa0045f172acff6108804e189'
            '5791272636736b70509ae5ddd29ba94caba52ba7cc90190e20b867d926a47f1fd062fe8c00cb5585e4def39814bfc7a2d5d191fed46b26847b0206f65647309d')

package() {
  cp -a {etc,usr} "$pkgdir"
  mv "$pkgdir/usr/share/doc/"{docker-engine,docker}
  mv "$pkgdir/usr/share/zsh/"{vendor-completions,site-functions}
}

# vim:set ts=2 sw=2 et:
