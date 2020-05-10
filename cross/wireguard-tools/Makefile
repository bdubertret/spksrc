PKG_NAME = wireguard-tools
PKG_VERS = 1.0.20200319
PKG_EXT = tar.xz
PKG_DIST_SITE = https://git.zx2c4.com/wireguard-tools/snapshot
PKG_DIST_NAME = $(PKG_NAME)-$(PKG_VERS).$(PKG_EXT)
PKG_DIR =  $(PKG_NAME)-$(PKG_VERS)

REQ_KERNEL = 1

HOMEPAGE = https://www.wireguard.com
COMMENT  = WireGuard® is an extremely simple yet fast and modern VPN that utilizes state-of-the-art cryptography. It aims to be faster, simpler, leaner, and more useful than IPsec, while avoiding the massive headache.
LICENSE  = GPLv2

DEPENDS = cross/libmnl

CONFIGURE_TARGET = nope

COMPILE_TARGET = wireguard-tools-compile
INSTALL_TARGET = wireguard-tools-install

include ../../mk/spksrc.cross-cc.mk

.PHONY: wireguard-tools-compile wireguard-tools-install
wireguard-tools-compile:
	$(RUN) && cd $(WORK_DIR)/$(PKG_NAME)-$(PKG_VERS)/src && $(MAKE)
wireguard-tools-install:
	install -m 755 -d $(STAGING_INSTALL_PREFIX)/bin
	install -m 755 $(WORK_DIR)/$(PKG_NAME)-$(PKG_VERS)/src/wg $(STAGING_INSTALL_PREFIX)/bin
	install -m 755 $(WORK_DIR)/$(PKG_NAME)-$(PKG_VERS)/src/wg-quick/linux.bash $(STAGING_INSTALL_PREFIX)/bin/wg-quick

