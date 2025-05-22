include $(TOPDIR)/rules.mk

PKG_NAME:=cmocka
PKG_VERSION:=1.1.7
PKG_RELEASE:=1

PKG_SOURCE:=cmocka-cmocka-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://gitlab.com/cmocka/cmocka/-/archive/cmocka-$(PKG_VERSION)
PKG_HASH:=243344de12f8df78fa639fb426dd02d4cb37eda61462e48e6a0e13a98b94602a
PKG_BUILD_DIR:=$(BUILD_DIR)/cmocka-cmocka-$(PKG_VERSION)
PKG_MAINTAINER:=Soft At Home <support.opensource@softathome.com>

PKG_LICENSE:=Apache-2.0
PKG_LICENSE_FILES:=COPYING

PKG_INSTALL:=1

CMAKE_BINARY_SUBDIR:=cmake_binary_subdir

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/cmocka
  SECTION:=Utils
  CATEGORY:=Utilities
  TITLE:=Unit testing framework for C with support for mock objects
  URL:=https://gitlab.com/cmocka/cmocka
endef

define Package/cmocka/description
 An elegant unit testing framework for C with support for mock objects.
 It only requires the standard C library, works on a range of computing platforms
 (including embedded) and with different compilers.
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libcmocka.so* $(1)/usr/lib
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/* $(1)/usr/lib/pkgconfig
endef

define Package/cmocka/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libcmocka.so* $(1)/usr/lib
endef

$(eval $(call BuildPackage,cmocka))
