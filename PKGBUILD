# Maintainer: BlackIkeEagle

pkgname=docker-ce-bin
_rpmfile=docker-ce-17.09.1.ce-1.fc25.x86_64.rpm
pkgver=17.09.1
pkgrel=1
pkgdesc='Pack, ship and run any application as a lightweight container, using official binaries'
arch=('x86_64')
url='https://www.docker.com/'
license=('Apache')
provides=('docker')
conflicts=('docker' 'docker-git')
replaces=('docker-bin')
depends=('bridge-utils' 'iproute2' 'device-mapper' 'sqlite' 'systemd' 'libseccomp')
optdepends=('btrfs-progs: btrfs backend support'
            'lxc: lxc backend support')
# don't strip binaries! A sha1 is used to check binary consistency.
options=('!strip')
source=(
  "https://download.docker.com/linux/fedora/25/x86_64/stable/Packages/$_rpmfile"
  "docker.sysusers")
sha512sums=('9203a5cc93e96a72bfdfbdce9fc1d27f0fda27c88a58e2202ded16bf60cb64535fb8ee38840e75f10f38089f5704b484b38c231231edfba2c7ef73b0ef778c62'
            '5791272636736b70509ae5ddd29ba94caba52ba7cc90190e20b867d926a47f1fd062fe8c00cb5585e4def39814bfc7a2d5d191fed46b26847b0206f65647309d')

package() {
  cp -a {etc,usr} "$pkgdir"
  mv "$pkgdir/usr/share/zsh/"{vendor-completions,site-functions}
  install -Dm644 "$srcdir/docker.sysusers" \
    "$pkgdir/usr/lib/sysusers.d/docker.conf"
}

# vim:set ts=2 sw=2 et:
