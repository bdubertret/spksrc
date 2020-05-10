PKG_NAME = wireguard-linux-compat
PKG_VERS = 1.0.20200506
PKG_EXT = tar.xz
PKG_DIST_SITE = https://git.zx2c4.com/wireguard-linux-compat/snapshot
PKG_DIST_NAME = $(PKG_NAME)-$(PKG_VERS).$(PKG_EXT)
PKG_DIR =  $(PKG_NAME)-$(PKG_VERS)

REQ_KERNEL = 1

HOMEPAGE = https://www.wireguard.com
COMMENT  = WireGuard® is an extremely simple yet fast and modern VPN that utilizes state-of-the-art cryptography. It aims to be faster, simpler, leaner, and more useful than IPsec, while avoiding the massive headache.
LICENSE  = GPLv2

CONFIGURE_TARGET = nope

COMPILE_TARGET = wireguard-linux-compat-compile
INSTALL_TARGET = wireguard-linux-compat-install

include ../../mk/spksrc.cross-cc.mk

.PHONY: wireguard-linux-compat-compile wireguard-linux-compat-install
wireguard-linux-compat-compile:
	$(RUN) && cd $(WORK_DIR)/$(PKG_NAME)-$(PKG_VERS)/src && KERNELDIR=$(KERNEL_DIR) CPPFLAGS="" CFLAGS="" LDFLAGS="" $(MAKE)
wireguard-linux-compat-install:
	install -m 644 $(WORK_DIR)/$(PKG_NAME)-$(PKG_VERS)/src/wireguard.ko $(STAGING_INSTALL_PREFIX)/
