include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-easymesh
PKG_VERSION:=3.8.17
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/torguardvpn/luci-app-easymesh.git
PKG_SOURCE_VERSION:=fe1999e6c3391fa4a1862dbef3755e97b4491e15
PKG_MIRROR_HASH:=skip

PKG_MAINTAINER:=TorGuard <admin@torguard.net>

LUCI_TITLE:=LuCI Support for EasyMesh
LUCI_DEPENDS:=+kmod-cfg80211 +batctl-default +kmod-batman-adv +bash +luci-lua-runtime +luci-compat +libiwinfo-lua +luci-proto-batman-adv

include $(TOPDIR)/feeds/luci/luci.mk
