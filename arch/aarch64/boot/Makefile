OBJCOPYFLAGS_zVisor := -O binary

targets := zVisor

$(obj)/zVisor: vmz FORCE
	$(call if_changed,objcopy)
