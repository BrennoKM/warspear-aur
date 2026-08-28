# Maintainer: Brenno Kevyn <brennokm@gmail.com>
# Contributor: Sergei Marochkin <me@ziggi.org>
# Contributor: Mikhail Velichko <efklid@gmail.com>
# Contributor: Vitaliy Popov <symbx.live@gmail.com>

pkgname='warspear'
pkgver=13.4.3
pkgrel=1
pkgdesc='Warspear Online is a cross-platform massively multiplayer online roleplaying game (MMORPG) for smart phones.'
arch=('i686' 'x86_64')
url='http://warspear-online.com/'
license=('custom')
depends=('mesa' 'openal' 'libxft' 'curl')

optdepends=(
  'xdg-utils: for desktop environment integration'
  'zenity: for graphical dialog boxes'
  'nvidia-utils: alternative OpenGL implementation for NVIDIA users'
)

source_i686=("http://distr.warspear-online.com/linux/pool/non-free/w/warspear/warspear_${pkgver}_i386.deb")
source_x86_64=("http://distr.warspear-online.com/linux/pool/non-free/w/warspear/warspear_${pkgver}_amd64.deb")

sha512sums_i686=('17e72dcd751ec1fdd3e3c9e44c86754bf40872d8f54b2dfe3cc1996bc100ee494b9902d1f3d4023a6e5c8bea505203e8abc477dc6e0d1cdd9b5da716689914fc')
sha512sums_x86_64=('6cc51ccf3ab910ae404b59cf35866da7f106ec0ab72c92aa4f1d8f42749bdfbc0b825faee32d4a37454984fdf249b7541d529337a60299f854e7c9446d904e0e')

prepare() {
    tar -xf data.tar.zst
}

package() {
    cp -dr --no-preserve=ownership opt usr "$pkgdir"/
}
