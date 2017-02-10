# Maintainer: Mike Javorski
# Contributor: Sébastien "Seblu" Luttringer

pkgname=docker-bin
_rpmfile=docker-engine-1.13.1-1.fc25.x86_64.rpm
pkgver=1.13.1
pkgrel=2
pkgdesc='Pack, ship and run any application as a lightweight container, using official binaries'
arch=('x86_64')
url='https://www.docker.com/'
license=('Apache')
provides=('docker')
conflicts=('docker-git')
depends=('bridge-utils' 'iproute2' 'device-mapper' 'sqlite' 'systemd' 'libseccomp' 'libtool')
optdepends=('btrfs-progs: btrfs backend support'
            'lxc: lxc backend support')
# don't strip binaries! A sha1 is used to check binary consistency.
options=('!strip')
install=$pkgname.install
source=(
  "https://yum.dockerproject.org/repo/main/fedora/25/Packages/$_rpmfile"
  "docker.sysusers")
sha512sums=('8c5f9bce48d4713d9bc034fa6bb8790a96bbf16036f09d3f3f445f5a4cc74d65050847ecbddd5ed1d6fc799b1eb2448c8d1c84acebb9290c813d8edb50e62818'
            '5791272636736b70509ae5ddd29ba94caba52ba7cc90190e20b867d926a47f1fd062fe8c00cb5585e4def39814bfc7a2d5d191fed46b26847b0206f65647309d')

package() {
  cp -a {etc,usr} "$pkgdir"
  mv "$pkgdir/usr/share/doc/"{docker-engine,docker}
}

# vim:set ts=2 sw=2 et:
