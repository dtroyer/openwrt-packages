#
# Copyright (C) 2007 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.

include $(TOPDIR)/rules.mk

PKG_NAME:=jq
PKG_VERSION:=1.5
PKG_RELEASE:=1

#https://github.com/stedolan/jq/releases/download/jq-1.5/jq-1.5.tar.gz
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/stedolan/jq/releases/download/$(PKG_NAME)-$(PKG_VERSION)/
PKG_MD5SUM:=0933532b086bd8b6a41c1b162b1731f9

PKG_LICENSE_FILES:=COPYING
PKG_MAINTAINER:=Dean Troyer <dtroyer@gmail.com>

PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/jq
  SECTION:=base
  CATEGORY:=Base system
  TITLE:=JSON query
  URL:=https://stedolan.github.io/jq/
  DEPENDS:=@!LINUX_2_4 #+libuuid
endef

define Package/jq/description
	jq is a lightweight and flexible command-line JSON processor.

	jq is like sed for JSON data - you can use it to slice and filter
	and map and transform structured data with the same ease that sed,
	awk, grep and friends let you play with text.

	jq is written in portable C, and it has zero runtime dependencies.
	You can download a single binary, scp it to a far away machine of
	the same type, and expect it to work.
endef

#CONFIGURE_ARG= --disable-maintainer-mode

define Package/jq/install	
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/jq $(1)/usr/bin	
endef

$(eval $(call BuildPackage,jq))
