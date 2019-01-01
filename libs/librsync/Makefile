#
# Copyright (C) 2019 Adam Romanek <romanek.adam@gmail.com>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=librsync
PKG_VERSION:=2.0.2
PKG_RELEASE:=1

PKG_SOURCE:=v$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/librsync/$(PKG_NAME)/archive/
PKG_HASH:=e67b9520ee84f7239be6e948795803bd95495091cc00bf6d0e8c6976032a4af1

PKG_LICENSE:=LGPL-2.1
PKG_LICENSE_FILES:=COPYING

CMAKE_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/librsync
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=Remote delta-compression library
	URL:=https://librsync.github.io/
endef

define Package/librsync/description
	Remote delta-compression library
endef

define Package/librsync/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/librsync.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,librsync))
