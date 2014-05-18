pkgname=genymotion
pkgver=2.2.0
pkgrel=2
pkgdesc="Complete set of tools that provides a virtual environment for Android."
arch=('x86_64')
license="UNKNOWN"
url="http://www.genymotion.com/"
depends=('virtualbox>=4.1.1' 'qtwebkit' 'libpng12' 'net-tools' 'qca' 'ffmpeg-compat' 'protobuf')
install=$pkgname.install
sha512sums=('48e9bafe1d64b688c51eceb8d129f44d690060ff9a6d82eefcf3295f7834516ce62439faf4f4454287f594fc410aafbafd30a43537ea3d295c42bee8e4e03ac7')
sha512sums+=('9eb31efd43f9e74d3f95d16906fee8c46cdc8ae8343e42150c2158ec923afee1d497c07c8d1bca1afd637f2d1d1a6c08aa0ad09d402a3d383df771ce8addf7e1')
source=("genymotion.desktop" "$pkgname.bin::http://files2.genymotion.com/genymotion/genymotion-$pkgver/genymotion-${pkgver}_x64.bin")
build() {
  cd $srcdir
}

package(){
  cd $srcdir

  install -d $pkgdir/opt
  chmod +x $pkgname.bin
  yes | ./$pkgname.bin -d $pkgdir/opt
  rm $pkgdir/opt/genymotion/libQt*

  install -d $pkgdir/usr/bin
  ln -s /opt/genymotion/genymotion $pkgdir/usr/bin/genymotion
  ln -s /opt/genymotion/genymotion-shell $pkgdir/usr/bin/genymotion-shell
  install -Dm644 $srcdir/genymotion.desktop $pkgdir/usr/share/applications/genymotion.desktop
  #chown -R root:root $pkgdir/opt/genymotion
}