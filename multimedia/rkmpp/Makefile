include $(TOPDIR)/rules.mk

PKG_NAME:=rkmpp
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=faf5ce8065e04be40889b5d1f37e467868ab83c4
PKG_SOURCE_URL:=http://git.binforce.lan:8081/binforce/client/box/rkmpp.git
PKG_HASH:=bbe4e90e4d2af1c26e0c7ebf6031311a

PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=COPYING
PKG_MAINTAINER:=Your Name <your.email@example.com>

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/rkmpp
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=rockchip mpp
	DEPENDS:=+libstdcpp
endef

CMAKE_OPTIONS += \
    -DCMAKE_BUILD_TYPE=Release 

define Build/Install
	$(call Build/Install/Default)
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
endef

define Package/rkmpp/install
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,rkmpp))
