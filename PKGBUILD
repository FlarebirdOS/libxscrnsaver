pkgname=libxscrnsaver
pkgver=1.2.5
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
sha256sums=(5057365f847253e0e275871441e10ff7846c8322a5d88e1e187d326de1cd8d00)

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

