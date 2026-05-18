# Maintainer: sysitn <thegreatandrewsh@gmail.com>
# Contributor: kajoox <kayquesousa02004@gmail.com> (original maintainer)

pkgname=espressif-ide-bin
pkgver=4.2.0
pkgrel=1
pkgdesc='Eclipse-based IDE for ESP-IDF development'
arch=('x86_64')
url="https://github.com/espressif/idf-eclipse-plugin"
license=('EPL-2.0')
depends=('java-runtime>=21' 'python' 'python-pip' 'gtk3' 'dfu-util')
optdepends=('cmake: for building ESP-IDF projects'
            'ninja: for building ESP-IDF projects'
            'gcc: for compiling projects'
            'git: for version control and ESP-IDF installation')

source=("https://dl.espressif.com/dl/idf-eclipse-plugin/ide/Espressif-IDE-${pkgver}-linux.gtk.x86_64.tar.gz")
sha256sums=('8dd49f6144fb758fe1a61757b0fc27221abe07bd55edb23baf1936f6cfc0204d')

package() {
    cd "$srcdir"
    install -dm755 "${pkgdir}/opt/${pkgname}"
    cp -r * "${pkgdir}/opt/${pkgname}"

    install -dm755 "${pkgdir}/usr/bin"
    ln -s "/opt/${pkgname}/Espressif-IDE" "${pkgdir}/usr/bin/${pkgname}"

    install -Dm644 /dev/stdin "${pkgdir}/usr/share/applications/${pkgname}.desktop" << 'EOF'
[Desktop Entry]
Type=Application
Name=Espressif-IDE
Comment=IDE for ESP-IDF development
Exec=/opt/espressif-ide-bin/Espressif-IDE/espressif-ide
Icon=/opt/espressif-ide-bin/Espressif-IDE/icon.xpm
Categories=Development;IDE;
Terminal=false
StartupNotify=true
EOF
}
