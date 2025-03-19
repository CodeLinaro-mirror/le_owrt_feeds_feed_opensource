include $(TOPDIR)/rules.mk

PKG_NAME:=libpcp
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=46341d68a605558c765f01e2b28a3bfa04002eb6
PKG_SOURCE_DATE:=2025-03-18
PKG_SOURCE_URL:=https://github.com/libpcpnatpmp/libpcpnatpmp
PKG_MIRROR_HASH:=370f4fd933de17084c9e6939d8fde4f0b82355253597535b14260262fb20b002

PKG_LICENSE:=BSD-2-Clause
PKG_LICENSE_FILES:=COPYING

PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

CONFIGURE_ARGS += --disable-server --disable-app

define Package/$(PKG_NAME)
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=PCP client library implements client side of PCP
  URL:=https://github.com/libpcpnatpmp/libpcpnatpmp
  DEPENDS:=
endef

define Package/$(PKG_NAME)/description
  PCP client library implements client side of PCP (RFC 6887) and NATPMP(RFC
  6886) protocols.  Switch to NATPMP is done automatically by version
  negotiation.  This library enables any network application to manage network
  edge device (e.g. to create NAT mapping or ask router for specific flow
  treatment).
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/pcp-client
	$(CP) $(PKG_INSTALL_DIR)/usr/include/pcp-client $(1)/usr/include
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/*.so* $(1)/usr/lib/
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/*.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
