# Maintainer: Aun-Ali Zaidi <admin@kodeit.net>
# Contributor: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>

pkgbase=linux-mbp
pkgver=5.9.16
_srcname=linux-${pkgver}
pkgrel=1
pkgdesc='Linux for MBP'
_srctag=v${pkgver%.*}-${pkgver##*.}
url="https://git.archlinux.org/linux.git/log/?h=v$_srctag"
arch=(x86_64)
license=(GPL2)
makedepends=(
  bc kmod libelf pahole cpio perl tar xz
  xmlto python-sphinx python-sphinx_rtd_theme graphviz imagemagick
  git
)
options=('!strip')

source=(
  https://www.kernel.org/pub/linux/kernel/v${pkgver//.*}.x/linux-${pkgver}.tar.xz
  https://www.kernel.org/pub/linux/kernel/v${pkgver//.*}.x/linux-${pkgver}.tar.sign
  config         # the main kernel config file
  sphinx-workaround.patch

  # Arch Linux patches
  0001-ZEN-Add-sysctl-and-CONFIG-to-disallow-unprivileged-C.patch
  0002-Bluetooth-Fix-LL-PRivacy-BLE-device-fails-to-connect.patch
  0003-Bluetooth-Fix-attempting-to-set-RPA-timeout-when-uns.patch
  0004-HID-quirks-Add-Apple-Magic-Trackpad-2-to-hid_have_sp.patch

  # Hack for AMD DC eDP link rate bug
  2001-drm-amd-display-Force-link_rate-as-LINK_RATE_RBR2-fo.patch

  # Apple SMC ACPI support
  3001-applesmc-convert-static-structures-to-drvdata.patch
  3002-applesmc-make-io-port-base-addr-dynamic.patch
  3003-applesmc-switch-to-acpi_device-from-platform.patch
  3004-applesmc-key-interface-wrappers.patch
  3005-applesmc-basic-mmio-interface-implementation.patch
  3006-applesmc-fan-support-on-T2-Macs.patch

  # T2 USB Keyboard/Touchpad support
  4001-HID-apple-Add-support-for-keyboard-backlight-on-supp.patch
  4002-HID-apple-Add-support-for-MacbookAir8-1-keyboard-tra.patch
  4003-HID-apple-Add-support-for-MacBookPro15-2-keyboard-tr.patch
  4004-HID-apple-Add-support-for-MacBookPro15-1-keyboard-tr.patch
  4005-HID-apple-Add-support-for-MacBookPro15-4-keyboard-tr.patch
  4006-HID-apple-Add-support-for-MacBookPro16-2-keyboard-tr.patch
  4007-HID-apple-Add-support-for-MacBookAir9-1-keyboard-tra.patch
  4008-HID-apple-Add-support-for-MacBookPro16-1-keyboard-tr.patch

  # Broadcom Wifi rambase debugging additions
  5001-brcmfmac-move-brcmf_mp_device-into-its-own-header.patch
  5002-brcmfmac-Add-ability-to-manually-specify-FW-rambase-.patch

  # MBP Peripheral support
  6001-media-uvcvideo-Add-support-for-Apple-T2-attached-iSi.patch	# UVC Camera support

  # Hack for i915 overscan issues
  7001-drm-i915-fbdev-Discard-BIOS-framebuffers-exceeding-h.patch

  # Broadcom WIFI/BT device support
  8001-brcmfmac-Add-initial-support-for-the-BRCM4355.patch
  8002-brcmfmac-Add-initial-support-for-the-BRCM4377.patch
)

validpgpkeys=(
  'ABAF11C65A2970B130ABE3C479BE3E4300411886'  # Linus Torvalds
  '647F28654894E3BD457199BE38DBBDC86092693E'  # Greg Kroah-Hartman
)

sha256sums=('b0d7abae88e5f91893627c645e680a95c818defd1b4fcaf3e2afb4b2b6b4ab86'
            'SKIP'
            'c008673216498690f296cf74fc42ec0874ab4b3802f610dfb2acfa2f268edb98'
            '8cb21e0b3411327b627a9dd15b8eb773295a0d2782b1a41b2a8839d1b2f5778c'
            '043f50b0b4d46fd3a92050ccac5ee814ced56f40377501e7aa64373072723d28'
            '3b59e6f5dcdbb1a109cdac98e715bf120a7d6e59bb6befda133b50c1f7d0fe41'
            '4c66abadb92dd781975384e515631bad702b772b9c34c9654ee27119daddca5d'
            '75701d7395b682335aa6fc4fb625d2f80bf9009ca8dceafc06f27c16e45fa794'
            '786dfc22e4c6ece883e7dedd0ba3f6c14018584df95450b2cb78f3da8b01f7cb'
            '41b6ddf1aacc4aa2eb5ea1a2e4c4861143e89f5c0846d1f2f18a1a2abc6ca1e6'
            '06a1f3f9b3d137cdf91ff33c92e60cf20fd1a06d40fbbd868af5e1d0bed5a161'
            'e61358ade79af985a1a3f30b6c80e739d4a2bb8f5d8405befa9b05374027d101'
            '4a9ea26412c648036ed48a0dbc3883741e5f6ccd262fe459bee13ab2527f6fac'
            'eac6c381860b5cfe25596263cc375e24f99715b4f1a774792db0d6a56915a5e3'
            '987c68b118c3b2a073523824ca59fe99d047442027120af1cf945f0043256d91'
            '8cb46bf2e11d4f54a6cefe39d3f2808e44e8e96efafac891ab2b7d2e30cbc09f'
            '5c7951ca03ffef1c8083c1d625ad98a4b6f756df04f153f057f3b16aafa268b7'
            '8f8042185376157f429f809c193d139920bfe01989ca729cf35e96916891b1e6'
            '0b44ac994d455add8bfa0badb93e5e161c7b65d5816da46f9828844a85256dc7'
            '7cf9dfed7e5e6712d228e78440adcb1f931eae138992ee0ae9c11be97e5719d6'
            'b0b918e10d2bfab0a1be7475f98a7f3155bc537b70c70328b34553ccc8bd6909'
            '25d27b2b49d08759cb80b53dac2809a2b934c6ea9195d650d297b859709b965c'
            '0de44eff8e9c82a1e25152c20b46b78189c8858bf6cb071f325148fdada37921'
            '4d22727c1456e268de1c39ac73f2dc0c1630ac25aa66364d99f94e29eba5c6b9'
            '7f41e52285bbdeeaf565e7a1e69860439a4cc302092b473301040f29fc2f5b64'
            '9640178d6251686c980c30fc528b3d70beac6ce8246bf433506a3f843808326c'
            '90a6012cdd8a64ede8e0bbaf7331960bd68f628e0973b65459188eb1ccb5b829'
            '3a7baa28d5f45bdbff23e838133f2e3c6896412ffb5a919b4992a7b2d17469d9'
            'edb804461e3820ef3397e1e236f7caabf906b6a13d03f406c8462ec476ecbbe5')

export KBUILD_BUILD_HOST=archlinux
export KBUILD_BUILD_USER=$pkgbase
export KBUILD_BUILD_TIMESTAMP="$(date -Ru${SOURCE_DATE_EPOCH:+d @$SOURCE_DATE_EPOCH})"

prepare() {
  cd $_srcname

  echo "Setting version..."
  scripts/setlocalversion --save-scmversion
  echo "-$pkgrel" > localversion.10-pkgrel
  echo "${pkgbase#linux}" > localversion.20-pkgname

  local src
  for src in "${source[@]}"; do
    src="${src%%::*}"
    src="${src##*/}"
    [[ $src = *.patch ]] || continue
    echo "Applying patch $src..."
    patch -Np1 < "../$src"
  done

  echo "Setting config..."
  cp ../config .config
  make olddefconfig

  make -s kernelrelease > version
  echo "Prepared $pkgbase version $(<version)"
}

build() {
  cd $_srcname
  make all
  make htmldocs
}

_package() {
  pkgdesc="The $pkgdesc kernel and modules"
  depends=(coreutils kmod initramfs)
  optdepends=('crda: to set the correct wireless channels of your country'
              'linux-firmware: firmware images needed for some devices')
  provides=(VIRTUALBOX-GUEST-MODULES WIREGUARD-MODULE)
  replaces=(virtualbox-guest-modules-arch wireguard-arch)
  provides=("linux=$pkgver")

  cd $_srcname
  local kernver="$(<version)"
  local modulesdir="$pkgdir/usr/lib/modules/$kernver"

  echo "Installing boot image..."
  # systemd expects to find the kernel here to allow hibernation
  # https://github.com/systemd/systemd/commit/edda44605f06a41fb86b7ab8128dcf99161d2344
  install -Dm644 "$(make -s image_name)" "$modulesdir/vmlinuz"

  # Used by mkinitcpio to name the kernel
  echo "$pkgbase" | install -Dm644 /dev/stdin "$modulesdir/pkgbase"

  echo "Installing modules..."
  make INSTALL_MOD_PATH="$pkgdir/usr" INSTALL_MOD_STRIP=1 modules_install

  # remove build and source links
  rm "$modulesdir"/{source,build}
}

_package-headers() {
  pkgdesc="Headers and scripts for building modules for the $pkgdesc kernel"
  provides=("linux-headers=$pkgver")

  cd $_srcname
  local builddir="$pkgdir/usr/lib/modules/$(<version)/build"

  echo "Installing build files..."
  install -Dt "$builddir" -m644 .config Makefile Module.symvers System.map \
    localversion.* version vmlinux
  install -Dt "$builddir/kernel" -m644 kernel/Makefile
  install -Dt "$builddir/arch/x86" -m644 arch/x86/Makefile
  cp -t "$builddir" -a scripts

  # add objtool for external module building and enabled VALIDATION_STACK option
  install -Dt "$builddir/tools/objtool" tools/objtool/objtool

  # add xfs and shmem for aufs building
  mkdir -p "$builddir"/{fs/xfs,mm}

  echo "Installing headers..."
  cp -t "$builddir" -a include
  cp -t "$builddir/arch/x86" -a arch/x86/include
  install -Dt "$builddir/arch/x86/kernel" -m644 arch/x86/kernel/asm-offsets.s

  install -Dt "$builddir/drivers/md" -m644 drivers/md/*.h
  install -Dt "$builddir/net/mac80211" -m644 net/mac80211/*.h

  # http://bugs.archlinux.org/task/13146
  install -Dt "$builddir/drivers/media/i2c" -m644 drivers/media/i2c/msp3400-driver.h

  # http://bugs.archlinux.org/task/20402
  install -Dt "$builddir/drivers/media/usb/dvb-usb" -m644 drivers/media/usb/dvb-usb/*.h
  install -Dt "$builddir/drivers/media/dvb-frontends" -m644 drivers/media/dvb-frontends/*.h
  install -Dt "$builddir/drivers/media/tuners" -m644 drivers/media/tuners/*.h

  echo "Installing KConfig files..."
  find . -name 'Kconfig*' -exec install -Dm644 {} "$builddir/{}" \;

  echo "Removing unneeded architectures..."
  local arch
  for arch in "$builddir"/arch/*/; do
    [[ $arch = */x86/ ]] && continue
    echo "Removing $(basename "$arch")"
    rm -r "$arch"
  done

  echo "Removing documentation..."
  rm -r "$builddir/Documentation"

  echo "Removing broken symlinks..."
  find -L "$builddir" -type l -printf 'Removing %P\n' -delete

  echo "Removing loose objects..."
  find "$builddir" -type f -name '*.o' -printf 'Removing %P\n' -delete

  echo "Stripping build tools..."
  local file
  while read -rd '' file; do
    case "$(file -bi "$file")" in
      application/x-sharedlib\;*)      # Libraries (.so)
        strip -v $STRIP_SHARED "$file" ;;
      application/x-archive\;*)        # Libraries (.a)
        strip -v $STRIP_STATIC "$file" ;;
      application/x-executable\;*)     # Binaries
        strip -v $STRIP_BINARIES "$file" ;;
      application/x-pie-executable\;*) # Relocatable binaries
        strip -v $STRIP_SHARED "$file" ;;
    esac
  done < <(find "$builddir" -type f -perm -u+x ! -name vmlinux -print0)

  echo "Stripping vmlinux..."
  strip -v $STRIP_STATIC "$builddir/vmlinux"

  echo "Adding symlink..."
  mkdir -p "$pkgdir/usr/src"
  ln -sr "$builddir" "$pkgdir/usr/src/$pkgbase"
}

_package-docs() {
  pkgdesc="Documentation for the $pkgdesc kernel"

  cd $_srcname
  local builddir="$pkgdir/usr/lib/modules/$(<version)/build"

  echo "Installing documentation..."
  local src dst
  while read -rd '' src; do
    dst="${src#Documentation/}"
    dst="$builddir/Documentation/${dst#output/}"
    install -Dm644 "$src" "$dst"
  done < <(find Documentation -name '.*' -prune -o ! -type d -print0)

  echo "Adding symlink..."
  mkdir -p "$pkgdir/usr/share/doc"
  ln -sr "$builddir/Documentation" "$pkgdir/usr/share/doc/$pkgbase"
}

pkgname=("$pkgbase" "$pkgbase-headers" "$pkgbase-docs")
for _p in "${pkgname[@]}"; do
  eval "package_$_p() {
    $(declare -f "_package${_p#$pkgbase}")
    _package${_p#$pkgbase}
  }"
done

# vim:set ts=8 sts=2 sw=2 et:
