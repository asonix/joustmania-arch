# Maintainer Riley Trautman <asonix.dev@gmail.com>

_pkgname=joustmania
pkgname=${_pkgname}-git
pkgver=v1.0.136.g8a8fea8
pkgrel=1
pkgdesc="JoustMania is a collection of PlayStation Move enabled party games"
url="joustmania.com"
arch=('any')
license=('MIT')
depends=('python' 'python-pip' 'psmoveapi-git' 'sdl' 'sdl_mixer' 'sdl_sound' 'portmidi' 'portaudio' 'sdl_image' 'sdl_ttf' 'blas' 'lapack' 'bluez' 'supervisor' 'ffmpeg' 'libsystemd' 'swig' 'alsa-lib' 'alsa-utils' 'alsa-tools' 'python-scipy' 'python-numpy' 'python-psutil' 'python-flask' 'python-flask-wtf' 'python-pyalsaaudio' 'python-pydub' 'python-pygame' 'python-pyaudio' 'python-yaml')
makedepends=('git')
provides=(${_pkgname})
conflicts=(${_pkgname})
source=("${_pkgname}::git+https://github.com/adangert/joustmania.git" 'joustmania.sh')
md5sums=('SKIP' 'SKIP')

pkgver() {
  cd "${srcdir}/${_pkgname}"
  git describe --tags |sed 's/-/./g'
}

package() {
    install -d -m755 "${pkgdir}/usr/share/${_pkgname}"
    install -D -m644 "${srcdir}/${_pkgname}/README.md" "${pkgdir}/usr/share/licenses/${_pkgname}/README.md"
    install -D -m644 "${srcdir}/${_pkgname}/LICENSE" "${pkgdir}/usr/share/licenses/${_pkgname}/LICENSE"
    install -D -m755 "${srcdir}/joustmania.sh" "${pkgdir}/usr/bin/joustmania"
    cp -r "${srcdir}/${_pkgname}"/* "${pkgdir}/usr/share/${_pkgname}"/
}
