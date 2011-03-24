# swig

include $(TOPDIR)/rules.mk

PKG_NAME:=swig
PKG_VERSION:=2.0.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=@SF/swig
PKG_MD5SUM:=eaf619a4169886923e5f828349504a29

include $(INCLUDE_DIR)/host-build.mk
include $(INCLUDE_DIR)/package.mk

define Package/swig
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Simplified Wrapper and Interface Generator
  URL:=http://www.swig.org
  DEPENDS:=+swig/host
endef

define Package/swig/description
SWIG is a software development tool that connects programs written in C and
C++ with a variety of high-level programming languages. SWIG is used with
different types of target languages including common scripting languages such
as Perl, PHP, Python, Tcl and Ruby.

You don\'t need to enable this package to build packages that rely on SWIG.
Instead just add \'+swig/host\' to the PKG_BUILD_DEPENDS line of your
package.
endef

# Compile for host

HOST_CONFIGURE_ARGS += --without-pcre

define Host/Configure
  $(call Host/Configure/Default)
endef

define Host/Compile
  $(call Host/Compile/Default)
endef

define Host/Install
  $(call Host/Install/Default)
endef

define Build/Configure
  $(call Build/Configure/Default,--without-pcre)
endef

# Compile for target

# Nothing to see here, it's all done in host-compile

define Package/swig/compile
endef

define Package/swig/install
endef

$(eval $(call HostBuild))
$(eval $(call BuildPackage,swig))
