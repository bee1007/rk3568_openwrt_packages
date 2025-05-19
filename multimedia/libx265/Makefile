include $(TOPDIR)/rules.mk

PKG_NAME:=libx265
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=master
PKG_SOURCE_URL:=http://git.binforce.lan:8081/binforce/client/box/x265.git
PKG_HASH:=5a7a73d1b38b51880e9ae55da4118d18

PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=COPYING
PKG_MAINTAINER:=Your Name <your.email@example.com>

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/libx265
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=H.265/HEVC video encoding library
 	DEPENDS:=+libstdcpp
endef

define Package/libx265/description
 	x265 is a free software library for encoding video streams into the H.265/HEVC format.
endef

CMAKE_OPTIONS += \
    -DCMAKE_BUILD_TYPE=Release \
    -DENABLE_CLI=OFF

CMAKE_SOURCE_DIR:=$(PKG_BUILD_DIR)/source

define Build/Install
	$(call Build/Install/Default)
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
endef

define Package/libx265/install
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib
endef

$(eval $(call BuildPackage,libx265))
