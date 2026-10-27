# incus-agent

include $(TOPDIR)/rules.mk

PKG_NAME:=incus-agent
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_LICENSE:=MIT

include $(INCLUDE_DIR)/package.mk

define Package/incus-agent
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Incus VM agent launcher
  DEPENDS:=+kmod-9pnet +kmod-fs-9p +kmod-vsock-virtio
  PKGARCH:=all
endef

define Package/incus-agent/description
  procd service that enables incus exec, incus file and state reporting in
  OpenWrt VMs: stage and run the incus-agent supplied by the Incus host
  (via the 9p "config" share or the agent:config CD-ROM)
endef

define Build/Compile
endef

define Package/incus-agent/install
	$(INSTALL_DIR) $(1)/etc/init.d $(1)/usr/libexec
	$(INSTALL_BIN) ./files/incus-agent.init $(1)/etc/init.d/incus-agent
	$(INSTALL_BIN) ./files/incus-agent-setup $(1)/usr/libexec/incus-agent-setup
endef

$(eval $(call BuildPackage,incus-agent))
