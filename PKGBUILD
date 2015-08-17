# Maintainer: Sébastien Martinez <garrik@garrik.info>

pkgbase=pypy-pymoult-hg
pkgname=('pypy-pymoult-hg')
pkgver=0.1
pkgrel=1
pkgdesc="A prototyping platform for DSU"
depends=('pypy-dsu')
makedepends=('mercurial')
arch=('any')
url="http://bitbucket.org/smartinezgd/pymoult"
license=('GPL')

_hgroot="http://bitbucket.org/smartinezgd/pymoult"
_hgrepo="pymoult"

build() {	
	cd "${srcdir}"

	if [[ -d "$_hgrepo" ]]; then
		cd "$_hgrepo"
		hg pull -u
		msg "The local files are updated."
	else
		hg clone "$_hgroot" "$_hgrepo"
	fi
}

package() {
	cd ${srcdir}/$_hgrepo
	pypy-dsu setup.py install --root="$pkgdir"
}
