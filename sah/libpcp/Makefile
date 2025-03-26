include $(TOPDIR)/rules.mk

PKG_NAME:=libpcp
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=721c40c4c0cc2f08e1c7046dd577f2cdea6344e2
PKG_SOURCE_DATE:=2025-03-19
PKG_SOURCE_URL:=https://github.com/libpcpnatpmp/libpcpnatpmp
PKG_MIRROR_HASH:=387a53ce6a49340b1fdb95e4fba7c95b6d7485930fdd029afcc23f59e031149a

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
