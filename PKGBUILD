# Maintainer: Gustavo Castro <gustawho[at]gmail[dot]com>

pkgname=scavis
pkgver=2.3
pkgrel=1
pkgdesc="An environment for scientific computation, data analysis and data visualization"
arch=('any')
url="http://jwork.org/scavis/"
license=('custom')
depends=('java-runtime')
source=("${pkgname}.png"
        "${pkgname}.desktop"
        "http://sourceforge.net/projects/scavis/files/${pkgver}/${pkgname}-${pkgver}.zip")
md5sums=('7497f0ea6fc54e4a927a9deb01d88154'
         '894a6c118a23b91a0d9726a780328890'
         'b8ed50b72d5c4154397c3f7b8a89bfec')
sha512sums=('c8ee268ed079f6b2dd4b0d14910e0e107460e89aadee082759d6a04d1090909735c6601cdaec57227efc444ef392471f090fd78517ebc64ece7a8cec773ab6a4'
            '4f422b2f129eee3ed1498b5be5aa2f0fb90997cafd698ec83141beb2489c5308c884dcf4af037da72700efaa55bbbf3b3fb557bfd8b74daa3dff9e6d4aff5cc4'
            '832d627a06874f2c5d24eb77fd29f8c458e0be0b44b0ffa97f18afaea4c9e56c23a6d39a5646c1f2404525db011762be10cdc1bbf5d99b18ed9ad84e2fca42e0')

prepare() {
  rm "${srcdir}/${pkgname}/"*.bat
  sed -i "s#\`pwd\`#\"/usr/share/java/${pkgname}\"#g" "${srcdir}/${pkgname}/${pkgname}.sh"
  sed -i 's#JYTHON_HOME=$JEHEP_HOME\"/lib/jython\"#JYTHON_HOME=$HOME\"/.jehep/jython\"#g' "${srcdir}/${pkgname}/${pkgname}.sh"
}

package() {
  install -d "${pkgdir}/usr/share/java/${pkgname}/"
  cp -dr --no-preserve=mode,ownership "${srcdir}/${pkgname}/"* "${pkgdir}/usr/share/java/${pkgname}/"
  install -m644 -D "${srcdir}/${pkgname}/Docs/license.txt" "${pkgdir}/usr/share/licenses/${pkgname}/license.txt"
  install -m755 -D "${srcdir}/${pkgname}/${pkgname}.sh" "${pkgdir}/usr/bin/${pkgname}.sh"
  install -m644 -D "${srcdir}/${pkgname}.png" "${pkgdir}/usr/share/pixmaps/${pkgname}.png"
  install -m644 -D "${srcdir}/${pkgname}.desktop" "${pkgdir}/usr/share/applications/${pkgname}.desktop"
}
