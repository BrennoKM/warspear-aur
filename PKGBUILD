# Maintainer: Brenno Kevyn <brennokm@gmail.com>
# Contributor: Sergei Marochkin <me@ziggi.org>
# Contributor: Mikhail Velichko <efklid@gmail.com>
# Contributor: Vitaliy Popov <symbx.live@gmail.com>

pkgname='warspear'
pkgver=13.6.0
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

sha512sums_i686=('1f2bebccbf0437fc4586588fc09689e03114309b4b7bec5d45cb2d4209f1cade7b454b2ce5ea026809e27729b7233f13f14cb08bc99bd24f1ed1c9e8be964740')
sha512sums_x86_64=('f702f1c652420ba1c43a879ed4dbd004b9ea2b27fbb040f9bc7dc130040d10e611391d695c919124e349846f5b1c1c3b075d7bf90f909ec8d6744f2f9dc578ba')

prepare() {
    tar -xf data.tar.zst
}

package() {
    cp -dr --no-preserve=ownership opt usr "$pkgdir"/
}
