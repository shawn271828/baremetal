# SPDX-License-Identifier: GPL-2.0
LDFLAGS_vmz	:= --no-undefined -X -nostdlib

KBUILD_CFLAGS	+= -mgeneral-regs-only

KBUILD_CFLAGS	+= $(call cc-option,-mabi=lp64)
KBUILD_AFLAGS	+= $(call cc-option,-mabi=lp64)

KBUILD_CPPFLAGS	+= -mlittle-endian
CHECKFLAGS	+= -D__AARCH64EL__
AS		+= -EL
KBUILD_LDFLAGS	+= -EL $(call ld-option, -maarch64elf, -maarch64linux)
UTS_MACHINE	:= aarch64
CHECKFLAGS	+= -D__aarch64__

head-y		:= arch/aarch64/kernel/head.o
core-y		:= arch/aarch64/

boot		:= arch/aarch64/boot
KBUILD_IMAGE	:= $(boot)/zVisor

all: zVisor

zVisor: vmz
	$(Q)$(MAKE) $(build)=$(boot) $(boot)/$@

archclean:
	$(Q)$(MAKE) $(clean)=$(boot)
