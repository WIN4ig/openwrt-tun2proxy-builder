include $(TOPDIR)/rules.mk

PKG_NAME:=tun2proxy
PKG_VERSION:=2023-07-01
PKG_RELEASE:=1
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/tun2proxy/tun2proxy.git
PKG_SOURCE_VERSION:=HEAD
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/tun2proxy
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Tun2Proxy Tunnel
  DEPENDS:=+kmod-tun +libpthread
endef

define Build/Prepare
    $(call Build/Prepare/Default)
    (cd $(PKG_BUILD_DIR); \
        cargo build --release; \
    )
endef

define Package/tun2proxy/install
    $(INSTALL_DIR) $(1)/usr/bin
    $(INSTALL_BIN) $(PKG_BUILD_DIR)/target/release/tun2proxy-bin $(1)/usr/bin/
endef

$(eval $(call BuildPackage,tun2proxy))