# Contributor:
# Maintainer:
pkgname="usbmount"
pkgver="0.0.23"
pkgrel=0
pkgdesc="Automatically mounts USB mass storage devices when they are plugged in."
url="tbd"
arch="noarch"
license="tbd"
depends="eudev lockfile-progs"
install="$pkgname.pre-install $pkgname.pre-deinstall $pkgname.post-deinstall"
options="!check"
source="
	00_create_model_symlink
	00_remove_model_symlink
	usbmount
	usbmount.conf
	90-usbmount.rules
	"

package() {
	install -m755 -D "$srcdir"/00_create_model_symlink "$pkgdir"/etc/usbmount/mount.d/00_create_model_symlink
	install -m755 -D "$srcdir"/00_remove_model_symlink "$pkgdir"/etc/usbmount/umount.d/00_remove_model_symlink
	install -m755 -D "$srcdir"/usbmount "$pkgdir"/usr/share/usbmount/usbmount
	install -m644 -D "$srcdir"/usbmount.conf "$pkgdir"/etc/usbmount/usbmount.conf
	install -m644 -D "$srcdir"/90-usbmount.rules "$pkgdir"/lib/udev/rules.d/90-usbmount.rules
}
sha512sums="1779a9d3f7286ea40cbb987a21e0d67377c9cc781af9f09d634d3dcf50046394476ea52940dbf00c4a396520351087e273d2dd1e59e0445c9e2d2c2b0b37dbf8  00_create_model_symlink
9bafc42f3f2110f51fde82de9954ab73d93cc6325a7e9476f6c010bfadcdeb03ec2caf47c6585335b737251b0e53d96a89f76325f5969b1b307c0750f414b96c  00_remove_model_symlink
22ca0c594abfd5f2411c0d165454283a4d5692bcb961cb78847a468dd8689087440bdc158a515833fa8e85a58cee61d18340cac3f05673ba35cee02d07218584  usbmount
9ed1b79b06e1bb2566b195f4ca80bab56c8f44788303842bae066fbd10bdac80fbe4e8ba5c41fb1a6eabe2a0e4afcc7a5440f050a6ecdf98efae267271ff448b  usbmount.conf
d833b27ad7fa91bda62d951a79860f030465f1460691da90fa1fe12142da2b9a6fd49c4686e186d55cc81c4a4d2b7024c1af689fe9bcc0f20913d213871088da  90-usbmount.rules"
