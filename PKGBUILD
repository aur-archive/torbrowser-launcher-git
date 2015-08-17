pkgname=torbrowser-launcher-git
pkgver=v0.1.8
pkgrel=1
pkgdesc="A program to help you download, keep updated, and run the Tor Browser Bundle."
arch=('any')
url="https://github.com/micahflee/torbrowser-launcher"
license=('MIT')
depends=('python2' 'gnupg' 'wmctrl' 'python2-psutil' 'python2-pyliblzma' 'python2-txsocksx' 'python2-service-identity')
makedepends=('git' 'python2-setuptools')
source=("$pkgname"::git://github.com/micahflee/torbrowser-launcher.git)
md5sums=('SKIP')

pkgver() {
  cd "$pkgname"
  local ver=$(git describe --always)
  printf "%s\n" "${ver//-/.}"
}

package() {
  cd "$pkgname"
  sed -i '1s/python$/python2/' torbrowser-launcher
  python2 setup.py install --root=$pkgdir
}

# vim:set ts=2 sw=2 et:
