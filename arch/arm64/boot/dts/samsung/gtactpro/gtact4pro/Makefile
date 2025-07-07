# SPDX-License-Identifier: GPL-2.0

ifeq ($(CONFIG_BUILD_ARM64_DT_OVERLAY),y)

define __sec_dtbo_build
dtbo-$(2) += $(1)
$(1)-base := $(3)
endef

define sec_dtbo_build
$(foreach dtbo, $(1), $(eval $(call __sec_dtbo_build, $(dtbo),$(2),$(3))))
endef

# YUPIK BASE DTB
SEC_YUPIK_BASE_DTB := ../../../vendor/qcom/yupik.dtb

# GTACT4PRO EUR
SEC_GTACT4PRO_EUR_DTBO := \
		gtact4pro_eur_openx_w00_r00.dtbo \
		gtact4pro_eur_openx_w00_r01.dtbo \
		gtact4pro_eur_openx_w00_r02.dtbo \
		gtact4pro_eur_openx_w00_r04.dtbo

$(eval $(call sec_dtbo_build, \
		$(SEC_GTACT4PRO_EUR_DTBO),$(CONFIG_MACH_GTACT4PRO_EUR_OPENX),$(SEC_YUPIK_BASE_DTB)))

always          := $(dtb-y)
subdir-y        := $(dts-dirs)
endif

clean-files := *.dtb *.reverse.dts *.dtbo


