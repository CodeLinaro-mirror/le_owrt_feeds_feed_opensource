#
# Copyright (C) 2014, 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=yajl
PKG_VERSION:=2.1.0
PKG_RELEASE:=4

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/lloyd/yajl
PKG_SOURCE_VERSION:=$(PKG_VERSION)
PKG_MIRROR_HASH:=skip

PKG_MAINTAINER:=Charles Southerland <charlie@stuphlabs.com>
PKG_LICENSE:=ISC
PKG_LICENSE_FILES:=COPYING
PKG_CPE_ID:=cpe:/a:yajl_project:yajl

CMAKE_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/host-build.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/yajl
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=Yet Another JSON Library
  URL:=https://lloyd.github.io/yajl
endef

define Package/yajl/description
  Yet Another JSON Library. YAJL is a small event-driven (SAX-style)
JSON parser written in ANSI C, and a small validating JSON generator.
YAJL is released under the ISC license.

  YAJL was created by Lloyd Hilaiel.
endef

define Package/yajl/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libyajl.so* $(1)/usr/lib/
endef

define Host/Install
	mkdir -p $(STAGING_DIR_HOSTPKG)/include
	mkdir -p $(STAGING_DIR_HOSTPKG)/lib
	mkdir -p $(STAGING_DIR_HOSTPKG)/lib/pkgconfig
	$(CP) $(HOST_BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)/include/yajl $(STAGING_DIR_HOSTPKG)/include
	$(CP) $(HOST_BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)/lib/* $(STAGING_DIR_HOSTPKG)/lib
	$(CP) $(HOST_BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)/share/pkgconfig/yajl.pc $(STAGING_DIR_HOSTPKG)/lib/pkgconfig
endef

$(eval $(call BuildPackage,yajl))
$(eval $(call HostBuild))
