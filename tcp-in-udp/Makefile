# SPDX-License-Identifier: AGPL-3.0-or-later
# Copyright (C) 2025-2026 Chester A. Unal <chester.a.unal@arinc9.com>

include $(TOPDIR)/rules.mk

PKG_NAME:=tcp-in-udp
PKG_VERSION:=1

PKG_LICENSE:=AGPL-3.0-or-later

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/multipath-tcp/tcp-in-udp.git
PKG_SOURCE_VERSION:=HEAD
#PKG_MIRROR_HASH:=229ac5e51596dd88e04e2163a4efc96622b2b0e3dd39294a88a1e854ac622d73

PKG_BUILD_DEPENDS:=bpf-headers

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/bpf.mk

define Package/tcp-in-udp
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Lightweight TCP in UDP tunnel using eBPF
  DEPENDS:=+libbpf $(BPF_DEPENDS)
endef

define Build/Compile
	$(call CompileBPF,$(PKG_BUILD_DIR)/tcp_in_udp_tc.c,-DBPF_PRINTK_UNSUPPORTED)
endef

define Package/tcp-in-udp/install
	$(INSTALL_DIR) $(1)/usr/lib/bpf
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/tcp_in_udp_tc.o $(1)/usr/lib/bpf
endef

$(eval $(call BuildPackage,tcp-in-udp))
