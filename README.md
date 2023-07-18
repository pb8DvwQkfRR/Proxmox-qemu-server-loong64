# Proxmox-qemu-server-loong64

#### Enable TCG emulation support for LoonArch64 architecture on Proxmox.

```
git clone https://git.proxmox.com/git/pve-qemu.git

	./configure \
	    --with-git-submodules=ignore \
	    --docdir=/usr/share/doc/pve-qemu-kvm \
	    --localstatedir=/var \
	    --prefix=/usr \
	    --sysconfdir=/etc \
---	    --target-list=$(HOST_CPU)-softmmu,aarch64-softmmu \
+++	    --target-list=$(HOST_CPU)-softmmu,aarch64-softmmu,loongarch64-softmmu \
	    --with-suffix="kvm" \
	    --with-pkgversion="${DEB_SOURCE}_${DEB_VERSION_UPSTREAM_REVISION}" \
	    --audio-drv-list="alsa" \
	    --datadir=/usr/share \
	    --libexecdir=/usr/lib/kvm \
	    --disable-capstone \
	    --disable-gtk \
	    --disable-guest-agent \
	    --disable-guest-agent-msi \
	    --disable-libnfs \
	    --disable-libssh \
	    --disable-sdl \
	    --disable-smartcard \
	    --disable-strip \
	    --disable-xen \
	    --enable-curl \
	    --enable-docs \
	    --enable-glusterfs \
	    --enable-gnutls \
	    --enable-libiscsi \
	    --enable-libusb \
	    --enable-linux-aio \
	    --enable-linux-io-uring \
	    --enable-numa \
	    --enable-opengl \
	    --enable-rbd \
	    --enable-seccomp \
	    --enable-slirp \
	    --enable-spice \
	    --enable-usb-redir \
	    --enable-virglrenderer \
	    --enable-virtfs \
	    --enable-zstd

mk-build-deps --install
apt install -y libproxmox-backup*
make deb
```
