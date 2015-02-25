#
# 2015 - mPlane Makefile
#

include $(TOPDIR)/rules.mk

PKG_NAME:=mplane-component
PKG_VERSION:=$(shell git ls-remote --tags 2>/dev/null | grep "refs/tags" | head -n1 | cut -d"/" -f3)
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git://github.com/fp7mplane/protocol-ri.git
PKG_SOURCE_SUBDIR:=mplane/
PKG_SOURCE_VERSION:=c931af136d8ce932e8d504d530e4006ebb996b34

PKG_SOURCE:=$(PKG_NAME).tar.gz

PKG_BUILD_DEPENDS:=mplane-common

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/mplane/mplane/mplane-common/files/mplane-common.mk
$(call include_mk, python3-package.mk)

define Package/mplane-component
  SECTION:=misc
  CATEGORY:=mPlane
  TITLE:=component instance implementing mPlane protocol
  URL:=https://www.ict-mplane.eu/public/public-deliverables
  DEPENDS:=+mplane-common +probe-meas-ott
  MAINTAINER:=Gabor Molnar <gabor.molnar@netvisor.hu>
endef

define Package/mplane-component/description
  The mPlane component is an instance implementing the mPlane protocol.
It schedules the measurments on various technologies, communicates with the supervisor/client
based on the application.
endef

define Build/Compile
endef

define Build/InstallDev
endef

define Package/mplane-component/install
	$(INSTALL_DIR) $(1)$(MPLANE_PKG_DIR)

	$(CP) $(PKG_BUILD_DIR)/../mplane/mplane/ott.py $(1)$(MPLANE_PKG_DIR)/
	$(CP) $(PKG_BUILD_DIR)/../mplane/mplane/ping.py $(1)$(MPLANE_PKG_DIR)/
	$(CP) $(PKG_BUILD_DIR)/../mplane/mplane/ping_ci.py $(1)$(MPLANE_PKG_DIR)/
endef

$(eval $(call BuildPackage,mplane-component))
