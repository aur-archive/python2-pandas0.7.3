# Maintainer: Mike Cribbens <firstname at lastname dot com>
pkgname=python2-pandas0.7.3
pkgver=0.7.3
pkgrel=2
pkgdesc="Cross-section and time series data analysis toolkit - Version 0.7.3"
arch=('i686' 'x86_64')
url="http://pandas.pydata.org/"
license=('BSD')
depends=('python2-numpy' 'python2-dateutil')
makedepends=('python2-distribute' 'cython2')
optdepends=('python-pytables: for HDF5-based storage'
            'python2-matplotlib: for plotting'
            'python2-pytz: for time zone support'
            'python2-scipy: for miscellaneous statistical functions'
            'scikits-statsmodels: for parts of pandas.stats')
options=(!emptydirs)
conflicts=('python2-pandas')
source=("http://pypi.python.org/packages/source/p/pandas/pandas-${pkgver}.tar.gz")
md5sums=('e4876ea5882accce15f6f37750f3ffec')

build() {
  cd "$srcdir"/pandas-$pkgver

  python2 setup.py build
}

package() {
  cd "$srcdir"/pandas-$pkgver
  python2 setup.py install --root="$pkgdir"/ --optimize=1

  sed -i -e "s|#![ ]*/usr/bin/env python$|#!/usr/bin/env python2|" \
    $(find "${pkgdir}" -name '*.py')

  install -D LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

