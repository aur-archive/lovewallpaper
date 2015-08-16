# Maintainer: 北京取道兴业  <info at lovebizhi a-dot com>
# Contributor: Dongfengweixiao <dongfengweixiao at gmail a-dot com>

pkgname=lovewallpaper
pkgver=1.1.1
pkgrel=2
pkgdesc="最专业的桌面高清壁纸软件"
arch=('i686' 'x86_64')
url="http://www.lovebizhi.com"
license=('custom')
depends=('libwebkit3' 'json-glib' 'libgee' 'gtk3' 'libsoup' 'libnotify')
install=${pkgname}.install

if [ "$CARCH" = "i686" ]; then
    _arch='i686'
    md5sums=('8bfdf041b2c866a9431fdd2373c164ff'
             'b0753b33dfb72a7354e6ab132fb03571')
elif [ "$CARCH" = "x86_64" ]; then
    _arch='x86_64'
    md5sums=('4f7826b57342578bd77219e68cbd0d37'
             'b0753b33dfb72a7354e6ab132fb03571')
fi

source=("http://gthemes-china.googlecode.com/files/LoveWallpaper_fedora_${_arch}.rpm" "lovewallpaper.desktop")


package() {
    msg "Preparing install"
    install -d "$pkgdir"/{opt,usr/share/{applications,glib-2.0/schemas}}
    mv -v opt/lovewallpaper "$pkgdir"/opt
    mv -v usr/share/applications "$pkgdir"/usr/share
    msg2 "Done preparing!"

    msg "Actual installation"
    install -m 644 /opt/lovewallpaper/script/lovewallpaper.gschema.xml "$pkgdir/usr/share/glib-2.0/schemas/"
    mv lovewallpaper.desktop "$pkgdir/usr/share/applications"
    msg2 "Installation finished!"
}
