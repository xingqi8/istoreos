include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=rtl8723be
PKG_VERSION:=2024-04-20
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define KernelPackage/rtl8723be
        SUBMENU:=Wireless Drivers
        TITLE:=Realtek RTL8723BE wireless drivers
        DEPENDS:=@(PCI_SUPPORT) +kmod-mac80211 +@DRIVER_11N_SUPPORT
        FILES:=$(PKG_BUILD_DIR)/rtl8723be.ko
        AUTOLOAD:=$(call AutoProbe,rtl8723be)
endef

define KernelPackage/rtl8723be/description
        Kernel module for Realtek RTL8723BE wireless drivers
endef

EXTRA_KCONFIG:= \
        CONFIG_REALTEK_PCI_RTL8723BE=m  

EXTRA_CFLAGS:= \
        $(patsubst CONFIG_%, -DCONFIG_%=1, $(patsubst %=m,%,$(filter %=m,$(EXTRA_KCONFIG)))) \
        $(patsubst CONFIG_%, -DCONFIG_%=1, $(patsubst %=y,%,$(filter %=y,$(EXTRA_KCONFIG)))) \

MAKE_OPTS:= \
        ARCH="$(LINUX_KARCH)" \
        CROSS_COMPILE="$(TARGET_CROSS)" \
        SUBDIRS="$(PKG_BUILD_DIR)" \
        EXTRA_CFLAGS="$(EXTRA_CFLAGS)" \
        $(EXTRA_KCONFIG)

define Build/Prepare
        mkdir -p $(PKG_BUILD_DIR)
        $(CP) ./src/* $(PKG_BUILD_DIR)/
endef

define Build/Compile
        $(MAKE) -C "$(LINUX_DIR)" \
                $(MAKE_OPTS) \
                modules
endef

$(eval	$(call	KernelPackage,rtl8723be))
include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=rtl8723be
PKG_VERSION:=2024-04-20
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define KernelPackage/rtl8723be
        SUBMENU:=Wireless Drivers
        TITLE:=Realtek RTL8723BE wireless drivers
        DEPENDS:=@(PCI_SUPPORT) +kmod-mac80211 +@DRIVER_11N_SUPPORT
        FILES:=$(PKG_BUILD_DIR)/rtl8723be.ko
        AUTOLOAD:=$(call AutoProbe,rtl8723be)
endef

define KernelPackage/rtl8723be/description
        Kernel module for Realtek RTL8723BE wireless drivers
endef

EXTRA_KCONFIG:= \
        CONFIG_REALTEK_PCI_RTL8723BE=m  

EXTRA_CFLAGS:= \
        $(patsubst CONFIG_%, -DCONFIG_%=1, $(patsubst %=m,%,$(filter %=m,$(EXTRA_KCONFIG)))) \
        $(patsubst CONFIG_%, -DCONFIG_%=1, $(patsubst %=y,%,$(filter %=y,$(EXTRA_KCONFIG)))) \

MAKE_OPTS:= \
        ARCH="$(LINUX_KARCH)" \
        CROSS_COMPILE="$(TARGET_CROSS)" \
        SUBDIRS="$(PKG_BUILD_DIR)" \
        EXTRA_CFLAGS="$(EXTRA_CFLAGS)" \
        $(EXTRA_KCONFIG)

define Build/Prepare
        mkdir -p $(PKG_BUILD_DIR)
        $(CP) ./src/* $(PKG_BUILD_DIR)/
endef

define Build/Compile
        $(MAKE) -C "$(LINUX_DIR)" \
                $(MAKE_OPTS) \
                modules
endef

$(eval	$(call	KernelPackage,rtl8723be))
