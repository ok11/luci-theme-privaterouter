include $(TOPDIR)/rules.mk

PKG_NAME:=tgv2ray
PKG_VERSION:=1.0.0-6
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/torguardvpn/tgv2ray.git
PKG_SOURCE_VERSION:=375ea1b7bf0d05b3489f27f8e877f6d0880c7d01
PKG_MIRROR_HASH:=ad02f4e2cda6834cd27693b3605f0f249d5b1ece525fb080bee9c0983f45460e

PKG_LICENSE:=GPL-3.0
PKG_MAINTAINER:=TorGuard <support@torguard.net>

include $(INCLUDE_DIR)/package.mk

define Package/tgv2ray
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=VPN
  TITLE:=TorGuard V2Ray / sing-box VPN
  DEPENDS:=+luci-lua-runtime +luci-compat +curl +jq +bash +coreutils-base64 +sing-box
  PKGARCH:=all
endef

define Package/tgv2ray/description
  LuCI interface for managing TorGuard V2Ray connections using sing-box.
endef

define Package/tgv2ray/conffiles
/etc/tgv2ray/config.json
endef

define Build/Compile
endef

define Package/tgv2ray/install
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_DIR) $(1)/etc/tgv2ray
	$(INSTALL_DIR) $(1)/lib/upgrade/keep.d
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/controller/admin
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/model/cbi/torguard
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/view/tgv2ray

	$(INSTALL_DATA) $(PKG_BUILD_DIR)/files/etc/config/tgv2ray $(1)/etc/config/
	$(INSTALL_BIN)  $(PKG_BUILD_DIR)/files/etc/init.d/tgv2ray $(1)/etc/init.d/
	$(INSTALL_BIN)  $(PKG_BUILD_DIR)/files/etc/uci-defaults/tgv2ray_def $(1)/etc/uci-defaults/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/files/etc/tgv2ray/config.json.template $(1)/etc/tgv2ray/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/files/etc/tgv2ray/v2ray_default.conf $(1)/etc/tgv2ray/
	$(INSTALL_BIN)  $(PKG_BUILD_DIR)/files/usr/bin/tgv2ray-config-gen $(1)/usr/bin/
	$(INSTALL_BIN)  $(PKG_BUILD_DIR)/files/usr/bin/tgv2ray-subscription $(1)/usr/bin/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/files/usr/lib/lua/luci/controller/admin/tgv2ray.lua $(1)/usr/lib/lua/luci/controller/admin/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/files/usr/lib/lua/luci/model/cbi/torguard/tgv2ray.lua $(1)/usr/lib/lua/luci/model/cbi/torguard/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/files/usr/lib/lua/luci/view/tgv2ray/buttons.htm $(1)/usr/lib/lua/luci/view/tgv2ray/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/files/usr/lib/lua/luci/view/tgv2ray/status.htm $(1)/usr/lib/lua/luci/view/tgv2ray/
endef

define Package/tgv2ray/prerm
#!/bin/sh
[ -n "$${IPKG_INSTROOT}" ] || {
	/etc/init.d/tgv2ray stop
	/etc/init.d/tgv2ray disable
}
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
