pkgname=qgroundcontrol
pkgver=2.9.5
pkgrel=1
pkgdesc="Open Source Micro Air Vehicle Ground Control Station"
arch=('x86_64')
url="https://github.com/mavlink/qgroundcontrol"
license=('GPL3')
depends=('qt5-tools' 'qt5-serialport' 'qt5-svg' 'qt5-webkit' 'qt5-quickcontrols' 'qt5-xmlpatterns' 'qt5-script' 'qt5-graphicaleffects' 'qt5-connectivity' 'espeak')
source=("https://github.com/mavlink/${pkgname}/releases/download/v${pkgver}/${pkgname}.tar.bz2" "https://raw.githubusercontent.com/mavlink/qgroundcontrol/master/resources/icons/qgroundcontrol.png" "https://raw.githubusercontent.com/mavlink/qgroundcontrol/master/qgroundcontrol.desktop")
md5sums=('')

package(){
        install -dm 755 $pkgdir/usr/share/$pkgname
        cp -Lr $srcdir/$pkgname/. $pkgdir/usr/share/$pkgname/
        install -dm755 $pkgdir/usr/bin
        echo -en "#!/bin/bash\ncd /usr/share/$pkgname\nexec ./qgroundcontrol-start.sh"  >$pkgdir/usr/bin/$pkgname
        chmod +x  $pkgdir/usr/bin/$pkgname
        install -dm755 $pkgdir/usr/share/applications/
        install -Dm644 $srcdir/$pkgname.desktop "$pkgdir"/usr/share/applications/
        install -dm755 $pkgdir/usr/share/pixmaps
        install -Dm644 $srcdir/$pkgname.png $pkgdir/usr/share/pixmaps/$pkgname.png
}
