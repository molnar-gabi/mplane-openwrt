#
# 2015 - mPlane Makefile
#

include $(TOPDIR)/rules.mk

PKG_NAME:=mplane-client
PKG_VERSION:=$(shell git ls-remote --tags 2>/dev/null | grep "refs/tags" | head -n1 | cut -d"/" -f3)
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git://github.com/fp7mplane/protocol-ri.git
PKG_SOURCE_SUBDIR:=mplane/
PKG_SOURCE_VERSION:=c931af136d8ce932e8d504d530e4006ebb996b34

PKG_SOURCE:=$(PKG_NAME).tar.gz

PKG_BUILD_DEPENDS:=mplane-common

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/mplane-client
  SECTION:=misc
  CATEGORY:=mPlane
  TITLE:=client instance implementing mPlane protocol
  URL:=https://www.ict-mplane.eu/public/public-deliverables
  DEPENDS:=+mplane-common
  MAINTAINER:=Gabor Molnar <gabor.molnar@netvisor.hu>
endef

define Package/mplane-client/description
  The mPlane client communicates with the supervisor/component
via the mPlane protocol (based on the scenario). It can redeem measurement result
or create 
endef

define Build/Compile
endef

define Build/InstallDev
endef

define Package/mplane-client/install
	$(INSTALL_DIR) $(1)/usr/lib/python3.4/mplane

	$(CP) $(PKG_BUILD_DIR)/../mplane/mplane/client.py $(1)/usr/lib/python3.4/mplane/
endef

$(eval $(call BuildPackage,mplane-client))
