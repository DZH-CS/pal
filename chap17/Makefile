
cfiles = features.s
files = mmxadd.s mmxcomp.s sse2math.s ssecomp.s ssemath.s
OBJS:=$(files:%.s=%.o)
COBJS:=$(cfiles:%.s=%.o)
ELFS:=$(files:%.s=%)
CELFS:=$(cfiles:%.s=%)
all: $(OBJS) $(ELFS) $(COBJS) $(CELFS)
$(OBJS): %.o: %.s
	as $< -o $@
$(ELFS): % : %.o
	ld $< -o $@
$(COBJS): %.o: %.s
	as $< -o $@
$(CELFS): % : %.o
	ld -lc -dynamic-linker /lib/ld-linux.so.2 $< -o $@
clear:
	@rm -rf $(OBJS) $(COBJS) $(ELFS) $(CELFS)

