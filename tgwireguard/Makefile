include $(TOPDIR)/rules.mk

PKG_NAME:=tgwireguard
PKG_VERSION:=2.0.9
PKG_RELEASE:=1

PKG_LICENSE:=GPL-2.0
PKG_MAINTAINER:=TorGuard

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=luci
  CATEGORY:=LuCI
  TITLE:=TorGuard WireGuard VPN
  DEPENDS:=+kmod-wireguard +wireguard-tools +luci-lua-runtime
  PKGARCH:=all
endef

define Package/$(PKG_NAME)/description
  LuCI configuration for WireGuard VPN, provided by TorGuard.
endef

define Build/Compile
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_DATA) ./root/etc/config/tgwireguard_cfg $(1)/etc/config/

	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./root/etc/init.d/tgwireguard $(1)/etc/init.d/

	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_BIN) ./root/etc/uci-defaults/tgwireguard_def $(1)/etc/uci-defaults/

	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/controller/admin
	$(INSTALL_DATA) ./root/usr/lib/lua/luci/controller/admin/tgwireguard.lua $(1)/usr/lib/lua/luci/controller/admin/

	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/model/cbi/torguard
	$(INSTALL_DATA) ./root/usr/lib/lua/luci/model/cbi/torguard/tgwireguard.lua $(1)/usr/lib/lua/luci/model/cbi/torguard/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
