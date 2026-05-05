include $(TOPDIR)/rules.mk

PKG_NAME:=tgopenvpn
PKG_VERSION:=25.050.05753
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/torguardvpn/tgopenvpn.git
PKG_SOURCE_VERSION:=4b42dac782df7b656740cbe262b27d66e95350f1
PKG_MIRROR_HASH:=skip

LUCI_TITLE:=LuCI support for TorGuard OpenVPN
LUCI_PKGARCH:=all
LUCI_DEPENDS:=+openvpn-openssl

define Package/tgopenvpn/conffiles
/etc/config/tgopenvpn_cfg
endef

include $(TOPDIR)/feeds/luci/luci.mk
