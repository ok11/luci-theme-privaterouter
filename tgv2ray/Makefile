include $(TOPDIR)/rules.mk

PKG_NAME:=tgv2ray
PKG_VERSION:=1.0.0
PKG_RELEASE:=6

PKG_LICENSE:=GPL-3.0
PKG_MAINTAINER:=TorGuard <support@torguard.net>

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=net
  CATEGORY:=Network
  TITLE:=TorGuard V2Ray / sing-box VPN
  DEPENDS:=+luci-lua-runtime +luci-compat +curl +jq +bash +coreutils-base64 +sing-box
  PKGARCH:=all
endef

define Package/$(PKG_NAME)/description
  LuCI interface for managing TorGuard V2Ray connections using sing-box.
endef

define Build/Compile
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_DATA) ./root/etc/config/tgv2ray $(1)/etc/config/

	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./root/etc/init.d/tgv2ray $(1)/etc/init.d/

	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_BIN) ./root/etc/uci-defaults/tgv2ray_def $(1)/etc/uci-defaults/

	$(INSTALL_DIR) $(1)/etc/tgv2ray
	$(INSTALL_DATA) ./root/etc/tgv2ray/config.json.template $(1)/etc/tgv2ray/
	$(INSTALL_DATA) ./root/etc/tgv2ray/v2ray_default.conf $(1)/etc/tgv2ray/

	$(INSTALL_DIR) $(1)/lib/upgrade/keep.d
	$(INSTALL_DATA) ./root/lib/upgrade/keep.d/tgv2ray $(1)/lib/upgrade/keep.d/

	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) ./root/usr/bin/tgv2ray-config-gen $(1)/usr/bin/
	$(INSTALL_BIN) ./root/usr/bin/tgv2ray-subscription $(1)/usr/bin/

	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/controller/admin
	$(INSTALL_DATA) ./root/usr/lib/lua/luci/controller/admin/tgv2ray.lua $(1)/usr/lib/lua/luci/controller/admin/

	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/model/cbi/torguard
	$(INSTALL_DATA) ./root/usr/lib/lua/luci/model/cbi/torguard/tgv2ray.lua $(1)/usr/lib/lua/luci/model/cbi/torguard/

	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/view/tgv2ray
	$(INSTALL_DATA) ./root/usr/lib/lua/luci/view/tgv2ray/buttons.htm $(1)/usr/lib/lua/luci/view/tgv2ray/
	$(INSTALL_DATA) ./root/usr/lib/lua/luci/view/tgv2ray/status.htm $(1)/usr/lib/lua/luci/view/tgv2ray/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
