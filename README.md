# Git Template for makepkg-template

This is a template for [pacman](https://www.archlinux.org/pacman/)'s makepkg-template capturing most of the [VCS package guidelines](https://wiki.archlinux.org/index.php/VCS_package_guidelines) from the [Arch Linux Wiki](https://wiki.archlinux.org/). It will

1. add git as a make dependency,
2. care for the built package to provide and conflict with its non-git variant and
3. clone `$url` as a package source, to be placed into the `$srcdir` as `$pkgname`.
 - These can be overwritten by setting `$_giturl` and `$_gitname`, respectively, before inputting the template.
4. Also, [a `pkgver` function](https://wiki.archlinux.org/index.php/VCS_package_guidelines#Git) will be inserted. It uses tags if available and automatically fall back to counting revisions otherwise.

To use it, [install this package](https://aur.archlinux.org/packages/git-makepkg-template/), add a line like

```
# template input; name=git
```

to your PKGBUILD and process it with `makepkg-template`. See the PKGBUILD of git-makepkg-template itself for an example.

- If you only need a `pkgver` function and care for sources and dependencies yourself, just include [`git-pkgver`](git-pkgver.template).
- To achieve the inverse and just get points (1) to (3) of the above list, use [`git-source`](git-source.template).
- [The `git` template](git.template) provides everything combined.
