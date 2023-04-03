include $(TOPDIR)/rules.mk

PKG_NAME:=libtar
PKG_RELEASE:=1
PKG_VERSION:=gen_1.2.20_v1.0.1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=$(PKG_VERSION)
PKG_SOURCE_URL:=git@gitlab.com:soft.at.home/opensource/libtar.git
PKG_MIRROR_HASH:=skip

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=COPYRIGHT

PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

CONFIGURE_ARGS += 

define Package/$(PKG_NAME)
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=C library for manipulating tar files
  URL:=https://gitlab.com/soft.at.home/opensource/libtar
  DEPENDS:=
endef

define Package/$(PKG_NAME)/description
	libtar is a library for manipulating tar files from within C programs.
	Here are some of its features:
	* Handles both POSIX tar file format and the GNU extensions.
	* API provides functions for easy use, such as tar_extract_all().
	* Also provides functions for more granular use, such as tar_append_regfile().
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/*.h $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/*.so* $(1)/usr/lib/
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/*.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
