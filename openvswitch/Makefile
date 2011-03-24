# OpenvSwitch

include $(TOPDIR)/rules.mk

PKG_NAME:=openvswitch
PKG_VERSION:=1.1.0pre2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://openvswitch.org/releases/
PKG_MD5SUM:=edec2b67ec26d683b767c0f86a7de8d1

include $(INCLUDE_DIR)/package.mk

define Package/openvswitch
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Open vSwitch
  URL:=http://openvswitch.org
  DEPENDS:=+libopenssl +librt
endef

define Package/openvswitch/description
Open vSwitch provides standard network bridging functions augmented with
support for the OpenFlow protocol for remote per-flow control of traffic.
endef

CONFIGURE_ARGS += \
	--prefix=/usr \
	--sysconfdir=/etc \
	--localstatedir=/var \
	--enable-ssl

TARGET_CFLAGS += -std=c99
TARGET_LDFLAGS += -lrt

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR) \
		CFLAGS="$(TARGET_CFLAGS)" \
		LDFLAGS="$(TARGET_LDFLAGS)"
endef

define Package/openvswitch/install
	$(MAKE) -C $(PKG_BUILD_DIR) \
		PREFIX="/usr" \
		DESTDIR=$(PKG_INSTALL_DIR) \
		install
	$(INSTALL_DIR) $(1)/usr/bin 
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin
endef

$(eval $(call BuildPackage,openvswitch))
