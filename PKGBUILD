# Maintainer: Brenno Kevyn <brennokm@gmail.com>
# Contributor: Sergei Marochkin <me@ziggi.org>
# Contributor: Mikhail Velichko <efklid@gmail.com>
# Contributor: Vitaliy Popov <symbx.live@gmail.com>

pkgname='warspear'
pkgver=13.5.0
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

sha512sums_i686=('ea0c98e59f4e0bb6009c5be09dbdfea729b7628baf55c2976e95f73f9ec05be8f5ff3bd47ea29f7cd49df752f738e4ecd928feae825a2807b0758c53d1762ddd')
sha512sums_x86_64=('f3494a4c81f50eac7e2ba3dbff9eca006bacdbe0d5d17f6e0f8d717f87dd8f200fdd1a3fac6e2384ad22df56b1c6668560a10732c05ae6bcd2f0d0e6a722b270')

prepare() {
    tar -xf data.tar.zst
}

package() {
    cp -dr --no-preserve=ownership opt usr "$pkgdir"/
}
