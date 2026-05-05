include $(TOPDIR)/rules.mk

PKG_NAME:=tgopenvpn
PKG_VERSION:=25.052.15245
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/torguardvpn/tgopenvpn.git
PKG_SOURCE_VERSION:=cfd9c4dcc0e8ac591c4933fb8955516b1b5b0561
PKG_MIRROR_HASH:=skip

LUCI_TITLE:=LuCI support for TorGuard OpenVPN
LUCI_PKGARCH:=all
LUCI_DEPENDS:=+openvpn-openssl

define Package/tgopenvpn/conffiles
/etc/config/tgopenvpn_cfg
endef

include $(TOPDIR)/feeds/luci/luci.mk
