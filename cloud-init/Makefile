# cloud-init

include $(TOPDIR)/rules.mk

PKG_NAME:=cloud-init
PKG_VERSION:=0.1
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define Package/cloud-init
  SECTION:=base
  CATEGORY:=Base system
  TITLE:=Cloud Init scripts
endef

define Package/cloud-init/description
Cloud init scripts
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
endef

define Build/Compile/Default
endef

define Build/Compile
	$(call Build/Compile/Default)
endef

define Package/cloud-init/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/cloud* $(1)/etc/init.d/
endef

$(eval $(call BuildPackage,cloud-init))

