include $(TOPDIR)/rules.mk

PKG_NAME:=tgwireguard2
PKG_VERSION:=2.0.9-r0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/torguardvpn/tgwireguard2.git
PKG_SOURCE_VERSION:=229429586a3fb877f222695589f6a3b5a6e4eb73
PKG_MIRROR_HASH:=feba926acc5c2b2e839309f2baafc0e575fd613bc275bfc5daff5eedba2d8100

include $(INCLUDE_DIR)/package.mk

define Package/tgwireguard2
  SECTION:=luci
  CATEGORY:=LuCI
  SUBMENU:=7. TorGuard
  TITLE:=LuCI config tools for TorGuard WireGuard client (profile 2)
  DEPENDS:=+kmod-wireguard +wireguard-tools +luci-lua-runtime
  PKGARCH:=all
endef

define Package/tgwireguard2/description
  LuCI configuration for WireGuard VPN second profile, provided by TorGuard.
endef

define Package/tgwireguard2/conffiles
/etc/config/tgwireguard2_cfg
endef

define Build/Compile
endef

define Package/tgwireguard2/install
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/controller/admin
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/model/cbi/torguard

	$(INSTALL_CONF) $(PKG_BUILD_DIR)/files/etc/config/tgwireguard2_cfg $(1)/etc/config/
	$(INSTALL_BIN)  $(PKG_BUILD_DIR)/files/etc/init.d/tgwireguard2 $(1)/etc/init.d/
	$(INSTALL_BIN)  $(PKG_BUILD_DIR)/files/etc/uci-defaults/tgwireguard2_def $(1)/etc/uci-defaults/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/files/usr/lib/lua/luci/controller/admin/tgwireguard2.lua $(1)/usr/lib/lua/luci/controller/admin/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/files/usr/lib/lua/luci/model/cbi/torguard/tgwireguard2.lua $(1)/usr/lib/lua/luci/model/cbi/torguard/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
