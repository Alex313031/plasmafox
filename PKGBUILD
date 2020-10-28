# Maintainer: torvic9 AT mailbox DOT org
# based on ideas by Waterfox and firefox-kde-opensuse

pkgname=plasmafox
_pkgname=firefox
pkgver=82.0.2
pkgrel=1
pkgdesc="Standalone web browser based on Firefox with better KDE integration"
arch=('i686' 'x86_64')
license=('MPL' 'GPL' 'LGPL')
url="https://build.opensuse.org/package/show/mozilla:Factory/MozillaFirefox"

depends=(gtk3 libxt mime-types dbus-glib ffmpeg nss ttf-font libpulse
		kplasmafoxhelper libvpx icu nspr dav1d aom harfbuzz graphite
		libwebp)

makedepends=('unzip' 'zip' 'diffutils' 'python-setuptools' 'python-psutil'
			 'python' 'yasm' 'mesa' 'imake' 'xorg-server-xvfb' 'libpulse'
			 'inetutils' 'autoconf2.13' 'rust' 'cargo' 'llvm' 'clang' 'gtk2'
			 'nodejs' 'cbindgen' 'nasm' 'zlib' 'lld')

optdepends=('networkmanager: Location detection via available WiFi networks'
            'speech-dispatcher: Text-to-Speech'
            'libnotify: Notification integration'
            'libdbusmenu-gtk3: global menu support')

provides=("plasmafox=${pkgver}")
#conflicts=('plasmafox-esr')
#_patchrev=4fd43e0d4a8f
_mbrev=2349
_patchrevsuse=e64141ffa905efdf657306eda2627c868b399852
_pfdate=20201019
options=('!emptydirs' '!strip')
#_patchurl=http://www.rosenauer.org/hg/mozilla/raw-file/$_patchrev
_patchurl=https://raw.githubusercontent.com/openSUSE/firefox-maintenance/$_patchrevsuse
source=(https://ftp.mozilla.org/pub/firefox/releases/$pkgver/source/$_pkgname-$pkgver.source.tar.xz{,.asc}
	#"hg+$_repo#tag=FIREFOX_${pkgver//./_}_RELEASE"
	mozconfig
	plasmafox.desktop
	vendor.js
	kde.js
	pgo-fix-missing-kdejs.patch
	add_missing_pgo_rule.patch
	revert-920beb95b042.patch
    # arch patches
	0001-Use-remoting-name-for-GDK-application-names.patch
	# Plasmafox patchset
	plasmafox-${_pfdate}.patch
	# Firefox patchset
	firefox-kde-$_patchrevsuse.patch::$_patchurl/firefox/firefox-kde.patch
	# Gecko/toolkit patchset
	mozilla-kde-$_patchrevsuse.patch::$_patchurl/mozilla-kde.patch
	mozilla-nongnome-proxies-$_patchrevsuse.patch::$_patchurl/mozilla-nongnome-proxies.patch
	# Menubar
	unity-menubar-r${_mbrev}+.patch
	# System Libs
	0005-bmo-847568-Support-system-harfbuzz.patch
	0006-bmo-847568-Support-system-graphite2.patch
	0007-bmo-1559213-Support-system-av1.patch
	# gentoo patches
	0029-LTO-Only-enable-LTO-for-Rust-when-complete-build-use.patch
	0036-bmo-1634404-Fix-popup-position-when-layout.css.devPi.patch
	# artwork
	about-logo.png
	about-logo@2x.png
	about-wordmark.svg
	plasmafox-wordmark.svg
	about.png
	default{16,22,24,32,48,64,128,256}.png
	# additions
	plasmafox{,-common}.profile
	plasmafox.psd
)
install=plasmafox.install
sha256sums=('8851cae2df9923844c3dc97a4f77f6f3c86cc6f298b888b38949fbf74fcf2ca9'
            'SKIP'
            '504ad23221d2ec6bce1af80ed30fd5c2b3408b11b96e6acac0df7e8df7481820'
            '6897dc8a9ef2a4d1b776e1ffb848c7db2653b4eee87585f62ef002443d58a096'
            '84e7309bcbb984b10e3ca11f85af7eb41fee1681c3564f98ff4a5469a93604a4'
            'b8cc5f35ec35fc96ac5c5a2477b36722e373dbb57eba87eb5ad1276e4df7236d'
            '2214d0df276fc3387aaf2b0facb47960783ea23c4673d9dcbd3a5daacb0f4c91'
            'f9067f62a25a7a77276e15f91cc9e7ba6576315345cfc6347b1b2e884becdb0c'
            '0e538b0cd6890ef35291a2c7ccb17c3de1005af69327db78c29f8e6c311b275c'
            '3bb7463471fb43b2163a705a79a13a3003d70fff4bbe44f467807ca056de9a75'
            '3368ae9de99ecc7f35c061b11837c53f85148aae59eb41016f8f52ebdffbf2c0'
            '4b91fcf04c65a99626f39de89146a2ee01fcf868c3fdde26704796a394c18e68'
            'b86972097f4eb1554de245b6203f5a5c2adf7c04899d987438fcb72c632b709f'
            'fbd95cbcbc32673ef549b43b0d2de3ef0ef4fa303b6336e64993f2c8a73264e4'
            '00f9adb917a9e40c60e6e7c3c339dbad52e515120a71df6a36e66450dee0756a'
            '9563276744f9fa95556bf4772c793b123fd8e789402e0efe1edd7ca92cf7988f'
            '06d641f1868a5b34885116ebf97e8af25c62fec4116980a75ceb460f2d62e187'
            '01b57a48c03527ccfe4304a0988c8b7dccf515e34d5c80b55f05757c2333e41e'
            '1034a3edda8ffa889fcb4dcf57cb93f8f296f7c37e5cfcf1e5c6071a6f8f4261'
            'f124581c57cc86889daa73d023068159cd56d23fa9e1d70784572f717c6ea71d'
            'f908e1ddf9399344dc0d6163d9e23b5966c656cd35d614732e8a1dee7f02f7b4'
            '6f791b85debe8c12d542b2a9f1b6851aea7df28a2f52e762e09b5db8ec11a349'
            'a450b5aee59b15cba4a32e641d189d6d3641965b3916f769362701bbbdb6ba1a'
            'bdb5ff6cf072421a7bfd5d6d525b01ecb449dca0bf2bbe1830c3060571ce7718'
            '5bb9b27c16e09afbd7434840a022da7b83aa10590be9ec3ed150a92c2f420c22'
            '59b6762531cb68ff6e53a162b1c78dfe0db0996f1f3b84487c4e380b940ef939'
            'd0d4cee53baf8cee3e6dcf2d5b508060ffe9ba45f4f7e7b73e8a00258e2e4c1b'
            'c85e92938aae8edabdae08dd38799048385fd21458bbc130baab30cef1558ace'
            '2d3d7f408c6d5a589f737f594028b85bcb372f7738600b629c5c9b3620115256'
            '33226603f128928c0f5a191016793ab2792d8603c5aacd03d83f001c3891872f'
            'ad4aadfe095ad46d43b66fc6e686511c7c4a81d452fb71f2eb4775936fb0179e'
            '7e2062a8df9e9e28c51ff6435872a688cff040fdfa38ef93bf92e52d676e6dbc'
            '0a646abac6405b2e5d3bd0f13dc003e0ed45e1ad5856079274eb2936fa6d321b'
            '83e3f72eb8220a9962791487faa399e7f1fe19e3863cab5f28e83416e6ac2374'
            '022e47dece0dcc8a593a17958fc89bd135af9aa0e4e7f2c1e27dc2573b3949aa'
            '22d33cd66a1e1a8ff2ae086de145490b22c8cc1cb748f0273462a70c563e0b91')

validpgpkeys=(14F26682D0916CDD81E37B6D61B7B526D98F0353)

prepare() {
  #cd mozilla-unified
  cd firefox-${pkgver}
  cp "$srcdir/mozconfig" .mozconfig
  sed -i 's/\"BrowserApplication\"\, \"firefox\"/\"BrowserApplication\"\, \"plasmafox\"/g' $srcdir/firefox-kde-$_patchrevsuse.patch
  sed -i 's/kmozillahelper/kplasmafoxhelper/g' $srcdir/mozilla-kde-$_patchrevsuse.patch

  # multilocale
  # mkdir $srcdir/mozbuild
  # ln -sf /mnt/sparelin/l10n-base $srcdir/mozbuild/l10n-central || exit 4
  # echo "ac_add_options --with-l10n-base=${srcdir}/mozbuild/l10n-central" >> .mozconfig

  # Arch patches
  echo "---- Arch patches"
  patch -Np1 -i ../0001-Use-remoting-name-for-GDK-application-names.patch

  # KDE patches (W. Rosenauer)
  echo "---- Patching for KDE"
  patch -Np1 -i ../mozilla-nongnome-proxies-$_patchrevsuse.patch
  patch -Np1 -i ../mozilla-kde-$_patchrevsuse.patch
  patch -Np1 -i ../firefox-kde-$_patchrevsuse.patch

  # add globalmenu support
  echo "---- Ubuntu global menu"
  patch -R -Np1 -i ../revert-920beb95b042.patch
  patch -Np1 -i ../unity-menubar-r${_mbrev}+.patch

  # add missing file Makefile for pgo builds
  patch -Np1 -i ../pgo-fix-missing-kdejs.patch
  patch -Np1 -i ../add_missing_pgo_rule.patch

  # gentoo patches
  patch -Np1 -i ../0029-LTO-Only-enable-LTO-for-Rust-when-complete-build-use.patch
  patch -Np1 -i ../0036-bmo-1634404-Fix-popup-position-when-layout.css.devPi.patch

  # use more system libs
  echo "---- Patching for system libs"
  patch -Np1 -i ../0005-bmo-847568-Support-system-harfbuzz.patch
  patch -Np1 -i ../0006-bmo-847568-Support-system-graphite2.patch
  patch -Np1 -i ../0007-bmo-1559213-Support-system-av1.patch

  # Plasmafox patches
  echo "---- Plasmafox patches"
  patch -Np1 -i ../plasmafox-${_pfdate}.patch

  # Artwork
  cp "$srcdir/about-wordmark.svg" ./browser/branding/unofficial/content/
  cp "$srcdir/plasmafox-wordmark.svg" ./browser/branding/unofficial/content/
  cp "$srcdir/about-logo.png" ./browser/branding/unofficial/content/
  cp "$srcdir/about-logo@2x.png" ./browser/branding/unofficial/content/
  cp "$srcdir/about.png" ./browser/branding/unofficial/
  for i in 16 22 24 32 48 64 128 256; do
      cp "$srcdir/default$i.png" browser/branding/unofficial/
  done
}

build() {
  cd firefox-${pkgver}
  export MOZ_NOSPAM=1
  export MOZBUILD_STATE_PATH="$srcdir/mozbuild"
  export STRIP=/bin/true
  export MACH_USE_SYSTEM_PYTHON=1

  ulimit -n 4096

  #export PATH=$HOME/clang11/bin:$PATH
  export CC='clang --target=x86_64-unknown-linux-gnu'
  export CXX='clang++ --target=x86_64-unknown-linux-gnu'
  export AR=llvm-ar
  export NM=llvm-nm
  export RANLIB=llvm-ranlib
  export STRIP=llvm-strip

  # Do PGO
  export DISPLAY=:92
  xvfb-run -a -n 92 -s "-screen 0 1920x1080x24 -nolisten tcp" \
  	./mach build

  ./mach buildsymbols

  # multilocale
  #export MOZ_CHROME_MULTILOCALE="de fr pl"
  #for AB_CD in $MOZ_CHROME_MULTILOCALE; do
  #	./mach build chrome-$AB_CD
  #done
}

package() {
  #cd mozilla-unified
  cd firefox-${pkgver}

  cp "$srcdir/kde.js" obj-x86_64-pc-linux-gnu/dist/bin/defaults/pref

  #AB_CD=multi ./mach package
  #DESTDIR="$pkgdir" AB_CD=multi ./mach install
  DESTDIR="$pkgdir" ./mach install

  install -Dvm644 "$srcdir/vendor.js" "$pkgdir/usr/lib/plasmafox/browser/defaults/preferences/vendor.js"
  install -Dvm644 "$srcdir/kde.js" "$pkgdir/usr/lib/plasmafox/browser/defaults/preferences/kde.js"

  install -Dvm644 "$srcdir/plasmafox.profile" "$pkgdir/usr/lib/plasmafox/distribution/plasmafox.profile"
  install -Dvm644 "$srcdir/plasmafox-common.profile" "$pkgdir/usr/lib/plasmafox/distribution/plasmafox-common.profile"
  install -Dvm644 "$srcdir/plasmafox.psd" "$pkgdir/usr/lib/plasmafox/distribution/plasmafox.psd"

  _distini="$pkgdir/usr/lib/plasmafox/distribution/distribution.ini"
  install -Dvm644 /dev/stdin "$_distini" <<END
[Global]
id=plasmafox
version=1.0
about=Plasmafox for Arch compatible distributions

[Preferences]
app.distributor=$pkgname
app.distributor.channel=$pkgname
END

  for i in 16 22 24 32 48 64 128 256; do
      install -Dvm644 browser/branding/unofficial/default$i.png \
        "$pkgdir/usr/share/icons/hicolor/${i}x${i}/apps/plasmafox.png"
  done

  install -Dvm644 browser/branding/unofficial/content/about-logo.png \
    "$pkgdir/usr/share/icons/hicolor/192x192/apps/plasmafox.png"
  install -Dm644 browser/branding/official/content/about-logo@2x.png \
    "$pkgdir/usr/share/icons/hicolor/384x384/apps/plasmafox.png"

  install -Dvm644 "$srcdir/plasmafox.desktop" "$pkgdir/usr/share/applications/plasmafox.desktop"

  # Install a wrapper to avoid confusion about binary path
  install -Dvm755 /dev/stdin "$pkgdir/usr/bin/$pkgname" <<END
#!/bin/sh
exec /usr/lib/$pkgname/plasmafox "\$@"
END

  # Replace duplicate binary with wrapper
  # https://bugzilla.mozilla.org/show_bug.cgi?id=658850
  ln -srfv "$pkgdir/usr/bin/$pkgname" "$pkgdir/usr/lib/$pkgname/plasmafox-bin"

  # Use system certificates
  local nssckbi="$pkgdir/usr/lib/$pkgname/libnssckbi.so"
  if [[ -e $nssckbi ]]; then
    ln -srfv "$pkgdir/usr/lib/libnssckbi.so" "$nssckbi"
  fi

  find . -name '*crashreporter-symbols-full.tar.zst' -exec \
	cp -fvt "$startdir" {} +
}

