# Maintainer: Dominik Fischer <d dot f dot fischer at web dot de>
pkgname=git-makepkg-template-git
pkgver=r0
pkgrel=1
pkgdesc="makepkg-template for git source packages"
arch=('any')
url="https://github.com/dffischer/git-makepkg-template"
license=('GPL')
depends=('pacman>=4.1.2' 'git')

# template input; name=git

package() {
  cd "$_gitname"
  install -m644 -Dt "$pkgdir/usr/share/$pkgname/" README.md
  local destdir="$pkgdir/usr/share/makepkg-template"
  find -iname '*.template' -type f -exec install -m644 -Dt "$destdir" '{}' +
  cd "$destdir"
  for file in *
  do
    ln -s $file ${file%-*.template}.template
  done
}
