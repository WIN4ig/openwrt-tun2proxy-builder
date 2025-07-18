include $(TOPDIR)/rules.mk

PKG_NAME:=tun2proxy
PKG_VERSION:=2023-07-01
PKG_RELEASE:=1
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk

define Package/tun2proxy
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Tun2Proxy Tunnel
  DEPENDS:=+kmod-tun +libpthread
endef

define Build/Prepare
    $(call Build/Prepare/Default)
endef

define Build/Compile
    # No compilation needed, binary is pre-built
endef

define Package/tun2proxy/install
    $(INSTALL_DIR) $(1)/usr/bin
    $(INSTALL_BIN) $(PKG_BUILD_DIR)/tun2proxy-bin $(1)/usr/bin/
endef

$(eval $(call BuildPackage,tun2proxy))