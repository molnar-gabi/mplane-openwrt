#
# 2015 - mPlane Makefile
#

include $(TOPDIR)/rules.mk

PKG_NAME:=mplane-common
PKG_VERSION:=$(shell git ls-remote --tags 2>/dev/null | grep "refs/tags" | head -n1 | cut -d"/" -f3)
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git://github.com/fp7mplane/protocol-ri.git
PKG_SOURCE_SUBDIR:=mplane/
PKG_SOURCE_VERSION:=c931af136d8ce932e8d504d530e4006ebb996b34

PKG_SOURCE:=$(PKG_NAME).tar.gz

PKG_BUILD_DEPENDS:=python3

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/mplane/mplane/mplane-common/files/mplane-common.mk
$(call include_mk, python3-package.mk)

define Package/mplane-common
  SECTION:=misc
  CATEGORY:=mPlane
  TITLE:=common library used by various mPlane protocol compatible instances
  URL:=https://www.ict-mplane.eu/public/public-deliverables
  DEPENDS:=+python3 +python3-yaml +python3-tornado +python3-ssl
  MAINTAINER:=Gabor Molnar <gabor.molnar@netvisor.hu>
endef

define Package/mplane-common/description
  common library used by various mPlane protocol compatible instances
endef

define Build/Compile
endef

define Build/InstallDev
endef

define Package/mplane-common/install
	$(INSTALL_DIR) $(1)$(MPLANE_PKG_DIR)

	$(CP) $(PKG_BUILD_DIR)/../mplane/mplane/model.py $(1)$(MPLANE_PKG_DIR)/
	$(CP) $(PKG_BUILD_DIR)/../mplane/mplane/utils.py $(1)$(MPLANE_PKG_DIR)/
	$(CP) $(PKG_BUILD_DIR)/../mplane/mplane/sec.py $(1)$(MPLANE_PKG_DIR)/
	$(CP) $(PKG_BUILD_DIR)/../mplane/mplane/sv_handlers.py $(1)$(MPLANE_PKG_DIR)/
	$(CP) $(PKG_BUILD_DIR)/../mplane/mplane/registry.json $(1)$(MPLANE_PKG_DIR)/
endef

$(eval $(call BuildPackage,mplane-common))
