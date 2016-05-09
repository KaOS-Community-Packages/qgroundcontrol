pkgname=qgroundcontrol
pkgver=2.9.6
pkgrel=1
pkgdesc="Open Source Micro Air Vehicle Ground Control Station"
arch=('x86_64')
url="https://github.com/mavlink/qgroundcontrol"
license=('GPL3')
depends=('qt5-tools' 'qt5-serialport' 'qt5-svg' 'qt5-webkit' 'qt5-quickcontrols' 'qt5-xmlpatterns' 'qt5-script' 'qt5-graphicaleffects' 'qt5-connectivity' 'espeak')
source=("https://github.com/mavlink/${pkgname}/releases/download/v${pkgver}/${pkgname}.tar.bz2" "https://raw.githubusercontent.com/mavlink/qgroundcontrol/master/resources/icons/qgroundcontrol.png" "https://raw.githubusercontent.com/mavlink/qgroundcontrol/master/qgroundcontrol.desktop")
md5sums=('1914137f3206218ce39bd0e208d2b674'
         '8899e5ad18baecbc1b68f2645cef33f6'
         '82731e75dfa9c7c04c65b612bc668037')

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
