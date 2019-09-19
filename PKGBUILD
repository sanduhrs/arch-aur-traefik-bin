# Maintainer: Stefan Auditor <stefan.auditor@erdfisch.de>

_pkgname='traefik'
pkgname="${_pkgname}-bin"
pkgver=2.0.0
pkgrel=1
pkgdesc='A modern reverse proxy'
arch=('i686' 'x86_64' 'armv6h' 'armv7h' 'aarch64')
url='https://github.com/containous/traefik'
license=('MIT')
install="${_pkgname}.install"
backup=(
  'etc/traefik/traefik.toml'
  'etc/logrotate.d/traefik'
)
source=(
  'traefik.logrotate'
  'traefik.service'
  'traefik.toml'
  "https://raw.githubusercontent.com/containous/${_pkgname}/v${pkgver}/LICENSE.md"
)
source_i686=("${_pkgname}_i686_${pkgver}"::"https://github.com/containous/${_pkgname}/releases/download/v${pkgver}/${_pkgname}_v${pkgver}_linux-386.tar.gz")
source_x86_64=("${_pkgname}_x86_64_${pkgver}"::"https://github.com/containous/${_pkgname}/releases/download/v${pkgver}/${_pkgname}_v${pkgver}_linux_amd64.tar.gz")
source_armv6h=("${_pkgname}_armv6h_${pkgver}"::"https://github.com/containous/${_pkgname}/releases/download/v${pkgver}/${_pkgname}_v${pkgver}_linux-armv6.tar.gz")
source_armv7h=("${_pkgname}_armv7h_${pkgver}"::"https://github.com/containous/${_pkgname}/releases/download/v${pkgver}/${_pkgname}_v${pkgver}_linux-armv7.tar.gz")
source_aarch64=("${_pkgname}_aarch64_${pkgver}"::"https://github.com/containous/${_pkgname}/releases/download/v${pkgver}/${_pkgname}_v${pkgver}_linux-arm64.tar.gz")
sha512sums=('d1dfacff1e7a5b9f8e8b4796fcfbb9c1bed6151013708078361ac31ae221dd956f746ec1e0bc5bd09a05763438d877318259577f6f0178d42f011bd737c31207'
            'd37b066ece7aee45c8481d6054d4a1e674345e91b484a98790366afaca7d55a85c61acc5485d651a2ee778d3889414d2d517cd5bc321435aea77382931921172'
            '39c08bd622b7d79a43ad1fad8bdceec7abab863f9386cb413683f72c7b98ba3d26f56b1b79ca5eeec90754fa7d4da51c4b3ca91a2adc6dc2eaf486b9847664da'
            '4988480b6057b0e36e74cd0c905e1e26767af047b00aebd888ae3fde4aaa6e9c8946c874efc698bdc6bbb6933f27ef074c366450e39cbdcad369f0107abddffd')
sha256sums_i686=('111788aded094721bd9ea4515d931892f8bae054e12814772e33ae6919eed39d')
sha256sums_x86_64=('c2a14604aca551e2b451fd8511838bbeb0c2656dcc8931c733fe09003715506c')
sha256sums_armv6h=('ea7a096b2a7cd7ae8784663b1571ef5034aa3287215b6134863f35cf3ae83771')
sha256sums_armv7h=('8ce9e46bce396cc501f6d65d91b446c21e81c8319b0e8391fa0fc5f23d84594c')
sha256sums_aarch64=('51071ffc12cb1c61079b0aac26f4588f8852af18ba8188455fd13635a8b475f9')

package() {
  install -d -m755 "${pkgdir}/var/log/traefik"

  install -D -m644 "${srcdir}/traefik.logrotate" "${pkgdir}/etc/logrotate.d/traefik"
  install -D -m644 "${srcdir}/traefik.service" "${pkgdir}/usr/lib/systemd/system/traefik.service"
  install -D -m644 "${srcdir}/traefik.toml" "${pkgdir}/etc/traefik/traefik.toml"

  install -D -m644 "${srcdir}/LICENSE.md" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  install -D -m755 "${srcdir}/${_pkgname}" "${pkgdir}/usr/bin/${_pkgname}"
}
