# Samsung SDM450 Project

dtb-$(CONFIG_MACH_J8Y18LTE_SWA_INS) += sdm450-sec-j8y18lte_swa_ins-r00.dtb \
					sdm450-sec-j8y18lte_swa_ins-r01.dtb \
					sdm450-sec-j8y18lte_swa_ins-r02.dtb \
					sdm450-sec-j8y18lte_swa_ins-r03.dtb

ifeq ($(CONFIG_ARM64),y)
always          := $(dtb-y)
subdir-y        := $(dts-dirs)
else
targets += dtbs
targets += $(addprefix ../, $(dtb-y))

$(obj)/../../%.dtb: $(src)/%.dts FORCE
        $(call if_changed_dep,dtc)

dtbs: $(addprefix $(obj)/../../,$(dtb-y))
endif
clean-files := *.dtb *.reserve.dts
