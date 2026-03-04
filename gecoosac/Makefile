include $(TOPDIR)/rules.mk

PKG_NAME:=gecoosac
PKG_VERSION:=2.2.20251015
PKG_RELEASE:=1

ifeq ($(ARCH),aarch64)
  PKG_ARCH:=ac_linux_arm64_upx
  PKG_HASH:=f45a5c08a8aa43b3f2417d4d915fe313f7fed5e26e79af5a7c2761526d798ce1
else ifeq ($(ARCH),arm)
  PKG_ARCH:=ac_linux_arm_upx
  PKG_HASH:=d38bfb9a23c52409714ef00767e46634900d777030474bdedd6624700fb33bc1
else ifeq ($(ARCH),mips)
  PKG_ARCH:=ac_linux_mips_upx
  PKG_HASH:=1bae6c82eb8273b2e3b10b845d2c00fc4b4e82a36b04412280c429a1f526aa7e
else ifeq ($(ARCH),mipsel)
  PKG_ARCH:=ac_linux_mipsle_upx
  PKG_HASH:=07d486be3ae1a58f0de1ad91f18469d0a7d40efad53dcbd4b282c1d3b813d9e5
else ifeq ($(ARCH),i386)
  PKG_ARCH:=ac_linux_386_upx
  PKG_HASH:=3d8ce710280224a5f6fb206c81f97b63eb915d5e3142bbafbb0170e651512be8
else ifeq ($(ARCH),x86_64)
  PKG_ARCH:=ac_linux_amd64_upx
  PKG_HASH:=5752b1a133b24bada54bfa7fb3d9225d70af9174e07aab578948632808f6fed4
else
  PKG_HASH:=dummy
endif

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(ARCH_PACKAGES)
PKG_SOURCE_URL:=https://github.com/openwrt-fork/openwrt-gecoosac/releases/download/V$(PKG_VERSION)/$(PKG_ARCH)?
UNPACK_CMD=$(CP) $(DL_DIR)/$(PKG_SOURCE) $(PKG_BUILD_DIR)/$(PKG_NAME)

PKG_LICENSE:=AGPL-3.0-only
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=lwb1978 <lwb1978@gmail.com> openwrt-fork

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=net
  CATEGORY:=Network
  TITLE:=gecoosac server (version $(PKG_VERSION))
  URL:=http://www.cnrouter.com/
  DEPENDS:=@(aarch64||arm||i386||mips||mipsel||x86_64)
endef

define Build/Compile
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/$(PKG_NAME) $(1)/usr/bin
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
