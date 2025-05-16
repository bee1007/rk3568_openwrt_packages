include $(TOPDIR)/rules.mk

PKG_NAME:=rkmpp
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=develop
PKG_SOURCE_URL:=http://git.binforce.lan:8081/binforce/client/box/rkmpp.git
PKG_HASH:=9d556f554a3d4084bc6b44fb454e582a

PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=COPYING
PKG_MAINTAINER:=Your Name <your.email@example.com>

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/rkmpp
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=rockchip mpp
endef

CMAKE_OPTIONS += \
    -DCMAKE_BUILD_TYPE=Release 

define Build/Install
    $(call Build/Install/Default)
endef

define Package/rkmpp/install
    $(INSTALL_DIR) $(1)/usr/lib
endef

$(eval $(call BuildPackage,rkmpp))
