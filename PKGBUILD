pkgname='thinkpad-l390-yoga-scripts-git'
_gitname='thinkpad-l390-yoga-scripts'
pkgver=20190507
pkgrel=1
pkgdesc='A simple set of scripts to control screen rotation and tablet mode for the Lenovo L390 Yoga, based on thinkpad-l380-yoga-scripts by ffejery and linux_detect_tablet_mode by alesguzik'
url="https://github.com/ffejery/thinkpad-l380-yoga-scripts"
source=('thinkpad-l380-yoga-scripts::git+https://github.com/ffejery/thinkpad-l380-yoga-scripts')
license=('GPL3')
arch=('any')
depends=('xorg-xrandr' 'xorg-xinput' 'xbindkeys' 'kbd' 'systemd' 'gawk' 'feh')
conflicts=('thinkpad-yoga-scripts-git' 'thinkpad-l390-yoga-scripts-git')
provides=('thinkpad-yoga-scripts-git' 'thinkpad-l390-yoga-scripts-git')
optdepends=(
	'onboard: onscreen keyboard'
	'xf86-input-wacom: for digitizer support'
	)
md5sums=('SKIP')
makedepends=('git')

pkgver() {
  cd "$_gitname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  cd $srcdir/$_gitname

  # Install scripts into /opt
  mkdir -p "$pkgdir/opt/$_gitname"
  ## Rotate scripts
  cp -r rotate.py "$pkgdir/opt/$_gitname"
  ## Watch tablet
  cp -r watch_tablet "$pkgdir/opt/$_gitname"

  # ThinkPad Yoga Systemd Service
  mkdir -p "$pkgdir/usr/lib/systemd/system/"
  cp *.service "$pkgdir/usr/lib/systemd/system/"

  # Install license
  install -D -m644 "LICENSE" "$pkgdir/usr/share/licenses/$_gitname/LICENSE"
}

 
