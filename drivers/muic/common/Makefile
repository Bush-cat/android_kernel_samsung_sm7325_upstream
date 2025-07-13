#
# Makefile for muic devices
#
subdir-ccflags-y := -Wformat

obj-$(CONFIG_MUIC_NOTIFIER)	+= common_muic.o
ifdef CONFIG_SEC_A73XQ_PROJECT
common_muic-y   := a73xq/muic_notifier.o muic_param.o
common_muic-$(CONFIG_MUIC_SYSFS) += a73xq/muic_sysfs.o
common_muic-$(CONFIG_MUIC_CORE) += a73xq/muic_core.o
obj-$(CONFIG_MUIC_MANAGER) += a73xq/muic_manager.o
else
common_muic-y	:= muic-core.o muic_notifier.o muic_param.o
common_muic-$(CONFIG_MUIC_COMMON_SYSFS) += muic_sysfs.o
endif
