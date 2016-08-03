# Maintainer: Dominik Fischer <d dot f dot fischer at web dot de>
pkgname=git-makepkg-templates-git
pkgver=r0
pkgrel=1
pkgdesc="makepkg-templates for git source packages"
arch=('any')
url="https://github.com/dffischer/git-makepkg-templates"
license=('GPL')
depends=('pacman>=4.1.2' 'git')
replaces=('git-makepkg-template')
conflicts=('git-makepkg-template')

# template input; name=git

package() {
  cd "$_gitname"
  install -m644 -Dt "$pkgdir/usr/share/doc/$pkgname/" README.md PKGBUILD
  local destdir="$pkgdir/usr/share/makepkg-template"
  find -iname '*.template' -type f -exec install -m644 -Dt "$destdir" '{}' +
  cd "$destdir"
  for file in *
  do
    ln -s $file ${file%-*.template}.template
  done
}
