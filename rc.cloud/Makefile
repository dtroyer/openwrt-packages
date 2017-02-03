# rc.cloud

include $(TOPDIR)/rules.mk

PKG_NAME:=rc.cloud
PKG_VERSION:=0.1
PKG_RELEASE:=3

include $(INCLUDE_DIR)/package.mk

define Package/rc.cloud
  SECTION:=base
  CATEGORY:=Base system
  TITLE:=RC commands for cloud instance
  DEPENDS:=+wget
endef

define Package/rc.cloud/description
RC commands for cloud instance
Minimal shell implementation of smoser's cloud-init
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
endef

define Build/Compile/Default
endef

define Build/Compile
	$(call Build/Compile/Default)
endef

define Package/rc.cloud/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/rc.cloud* $(1)/etc/init.d/
endef

$(eval $(call BuildPackage,rc.cloud))

