#
# Copyright 2017 NXP
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=mc
PKG_VERSION:=2017.09
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/qoriq-open-source/mc-binary.git
PKG_SOURCE_VERSION:=824745fe1580b281bebb808321c3f41353a3140a
PKG_MIRROR_HASH:=9c8e154cf070b2ddd1198646ae9c6a7fc148a241b4b1d49f6c6f16aa01b67f16

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)-$(BUILD_VARIANT)/$(PKG_NAME)-$(PKG_VERSION)

PKG_FLAGS:=nonshared

include $(INCLUDE_DIR)/package.mk

define Package/layerscape-mc-ls1088ardb
  SECTION:=firmware
  CATEGORY:=Firmware
  DEPENDS:=@TARGET_layerscape
  TITLE:=NXP LS1088ARDB MC firmware
  VARIANT:=ls1088ardb
  CONFIG:=ls1088a/mc_10.3.4_ls1088a_20170929.itb
endef

define Package/layerscape-mc-ls2088ardb
  SECTION:=firmware
  CATEGORY:=Firmware
  DEPENDS:=@TARGET_layerscape
  TITLE:=NXP LS2088ARDB MC firmware
  VARIANT:=ls2088ardb
  CONFIG:=ls2088a/mc_10.3.4_ls2088a_20170929.itb
endef

define Build/Compile
endef

define Package/layerscape-mc-ls1088ardb/install
	$(INSTALL_DIR) $(STAGING_DIR_IMAGE)
	$(CP) $(PKG_BUILD_DIR)/$(CONFIG) $(STAGING_DIR_IMAGE)/ls1088ardb-mc.itb
endef

define Package/layerscape-mc-ls2088ardb/install
	$(INSTALL_DIR) $(STAGING_DIR_IMAGE)
	$(CP) $(PKG_BUILD_DIR)/$(CONFIG) $(STAGING_DIR_IMAGE)/ls2088ardb-mc.itb
endef

$(eval $(call BuildPackage,layerscape-mc-ls1088ardb))
$(eval $(call BuildPackage,layerscape-mc-ls2088ardb))
