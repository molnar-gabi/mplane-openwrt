#
# 2014 OpenWrt.org
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-tornado
PKG_VERSION:=4.0.2
PKG_RELEASE:=1

PKG_SOURCE:=tornado-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/t/tornado/
PKG_MD5SUM:=985c0e704b765c33a6193d49d1935588
PKG_BUILD_DIR:=$(BUILD_DIR)/tornado-$(PKG_VERSION)/

PKG_BUILD_DEPENDS:=python3-setuptools

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-tornado
  SUBMENU:=Python3-libraries
  SECTION:=misc
  CATEGORY:=mPlane
  TITLE:=Tornado for python3
  URL:=https://pypi.python.org/pypi/tornado
  DEPENDS:=+python3
  MAINTAINER:=Gabor Molnar <gabor.molnar@netvisor.hu>
endef

define Package/python3-tornado/description
	Tornado is a Python web framework and asynchronous networking library, originally developed at FriendFeed.
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

define Package/python3-tornado/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)

endef

$(eval $(call BuildPackage,python3-tornado))
