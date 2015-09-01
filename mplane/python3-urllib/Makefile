#
# 2014 OpenWrt.org
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-urllib
PKG_VERSION:=1.11
PKG_RELEASE:=1

PKG_SOURCE:=urllib3-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/u/urllib3/
PKG_MD5SUM:=4cdfe9b51c181700f9c7beb84bb42770
PKG_BUILD_DIR:=$(BUILD_DIR)/urllib3-$(PKG_VERSION)/

PKG_BUILD_DEPENDS:=python3-setuptools

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-urllib
  SUBMENU:=Python3-libraries
  SECTION:=misc
  CATEGORY:=mPlane
  TITLE:=Urllib for python3
  URL:=https://pypi.python.org/pypi/urllib3
  DEPENDS:=+python3
  MAINTAINER:=Gabor Molnar <gabor.molnar@netvisor.hu>
endef

define Package/python3-urllib/description
	HTTP library with thread-safe connection pooling, file post, and more.
endef

define Build/Compile
	$(call Build/Compile/PyMod,., \
		install --prefix="/usr" --root="$(PKG_INSTALL_DIR)" \
	)
endef

define Build/InstallDev
	$(INSTALL_DIR) $(STAGING_DIR)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(STAGING_DIR)$(PYTHON_PKG_DIR)/
	[ ! -e $(PKG_INSTALL_DIR)/usr/include ] || $(CP) \
		$(PKG_INSTALL_DIR)/usr/include/* \
		$(STAGING_DIR)/usr/include/
endef

define Package/python3-urllib/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)

endef

$(eval $(call BuildPackage,python3-urllib))
