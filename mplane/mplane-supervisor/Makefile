#
# 2015 - mPlane Makefile
#

include $(TOPDIR)/rules.mk

PKG_NAME:=mplane-supervisor
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

define Package/mplane-supervisor
  SECTION:=misc
  CATEGORY:=mPlane
  TITLE:=supervisor instance implementing mPlane protocol
  URL:=https://www.ict-mplane.eu/public/public-deliverables
  DEPENDS:=+mplane-common
  MAINTAINER:=Gabor Molnar <gabor.molnar@netvisor.hu>
endef

define Package/mplane-supervisor/description
  Supervisor plays a special role in the architecture, working as a sort of glue between all other ele-
ments, so ,depending on the speci ic application and implementation, a supervisor can provide dif-
ferent functionalities and implementation logics. For example in a Internet Service Provider front
end a supervisor can enforce authorization functions, allowing access to speci ic probes only to
well known agents (reasoners or clients more in general) to request only authorized measures.
In a closed context such a functionality could not be required simply passing through all requests
coming from components exposing a certi icate signed by a well-known root-CA. In a troubleshoot-
ing scenario, the supervisor can integrated reasoning functions or expose registered capabilities
through its (mPlane) APIs to an external reasoning function.
endef

define Build/Compile
endef

define Build/InstallDev
endef

define Package/mplane-supervisor/install
	$(INSTALL_DIR) $(1)$(MPLANE_PKG_DIR)

	$(CP) $(PKG_BUILD_DIR)/../mplane/mplane/supervisor.py $(1)$(MPLANE_PKG_DIR)/
endef

$(eval $(call BuildPackage,mplane-supervisor))
