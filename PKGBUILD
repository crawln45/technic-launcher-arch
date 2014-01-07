# Maintainer: Crawln45 <crawl45@gmail.com>
# Forked from : Archimaredes <microphonics17@gmail.com>

pkgname=technic-launcher-git
pkgver=000
pkgrel=1
pkgdesc="The Technic Platform's launcher, which allows you to install and play dozens of Technic modpacks for Minecraft, including Tekkit, Voltz, and Hexxit."
arch=(any)
url=http://www.technicpack.net/download
license=("custom:SpoutDev License Version 1")
depends=("java-environment" "sh")
provides=(tekkit minecraft-technic-launcher)
conflicts=(tekkit minecraft-technic-launcher)
noextract=(TechnicLauncher.jar)
install=technic-launcher.install

source=("$pkgname"::"git://github.com/crawln45/technic-launcher-arch.git")

md5sums=("SKIP"
		  "SKIP")
pkgver () {
	curl -s http://build.technicpack.net/job/TechnicLauncher/lastSuccessfulBuild/buildNumber | grep -Eo "[0-9]{0,5}
}
package() {
    install -D -m 644 "${srcdir}/LICENSE"		    "${pkgdir}/usr/share/licenses/technic-launcher/LICENSE"
    install -D -m 755 "${srcdir}/technic-launcher"	    "${pkgdir}/usr/bin/technic-launcher"
    install -D -m 644 "${srcdir}/technic-launcher.desktop"  "${pkgdir}/usr/share/applications/technic-launcher.desktop"
    curl --output ${srcdir}/TechnicLauncher.jar http://mirror.technicpack.net/launcher/$pkgver/TechnicLauncher.jar
    install -D -m 644 "${srcdir}/technic-launcher.png"	    "${pkgdir}/usr/share/pixmaps/technic-launcher.png"
    install -D -m 644 "${srcdir}/TechnicLauncher.jar"	    "${pkgdir}/usr/share/technic-launcher/TechnicLauncher.jar"
}
