# SPDX-License-Identifier: GPL-2.0
#
# Copyright (C) 2016-2019 Yousong Zhou <yszhou4tech@gmail.com>

include $(TOPDIR)/rules.mk

PKG_NAME:=pkcs11-provider
PKG_SOURCE_VERSION:=v1.1.0
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE_PROTO:=git
PKG_MIRROR_HASH:=skip
PKG_SOURCE_URL:=https://github.com/latchset/pkcs11-provider.git

PKG_LICENSE:=Apache_v2
PKG_LICENSE_FILES:=LICENSES/Apache-2.0.txt

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/meson.mk

define Package/$(PKG_NAME)
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=pkcs11-provider
  URL:=https://github.com/latchset/pkcs11-provider/
  DEPENDS:=+libopenssl
endef

define Package/$(PKG_NAME)/description
  This is an Openssl 3.x provider to access Hardware or Software Tokens using the PKCS#11 Cryptographic Token Interface
  This code targets version 3.1 of the interface but should be backwards compatible to previous versions as well.
endef

define Build/Install
	$(INSTALL_DIR) $(PKG_INSTALL_DIR)/usr/lib/ossl-modules
	$(CP) $(MESON_BUILD_DIR)/src/*.so $(PKG_INSTALL_DIR)/usr/lib/ossl-modules/
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib/ossl-modules
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/ossl-modules/*.so $(1)/usr/lib/ossl-modules
endef


$(eval $(call BuildPackage,$(PKG_NAME)))
