#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=fscryptctl
PKG_VERSION:=1.2.0
PKG_RELEASE:=1
PKG_JOBS:=fscryptctl

PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=v1.2.0
PKG_SOURCE_URL:=https://github.com/google/fscryptctl.git
PKG_MIRROR_HASH:=skip
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

PKG_MAINTAINER:=Joe Richey <joerichey@google.com>, Eric Biggers <ebiggers@google.com>
PKG_LICENSE:=Apache-2.0
PKG_LICENSE_FILES:=LICENSE

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  MENU:=1
  DEPENDS:=
  SECTION:=libs
  CATEGORY:=Libraries
  URL:=https://github.com/google/fscryptctl
  TITLE:=FSCryptCtl for Linux filesystem encryption
endef

define Package/fscryptctl/description
 fscryptctl is a low-level tool written in C that handles raw keys
 and manages policies for Linux filesystem encryption,
 specifically the "fscrypt" kernel interface which is supported
 by the ext4, f2fs, UBIFS, and CephFS filesystems.
endef

define Build/Compile
	$(call Build/Compile/Default, PKG_JOBS=fscryptctl)
endef

define Build/Install
	$(INSTALL_DIR) $(PKG_INSTALL_DIR)/bin
	$(CP) $(PKG_BUILD_DIR)/fscryptctl $(PKG_INSTALL_DIR)/bin/
endef

define Build/InstallDev
endef

define Package/fscryptctl/install
	$(INSTALL_DIR) $(1)/bin
	$(CP) $(PKG_INSTALL_DIR)/bin/fscryptctl $(1)/bin/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
