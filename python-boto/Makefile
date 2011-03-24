# Boto

include $(TOPDIR)/rules.mk

PKG_NAME:=python-boto
PKG_VERSION:=1.9b
PKG_RELEASE:=1

PKG_SOURCE:=boto-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://boto.googlecode.com/files
PKG_MD5SUM:=4fc2fd7b70a971b1363f8465aafe7091
PKG_BUILD_DIR:=$(BUILD_DIR)/boto-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-boto
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=Boto
  URL:=http://code.google.com/p/boto/
  DEPENDS:=+python
endef

define Package/python-boto/description
Boto is an integrated interface to current and future infrastructural 
services offered by Amazon Web Services.
endef

#define Build/Prepare
#	$(call Build/Prepare/Default)
#endef

#define Build/Configure
#	echo "[build_ext]" >>$(PKG_BUILD_DIR)/setup.cfg
#	echo "openssl=$(OPENSSL)" >>$(PKG_BUILD_DIR)/setup.cfg
#endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/python-boto/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) $(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* $(1)$(PYTHON_PKG_DIR)
endef

$(eval $(call BuildPackage,python-boto))
