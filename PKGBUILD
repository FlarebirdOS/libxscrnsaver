pkgname=libxscrnsaver
pkgver=1.2.4
pkgrel=1
pkgdesc="libXScrnSaver contains the X.org screen saver library"
arch=('x86_64')
url="https://xorg.freedesktop.org/"
license=('X11')
depends=(
    'glibc'
    'libx11'
    'libxext'
    'xorgproto'
)
makedepends=('xorg-util-macros')
source=(https://www.x.org/pub/individual/lib/libXScrnSaver-${pkgver}.tar.xz)
sha256sums=(75cd2859f38e207a090cac980d76bc71e9da99d48d09703584e00585abc920fe)

build() {
    cd libXScrnSaver-${pkgver}

    local configure_args=(
        --sysconfdir=/etc
        --localstatedir=/var
        --disable-static
        --docdir=/usr/share/doc/libXScrnSaver-${pkgver}
        ${configure_options}
    )

    ./configure "${configure_args[@]}"

    make
}

package() {
    cd libXScrnSaver-${pkgver}

    make DESTDIR=${pkgdir} install
}

