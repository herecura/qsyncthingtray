# OLD Maintainer: xduugu
# OLD Maintainer: MrSerenity
# Maintainer: derlafff (aur@2-47.ru)

pkgname=qsyncthingtray
pkgver=0.5.8
pkgrel=1
pkgdesc="tray app for syncthing"
arch=('x86_64')
url="https://github.com/sieren/QSyncthingTray"
license=('LGPL2.1')
depends=('qt5-location' 'qt5-webengine')
makedepends=('cmake')
source=("$pkgname-$pkgver.tar.gz::https://github.com/sieren/QSyncthingTray/archive/$pkgver.tar.gz"
        "$pkgname.desktop")
sha512sums=('8aeed6d0ec6d8aad606ac3d0cbe0da7e3da13af63ce7c391e548284e622322c087d103e6cefd432c3fc024d7be34a5b805584e3b4f39fb7179cd0dc96d26e236'
            'e0dae1d01af7f0d842da6baac6a705b83979a9a31e8e03181ea9e00a4d389bb2dff93080badadb26e5055ea80b616494687e5f69a4258a6c670a2bb5e0c96c16')

_pkgname=QSyncthingTray

build() {
  cd "$_pkgname-$pkgver"
  mkdir -p build
  cd build
  cmake ..
  make
}

package() {
  cd "$_pkgname-$pkgver"
  install -Dm755 "build/$_pkgname" "$pkgdir/usr/bin/$_pkgname"

  # install .desktop file
  install -Dm755 "$srcdir/$pkgname.desktop" "$pkgdir/usr/share/applications/$pkgname.desktop"
  install -Dm755 "resources/images/Icon1024.png" "$pkgdir/usr/share/pixmaps/$pkgname.png"
}

