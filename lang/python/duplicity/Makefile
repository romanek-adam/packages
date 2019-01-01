# Copyright (C) 2019 Adam Romanek <romanek.adam@gmail.com>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=duplicity
PKG_VERSION:=0.7.19
PKG_RELEASE:=1
PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=COPYING

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://code.launchpad.net/duplicity/0.7-series/$(PKG_VERSION)/+download/
PKG_HASH:=a6aa905a63df5101193d3e8fd4ffdf35acb9307b184ac7a9d68a76aaed6ce929

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk

define Package/duplicity
	SUBMENU:=Python
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=Encrypted bandwidth-efficient backup using the rsync algorithm
	URL:=http://duplicity.nongnu.org/
	DEPENDS:=+python +librsync +gnupg
endef

define Package/duplicity/description
	Encrypted bandwidth-efficient backup using the rsync algorithm
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/duplicity/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) \
	    $(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
	    $(1)$(PYTHON_PKG_DIR)
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/duplicity* \
	    $(1)/usr/bin
	# fix python exec path in scripts
	#$(SED) 's/#!.*/#!\/usr\/bin\/python/g' $(1)/usr/bin/gunicorn*
endef

$(eval $(call BuildPackage,duplicity))
