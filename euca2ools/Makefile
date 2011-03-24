# Euca2ools

include $(TOPDIR)/rules.mk

PKG_NAME:=euca2ools
PKG_VERSION:=1.3.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://eucalyptussoftware.com/downloads/releases
PKG_MD5SUM:=a835e8fabd5875a5c8dbcba1bf89d402
#PKG_BUILD_DIR:=$(BUILD_DIR)/boto-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/euca2ools
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=Euca2ools
  URL:=http://open.eucalyptus.com/downloads
  DEPENDS:=+python +python-boto +python-m2crypto
endef

define Package/euca2ools/description
Euca2ools are command-line tools for interacting with Web services that 
export a REST/Query-based API compatible with Amazon EC2 and S3 services.
endef

#define Build/Prepare
#	$(call Build/Prepare/Default)
#endef

define Build/Configure
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR) \
		PREFIX="/usr" \
		DESTDIR=$(PKG_INSTALL_DIR) \
		build
endef

define Package/euca2ools/install
	$(MAKE) -C $(PKG_BUILD_DIR) \
		PREFIX="/usr" \
		DESTDIR=$(PKG_INSTALL_DIR) \
		install
	$(INSTALL_DIR) $(1)/usr/bin 
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin
endef

$(eval $(call BuildPackage,euca2ools))
