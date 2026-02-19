# SPDX-License-Identifier: AGPL-3.0-or-later
# Copyright (C) 2025-2026 Chester A. Unal <chester.a.unal@arinc9.com>

include $(TOPDIR)/rules.mk

PKG_NAME:=bsbf-resources
PKG_VERSION:=1

PKG_LICENSE:=AGPL-3.0-or-later

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/bondingshouldbefree/bsbf-resources.git
PKG_SOURCE_VERSION:=HEAD

include $(INCLUDE_DIR)/package.mk

define Package/bsbf-iperf
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-iperf
endef

define Package/bsbf-mptcp
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-mptcp
endef

define Package/bsbf-netspeed
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-netspeed
endef

define Package/bsbf-quectel-usbnet
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-quectel-usbnet
endef

define Package/bsbf-route
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-route
endef

define Package/bsbf-tcp-in-udp
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-tcp-in-udp
  DEPENDS:=+tcp-in-udp
endef

define Package/bsbf-usb-netdev-autodhcp
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-usb-netdev-autodhcp
endef

define Build/Compile
endef

define Package/bsbf-iperf/install
	$(INSTALL_DIR) $(1)/usr/local/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-iperf $(1)/usr/local/sbin
endef

define Package/bsbf-mptcp/install
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_CONF) ./files/etc/config/bsbf-mptcp $(1)/etc/config

	$(INSTALL_DIR) $(1)/etc/hotplug.d/iface
	$(INSTALL_BIN) ./files/etc/hotplug.d/iface/99-bsbf-mptcp $(1)/etc/hotplug.d/iface

	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/etc/init.d/bsbf-mptcp $(1)/etc/init.d

	$(INSTALL_DIR) $(1)/usr/local/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-mptcp $(1)/usr/local/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-mptcp-helper $(1)/usr/local/sbin
endef

define Package/bsbf-netspeed/install
	$(INSTALL_DIR) $(1)/usr/local/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-netspeed $(1)/usr/local/sbin
endef

define Package/bsbf-quectel-usbnet/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/etc/init.d/bsbf-quectel-usbnet $(1)/etc/init.d

	$(INSTALL_DIR) $(1)/usr/local/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-quectel-usbnet $(1)/usr/local/sbin
endef

define Package/bsbf-route/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/etc/init.d/bsbf-route $(1)/etc/init.d

	$(INSTALL_DIR) $(1)/usr/local/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-route $(1)/usr/local/sbin
endef

define Package/bsbf-tcp-in-udp/install
	$(INSTALL_DIR) $(1)/etc/hotplug.d/iface
	$(INSTALL_BIN) ./files/etc/hotplug.d/iface/99-bsbf-tcp-in-udp $(1)/etc/hotplug.d/iface

	$(INSTALL_DIR) $(1)/usr/local/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-tcp-in-udp $(1)/usr/local/sbin
endef

define Package/bsbf-usb-netdev-autodhcp/install
	$(INSTALL_DIR) $(1)/etc/hotplug.d/net
	$(INSTALL_BIN) ./files/etc/hotplug.d/net/99-bsbf-usb-netdev-autodhcp $(1)/etc/hotplug.d/net
endef

$(eval $(call BuildPackage,bsbf-iperf))
$(eval $(call BuildPackage,bsbf-mptcp))
$(eval $(call BuildPackage,bsbf-netspeed))
$(eval $(call BuildPackage,bsbf-quectel-usbnet))
$(eval $(call BuildPackage,bsbf-route))
$(eval $(call BuildPackage,bsbf-tcp-in-udp))
$(eval $(call BuildPackage,bsbf-usb-netdev-autodhcp))
