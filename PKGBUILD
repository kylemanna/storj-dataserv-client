# Maintainer: Kyle Manna <kyle[at]kylemanna[d0t]com>
pkgname=storj-dataserv-client
_pkgname=${pkgname/storj-/}
pkgver=2.1.12
pkgrel=1
pkgdesc="Storj Client for storing and auditing data"
url="https://github.com/Storj/dataserv-client"
depends=('python'
         'python-pip'
         'python-future'
         'python-randomio'
         'python-partialhash'
         'python-btctxstore'
         'python-psutil'
         'python-storjcore'
         'python-storjnode'
         'python-crochet'
         'python-pyp2p'
         )
optdepends=()
license=('MIT')
arch=('any')
source=("https://github.com/Storj/${_pkgname}/archive/v${pkgver}.tar.gz")
sha256sums=('8db7b245d81305cb2209ca554159cfb6f2886b73482e60092b80a8d15f668703')

build() {
    cd "$srcdir/$_pkgname-$pkgver"
    python setup.py build
}

package() {
    cd "$srcdir/$_pkgname-$pkgver"
    python setup.py install --root="$pkgdir" --optimize=1 
    rm -rf ${pkgdir}/usr/lib/python*/site-packages/tests/
}

