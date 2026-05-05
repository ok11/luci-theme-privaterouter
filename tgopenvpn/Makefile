include $(TOPDIR)/rules.mk

PKG_NAME:=tgopenvpn
PKG_VERSION:=25.052.15245
PKG_RELEASE:=1

PKG_LICENSE:=GPL-2.0
PKG_MAINTAINER:=TorGuard

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=luci
  CATEGORY:=LuCI
  TITLE:=TorGuard OpenVPN
  DEPENDS:=+openvpn-openssl +luci-lua-runtime
  PKGARCH:=all
endef

define Package/$(PKG_NAME)/description
  LuCI support for TorGuard OpenVPN connections.
endef

define Build/Compile
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_DATA) ./root/etc/config/tgopenvpn_cfg $(1)/etc/config/

	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./root/etc/init.d/tgopenvpn $(1)/etc/init.d/

	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_BIN) ./root/etc/uci-defaults/tgopenvpn_def $(1)/etc/uci-defaults/

	$(INSTALL_DIR) $(1)/etc/openvpn/torguard
	$(INSTALL_DATA) ./root/etc/openvpn/torguard/ca.crt $(1)/etc/openvpn/torguard/
	$(INSTALL_DATA) ./root/etc/openvpn/torguard/ta.key $(1)/etc/openvpn/torguard/

	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/controller/admin
	$(INSTALL_DATA) ./root/usr/lib/lua/luci/controller/admin/tgopenvpn.lua $(1)/usr/lib/lua/luci/controller/admin/

	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/model/cbi/torguard
	$(INSTALL_DATA) ./root/usr/lib/lua/luci/model/cbi/torguard/tgopenvpn.lua $(1)/usr/lib/lua/luci/model/cbi/torguard/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
