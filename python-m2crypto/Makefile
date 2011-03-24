# M2Crypto

include $(TOPDIR)/rules.mk

PKG_NAME:=python-m2crypto
PKG_VERSION:=0.21.1
PKG_RELEASE:=1

PKG_SOURCE:=M2Crypto-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://pypi.python.org/packages/source/M/M2Crypto/
PKG_MD5SUM:=f93d8462ff7646397a9f77a2fe602d17
PKG_BUILD_DEPENDS:=+swig/host
PKG_BUILD_DIR:=$(BUILD_DIR)/M2Crypto-$(PKG_VERSION)

OPENSSL:=../openssl-0.9.8p

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-m2crypto
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=MeTooCrypto
  URL:=http://chandlerproject.org/Projects/MeTooCrypto
  DEPENDS:=+python
endef

define Package/python-m2crypto/description
M2Crypto is the most complete Python wrapper for OpenSSL.
endef

define Build/Prepare
	$(call Build/Prepare/Default)
endef

define Build/Configure
	echo "[build_ext]" >>$(PKG_BUILD_DIR)/setup.cfg
	echo "openssl=$(OPENSSL)" >>$(PKG_BUILD_DIR)/setup.cfg
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/python-m2crypto/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) $(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* $(1)$(PYTHON_PKG_DIR)
endef

$(eval $(call BuildPackage,python-m2crypto))
