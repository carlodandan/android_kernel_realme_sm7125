# SPDX-License-Identifier: GPL-2.0
ifeq ($(CONFIG_BRAND_SHOW_FLAG),realme)
    ifeq ($(CONFIG_SHIPPING_API_LEVEL),28)
        dts-dirs += 19781
    else
        dts-dirs += 19696
    endif
else
    ifeq ($(BRAND_SHOW_FLAG),oneplus)
        dts-dirs += 18821
        dts-dirs += 18857
        dts-dirs += 18865
        dts-dirs += 19801
        dts-dirs += 19863
        dts-dirs += 19861
    else
        dts-dirs += 19365
        dts-dirs += 19567
        dts-dirs += 19031
        dts-dirs += 19111
        dts-dirs += 20261
        dts-dirs += 206B1
        dts-dirs += 18115
        dts-dirs += 19081
        dts-dirs += 18501
        dts-dirs += 18503
        dts-dirs += 20711
        dts-dirs += 20331
    endif
endif

subdir-y	:= $(dts-dirs)

dtstree		:= $(srctree)/$(src)

dtb-$(CONFIG_OF_ALL_DTBS) := $(patsubst $(dtstree)/%.dts,%.dtb, $(foreach d,$(dts-dirs), $(wildcard $(dtstree)/$(d)/*.dts)))

always		:= $(dtb-y)

targets += dtbs

DTB_NAMES := $(subst $\",,$(CONFIG_BUILD_ARM64_APPENDED_DTB_IMAGE_NAMES))
ifneq ($(DTB_NAMES),)
DTB_LIST := $(addsuffix .dtb,$(DTB_NAMES))
else
DTB_LIST := $(dtb-y)
endif
targets += $(DTB_LIST)

dtbs: $(addprefix $(obj)/, $(DTB_LIST))

clean-files := dts/*.dtb *.dtb
